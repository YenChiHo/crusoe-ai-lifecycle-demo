# Crusoe AI Lifecycle Demo

An interactive booth demo of the full model lifecycle on Crusoe Cloud: prepare data, fine-tune, post-train with reinforcement learning, evaluate and register, then serve. It is built for events such as SGLang Summit and KubeCon, and for customer conversations with AI startups, AI-native companies and enterprise AI teams.

It is a single self-contained `index.html` with no build step.

## Run it

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000. An internet connection is needed for the Google Fonts; everything else is inline.

## Pages

| Key | Page | Crusoe service |
|---|---|---|
| 0 | Flow: the whole pipeline animated on one map | All |
| 1 | Prepare data | Crusoe Cloud |
| 2 | Fine-tune | Serverless Fine-Tuning, Managed Slurm, Crusoe Managed Kubernetes |
| 3 | Post-train with RL | Crusoe Managed RL |
| 4 | Evaluate & register | Crusoe Managed MLflow |
| 5 | Serve | Crusoe Managed Inference, Self-Serve Endpoints |
| 6 | Platform: one GPU fleet across every step | Crusoe Cloud |
| 7 | Why Crusoe: comparison, run of show, links | |

The switches under the top bar change the content on every page:

- **Industry:** Physical AI (warehouse manipulation planner), financial services (AML alert triage), healthcare (clinical coding), biotech (kinase inhibitor generation)
- **Customer:** AI startup, AI native, Enterprise AI
- **Talk track:** General, SGLang Summit, KubeCon

## Booth controls

- `0`–`7` jump to a page; `←` `→` move between pages
- `Space` on page 0 plays the flow
- `F` goes fullscreen
- **Tour** cycles through every page and moves to the next industry each loop, for an unattended screen

## Before showing it

- Training curves, rewards, scores and model outputs are simulated and labelled as such on every page.
- Fine-tuning, MLflow and inference code follows the public examples in [crusoecloud/crusoe-developer-hub](https://github.com/crusoecloud/crusoe-developer-hub). The Managed RL code follows the Tinker API pattern that the service is compatible with; confirm client setup with the Managed RL team.
- Crusoe Managed RL and Crusoe Managed MLflow are in private preview.
- MemoryAlloy™ technology figures are Crusoe's published results on GPT-OSS-120B versus vLLM.

## Versions

Demo-ready versions are tagged `vX.Y-demo` and published as GitHub releases. Use the latest release at events.
