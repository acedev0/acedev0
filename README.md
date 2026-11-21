<!--
  Profile README for github.com/acedev0

  Setup
  - The repo must be named exactly "acedev0" (same as the username) and be public.
  - Needs ./assets/banner.svg in the same repo. The header is self-hosted, so it
    can't break when a third-party image service is down.
-->

<div align="center">

<img src="./assets/banner.svg" alt="Ace (@acedev0): Streaming · AI · Formal Verification" width="100%" />

<br />

<a href="https://t.me/Aceddev"><img src="https://img.shields.io/badge/Telegram-Message_me-229ED9?style=for-the-badge&amp;logo=telegram&amp;logoColor=white" alt="Message Ace on Telegram" /></a>
&nbsp;
<a href="mailto:Acedevmc@gmail.com"><img src="https://img.shields.io/badge/Email-Get_in_touch-EA4335?style=for-the-badge&amp;logo=gmail&amp;logoColor=white" alt="Email Ace" /></a>

<br /><br />

<sub>
<a href="#featured-work">Featured work</a> &nbsp;·&nbsp;
<a href="#neurosymbolic-ai-loop">AI &amp; Verification</a> &nbsp;·&nbsp;
<a href="#how-the-streaming-stack-works">Streaming stack</a> &nbsp;·&nbsp;
<a href="#engineering-distribution">Focus</a> &nbsp;·&nbsp;
<a href="#how-i-build">Principles</a> &nbsp;·&nbsp;
<a href="#toolbox">Toolbox</a> &nbsp;·&nbsp;
<a href="#lets-talk">Contact</a>
</sub>

</div>

<br />

## Hey, I'm Ace 👋

I build systems that bridge **Generative AI**, **Formal Verification**, and **High-Throughput Network Plumbing**.

My work focuses on the intersection of probabilistic models and deterministic guarantees:
- 🧠 **Neurosymbolic AI & LLMs:** Harnessing modern LLMs to synthesize code patches, coupled with **Z3 SMT solvers** that mathematically prove safety before a single line ships.
- ⚡ **Zero-Disk Media Streaming:** Custom byte-range proxies translating HTTP `Range` requests into real-time **MTProto chunks** without touching the server's disk.
- 🌐 **Real-Time Synchronized Web Apps:** Reactive multi-client sync architectures on **Next.js**, **WebSockets**, and **Prisma**.

I spend most of my time on what happens *off* the happy path: memory ceilings, token budgets, failure recovery, concurrency locks, and where the trust boundaries sit.

<table>
  <tr>
    <td width="33%" valign="top">
      <h4>🧠 Neurosymbolic AI</h4>
      <a href="https://github.com/acedev0/verifix"><b>VeriFix</b></a>: Binding <b>LLM generative synthesis</b> to <b>Z3 SMT formal verification</b> in a self-healing CEGIS loop.
    </td>
    <td width="33%" valign="top">
      <h4>⚡ Zero-Disk Streaming</h4>
      Tagged releases of <a href="https://github.com/acedev0/cinevault"><b>CineVault</b></a> and <a href="https://github.com/acedev0/televault"><b>TeleVault</b></a>: Streaming multi-gigabyte media with flat memory ceilings.
    </td>
    <td width="33%" valign="top">
      <h4>🌐 Real-Time Systems</h4>
      <b>Ace Hub</b> and <a href="https://github.com/acedev0/AceUnzipBot"><b>AceUnzipBot</b></a>: Lockstep watch-parties and FIFO MTProto workers.
    </td>
  </tr>
</table>

**Ask me about:**
`Generative AI & LLMs` · `Z3 SMT Formal Verification` · `CEGIS Loops` · `MTProto / Telethon` · `HTTP Range Requests` · `Async Python Concurrency` · `Docker in Production`

<br />

## Featured work

<table>
  <tr>
    <td width="50%" valign="top">
      <h3>🛡️ <a href="https://github.com/acedev0/verifix">VeriFix</a></h3>
      <p><b>Neurosymbolic code repair: LLM generative patching meets Z3 formal verification.</b></p>
      <p>Combines LLMs with an SMT constraint solver in a CounterExample-Guided Inductive Synthesis (CEGIS) loop. Solvers mathematically prove patches or generate concrete counterexample models to trigger LLM self-correction.</p>
      <p><code>Python</code> <code>LLMs</code> <code>Z3 Solver</code> <code>Formal Verification</code> <code>AST</code></p>
      <p>
        <a href="https://github.com/acedev0/verifix/releases"><img src="https://img.shields.io/github/v/release/acedev0/verifix?style=flat-square&amp;label=release&amp;color=3fb950" alt="Latest VeriFix release" /></a>
        <img src="https://img.shields.io/github/last-commit/acedev0/verifix?style=flat-square" alt="VeriFix last commit" />
      </p>
    </td>
    <td width="50%" valign="top">
      <h3>🎬 <a href="https://github.com/acedev0/cinevault">CineVault</a></h3>
      <p><b>Netflix-style discovery and streaming, powered by Telegram.</b></p>
      <p>Search for a title, press play, and the bytes flow from Telegram directly to the browser or VLC player via HTTP range requests. No persistent media storage on the server.</p>
      <p><code>Python</code> <code>FastAPI</code> <code>Telethon</code> <code>MTProto</code> <code>Docker</code></p>
      <p>
        <a href="https://github.com/acedev0/cinevault/releases"><img src="https://img.shields.io/github/v/release/acedev0/cinevault?style=flat-square&amp;label=release&amp;color=3fb950" alt="Latest CineVault release" /></a>
        <img src="https://img.shields.io/github/last-commit/acedev0/cinevault?style=flat-square" alt="CineVault last commit" />
      </p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h3>📺 <a href="https://github.com/acedev0/televault">TeleVault</a></h3>
      <p><b>A private media library with a custom browser player.</b></p>
      <p>Playback runs on zero-disk byte-range streaming, thumbnails are WebP, and access is locked down with security-focused controls, including Argon2id hashing.</p>
      <p><code>Python</code> <code>FastAPI</code> <code>Telethon</code> <code>Argon2id</code> <code>Docker</code></p>
      <p>
        <a href="https://github.com/acedev0/televault/releases"><img src="https://img.shields.io/github/v/release/acedev0/televault?style=flat-square&amp;label=release&amp;color=3fb950" alt="Latest TeleVault release" /></a>
        <img src="https://img.shields.io/github/last-commit/acedev0/televault?style=flat-square" alt="TeleVault last commit" />
      </p>
    </td>
    <td width="50%" valign="top">
      <h3>📦 <a href="https://github.com/acedev0/AceUnzipBot">AceUnzipBot</a></h3>
      <p><b>Bulk archive extraction inside Telegram.</b></p>
      <p>Powered by 7-Zip. Jobs run through an asynchronous FIFO queue with live progress bars and thumbnails, plus a dedicated CLI and VPS deployment tooling.</p>
      <p><code>Python</code> <code>Telethon</code> <code>7-Zip</code> <code>AsyncIO</code> <code>Linux</code></p>
      <p>
        <a href="https://github.com/acedev0/AceUnzipBot/releases"><img src="https://img.shields.io/github/v/release/acedev0/AceUnzipBot?style=flat-square&amp;label=release&amp;color=3fb950" alt="Latest AceUnzipBot release" /></a>
        <img src="https://img.shields.io/github/last-commit/acedev0/AceUnzipBot?style=flat-square" alt="AceUnzipBot last commit" />
      </p>
    </td>
  </tr>
  <tr>
    <td colspan="2" valign="top">
      <h3>🍿 Ace Hub</h3>
      <p><b>Video discovery and synchronized watch parties.</b></p>
      <p>Real-time playback sync keeps every viewer in lockstep, on a responsive modern interface backed by a Prisma-managed database and WebSockets.</p>
      <p><code>Next.js 15</code> <code>React 19</code> <code>Prisma</code> <code>Socket.IO</code> <code>WebSockets</code></p>
      <p>
        <img src="https://img.shields.io/badge/status-in_development-8957e5?style=flat-square" alt="Ace Hub is in development" />
        <img src="https://img.shields.io/badge/access-private_repo-343434?style=flat-square" alt="Private Repository" />
      </p>
    </td>
  </tr>
</table>

<br />

## Architecture & Systems

### Neurosymbolic AI Loop

> [!NOTE]
> **Probabilistic generation needs deterministic verification.** LLMs generate intuitive patches; the Z3 SMT solver either mathematically proves the contract or extracts the exact failing edge-case input.

```mermaid
flowchart LR
    A["Buggy Code + Spec<br/>(@requires / @ensures)"] --> B["Symbolic Executor<br/>AST & Path Constraints"]
    B --> C{"Z3 SMT Solver<br/>Satisfiability Check"}
    C -->|"UNSAT<br/>(No counterexamples)"| D["✔ Formally Proven Sound<br/>Ready for Production"]
    C -->|"SAT<br/>(Violation found)"| E["Concrete Counterexample<br/>(e.g., x=None, amt &gt; bal)"]
    E --> F["LLM Patch Generator<br/>(Prompt + Concrete Failure Model)"]
    F --> G["AST Patcher<br/>Apply Candidate"]
    G --> B
```

<br />

### Zero-Disk Streaming Stack

> [!NOTE]
> **The server is a pipe, not a warehouse.** Bytes move from Telegram to the client player as they are requested, and nothing is retained on disk.

```mermaid
flowchart LR
    A["Player<br/>Browser / VLC"] -->|"GET + Range: bytes=a-b"| B["FastAPI<br/>Auth &amp; Range Parser"]
    B -->|"Chunk requests (1 MiB)"| C["Telethon<br/>MTProto Client"]
    C <-->|"Encrypted MTProto"| D[("Telegram Datacenter")]
    B -.->|"206 Partial Content<br/>Streamed chunk-by-chunk"| A
```

- **Range-first:** Each `Range: bytes=a-b` request maps directly to the minimal set of MTProto chunk fetches.
- **Flat memory:** Chunks stream into the HTTP response buffer on the fly. Memory use stays constant regardless of whether the file is 50 MB or 10 GB.
- **Immediate cancellation:** When the viewer scrubs or disconnects, the in-flight MTProto stream is aborted immediately.

<br />

## Engineering Distribution

```mermaid
pie title Stack & Engineering Focus
    "AI & Neurosymbolic Systems (LLMs + Z3)" : 35
    "Zero-Disk Streaming & MTProto" : 30
    "Real-Time Sockets & Next.js" : 20
    "Systems, Docker & Linux Ops" : 15
```

<br />

## How I build

| Principle | In practice |
| :-- | :-- |
| **Prove, don't guess** | LLMs propose candidate solutions; formal SMT solvers mathematically verify correctness before deployment. |
| **Stream, don't store** | Data flows from source to client. Nothing sits on the server waiting to be pruned. |
| **Bound everything** | Memory, concurrency, LLM token limits, and queue depths all have explicit hard ceilings. |
| **Automate the repetitive** | If I do it twice by hand, it becomes a script, a background queue, or a service. |
| **Design for failure** | Retries, cancellation, and recovery are fundamental architectural pillars, not post-incident patches. |
| **Keep trust boundaries explicit** | Cryptographic hashing (Argon2id), auth tokens, and permissions live at strictly drawn edges. |

<br />

## Toolbox

<table>
  <tr>
    <td><b>AI &amp; Verification</b></td>
    <td>
      <img src="https://img.shields.io/badge/LLMs-Large_Language_Models-7C3AED?style=flat-square&amp;logo=openai&amp;logoColor=white" alt="LLMs" />
      <img src="https://img.shields.io/badge/Google_Gemini-8E75B2?style=flat-square&amp;logo=google&amp;logoColor=white" alt="Gemini" />
      <img src="https://img.shields.io/badge/Z3_SMT_Solver-22C55E?style=flat-square" alt="Z3 SMT Solver" />
      <img src="https://img.shields.io/badge/Formal_Verification-6366F1?style=flat-square" alt="Formal Verification" />
      <img src="https://img.shields.io/badge/CEGIS_Loops-38BDF8?style=flat-square" alt="CEGIS" />
      <img src="https://img.shields.io/badge/AST_Manipulation-F59E0B?style=flat-square" alt="AST Analysis" />
    </td>
  </tr>
  <tr>
    <td><b>Languages</b></td>
    <td>
      <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&amp;logo=python&amp;logoColor=white" alt="Python" />
      <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&amp;logo=typescript&amp;logoColor=white" alt="TypeScript" />
      <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&amp;logo=javascript&amp;logoColor=black" alt="JavaScript" />
      <img src="https://img.shields.io/badge/Bash-4EAA25?style=flat-square&amp;logo=gnubash&amp;logoColor=white" alt="Bash" />
      <img src="https://img.shields.io/badge/SQL-4479A1?style=flat-square&amp;logo=postgresql&amp;logoColor=white" alt="SQL" />
    </td>
  </tr>
  <tr>
    <td><b>Backend</b></td>
    <td>
      <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&amp;logo=fastapi&amp;logoColor=white" alt="FastAPI" />
      <img src="https://img.shields.io/badge/Telethon-2AABEE?style=flat-square&amp;logo=telegram&amp;logoColor=white" alt="Telethon" />
      <img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&amp;logo=nodedotjs&amp;logoColor=white" alt="Node.js" />
      <img src="https://img.shields.io/badge/AsyncIO-3776AB?style=flat-square&amp;logo=python&amp;logoColor=white" alt="AsyncIO" />
    </td>
  </tr>
  <tr>
    <td><b>Frontend</b></td>
    <td>
      <img src="https://img.shields.io/badge/Next.js_15-000000?style=flat-square&amp;logo=nextdotjs&amp;logoColor=white" alt="Next.js" />
      <img src="https://img.shields.io/badge/React_19-61DAFB?style=flat-square&amp;logo=react&amp;logoColor=black" alt="React" />
      <img src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&amp;logo=tailwindcss&amp;logoColor=white" alt="Tailwind CSS" />
    </td>
  </tr>
  <tr>
    <td><b>Real-Time</b></td>
    <td>
      <img src="https://img.shields.io/badge/Socket.IO-010101?style=flat-square&amp;logo=socketdotio&amp;logoColor=white" alt="Socket.IO" />
      <img src="https://img.shields.io/badge/WebSockets-6E40C9?style=flat-square" alt="WebSockets" />
      <img src="https://img.shields.io/badge/MTProto-229ED9?style=flat-square&amp;logo=telegram&amp;logoColor=white" alt="MTProto" />
      <img src="https://img.shields.io/badge/HTTP_Range_Requests-4B5563?style=flat-square" alt="HTTP range requests" />
    </td>
  </tr>
  <tr>
    <td><b>Data &amp; Security</b></td>
    <td>
      <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&amp;logo=postgresql&amp;logoColor=white" alt="PostgreSQL" />
      <img src="https://img.shields.io/badge/SQLite-003B57?style=flat-square&amp;logo=sqlite&amp;logoColor=white" alt="SQLite" />
      <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&amp;logo=redis&amp;logoColor=white" alt="Redis" />
      <img src="https://img.shields.io/badge/Prisma-2D3748?style=flat-square&amp;logo=prisma&amp;logoColor=white" alt="Prisma" />
      <img src="https://img.shields.io/badge/Argon2id-10B981?style=flat-square" alt="Argon2id" />
    </td>
  </tr>
  <tr>
    <td><b>Ops &amp; Infra</b></td>
    <td>
      <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&amp;logo=docker&amp;logoColor=white" alt="Docker" />
      <img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&amp;logo=linux&amp;logoColor=black" alt="Linux" />
      <img src="https://img.shields.io/badge/systemd-4B5563?style=flat-square&amp;logo=linux&amp;logoColor=white" alt="systemd" />
      <img src="https://img.shields.io/badge/Nginx-009639?style=flat-square&amp;logo=nginx&amp;logoColor=white" alt="Nginx" />
      <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&amp;logo=git&amp;logoColor=white" alt="Git" />
    </td>
  </tr>
</table>

<br />

## What I can help with

- **AI & Neurosymbolic Engineering:** LLM agent tool calling, structured generation, CEGIS self-repair, SMT formal contract proofs.
- **Telegram Automation & MTProto:** Telethon userbots, bot transactions, high-volume queue workers, MTProto chunk streaming.
- **Zero-Disk Streaming Engines:** Range-request media proxies that stream directly from cloud networks with flat memory.
- **Real-Time Collaborative Apps:** Synchronized state, WebSockets, Next.js frontend architectures.
- **Production Hardening:** Dockerizing complex Python/Node runtimes, systemd daemon management, secure reverse proxies.

<br />

## Let's talk

Got an ambitious challenge involving **LLMs & AI**, **formal verification**, **streaming infrastructure**, or **real-time systems**? Message me on [Telegram](https://t.me/Aceddev) or [send an email](mailto:Acedevmc@gmail.com).

<div align="center">

<br />

**Stream, don't store. Prove, don't guess.**

<sub>Built by Ace, <a href="https://github.com/acedev0">@acedev0</a></sub>

</div>
