###  Experiments in discrete math

Follow along as I try to keep up with Steve Brunton ( https://www.youtube.com/c/Eigensteve ), and
his classes *Beginning Scientific Computing* (AMATH 301) and *Engineering Mathematics* (ME 564).  He does
the assignments in Matlab, but I attempt to do them in Julia/Pluto.

The course text is available here:
http://courses.washington.edu/am301/docs/pdf/301.pdf

The 2017 course Syllabus I used,
https://amath.washington.edu/courses/2017/summer/amath/301/a

----
#### Week 1 - Programming environment introduction

( Lecture links for matlab and python : http://courses.washington.edu/am301/page10/video.html )

- [Vectors and Matrices](./amath301_W01L01_Vectors.jl)
- [Logic, Loops and Interations](./amath301_W01L02_Logic.jl)
- [Plotting and Importing/Exporting Data](./amath301_W01L03_Plotting.jl)

( Suppliments : http://courses.washington.edu/am301/page11/video.html )

- [Computer Bits](./amath301_W01S01_Bits.jl)
- [Computational Complexity](./amath301_W01S02_Benchmarking.jl)
- [Vector Elements](./amath301_W01S03_Elements.jl)
- [Functions](./amath301_W01S04_Functions.jl)

#### Week 2 - Linear Systems and Linear Algebra

( Lecture links and suppliments : http://courses.washington.edu/am301/page1/page5/video.html )

- Vector/Matrix operations
- [Gaussian Elimination](./amath301_W02L05_Gauss.jl)
- [LU Decomposition](./amath301_W02L06_LU.jl) (includes LU suppliment material)

Suppliments

- [Matrix Models](./amath301_W02S01_Models.jl)
- [Condition numbers](./amath301_W02S02_Condition.jl)

#### Week 3 - Iterative Methods for Linear Systems

( Lecture links : http://courses.washington.edu/am301/page1/page6/video.html )

- [Iterative Solving](./amath301_W03L07_Iterative.jl)
- Eigenvalues/Eigenvectors
- [Stability and Convergence](./amath301_W03L09_Stability.jl)

#### Week 4 - Curve Fitting

( Lecture links and suppliments : http://courses.washington.edu/am301/page2/page13/video.html )

- [Least Squares](./amath301_W04L10_Fit.jl)
- [Polynomial Fits](./amath301_W04L11_Splines.jl)
- [Data Fitting](./amath301_W04L12_DataFit.jl)

The suppliment on functions seems a repeat of Week 1 functions suppliment.

#### Week 5 - Optimization

( Lecture links : http://courses.washington.edu/am301/page2/page14/video.html )

- [General Optimization](./amath301_W05L13_Optimization.jl)
- [Derivative Optimization](./amath301_W05L14_Unconstrained.jl)
- [Genetic Algorithms](./amath301_W05L15_LinProg.jl)

#### Week 6 - Numerical Integration and Differentiation

( Lecture links and suppliments : http://courses.washington.edu/am301/page3/page7/video.html )

- [Numerical Differentiation](./amath301_W06L16_FiniteDiff.jl)
- [Higher Order Differentiation](./amath301_W06L17_Diffs.jl)
- [Integration](./amath301_W06L18_Integration.jl)

Suppliment

- Mean Value Theorem

#### Week 7 - Differential Equations

(Lecture links and suppliments : http://courses.washington.edu/am301/page3/page8/video.html )

- [Time Stepping ODEs](./amath301_W07L19_TimeStep)
- [Error and Stability](./amath301_W07L20_Stability.jl)
- General Schemes to reduce error

Suppliment

- [Using 4th Order Solver](./amath301_W07S01_ODESolve.jl)

#### Week 8 - Advanced Differential Equations

(Lecture links and suppliments : http://courses.washington.edu/am301/page3/page9/video.html )

- [Runge Kutta](./amath301_W08L22_RungeKutta.jl)
- [Simulation Performance](./amath301_W08L23_Performance.jl)
- Double Gyre

Suppliment

- [Functions](./amath301_W01S04_Functions.jl)  * repeat from week 1
- [Phase Plots](./amath301_W08S01_PhasePlot.jl)
- [Double Pendulum](./amath301_W08S02_DoublePendulum.jl)

Extra reference:

[Comparison of Integrators (double pendulum) PDF](http://courses.washington.edu/am301/pdf/MAE541_PRES.pdf)

#### Week 9 - Singular Value Decomposition

(Lecture links : http://courses.washington.edu/am301/page1/page15/video.html )

- Singular Value Decomposition (svd)
- Principal Component Analysis (pca, variances and covariances)
- Facial Recognition

#### Week 10 - Fast Fourier Transform

(Lecture links and suppliments : http://courses.washington.edu/am301/page4/page12/video.html )

- [Fourier Transform](./amath301_w10L28_Fourier.jl)
- [Fast Fourier Transform](./amath301_W10L29_FFT.jl)
- Image Compression

Suppliments

- [Live audio FFT](./amath301_W10S01_AudioFFT.jl)
- [Discrete Fourier Transform](./amath301_W10S02_DFT.jl)

----
#### Bootstrap

There is a script for determining all the modules required for these pages so that they can be loaded in bulk.
My appologies, but it is written in `perl`, as I have not learned how to do this as easily in `julia` yet.

    perl add.pl | julia

This will generate **julia** commands for loading all the packages the current directory requires.
Without the pipe the output looks something like this:

    using Pkg
    Pkg.add( ["AbstractPlotting","BenchmarkTools","Clp","Colors","Compose","DSP","Dates","Dierckx","DifferentialEquations","FFTW","FileIO","ForwardDiff","HypertextLiteral","InteractiveUtils","Interpolations","JLD","JSON","JSServe","JuMP","LibSndFile","Libdl","LinearAlgebra","LoopVectorization","LsqFit","Markdown","MathOptInterface","NumericalIntegration","ODE","Optim","ParameterizedFunctions","Pkg","Plots","Pluto","Polynomials","QuadGK","Random","SampledSignals","Statistics","Trapz","WGLMakie"])

#### Warm up

The interactive use of **julia** will be a little better if some of the common packages are pre-loaded,
though this is changing over time as the core platform team works to improve startup performance.

    using Pluto ;  using Plots ;  using JLD ;  using JSON ; 
    using Statistics ;  using LinearAlgebra ;  using ODE ;  using Random ;
    Pluto.run()

#### Lost technology

I haven't found an example of Phase Planes in Julia yet, so for now I'm relying on the web page:
https://aeb019.hosted.uark.edu/pplane.html

