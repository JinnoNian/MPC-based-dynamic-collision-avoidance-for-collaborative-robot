# MPC-based-dynamic-collision-avoidance-for-collaborative-robot

This project demonstrates the implementation of a 3D Model Predictive Control (MPC) approach with obstacle avoidance. The program optimizes a robot's trajectory to reach a target while avoiding dynamic obstacles, taking into account Gaussian noise and dynamically adjusting safety distances.

## Features
- 3D trajectory planning using MPC.
- Obstacle avoidance with dynamically adjusted safety distances.
- Incorporates Gaussian noise to simulate uncertainties.
- Dual optimization techniques: Particle Swarm Optimization (PSO) and Simulated Annealing (SA).
- Visualization of the robot's trajectory, obstacle path, and safety distances using Matplotlib 3D plots.

## Prerequisites

### Libraries
The following Python libraries are required to run the program:

- `numpy` (for matrix operations and numerical calculations)
- `pyswarm` (for Particle Swarm Optimization)
- `cvxpy` (for convex optimization)
- `matplotlib` (for 3D visualization and animations)

### Installation
Install the required libraries using pip:
```bash
pip install numpy pyswarm cvxpy matplotlib
```

## Explanation of the Code
The program consists of the following main components:

1. **System Model**: Defines the robot's dynamics using state-space matrices (A, B).
2. **Obstacle Dynamics**: Updates the obstacle's position with a sinusoidal path and Gaussian noise.
3. **MPC Optimization**:
   - **Convex Optimization**: Uses `cvxpy` for optimizing the trajectory when the robot is in a safer region.
   - **Heuristic Methods**: Combines PSO and SA for scenarios with closer proximity to obstacles.
4. **Visualization**:
   - Uses `matplotlib` to plot the robot's trajectory, target, and dynamically adjusted safety distances.
   - Generates a GIF animation of the trajectory.

## Notes
- The `max_noise` parameter simulates uncertainty in the obstacle's position.
- The program dynamically adjusts the safety distance (`epsilon`) based on noise confidence and obstacle velocity.
- The simulation stops when the robot reaches the target or violates position constraints.
