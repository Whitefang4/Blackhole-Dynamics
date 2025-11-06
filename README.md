🌀 Black Hole Dynamics — Learning Relativistic Orbital Behavior with Neural ODEs

This project explores how Neural ODEs (Universal Differential Equations) can learn relativistic corrections in black hole orbital dynamics. Using the Julia SciML ecosystem, we model Newtonian, Schwarzschild (relativistic), and neural-augmented orbits, and compare their ability to reproduce gravitational-wave–like signals.

🚀 Project Overview

Classical orbital models capture black hole motion under Newtonian or Schwarzschild metrics. However, real gravitational systems often exhibit additional corrections that are hard to model explicitly.

This project integrates a Neural Network inside an ODE (via Universal Differential Equations) to learn these missing physical effects directly from data.

We:

Simulate true relativistic orbital motion

Compute corresponding gravitational waveforms using quadrupole physics

Train a Neural ODE to match the observed waveform

Compare:

✅ True relativistic model

✅ Newtonian approximation

✅ Neural ODE (learned corrections)

🧠 Key Features

Neural ODE (UDE) built with Lux.jl

Physics-based ODE solvers using OrdinaryDiffEq.jl

Automatic differentiation via Zygote

Gradient-based training with ADAM + BFGS

Gravitational waveform generation using quadrupole moment equations

Long-term prediction and orbit reconstruction

Clear visualization of learned vs true vs Newtonian trajectories

🛠️ Tech Stack

Julia

SciML Ecosystem

OrdinaryDiffEq.jl

DiffEqFlux / SciMLSensitivity

Optimization.jl

Lux.jl (Neural Networks)

Zygote.jl (AD)

ComponentArrays.jl

Plots.jl

DataFrames.jl

📂 Project Structure
blackhole-dynamics/
│── src/
│   ├── models.jl              # Newtonian, Relativistic, and NN-augmented ODE models
│   ├── waveform.jl            # Quadrupole moment & gravitational wave computations
│   ├── utils.jl               # Orbit conversion, finite-difference tools
│── training/
│   ├── train_ude.jl           # Training loop for Neural ODE (Adam + BFGS)
│   ├── loss_functions.jl
│── plots/
│   ├── orbit_plots.ipynb      # Orbit visualizations
│   ├── waveform_plots.ipynb
│── data/
│── README.md


(Adjust based on your actual repo structure.)

📘 How It Works
✅ 1. Simulate True Relativistic Orbit

We solve the Schwarzschild-based ODE to generate reference orbits and gravitational-wave–like strain signals.

✅ 2. Build a Neural ODE

A neural network is injected into the system dynamics:

NN = Lux.Chain(
    x -> cos.(x),
    Lux.Dense(1, 32, cos),
    Lux.Dense(32, 32, cos),
    Lux.Dense(32, 2)
)


The NN learns missing relativistic corrections.

✅ 3. Train the UDE

We minimize waveform reconstruction error:

Adam optimizer for coarse updates

BFGS for fine convergence

✅ 4. Compare Results

We visualize:

Learned vs true orbit

Learned vs true waveform

Newtonian vs relativistic deviations

📊 Results

The Neural ODE successfully learns relativistic corrections hidden in waveform data.

It reconstructs orbital trajectories with high accuracy.

It generalizes well for long-term forecasting beyond the training window.

Outperforms the Newtonian model by a wide margin.
