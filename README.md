# Parallel Particle Simulation (MPI)

This repository contains my MPI-parallelized particle simulator, developed in C++ on the DOE-NERSC Perlmutter supercomputer. It slashes runtime from 194s to 1s for 1M particles across 128 tasks, achieving a 194× speedup over the serial baseline through distributed memory parallelization.

## Project Structure

**MAIN FILES:**  
- `main.cpp` → Entry point for the simulation, orchestrating MPI setup and execution.  
- `mpi.cpp` → Core parallel implementation of the particle simulation using MPI for up to 128 tasks.  
- `common.h` → Shared definitions and utilities for particle data and simulation parameters.

## Overview

**Duration:** January 2025 – March 2025  
**Goal:** Accelerate a particle interaction simulation using MPI in a distributed memory environment.  
**Key Results:**  
- **Runtime:** 1s (down from 194s serial)  
- **Speedup:** 194× on 128 tasks (2 nodes, 64 tasks per node)  
- **Complexity:** Reduced from O(n²) to O(n) via spatial binning  
- **Scalability:** Analyzed strong/weak scaling, achieving 100% efficiency at 1 rank  

## Features

- **MPI Parallelization:** Distributes workload across 128 tasks using a 2D processor grid and ghost particle exchanges for efficient distributed memory computing.  
- **Spatial Binning:** Optimizes 1M-particle simulations by reducing complexity from O(n²) to O(n) with a streamlined grid layout.  
- **Performance Optimization:** Enhances cache efficiency with a flattened 1D grid and cuts overhead via a two-step grid-building process.  
- **Memory Efficiency:** Pre-allocates memory to stabilize performance and minimize allocation costs during runtime.

## Tech Stack

- **Languages:** C++  
- **Tools:** MPI, GCC, Git, Perlmutter Supercomputer (NERSC), Command Line  
- **Libraries:** MPI (Message Passing Interface), Standard C++ (no external dependencies beyond MPI)
