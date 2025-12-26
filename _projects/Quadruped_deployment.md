---
layout: page
title: Learning-based Control with Low-level Interface
description: Develop low-level control interface for quadruped robots, with reinforcement learning in IsaacGym and real-world deployment.
img: assets/img/deployment.gif
redirect:
importance: 2
category: work
---

Building bottom up, I first developed a low-level control interface for single joint by UDP protocol, enabling position control for legs, including user-input position or sinusoidal position (as shown below). Then, I port from UDP to [lcm](https://lcm-proj.github.io/lcm/) protocol, with a publisher-subscriber architecture for sending robot commands and receiving its states.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PositionControl.gif" title="Position Control" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PositionControl_Sinusoidal.gif" title="Sinusoidal Position Control" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
After that, I deployed existing gait generator to real robot controlling four legs in the same time. Finally, I trained multiple locomotion policies (flat only, general) in IsaacGym and deployed them to real robot, where I also integrated IMU sensor to provide necessary observations for the policy.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Pattern_Generator.gif" caption="Pattern Generator" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/IsaacGym_eval.gif" caption="IsaacGym evaluation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Below is the final deployment result for robust locomotion.

<figure class="video-wide" style="text-align:center">
  {% include video.liquid path="https://www.youtube.com/embed/M_Wu1FNsxcE" width="100%" %}
  <figcaption><em>Walking on a QRC practice terrain</em></figcaption>
</figure>
