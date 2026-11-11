<div align="center">

# Alastair Green · `@helvector`

**Generative AI production systems: agents, tools, checks and craft.**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-alastairgreen-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/alastairgreen/)
[![Email](https://img.shields.io/badge/Email-alastair@onestepbeyond.us-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:alastair@onestepbeyond.us)

</div>

---

I work where generative AI meets VFX, production technology and creative automation.

Models will continually change, yet the system has to evolve slowly. Agents can run the tools, but human artists need to be the gatekeepers of taste.

> **How do you turn fast-changing models into creative work that is repeatable, controllable and good enough for real production?**

---

## The path I've been on

```
prompting → workflows → agents → tools → structured data → production infrastructure
```

### 1. Prompting is turning into context engineering · *Tested*

I keep a large prompt knowledge base built on photography, cinematography, tabletop, beauty and automotive craft. But the prompt is now a small part of what goes into a generation:

```
instructions + references + masks + camera data + brand rules
+ 3D assets + previous frames + metadata + tool outputs + pass/fail criteria
```

**Built:** prompt co-writers for one job each (product, interiors, automotive), each with locked grounding rules such as label fidelity and set continuity, so the model stops inventing things.

### 2. Agentic VFX · *Tested on real shots, still R&D*

The LLM stops writing prompts and becomes a **supervisor that picks specialist tools**:

```
understand shot → find target → segment / track → build mask → prep input
→ generate / modify → compare against source → QC → retry if needed → package
```

Vehicle and product shots give a model nowhere to hide: geometry, badges, reflections and continuity all have to stay correct. A typical test: track an object with SAM, remove it from the input, follow it with a moving crop, let the model rebuild the surface, then have an automated check pass or reject it.

The real question isn't "can AI remove this?" It's whether you can build something that removes it, checks it, retries, records cost and becomes a tool someone else can use.

### 3. Probabilistic vs deterministic · *Principle*

| Probabilistic (models) | Deterministic (pipeline) |
|---|---|
| inventing missing pixels | tracking, masks, crops |
| relighting, restyling | compositing back onto the source |
| variation | keeping everything outside the edit identical |

**Built:** pixel-safe edit pipelines. Crop, generate, comp back, and measure that every pixel outside the edit matches the source.

### 4. ComfyUI as a tool forge · *Experimental → Direction*

Less an image UI, more a place to build **repeatable production operations**: removal, product replacement, relighting, segmentation, cleanup, localisation, upscaling, visual QC.

```
specialist models → ComfyUI graph → reusable tool → agent / orchestrator → artist
```

**Built:** a ComfyUI node pack, workflows and CLI scripts for video model pipelines.

### 5. Camera craft as data · *Experimental*

Commercial cinematography holds knowledge nobody wrote down: pack shots, beauty turns, pushes, orbits, reveals, car passes. The aim is a **craft-motion library** of the moves a good DP would actually use, with 3D and digital twins as the control layer, not the final render.

**Built:**
- A virtual camera that measures how real commercials were shot and rebuilds the moves as metre-scaled 3D playblasts that steer generative video
- A tracking-target generator: one SVG in, a printable sheet of 60 uniquely coded targets out
- A Windows build of video motion capture with humanoid retargeting and FBX export

### 6. Evaluating for production, not demos · *Tested*

What I check: **product fidelity**, **temporal consistency**, **motion**, **editability**, **failure rate**, **time and cost per usable shot**, **pipeline fit** and **repeatability**. Research benchmarks (VBench, EvalCrafter, VideoGen-Reward) help, but they don't tell you whether *your* product came out right.

**Built:** VideoAB for synced wipe comparisons, and a blind A/B bench for whether a voice performance survives translation.

### 7. The economics of a usable result · *Direction*

```
cost per generation × generations per accepted result × retry rate
+ human intervention + finishing time = what it actually costs
```

API price isn't production cost, and seats handed out isn't adoption.

### 8. Governance and provenance · *Direction*

Lock tools down too hard and artists drift to personal accounts. Leave them loose and professional work becomes impossible. For any output you should be able to say which model, which workflow version, who ran it, what went in, what it cost, and whether you can recreate it.

**Built:** a C2PA Content Credentials inspector that runs entirely in the browser, and a studio mission control where every project tile, health check and repo link comes from one config file.

### 9. Keep the agent swappable · *Direction*

General AI handles intent, context and permissions. Specialist tools handle VFX, image, video, 3D and finishing. Claude is my current supervisor, but the design shouldn't care which tool-using model fills that slot.

---

## How I work

Find a real production problem → build the ugly experiment → measure it → find the repeatable part → make it a tool → add QC and governance → share it → repeat.

---

## Public repos

| Repo | What it does |
|---|---|
| [**pain-cave-timer**](https://github.com/helvector/pain-cave-timer) | Glanceable interval timer for indoor cycling. Reads coached workouts straight from TrainingPeaks emails. |
| [**VideoAB**](https://github.com/helvector/VideoAB) | Side-by-side MP4 comparison with a draggable wipe, synced playback and loop regions. |
| [**toyxyz_RGBMocap**](https://github.com/helvector/toyxyz_RGBMocap) | Native Windows video motion capture with retargeting and FBX/VMD export. |

Most of my work is private studio tooling. Happy to talk through any of it.

---

## Stack

- **Agents:** Claude · GPT · Gemini · MCP
- **Generative media:** Google · FLUX · Kling · Seedance · Magnific · ElevenLabs
- **Code:** TypeScript · JavaScript · Python · Node.js
- **Creative tooling:** ComfyUI · Blender · Three.js · SAM
- **Ship:** Next.js · Tailwind · Vercel · Google Cloud · AWS · Replit

---

## Things I'm trying to prove

- Can production camera craft become a reusable library that agents and models can use?
- Can agents run VFX tools reliably enough to take over repetitive shots?
- Can segmentation + generation + automated QC cut manual VFX work without losing quality?
- Can ComfyUI become a governed tool-building layer, not just an artist UI?
- How should AI production cost be measured when failure is part of the process?
- How much craft can an agent hold before the human becomes the exception handler instead of the operator?
- Where should probabilistic AI stop and deterministic VFX begin?

<div align="center">

*Always experimenting. Always one step beyond.*

</div>
