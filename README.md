<!--
  Profile README for github.com/acedev0
  - The repo must be named exactly "acedev0" (same as the username) and be public.
  - Needs ./assets/banner.svg in the same repo. The header is self-hosted, so it
    can't break when a third-party image service is down.
-->

<div align="center">

<img src="./assets/banner.svg" alt="Ace (@acedev0): building systems that move data, not problems" width="100%" />

<br />

<a href="https://t.me/Aceddev"><img src="https://img.shields.io/badge/Telegram-Message_me-229ED9?style=for-the-badge&amp;logo=telegram&amp;logoColor=white" alt="Message Ace on Telegram" /></a>
&nbsp;
<a href="mailto:Acedevmc@gmail.com"><img src="https://img.shields.io/badge/Email-Get_in_touch-EA4335?style=for-the-badge&amp;logo=gmail&amp;logoColor=white" alt="Email Ace" /></a>

</div>

## Hey, I'm Ace

I'm an independent developer who builds the plumbing behind Telegram-native products: **MTProto automation**, **media streaming that never touches the disk**, and the **real-time web apps** that sit on top of them.

I spend most of my time on what happens *off* the happy path: memory ceilings, concurrency limits, failure recovery, and where the trust boundaries sit.

<table>
  <tr>
    <td width="33%" valign="top">
      <b>Building</b><br />
      <a href="https://github.com/acedev0/ace-hub">Ace Hub</a>, a watch-party platform with synchronized playback on Next.js, Socket.IO and Prisma.
    </td>
    <td width="33%" valign="top">
      <b>Shipping</b><br />
      Tagged releases of CineVault, TeleVault and AceUnzipBot.
    </td>
    <td width="33%" valign="top">
      <b>Exploring</b><br />
      Queues, retries and observability for long-running jobs, and leaner byte-range streaming.
    </td>
  </tr>
</table>

**Ask me about:** Telethon and MTProto, HTTP range requests, async Python concurrency, and running services safely with Docker and systemd.

## Featured work

<!-- Private repo? Shields can't read it, so delete that card's release / last-commit badges. -->
<table>
  <tr>
    <td width="50%" valign="top">
      <h3>🎬 <a href="https://github.com/acedev0/cinevault">CineVault</a></h3>
      <p>Netflix-inspired movie discovery and streaming built on Telegram. Search for a title, press play, and the bytes flow from Telegram to the player over HTTP range requests, with no persistent media storage on the server.</p>
      <p><code>Python</code> <code>FastAPI</code> <code>Telethon</code> <code>Docker</code></p>
      <p>
        <a href="https://github.com/acedev0/cinevault/releases"><img src="https://img.shields.io/github/v/release/acedev0/cinevault?style=flat-square&amp;label=release&amp;color=3fb950" alt="Latest CineVault release" /></a>
        <img src="https://img.shields.io/github/last-commit/acedev0/cinevault?style=flat-square" alt="CineVault last commit" />
      </p>
    </td>
    <td width="50%" valign="top">
      <h3>📦 <a href="https://github.com/acedev0/AceUnzipBot">AceUnzipBot</a></h3>
      <p>Archive extraction for Telegram, powered by 7-Zip. Bulk jobs run through a FIFO queue with live progress and thumbnails, plus a dedicated CLI and deployment tooling.</p>
      <p><code>Python</code> <code>Telethon</code> <code>7-Zip</code> <code>Linux</code></p>
      <p>
        <a href="https://github.com/acedev0/AceUnzipBot/releases"><img src="https://img.shields.io/github/v/release/acedev0/AceUnzipBot?style=flat-square&amp;label=release&amp;color=3fb950" alt="Latest AceUnzipBot release" /></a>
        <img src="https://img.shields.io/github/last-commit/acedev0/AceUnzipBot?style=flat-square" alt="AceUnzipBot last commit" />
      </p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h3>📺 <a href="https://github.com/acedev0/televault">TeleVault</a></h3>
      <p>A private Telegram media library with a custom browser player. Playback runs on byte-range streaming, thumbnails are WebP, and access is protected with security-focused controls, including Argon2id hashing.</p>
      <p><code>Python</code> <code>FastAPI</code> <code>Telethon</code> <code>Docker</code></p>
      <p>
        <a href="https://github.com/acedev0/televault/releases"><img src="https://img.shields.io/github/v/release/acedev0/televault?style=flat-square&amp;label=release&amp;color=3fb950" alt="Latest TeleVault release" /></a>
        <img src="https://img.shields.io/github/last-commit/acedev0/televault?style=flat-square" alt="TeleVault last commit" />
      </p>
    </td>
    <td width="50%" valign="top">
      <h3>🍿 <a href="https://github.com/acedev0/ace-hub">Ace Hub</a></h3>
      <p>Video discovery and synchronized watch parties. Real-time playback sync keeps multiple viewers in lockstep, on a responsive interface backed by a Prisma-managed database.</p>
      <p><code>Next.js</code> <code>React</code> <code>Prisma</code> <code>Socket.IO</code></p>
      <p>
        <img src="https://img.shields.io/badge/status-in_development-8957e5?style=flat-square" alt="Ace Hub is in development" />
        <img src="https://img.shields.io/github/last-commit/acedev0/ace-hub?style=flat-square" alt="Ace Hub last commit" />
      </p>
    </td>
  </tr>
</table>

## How the streaming stack works

CineVault and TeleVault share one idea: **the server is a pipe, not a warehouse.**

```mermaid
flowchart LR
    A["Player<br/>browser or VLC"] -->|"GET + Range header"| B["FastAPI<br/>auth and range parsing"]
    B -->|"chunk requests"| C["Telethon<br/>MTProto client"]
    C <-->|"MTProto"| D[("Telegram")]
    B -.->|"206 Partial Content<br/>streamed chunk by chunk"| A
```

<!-- Check these three bullets against what the code really does before publishing. -->
- **Range-first.** Each `Range: bytes=a-b` request is mapped to the smallest set of MTProto chunk fetches that covers it, so seeking and scrubbing stay cheap.
- **Flat memory.** Chunks are handed to the HTTP response as the client consumes them. Nothing is buffered to disk, and memory use doesn't grow with file size.
- **Stop when the viewer stops.** When a player seeks away or disconnects, the in-flight download is cancelled instead of burning bandwidth.

**Rules I build by:** stream, don't store. Bound memory and concurrency. Automate the repetitive. Design for failure. Keep trust boundaries explicit.

## Toolbox

<table>
  <tr>
    <td><b>Languages</b></td>
    <td>
      <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&amp;logo=python&amp;logoColor=white" alt="Python" />
      <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&amp;logo=typescript&amp;logoColor=white" alt="TypeScript" />
      <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&amp;logo=javascript&amp;logoColor=black" alt="JavaScript" />
      <img src="https://img.shields.io/badge/Bash-4EAA25?style=flat-square&amp;logo=gnubash&amp;logoColor=white" alt="Bash" />
    </td>
  </tr>
  <tr>
    <td><b>Backend</b></td>
    <td>
      <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&amp;logo=fastapi&amp;logoColor=white" alt="FastAPI" />
      <img src="https://img.shields.io/badge/Telethon-2AABEE?style=flat-square&amp;logo=telegram&amp;logoColor=white" alt="Telethon" />
      <img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&amp;logo=nodedotjs&amp;logoColor=white" alt="Node.js" />
    </td>
  </tr>
  <tr>
    <td><b>Frontend</b></td>
    <td>
      <img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&amp;logo=nextdotjs&amp;logoColor=white" alt="Next.js" />
      <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&amp;logo=react&amp;logoColor=black" alt="React" />
      <img src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&amp;logo=tailwindcss&amp;logoColor=white" alt="Tailwind CSS" />
      <img src="https://img.shields.io/badge/Socket.IO-010101?style=flat-square&amp;logo=socketdotio&amp;logoColor=white" alt="Socket.IO" />
    </td>
  </tr>
  <tr>
    <td><b>Data</b></td>
    <td>
      <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&amp;logo=postgresql&amp;logoColor=white" alt="PostgreSQL" />
      <img src="https://img.shields.io/badge/SQLite-003B57?style=flat-square&amp;logo=sqlite&amp;logoColor=white" alt="SQLite" />
      <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&amp;logo=redis&amp;logoColor=white" alt="Redis" />
      <img src="https://img.shields.io/badge/Prisma-2D3748?style=flat-square&amp;logo=prisma&amp;logoColor=white" alt="Prisma" />
    </td>
  </tr>
  <tr>
    <td><b>Ops</b></td>
    <td>
      <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&amp;logo=docker&amp;logoColor=white" alt="Docker" />
      <img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&amp;logo=linux&amp;logoColor=black" alt="Linux" />
      <img src="https://img.shields.io/badge/Nginx-009639?style=flat-square&amp;logo=nginx&amp;logoColor=white" alt="Nginx" />
      <img src="https://img.shields.io/badge/systemd-4B5563?style=flat-square&amp;logo=linux&amp;logoColor=white" alt="systemd" />
      <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&amp;logo=git&amp;logoColor=white" alt="Git" />
    </td>
  </tr>
</table>

## Let's talk

Got something involving Telegram automation, streaming infrastructure, or a real-time web app? Message me on [Telegram](https://t.me/Aceddev) or [send an email](mailto:Acedevmc@gmail.com). I'm happy to talk it through.

<div align="center">

<br />

**Stream, don't store.**

<sub>Built by Ace, <a href="https://github.com/acedev0">@acedev0</a></sub>

</div>
