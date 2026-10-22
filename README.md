# World2HOSI: A Multi-Expert Harness for Long-Horizon Human-Object-Scene Interaction Generation

<p align="center">
  <a href="https://arxiv.org/pdf/2610.27725"><img src="https://img.shields.io/badge/Paper-PDF-blue?style=flat-square" alt="Paper PDF"></a>
  <a href="https://arxiv.org/abs/2610.27725"><img src="https://img.shields.io/badge/arXiv-2610.27725-b31b1b?style=flat-square&amp;logo=arxiv&amp;logoColor=white" alt="arXiv"></a>
  <a href="https://nintreesssss.github.io/World2HOSI/"><img src="https://img.shields.io/badge/Project%20Page-World2HOSI-e3b341?style=flat-square" alt="Project Page"></a>
</p>

**Code coming soon.**

World2HOSI turns reconstructed 3D Gaussian scenes and natural-language instructions into continuous human-object-scene interactions. By coordinating navigation, object manipulation, and scene interaction experts around a shared, evolving world state, it supports multi-stage tasks without training an additional unified motion generator.

![World2HOSI teaser](assets/teaser.png)

## Abstract

Long-horizon human-object-scene interaction (HOSI) is central to embodied AI, animation, and game development. Existing human-object interaction (HOI) and human-scene interaction (HSI) models excel in their respective domains, but none alone covers tasks requiring multiple interaction skills. Training unified HOSI models is hindered by scarce and costly data.

We introduce World2HOSI, a multi-expert orchestration harness that generates continuous HOSI data from 3D Gaussian Splatting (3DGS) scenes and natural language instructions. Our key insight is that long-horizon HOSI hinges not on a stronger single model but on orchestration. Given a shared, structured scene state and an orchestration harness grounded in it, existing experts can jointly accomplish tasks beyond the reach of any of them alone.

World2HOSI realizes this insight as a closed loop around a persistent scene state built from decoupled background and object assets. A harness plans action stages over this state, invokes experts via their native conditioning interfaces, and writes each action's effects back, so that every invocation is grounded in the evolving world.

To reduce physical artifacts, bounded residual optimization and contact-driven physics simulation further ensure the physical plausibility of human motion and object manipulation, respectively, while preserving interaction intent. Experiments and a perceptual user study show that World2HOSI achieves the best task completion and interaction quality on the evaluated HOSI tasks, while generating more diverse data.

## Pipeline

![World2HOSI pipeline](assets/pipeline.png)

The pipeline organizes the scene into interactive assets, breaks an instruction into action stages, and invokes the appropriate motion experts. Each action updates the scene state so later interactions follow the new object locations. Optional physics-based refinement improves physical plausibility while preserving the intended interaction.

## Long-Horizon Demonstrations

### Sequence 1: Move a Chair, Drink Coffee, and Sit Down

![Long-horizon demonstration 1](assets/long_sequence1.gif)

> **Instruction:** Move the chair to the threshold, then walk over and take a sip of coffee. After finishing it, place the cup on the nearby table, and finally sit down in the chair.

### Sequence 2: Move Books, Adjust a Stool, and Sit Down

![Long-horizon demonstration 2](assets/long_sequence2.gif)

> **Instruction:** Walk over and move the books to the table nearby, then walk over and adjust the stool, and finally sit down.

