# 🦆 microduck-docker

**The [Microduck](https://pollen-robotics.com/microduck) robot simulator - in one command.**

<p align="center">
  <a href="https://hub.docker.com/r/ajeetraina777/microduck-docker"><img alt="Docker Pulls" src="https://img.shields.io/docker/pulls/ajeetraina777/microduck-docker?logo=docker&logoColor=white&color=2496ED"></a>
  <a href="https://hub.docker.com/r/ajeetraina777/microduck-docker/tags"><img alt="Image size" src="https://img.shields.io/docker/image-size/ajeetraina777/microduck-docker/latest?logo=docker&logoColor=white"></a>
  <a href="https://github.com/ajeetraina/microduck-docker/actions/workflows/build.yml"><img alt="Build" src="https://github.com/ajeetraina/microduck-docker/actions/workflows/build.yml/badge.svg"></a>
  <img alt="Architectures" src="https://img.shields.io/badge/arch-amd64%20%7C%20arm64-informational">
</p>

Microduck is a 25 cm robot that walks on two legs, made by [Pollen Robotics](https://pollen-robotics.com)
and open-sourced with Hugging Face. This image lets you **watch it walk, teach it
tricks, and train your own robot brain** - in your browser, on the computer you
already have.

You do **not** need the real robot, Python, a GPU, or any knowledge of neural
networks. You need Docker and one line:

```bash
docker run --rm -p 63317:63317 -p 8788:8788 ajeetraina777/microduck-docker
```

Then open **<http://localhost:63317>** 🎉

---

## What you get

Everything is already inside the image - no downloads on first run, no setup.

| Inside the box | What it means |
|---|---|
| 🧠 **9 pretrained robot brains** | walking, standing, kicking a ball, a forward roll… press play and watch |
| 🦴 **The real robot model** | the actual 3D Microduck, with real joint limits and real physics (MuJoCo) |
| 🎓 **Teach panel** | ask for a trick in plain English - "stand on one leg" - and watch it learn |
| 🏋️ **Full training toolkit** | train a brand-new walking brain on your own laptop's CPU in minutes |
| 🎬 **Video capture** | film your robot and export mp4/GIF to share |
| 🖥️ **Runs anywhere** | Intel, AMD, Apple Silicon, Raspberry Pi |

See [`docs/USER-MANUAL.md`](docs/USER-MANUAL.md) for every command, and
[`docs/BUILD.md`](docs/BUILD.md) for building and publishing the image yourself.

---

## Run it

```bash
# simplest
docker run --rm -p 63317:63317 -p 8788:8788 ajeetraina777/microduck-docker

# or with docker compose (keeps trained policies + captures in a volume)
docker compose up
```

Running it inside a hardened **Docker Sandboxes (sbx) microVM**?
See [ajeetraina/microduck-docker-sandbox](https://github.com/ajeetraina/microduck-docker-sandbox).

---

## Based on / credits

This repository **builds on** the excellent packaging work of
[**srayuth089/microduck-docker**](https://github.com/srayuth089/microduck-docker)
(Apache-2.0) and republishes the image under the `ajeetraina777` Docker Hub
namespace, with the build wired to publish via GitHub Actions.

The simulator itself is the work of three upstream projects, all credited in
[`NOTICE`](NOTICE):

- [`pollen-robotics/microduck_rl`](https://github.com/pollen-robotics/microduck_rl) - robot model + physics
- [`jonathanhawkins/microduck-lab`](https://github.com/jonathanhawkins/microduck-lab) - the lab + viewer
- [`IronSpiderMan/MicroDuckModels`](https://github.com/IronSpiderMan/MicroDuckModels) - the pretrained brains

---

## ⚠️ License - non-commercial

Code here is **Apache-2.0** (see [LICENSE](LICENSE)). **But** the image bundles the
Microduck 3D model and the pretrained policies, which carry a **Creative Commons
BY-SA-NC** (non-commercial) clause. So **the image as a whole may not be used
commercially.** Educational, personal, research and hobby use are all fine. See
[`NOTICE`](NOTICE) for the full breakdown.
