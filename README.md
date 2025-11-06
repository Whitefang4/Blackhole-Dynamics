🌀 Black Hole Dynamics — Learning Relativistic Orbital Behavior with Neural ODEs

This project explores how Neural ODEs (Universal Differential Equations) can learn relativistic corrections in black hole orbital dynamics. Using the Julia SciML ecosystem, we model Newtonian, Schwarzschild (relativistic), and neural-augmented orbits, and compare their ability to reproduce gravitational-wave–like signals.

🚀 Project Overview

Classical orbital models capture black hole motion under Newtonian or Schwarzschild metrics. However, real gravitational systems often exhibit additional corrections that are hard to model explicitly.

This project integrates a Neural Network inside an ODE (via Universal Differential Equations) to learn these missing physical effects directly from data.

We:

Simulate true relativistic orbital motion .Compute corresponding gravitational waveforms using quadrupole physics.Train a Neural ODE to match the observed waveform

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



📊 Results

The Neural ODE successfully learns relativistic corrections hidden in waveform data.
It reconstructs orbital trajectories with high accuracy.
It generalizes well for long-term forecasting beyond the training window.
Outperforms the Newtonian model by a wide margin.
