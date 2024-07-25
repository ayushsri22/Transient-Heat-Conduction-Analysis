# Transient Heat Conduction - ESC 113 Term Project


## Introduction
Understanding the temperature distribution and behavior of objects immersed in different fluids is essential for designing systems that involve heat exchange, such as cooling systems, industrial processes, and thermal management in general. 

In this project, we analyze the heat transfer process when a steel ball is immersed in a fluid (oil tank) with a temperature higher than the initial temperature of the ball. By solving the governing energy balance equation, we can predict the temperature of the ball after a specific time using numerical techniques like the fourth-order Runge-Kutta (R-K-4) method.

## Problem Statement
Consider a steel ball (diameter = 10 cm) with the following properties:
- Thermal conductivity (k): 40 W/m·K
- Density (ρ): 8000 kg/m³
- Specific heat capacity (Cp): 400 J/kg·K

The initial temperature of the ball is 300 K. It is immersed in a large oil tank at 400 K. The convective heat transfer coefficient (h) at the sphere surface is 3000 W/m²·K. Assume there is no radial temperature gradient inside the ball.

We will use the R-K-4 numerical technique to solve the governing first-order energy balance equation to predict the temperature of the sphere at t = 1 min after immersion in the oil tank. The calculations will be performed with time steps Δt = 10 s and Δt = 5 s. We will also graphically depict the slopes comprising all stages of the RK method and calculate the rate of temperature increase at t = 0, 0.5, and 1.0 min.



## Numerical Methods Used
1. **Explicit Euler's Method**
    - Formula: y(i+1) = y(i) + hf(x(i), y(i))
    - Step value until numerically stable: 15

2. **Implicit Euler's Method**
    - Formula: y(i+1) = y(i) + hf(x(i+1), y(i+1))
    - Known for unconditional numerical stability.

3. **Runge-Kutta 4 (RK-4) Method**
    - Formula: yi+1 = yi + (1/6) (k1 + 2k2 + 2k3 + k4)
    - Where:
        - k1 = hf(xi, yi)
        - k2 = hf[xi + (1/2)h, yi + (1/2)k1]
        - k3 = hf[xi + (1/2)h, yi + (1/2)k2]
        - k4 = hf(xi + h, yi + k3)

## Results
We solved the heat conduction problem using three different approaches and compared the outcomes:

1. **Explicit Euler's Method**: 
    - Observed a step value till numerically stable (step value: 15).
    
2. **Implicit Euler's Method**: 
    - Exhibited unconditional numerical stability.
    
3. **Runge-Kutta 4 Method**:
    - Demonstrated that the temperature increases, but the rate of increase decreases over time.
    - Found to be more effective due to a lower error order (O(h^4)) compared to explicit and implicit Euler methods (O(h^2)).

## Conclusion
The RK-4 method proved to be the most effective among the three methods tested, given its higher accuracy (error order of O(h^4)) compared to the Euler methods (error order of O(h^2)). The results indicate the practicality and efficiency of the RK-4 method in solving transient heat conduction problems.

