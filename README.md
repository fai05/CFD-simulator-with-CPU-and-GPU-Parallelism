# Comparing Parallel Strategies for Fluid Dynamics Simulation
This project implements a high-performance Computational Fluid Dynamics (CFD) solver for the 2D Navier-Stokes equations, designed to run efficiently on resource-constrained environments such as Google Colab. It explores three parallelization strategies:

- **Sequential (Baseline)**
- **CPU Multiprocessing**
- **GPU Acceleration using PyTorch**

The solver demonstrates significant speedup on GPUs and on CPUs making advanced CFD simulations accessible for educational and research purposes without requiring dedicated HPC clusters.

## Features

- **Adaptive Parallelization:** Automatically detects available hardware resources (CPU cores, GPU availability) and selects the optimal execution strategy.
- **Domain Decomposition:** Efficient workload partitioning for multiprocessing to maximize CPU utilization.
- **GPU Acceleration:** Leverages PyTorch tensor operations for fast, scalable computation on CUDA-enabled GPUs.
- **Performance Benchmarking:** Integrated tools to measure execution time, speedup, and scaling efficiency.
- **Real-Time Visualization:** Animation of fluid flow results for immediate feedback and analysis.
- **Modular Design:** Easily extendable solver components with a consistent API for different parallelization backends.

## Installation
Clone the repository:
git clone https://github.com/fai05/CFD-simulator-with-CPU-and-GPU-Parallelism.git

Dependencies include:
- Python 3.8+
- PyTorch
- NumPy
- Matplotlib (for visualization)
- Multiprocessing (built-in Python module)

## Usage
Run the block in your preferred notebook platform and select your hardware (mode).

The system will automatically detect available resources if no mode is specified.

## References

This work builds upon recent advances in CFD parallelization, GPU computing, and HPC accessibility, inspired by:

- GPU-accelerated CFD with CUDA kernels
- Domain decomposition strategies for multi-GPU systems
- Python frameworks integrating C++/CUDA backends
- Adaptive mesh refinement and load balancing techniques

## Contributing

Contributions are welcome! Please open issues or submit pull requests for bug fixes, performance improvements, or new features.

by Faiza Reza 
