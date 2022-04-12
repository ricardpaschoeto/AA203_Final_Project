<h1 align="center"> Differentiable MPC applied in a simulated Self Driving Car (CARLA Simulator) </h1>

<p align="center">
  <img
    src="https://user-images.githubusercontent.com/19806622/162852879-2b87ec45-bb82-4fca-b396-9e3d709ae09c.png"
 >
 </p>

## Índex 

* [Developers](#developers)
* [Tecnologies Applied](#tecnologies-applied)
* [Project Description](#project-description)
* [Carla Simulator](#carla-simulator)
* [Motivation](#motivation)
* [Contributions](#contributions)
* [Related Work](#related-work)
* [Project setting](#project-setting)
* [Preliminary Results](#preliminary-results)
* [Problem Statement](#problem-statement)
* [Approach](#approach)
* [Experiments](#experiments)
* [Conclusions and Future Work](#conclusions-and-future-work)
* [References](#references)

## Developers

| [<img src="https://avatars.githubusercontent.com/u/19806622?s=40&v=4" width=115><br><sub>Ricardo Paschoeto </sub>](https://github.com/ricardpaschoeto) |  [<img src="https://avatars.githubusercontent.com/u/4451713?v=4" width=115><br><sub>Srikanth Vidapanakal</sub>](https://github.com/sreakdgeek) |
| :---: | :---: |

## Tecnologies Applied
 
 * PyTorch/numpy
 * CARLA Simulator
 * Differentiable MPC library
 * [locuslab/mpc.pytorch](https://locuslab.github.io/mpc.pytorch/)

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
 
 ## Carla Simulator
 
 <p align="center">
  <img
    width="800"
    height="500"
    src="https://user-images.githubusercontent.com/19806622/162863465-6b600c42-9588-4268-9be3-4bc308d0fa71.png"
  >
 </p>
 
<p align="justify"> CARLA is an open-source simulator developed to support, train and validate autonomous vehicle systems. It provides open source, protocols and various scenarios. It also extends support for a Conditional Imitation Learning Agent.</p>

### Conditional Imitation Learning Agent

We intend to use conditional imitation learning agent trained on CARLA simulator for our exper-
iments. Below are the measurements and controls provided as part of the dataset:
1. Steer, float
2. Gas, float
3. Brake, float
4. Hand Brake, boolean
5. Reverse Gear, boolean
6. Steer Noise, float
7. Gas Noise, float
8. Brake Noise, float
9. Position X, float
10. Position Y, float
11. Speed, float
12. Collision Other, float
13. Collision Pedestrian, float
14. Collision Car, float
15. Opposite Lane Inter, float
16. Sidewalk Intersect, float
17. Acceleration X, float
18. Acceleration Y, float
19. Acceleration Z, float
20. Platform time, float
21. Game Time, float
22. Orientation X, float
23. Orientation Y, float
24. Orientation Z, float
25. High level command, int ( 2 Follow lane, 3 Left, 4 Right, 5 Straight)
26. Noise, Boolean ( If the noise, perturbation, is activated, (Not Used) )
27. Camera (Which camera was used)
28. Angle (The yaw angle for this camera)

Reference: (https://github.com/carla-simulator/imitation-learning)

<p align="justify"> The key idea of conditional imitation learning is that an end-to-end learning agent cannot handle the intersection unless explicitly guided by navigational commands.</p>

Reference: (http://vladlen.info/papers/conditional-imitation.pdf)
 
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

<p align="justify"> In the last years, we have a considerable number of works related to Model Predictive Control (MPC), indirect methods, and iLQR to applying in autonomous systems. In our project, this material was essential to create the foundations.</p>

<h3 align="justify"> Differentiable MPC for End-to-end Planning and Control [1]</h3>  <p align="justify"> In this work, the authors presented the foundations of Differentiable iLQR. They used this concept to implement Differentiable Model Predictive Control (MPC) as a Python library.</p>

<h3 align="justify"> Real-time MPC with iLQR for Self-Driving in Carla [2]</h3> <p align="justify"> In this work the authot presented the concepts to apply iLQR and MPC to an autonomous vehicle system using Neural Networks together explicit system dynamics.</p>

<h3 align="justify"> Robust Model Predictive Control for Autonomous Vehicle/Self-Driving Cars [3] </h3> <p align="justify"> In this paper the authors presented an approach for controlling front steering of an autonomous vehicle. The paper was our source regarding to Bicycle Model and model dynamics.</p>

<h3 align="justify"> Control-Limited Differential Dynamic Programming [4] </h3> <p align="justify"> The authors propose a generalization of DDP which box inequality constraints on the controls using indirect methods and iLQR. The approach proposed was applied in a Car Parking and Humanoid Robot.</p>

<h3 align="justify"> Constrained Iterative LQR for On-Road Autonomous Driving Motion Planning [5] </h3> <p align="justify"> The authors presented a new implementation of the iLQR algorithm to an autonomous driving car but with constraints applied (CILQR).</p>

<h3 align="justify"> End-to-end Driving via Conditional Imitation Learning [6] </h3> <p align="justify"> In this paper the authors presented a new approach to imitation learning policy, generate by on high-level command input. They showed a simulation using the CARLA simulator.</p>

## Project setting

The statements of project settings follow the steps below:

* <p align="justify"> First, we need to decide the dynamics for our model based Differentiable MPC. For the autonomous system, we have some options: Drone, autonomous car, autonomous robot, and so on. The choices come with a dynamic set with evolves different levels of complexity. We chose Autonomous vehicle driving setup with Carla-based simulation.</p>
* <p align="justify"> Key idea of our work is to apply differentiable MPC where the cost and dynamics of the Autonomous Vehicle are learnt by optimizing the imitation learning loss using only observed controls as shown below:</p>

<p align="center">
  <img
    src="https://user-images.githubusercontent.com/19806622/162862170-bfc12c7a-3be7-421b-927c-5295326bea5c.png"
  >
 </p>
 
 Typically the expected dynamics of an autonomous vehicle are described below:
 
 <p align="center">
  <img
    src="https://user-images.githubusercontent.com/19806622/162862265-9d79f663-521e-4da3-a3a5-c28ac242f3fa.png"
  >
 </p>

 <p align="center">
  <img
    src="https://user-images.githubusercontent.com/19806622/162863241-1014693e-1ed6-4087-a7c9-d90fb135c25c.png"
  >
 </p>

* x, y - Position
* &psi; - Orientation
* v - velocity
* CTE - cross track error
* a - Acceleration
* &delta; - steering angle (range: -25 degrees to +25 degrees)

<p align="justify"> Goal of this project is that without explicitly defining the dynamics, differentiable MPC controller would learn the dynamics and cost from the expert agent by explicitly imitating the control actions and overall minimizing the imitation loss.</p>

## Preliminary Results

<p align="justify"> Our first simulations were done to familiarize with the coding process to generate the learning data from Differentiable MPC. We use the sample data from cart-pole to generate data that we can use as a benchmark for our data in the future.</p>

<p align="center">
  <img
    src="https://user-images.githubusercontent.com/19806622/162865094-88b5f7ec-44a5-4174-8e45-ac4d3b608ba0.png"
  >
 </p>
 
<p align="center">Figure 2: Imitation Learning loss.</p>

