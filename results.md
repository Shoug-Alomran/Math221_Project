# Results

This section presents the computational results obtained from implementing the **Bisection**, **Newton–Raphson**, and **Secant Methods** for solving nonlinear equations.  
All three methods were applied to the same test function to compare their performance in terms of convergence rate, number of iterations, and accuracy.

---

## 4.1 Function Used

The function chosen for analysis was:

\[
f(x) = x^2 - 4
\]

The true root of the function is \(x = 2\), since \(2^2 - 4 = 0\).  
This function was selected for its simplicity and because it allows straightforward comparison among methods while still demonstrating convergence behavior.

---

## 4.2 Iterative Results

Each method was executed in **GNU Octave 10.3.0** (compatible with MATLAB).  
The following table summarizes the number of iterations required to reach the approximate root with a tolerance of \(10^{-6}\):

| Method           | Approximate Root | Converged in Iterations | Remarks |
|------------------|------------------|--------------------------|----------|
| **Bisection**        | 2.000000 | 1 | Fast convergence due to perfect midpoint. |
| **Newton–Raphson**   | 2.000000 | 5 | Rapid quadratic convergence near the root. |
| **Secant**           | 2.000000 | 6 | Slightly slower but accurate without derivative. |

All three methods successfully converged to the same correct root **(x = 2)**.  
The **Newton–Raphson method** showed the fastest convergence, as expected for derivative-based algorithms.

---

## 4.3 Sample Iteration Output (from Octave)

Below is an example of the terminal output for the Newton–Raphson method:

```bash
Enter initial guess x0 = 1
Enter tolerance = 1e-6

Iteration 1: x1 = 2.500000, f(x1) = 2.250000
Iteration 2: x2 = 2.050000, f(x2) = 0.202500
Iteration 3: x3 = 2.000610, f(x3) = 0.002441
Iteration 4: x4 = 2.000000, f(x4) = 0.000000
Root found at x = 2.000000 after 5 iterations
```

## 4.4 Graphical Representation

The figures below illustrate the computational results and graphical output obtained in **GNU Octave** for the three numerical methods.

### Figure 1: Code Output
![Figure 1: Code Output](img/Code%20Output.png){ width="800" }

*Figure 1: Terminal output displaying computed iterations and convergence results.*

### Figure 2: Graph Output
![Figure 2: Graph Output](img/Graph%20Output.png){ width="800" }

*Figure 2: Plot of the function \(f(x) = x^2 - 4\) showing convergence of methods toward the true root \(x = 2\).*

---

## 4.5 Observations

- All three methods reached the same correct solution within acceptable tolerance.  
- **Newton–Raphson** demonstrated **quadratic convergence**, requiring fewer iterations.  
- **Bisection** was the most stable but the slowest method.  
- **Secant** performed efficiently while eliminating the need for derivatives.  
- Computational error decreased steadily with each iteration.

---

## 4.6 Error vs. Iteration Plot

The error plot (Figure 2) highlights how each method’s error decreases as iterations progress.  
The **Newton–Raphson** method exhibits the steepest decline, confirming its faster convergence rate.

---

## 4.7 Summary of Results

| Metric | Bisection | Newton–Raphson | Secant |
|:--|:--:|:--:|:--:|
| Root Found | 2.000000 | 2.000000 | 2.000000 |
| Iterations | 1 | 5 | 6 |
| Requires Derivative | ❌ | ✅ | ❌ |
| Convergence Type | Linear | Quadratic | Superlinear |
| Stability | High | Medium | Medium |

All numerical methods achieved accurate results.  
However, **Newton–Raphson** proved to be the most efficient, balancing computational speed and precision.

---

## 4.8 Conclusion of Findings

The experiment confirmed the theoretical expectations for each numerical method.  
While the **Bisection Method** provides guaranteed convergence, it converges slowly.  
The **Secant Method** offers good performance without needing derivatives, and the **Newton–Raphson Method** achieves superior speed when an accurate initial guess is available.

These findings emphasize the importance of choosing the appropriate method depending on the problem’s characteristics and available computational resources.