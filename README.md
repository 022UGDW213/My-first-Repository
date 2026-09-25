# My First Repository

> Created by [022UGDW213 (Time Loops)](https://github.com/022UGDW213) — Tech Enthusiast | Cybersecurity | AI Explorer

## About

This is my first GitHub repository, kept as a portfolio showcase and a learning record for
version control, web development, and AI.

## Repository Contents

| File | Description |
|------|-------------|
| `README.md` | This documentation |
| `architecture.drawio` | Architecture diagram of the iBot Synthetic Intelligence V8 service stack (draw.io / diagrams.net), drawn from live `/health` probes taken 2026-09-26 |
| `Email Signature.html` | Self-contained HTML email signature — inline CSS only, no scripts, no external requests |
| `bg.mp4` | Video asset — H.264 High Profile (AVC) 1920×1080 at 29.97 fps with AAC-LC 44.1 kHz stereo audio, 11.08 s, 8.04 MiB |
| `DEPLOY.md` | Deployment record for the initial committed release |
| `LICENSE` | MIT License |
| `.gitignore` | Ignore rules for OS, editor, Python and Node build artefacts |

Every file listed above exists in the repository (checked 2026-09-26). All of the data in this
repository is real and was command-verified on that date; see [Verification](#verification).

## Tech Stack

Languages and platforms used by the repository owner:

- **Languages:** Python, HTML, CSS, JavaScript, C
- **AI/ML:** TensorFlow, PyTorch, Ollama, HuggingFace
- **Cloud:** AWS (EC2, Bedrock), Cloudflare
- **OS:** macOS, Linux, HarmonyOS NEXT

Toolchain measured on the workstation used to maintain this repository, 2026-09-26:

| Tool | Version | Command |
|------|---------|---------|
| Node.js | v22.23.2 | `node --version` |
| npm | 12.0.2 | `npm --version` |
| Python | 3.10.12 | `python3 --version` |
| g++ | 11.4.0 (Ubuntu 11.4.0-1ubuntu1~22.04.3) | `g++ --version` |
| Git | 2.34.1 | `git --version` |
| Docker | 29.1.3 | `docker --version` |
| Kernel | Linux 6.8.0-136-generic x86_64 | `uname -srm` |
| Distribution | iBot Synthetic Intelligence 8.3.0 (AGI + Quantum) | `. /etc/os-release` |

## Connect

- GitHub: [@022UGDW213](https://github.com/022UGDW213)
- Website: [o22ugdw213.network](https://o22ugdw213.network)
- YouTube: [@O22UGDW213](https://youtube.com/@O22UGDW213)

## Projects

- **iBot Synthetic Intelligence** — autonomous AI platform. The source repository is private, so
  no public repository link is given here. Measured on 2026-09-26: **697 skill packs** under
  `.agents/skills`, and **12 of 14** probed local service endpoints answering `/health` (the
  running set changes between restarts). Public entry point:
  [o22ugdw213.network](https://www.o22ugdw213.network)
- [Harmony-OS-Next](https://github.com/022UGDW213/Harmony-OS-Next) — HarmonyOS development
- [Python-Programing](https://github.com/022UGDW213/Python-Programing) — Python scripts and AI tools
- [Network](https://github.com/022UGDW213/network) — web application dashboard

## Verification

Every number in this README was produced by the commands below on 2026-09-26 on the workstation
used to maintain this repository. Relative paths are relative to the iBot Synthetic Intelligence
V8 source tree. The live-service figures are a snapshot of one probe, not constants — which
services are listening changes between restarts.

| Value | Command | Result |
|-------|---------|--------|
| Skill packs | `find .agents/skills -maxdepth 2 -name SKILL.md -type f \| wc -l` | `697` |
| Entries in `.agents/skills` | `ls -A .agents/skills \| wc -l` | `699` — 697 skill directories plus 2 bundled MIT licence text files |
| MCP server files | `ls mcp/*.mjs \| wc -l` | `39` |
| Agents registered (Agents API) | `curl -s http://127.0.0.1:4003/agents` | `39` |
| Agents registered (Orchestrator) | `curl -s http://127.0.0.1:4002/health` | `7` |
| Service endpoints answering `/health` | `for p in 18789 18790 3000 4002 4003 4040 9008 9009 9003 9002 9007 11434 18900 18901; do curl -s -m 4 -o /dev/null -w "$p %{http_code}\n" http://127.0.0.1:$p/health; done` | `200` for 12 ports (18789, 18790, 3000, 4002, 4003, 4040, 9008, 9009, 9003, 9002, 9007, 18901); `000` for `11434` and `18900` — probe taken 2026-09-25T21:01:57Z |
| Ollama listening socket | `ss -ltn \| grep -E ':11434\|:18900'` | no match for either port |
| Mythos Cortex service state | `systemctl is-active mythos-cortex` | `inactive` — `mythos-cortex.service` exited 2026-09-26 01:00:06 with `status=0/SUCCESS`, so the port has no listener |
| Ollama model manifests on disk | `find /root/.ollama/models/manifests -type f \| wc -l` | `29` manifests present, Ollama server not running |
| `bg.mp4` codec, resolution, frame rate | GStreamer `qtdemux` pad caps | `video/x-h264, profile=high, level=4, width=1920, height=1080, framerate=30000/1001` |
| `bg.mp4` audio | GStreamer `qtdemux` audio pad caps | `audio/mpeg, mpegversion=4, profile=lc, rate=44100, channels=2` |
| `bg.mp4` duration and size | MP4 `mvhd` box (timescale 1000, duration 11078) and file size | 11.078 s, 8,425,453 bytes (8.04 MiB) |
| `LICENSE` | GitHub licence detection on this repository's page | `MIT license` |

No H.264 decoder is installed on this workstation (`gst-launch-1.0` reports "Missing decoder:
H.264 (High Profile)"), so no frame of `bg.mp4` was decoded for this check — the video facts above
come from the container's own headers and demuxer caps.

## License

MIT License — see [LICENSE](LICENSE)
