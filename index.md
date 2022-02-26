**Abstract:** Equivariant neural networks enforce symmetry within the structure of their convolutional layers, resulting in a substantial improvement in sample efficiency when learning an equivariant or invariant function. Such models are applicable to robotic manipulation learning which can often be formulated as a rotationally symmetric problem. This paper studies equivariant model architectures in the context of Q-learning and actor-critic reinforcement learning. We identify equivariant and invariant characteristics of the optimal Q-function and the optimal policy and propose equivariant DQN and SAC algorithms that leverage this structure. We present experiments that demonstrate that our equivariant versions of DQN and SAC can be significantly more sample efficient than competing algorithms on an important class of robotic manipulation problems.

<style>
.column {
  float: left;
  width: 33.33%;
}
.lc{
  float: left;
  width: 16.66%;
}
.caption {
    margin: 0;
    vertical-align: baseline;
    text-align: center;
}
img.rounded {
  object-fit: cover;
  border-radius: 50%;
  height: 120px;
  width: 120px;
  margin-left: auto;
  margin-right: auto;
  display: block;
}
.people_column {
  float: left;
  width: 150px;
}
</style>

## Paper
Published at The Tenth International Conference on Learning Representations (ICLR 2022)  
**Spotlight Presentation**  
[OpenReview](https://openreview.net/forum?id=7F9cOhdvfk_)

<div style="width:100%; display:flex">
  <div class="people_column">
    <img src="img/dian.jpeg" class="rounded">
    <p class="caption">
      <a href="https://pointw.github.io">Dian Wang</a>
    </p>
  </div>
  <div class="people_column">
    <img src="img/robin.jpeg" class="rounded">
    <p class="caption">
      <a href="http://mathserver.neu.edu/robin/">Robin Walters</a>
    </p>
  </div>
  <div class="people_column">
    <img src="img/rob.jpeg" class="rounded">
    <p class="caption">
      <a href="http://www.ccs.neu.edu/home/rplatt/">Robert Platt</a>
    </p>
  </div>
</div>

Khoury College of Computer Sciences  
Northeastern University


## Idea
<p align="center">
  <img src="img/equi.gif" width="400px">
</p>

This work studies the SO(2) equivariant property of robotic manipulation in the context of reinforcement learning. We use equivariant networks to enforce the equivariance in the structure of the networks to improve the sample efficiency.

<p align="center">
  <img src="img/dqn.png" width="250px">
</p>

In Equivariant DQN, if the input state of the Q-network is rotated, the output of the Q-network (where the value of each cell in the 3x3 grid represents the Q-value of moving towards a specific direction) will be rotated by the same amount. 

<p align="center">
  <img src="img/actor_critic.png" width="600px">
</p>

In Equivariant SAC, if the input state of the actor (left) is rotated, the output action of the actor will be rotated by the same amount. If the input state and action of the critic (right) are rotated, the output Q-value of the critic will remain the same.

<div>
  <div class="column">
    <img src="img/pick.gif" style="width:100%">
    <p class="caption">Object Picking</p>
  </div>
  <div class="column">
    <img src="img/pull.gif" style="width:100%">
    <p class="caption">Block Pulling</p>
  </div>
  <div class="column">
    <img src="img/drawer.gif" style="width:100%">
    <p class="caption">Drawer Opening</p>
  </div>
</div>

<div>
  <div class="column">
    <img src="img/stack.gif" style="width:100%">
    <p class="caption">Block Stacking</p>
  </div>
  <div class="column">
    <img src="img/h1.gif" style="width:100%">
    <p class="caption">House Building</p>
  </div>
  <div class="column">
    <img src="img/corner.gif" style="width:100%">
    <p class="caption">Corner Picking</p>
  </div>
</div>

Our Equivariant SAC can solve different manipulation tasks with extraordinarily high sample effeciency.

## Video

## Code

[https://github.com/pointW/equi_rl](https://github.com/pointW/equi_rl)

## Citation
{% raw %}
```
@inproceedings{
wang2022so2equivariant,
title={{$\mathrm{SO}(2)$}-Equivariant Reinforcement Learning},
author={Dian Wang and Robin Walters and Robert Platt},
booktitle={International Conference on Learning Representations},
year={2022},
url={https://openreview.net/forum?id=7F9cOhdvfk_}
}
```
{% endraw %}

## Contact
If you have any questions, please feel free to contact [Dian Wang](https://pointw.github.io) at wang[dot]dian[at]northeastern[dot]edu.
