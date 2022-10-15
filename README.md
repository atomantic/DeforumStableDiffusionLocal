### Slowly-Grokking is bit of a bodger.

I don't know the best way to do anything or how to contribute to other's projects in an effective way,
but I am more than happy to help if I can.

### real credit goes to those that have done the work before me

Features added:

```
-set FPS via settings file ("fps": 12,)
-Adjust Strength_schedule per frame in 2D/3D animations {"36": 0.65,}
-now creates 'n_batch' renders in 2D/3D  (remember to have random seed -1)
-added audio to video output "audio_path"
```

ToDo:

```
-Add other settings to Anim_settings
-Add FPS/Prompt Frame math (autoscale promptFrames upon fps adjustment, or allow seconds to be input intead of frames)
-Add cycle/pattern support for anim_settings and prompts (loop through prompts)
-Seed previews for arbitary frames
-Enable animation prompts to reinit between scenes (generating each prompt individually) or at will
-WebUI
-discord/other remote CC
-Masking and remasking
-img2txt -> init -> txt2img
-Seed/preset saving.
-advanced img2img
-whisper, gpt3, CLIP... you see the future?
```

I will be focusing on quality of life features to make long form generations more feasible and coherent.
(D)SD is already capable, but creating complex works is tedious. The main objective here is to simplify the workflow and save time.
SD is amazing, but we still have more ideas than we could create in a lifetime. I aim to add more than just SD to this toolset, and enable
quality, longer-form content to be produced in a time-friendly manner. The goal is add more intentionality to generated art to allow our imaginations to shine
moreso than the randomly-generated, low-effort content currently flooding the world.

<br>
<br>

- \*\*this repo forked from [HelixNGC7293](https://github.com/HelixNGC7293/DeforumStableDiffusionLocal)
- **Local Version by [DGSpitzer](https://www.youtube.com/channel/UCzzsYBF4qwtMwJaPJZ5SuPg) [大谷的游戏创作小屋](https://space.bilibili.com/176003)**
- **Special Thanks to [VIVY Has A Dream](https://github.com/vivyhasadream) for all the help!**

Made this quick local Windows version mostly based on the Colab code by deforum, which supports very cool turbo mode animation output for Stable Diffusion!

As an artist and Unity game designer, I may not very familiar with Python code, so let me know whether there is any improvement for this project!

It's tested working on Windows 10 with RTX 2080 SUPER and RTX 3090 GPU (it runs somehow much faster on my local 3090 then Colab..), **I haven't tested it on Mac though.**

## Installation

You can use an [anaconda](https://conda.io/) environment to host this local project:

```
conda create --name dsd python=3.8.5 -y
conda activate dsd
```

And then cd to the cloned folder, run the setup code, and wait for ≈ 5min until it's finished

```
python setup.py
```

## Manually download 3 Model Files

**You need to get the `sd-v1-4.ckpt` file and put it on the `./models` folder first to use this. It can be downloaded from [HuggingFace](https://huggingface.co/CompVis/stable-diffusion).**

**Additionally, you should put `dpt_large-midas-2f21e586.pt` on the `./models` folder as well, [the download link is here](https://github.com/intel-isl/DPT/releases/download/1_0/dpt_large-midas-2f21e586.pt)**

**There should be another extra file `AdaBins_nyu.pt` which should be downloaded into `./pretrained` folder, [the download link is here](https://cloudflare-ipfs.com/ipfs/Qmd2mMnDLWePKmgfS8m6ntAg4nhV5VkUyAydYBp8cWWeB7/AdaBins_nyu.pt)**

## How to use it?

For more info go see [HelixNGC7293](https://github.com/HelixNGC7293/DeforumStableDiffusionLocal)
I only use this command at the moment:

```
python run.py --enable_animation_mode --settings runSettings_Template.json
```

**The output results will be available at `./output` folder.**

All the needed variables & prompts for Deforum Stable Diffusion are set in the txt file (You can refer to the [Colab](https://colab.research.google.com/github/deforum/stable-diffusion/blob/main/Deforum_Stable_Diffusion.ipynb) page for definition of all the variables), you can have many of settings files for different tasks. There is a template file called `runSettings_Template.json`. You can create your own txt settings file as well.

That's it!
