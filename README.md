<h1 align="center"> Differentiable MPC applied in a simulated Self Driving Car (CARLA Simulator) </h1>

<p align="center">
  <img
    src="https://user-images.githubusercontent.com/19806622/162852879-2b87ec45-bb82-4fca-b396-9e3d709ae09c.png"
 >
 </p>

## Índex 

* [Project Description](#project-description)
* [Motivation](#motivation)
* [Contributions](#contributions)
* [Related Work](#related-work)
* [Tecnologies Applied](#tecnologies-applied)
* [Developers](#developers)
* [Conclusion](#conclusion)

## Project Description

<p align="justify"> This project is based on the paper "Differentiable MPC for End-to-end Planning and Control" and
the proposal is to study in deep the theory presented and implement the Model Predictive Control
(MPC) as a policy class for reinforcement learning in continuous state and action spaces and to
apply it to planning and control of autonomous vehicles satisfying trajectory optimization and most
effcient path.
The MPC is used to control a process while satisfying a set of constraints. MPC models predict
the change in the dependent variables of modeled system that will be caused by changes in the
independent variables, therefore provides one way of combining the advantages of model-free and
model-based approaches.
MPC formulation[1] shows up that MPC is based on iterative, fnite-horizon (at time t the
current state is a sample[2]) of the optimization of a plant model (cost-minimizing control strategy
is computed[2] for a short time horizon in the future). In this project, the MPC generate a policy
class u = &pi; (x<sub>init</sub>;C; f). Considering the cost C and dynamics model f. The approach involves
learning by differentiating through MPC and using KKT conditions of the convex optimization at
fixed point of the controller. The cost and dynamics of the controller are learnt by minimizing the
Imitation learning loss in an end-to-end fashion. Our goal is to develop a robust end-to-end MPC
controller in an Autonomous Driving setting. Below is presented the model proposed:</p>

<p align="center">
  <img
    src="https://user-images.githubusercontent.com/19806622/162855872-02362be6-4a69-4372-8421-a0ae3a0454e1.png"
  >
 </p>
 
 ## Motivation
 
<p align="justify"> We chose this project by giving the chance to mix the interest of the group members in the subject
related to the artifcial intelligence area and control theory. The main objective was to look for a
project that we can apply the concepts and ideas from the areas above in a real-life situation: path
optimization and improvement performance of the autonomous system. And join the knowledge
and experience of group members acquired and improved in related courses and training in related
fields. Another point to highlight is associated with the technical advancements and opportunities
in autonomous systems, Robotics, and Control.</p>

## Contributions

Below we enumerate our project contributions:

* <p align="justify"> Our project has based on the paper [1], and it is an opportunity to extend the Theory presented by testing it with another dynamic model system (Actually works on Pendulum and Cartpole dynamics). </p>
* <p align="justify"> Delivering new simulation data and reinforce concepts over recent techniques such as Differentiable MPC controller.</p>
* <p align="justify"> The project can be used by researchers/students, in the future, in real-life projects, or basis for depth research.</p>

## Related Work

<p align="justify"> In the paper "Brandon Amos, Ivan Dario Jimenez Rodriguez, Jacob Sacks, Byron Boots, J. Zico Kolter - Differentiable MPC for End-to-end Planning and Control, Oct 2019", the authors present the basis for using the Differentiable Model Predictive Control (MPC) as a policy for reinforcement learning in continuous pair action/state. The objective is to combine the behaviors of model-free and model-based technics. The approach is based on the fact that model-free reinforcement learning suffers from poor sample complexity and generalization, and these could be improved using Differentiable MPC as "expert" to generate qualifed data samples to the model-free system. Below is shown the MPC optimization problem:</p>



## Tecnologies Applied
 
 * Python 3.5.7
 * PyTorch/numpy
 * CARLA Simulator
 * Differentiable MPC library
 * [locuslab/mpc.pytorch](https://locuslab.github.io/mpc.pytorch/)

## Developers

| [<img src="https://avatars.githubusercontent.com/u/19806622?s=40&v=4" width=115><br><sub>Ricardo Paschoeto </sub>](https://github.com/ricardpaschoeto) |  [<img src="https://avatars.githubusercontent.com/u/4451713?v=4" width=115><br><sub>Srikanth Vidapanakal</sub>](https://github.com/sreakdgeek) |
| :---: | :---: |

