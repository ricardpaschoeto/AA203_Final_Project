<h1 align="center"> Differentiable MPC applied in a simulated Self Driving Car (CARLA Simulator) </h1>

<p align="center">
  <img
    src="https://user-images.githubusercontent.com/19806622/162852879-2b87ec45-bb82-4fca-b396-9e3d709ae09c.png"
 >
 </p>

## Índex 

* [Project Description](#project-description)
* [Project Status](#Project-Status)
* [Application Funcionalities and Demonstration](#application-funcionalities-and-demonstration)
* [Project Access](#acesso-ao-projeto)
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
    src="https://user-images.githubusercontent.com/19806622/162855349-09b272ad-7f7b-4551-8256-2754b44c7243.png"
  >
 </p>


