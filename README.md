🌀 Black Hole Dynamics — Learning Relativistic Orbital Behavior with Neural ODEs

This project explores how Neural ODEs (Universal Differential Equations) can learn relativistic corrections in black hole orbital dynamics. Using the Julia SciML ecosystem, we model Newtonian, Schwarzschild (relativistic), and neural-augmented orbits, and compare their ability to reproduce gravitational-wave–like signals.

🚀 Project Overview

Classical orbital models capture black hole motion under Newtonian or Schwarzschild metrics. However, real gravitational systems often exhibit additional corrections that are hard to model explicitly.

This project integrates a Neural Network inside an ODE (via Universal Differential Equations) to learn these missing physical effects directly from data.

We:

Simulate true relativistic orbital motion .Compute corresponding gravitational waveforms using quadrupole physics.Train a Neural ODE to match the observed waveform



🧠 Key Features

-Neural ODE (UDE) built with Lux.jl

-Physics-based ODE solvers using OrdinaryDiffEq.jl

-Automatic differentiation via Zygote

-Gradient-based training with ADAM + BFGS

-Gravitational waveform generation using quadrupole moment equations

-Long-term prediction and orbit reconstruction

-Clear visualization of learned vs true vs Newtonian trajectories


🛠️ Tech Stack

-Julia

-SciML Ecosystem

    -OrdinaryDiffEq.jl

    -DiffEqFlux / SciMLSensitivity

    -Optimization.jl

-Lux.jl (Neural Networks)

-Zygote.jl (AD)

-ComponentArrays.jl

-Plots.jl

-DataFrames.jl

📊 Results

-The Neural ODE successfully learns relativistic corrections hidden in waveform data.

-It reconstructs orbital trajectories with high accuracy.

-It generalizes well for long-term forecasting beyond the training window.

-Outperforms the Newtonian model by a wide margin.

## How to Run (Quick)

- Install the latest version of Julia (1.10+ recommended).
- Clone this repo and open it in a terminal.
- Add the required libraries:
  - If the repo has `Project.toml`: 
    - Run: `julia --project -e 'using Pkg; Pkg.instantiate()'`
  - Otherwise (manual install):
    - Run: `julia -e 'using Pkg; Pkg.add(["OrdinaryDiffEq","SciMLSensitivity","DiffEqFlux","Optimization","OptimizationOptimJL","OptimizationOptimisers","Lux","Zygote","ComponentArrays","Plots","DataFrames"])'`
- Run the training script:
  - `julia --project training/train_ude.jl`
- View the plots/output in the terminal or saved images in the `plots/` folder (if enabled).

