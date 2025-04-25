# cfd-sim
Efficient 2D CFD solver for resource-limited platforms like Google Colab, featuring adaptive parallelization (sequential, CPU multiprocessing, GPU acceleration) for up to 18x speedup, making advanced simulations accessible for education and research.


# CFD Simulation: Parallelized 2D Navier-Stokes Solver on Resource-Constrained Platforms

## Overview

This project implements a high-performance Computational Fluid Dynamics (CFD) solver for the 2D Navier-Stokes equations, designed to run efficiently on resource-constrained environments such as Google Colab. It explores three parallelization strategies:

- **Sequential (Baseline)**
- **CPU Multiprocessing**
- **GPU Acceleration using PyTorch**

The solver demonstrates significant speedups-up to 18× on GPUs and 2–4× on CPUs-making advanced CFD simulations accessible for educational and research purposes without requiring dedicated HPC clusters.

## Features

- **Adaptive Parallelization:** Automatically detects available hardware resources (CPU cores, GPU availability) and selects the optimal execution strategy.
- **Domain Decomposition:** Efficient workload partitioning for multiprocessing to maximize CPU utilization.
- **GPU Acceleration:** Leverages PyTorch tensor operations for fast, scalable computation on CUDA-enabled GPUs.
- **Performance Benchmarking:** Integrated tools to measure execution time, speedup, and scaling efficiency.
- **Real-Time Visualization:** Animation of fluid flow results for immediate feedback and analysis.
- **Modular Design:** Easily extendable solver components with a consistent API for different parallelization backends.

## Motivation

CFD simulations traditionally require powerful computing clusters, limiting accessibility for students and researchers with limited resources. This project bridges that gap by adapting HPC principles for cloud platforms like Google Colab, enabling:

- Cost-effective, scalable CFD simulations
- Hands-on learning of parallel computing and fluid dynamics
- Practical framework for research in resource-limited environments

## Installation

1. Clone the repository:

git clone https://github.com/yourusername/cfd-simulation.git
cd cfd-simulation



Dependencies include:

- Python 3.8+
- PyTorch
- NumPy
- Matplotlib (for visualization)
- Multiprocessing (built-in Python module)

## Usage

Run the simulation notebook or script with your preferred parallelization mode:

- **Sequential (default):**

python run_simulation.py --mode sequential --grid_size 128


- **CPU Multiprocessing:**

python run_simulation.py --mode multiprocessing --grid_size 256 --processes 4



- **GPU Acceleration:**

python run_simulation.py --mode gpu --grid_size 512



The system will automatically detect available resources if no mode is specified.

## Project Structure

/cfd-simulation
│
├── core/ # Core simulation engine implementing Navier-Stokes solver
├── parallel/ # Parallelization strategies (sequential, multiprocessing, GPU)
├── visualization/ # Visualization engine for real-time animation
├── performance/ # Benchmarking and performance analysis tools
├── run_simulation.py # Main entry point for running simulations
├── requirements.txt # Python dependencies
└── README.md # This file


## Methodology

### Adaptive Parallelization Strategy

- **Runtime Resource Detection:** Automatically identifies CPU cores and GPU availability.
- **Dynamic Strategy Selection:** Chooses the best parallelization approach based on problem size and hardware.
- **Graceful Degradation:** Falls back to less intensive modes if resources are limited or unavailable.

### Domain-Specific Optimizations

- Specialized kernels for diffusion, advection, and pressure projection optimized for CPU and GPU.
- Memory access patterns tailored for cache efficiency and GPU throughput.
- Overlapping computation and communication in multiprocessing to reduce idle time.

### Framework Architecture

- Modular solver components with interchangeable implementations.
- Unified API abstracts hardware-specific details.
- Built-in instrumentation for profiling and optimization.

## Performance

- GPU acceleration achieves up to **18× speedup** over sequential runs for large grid sizes.
- CPU multiprocessing provides **2–4× speedup** depending on core count.
- Detailed benchmarking and visualization tools included to analyze performance.

## References

This work builds upon recent advances in CFD parallelization, GPU computing, and HPC accessibility, inspired by:

- GPU-accelerated CFD with CUDA kernels
- Domain decomposition strategies for multi-GPU systems
- Python frameworks integrating C++/CUDA backends
- Adaptive mesh refinement and load balancing techniques

## Contributing

Contributions are welcome! Please open issues or submit pull requests for bug fixes, performance improvements, or new features.

## License

This project is licensed under the MIT License.

## Contact

For questions or collaboration, please contact:

- Dr. Manjula V (manjula.v@vit.ac.in)  
- Sooraj Naarayanan (sooraj.naarayanan2022@vitstudent.ac.in)  
- Faiza Reza (faiza.reza2022@vitstudent.ac.in)
