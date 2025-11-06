# Methods

This section explains the three numerical methods applied in this project to find the roots of nonlinear equations: **Bisection**, **Newton–Raphson**, and **Secant** methods.  
Each method is based on iterative computation that refines an initial estimate of the root until a predefined tolerance is satisfied.

---

## 1. Bisection Method

The **Bisection Method** is a simple and reliable root-finding technique that repeatedly divides an interval in half and selects the subinterval that contains the root.  
It is based on the **Intermediate Value Theorem**, which states that if \(f(a)\) and \(f(b)\) have opposite signs, there must exist at least one root between them.

**Procedure:**
1. Choose two initial guesses \(a\) and \(b\) such that \(f(a) \times f(b) < 0\).  
2. Compute the midpoint:
   \[
   x_m = \frac{a + b}{2}
   \]
3. Evaluate \(f(x_m)\):
   - If \(f(a) \times f(x_m) < 0\), the root lies in \([a, x_m]\).
   - Otherwise, it lies in \([x_m, b]\).
4. Repeat until the interval width \(|b - a|\) is less than the given tolerance \(\varepsilon\).

**Stopping Criterion:**
\[
|f(x_m)| < \varepsilon
\]

**Advantages:**
- Always convergent if \(f(a)f(b) < 0\).
- Simple and easy to implement.

**Limitations:**
- Slow convergence rate.
- Requires the sign of \(f(a)\) and \(f(b)\) to be opposite.

---

## 2. Newton–Raphson Method

The **Newton–Raphson Method** is a faster, derivative-based technique that uses the tangent line at a given point to estimate the root.  
It is one of the most efficient root-finding algorithms when the function is differentiable and the initial guess is close to the true root.

**Formula:**
\[
x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}
\]

**Procedure:**
1. Choose an initial approximation \(x_0\).  
2. Compute the next iteration using the formula above.  
3. Continue until \(|x_{n+1} - x_n| < \varepsilon\).

**Advantages:**
- Rapid convergence near the root.  
- Requires fewer iterations than the Bisection Method.  

**Limitations:**
- Requires the derivative \(f'(x)\).  
- May diverge if the initial guess is far from the actual root or if \(f'(x)\) is close to zero.  

---

## 3. Secant Method

The **Secant Method** is similar to the Newton–Raphson Method but eliminates the need for computing derivatives by approximating them using finite differences.  
It uses two initial guesses to estimate the slope of the secant line passing through the function.

**Formula:**
\[
x_{n+1} = x_n - f(x_n) \frac{x_n - x_{n-1}}{f(x_n) - f(x_{n-1})}
\]

**Procedure:**
1. Choose two initial approximations \(x_0\) and \(x_1\).  
2. Compute \(x_2\) using the formula above.  
3. Replace the older point and repeat the process until convergence.

**Advantages:**
- Faster than the Bisection Method.  
- Does not require the derivative \(f'(x)\).  

**Limitations:**
- May fail if \(f(x_n) - f(x_{n-1}) = 0\).  
- Convergence is not guaranteed if the initial guesses are poorly chosen.

---

## Summary of Methods

| Method           | Requires Derivative | Convergence Speed | Reliability |
|------------------|--------------------|------------------|--------------|
| Bisection        | ❌ No              | Slow             | Always convergent |
| Newton–Raphson   | ✅ Yes             | Fast             | Conditional |
| Secant           | ❌ No (approx.)    | Moderate         | Conditional |

Each of these methods provides a trade-off between speed, accuracy, and robustness.  
In this project, all three were implemented in **GNU Octave** to compute the same root and compare their convergence behaviors.