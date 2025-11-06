# 5. Comparison of Numerical Methods

This section compares the three numerical techniques — **Bisection**, **Newton–Raphson**, and **Secant Methods** — based on their performance, convergence rate, stability, and computational efficiency.  
All methods were applied to the same test function \( f(x) = x^2 - 4 \) and successfully converged to the root \( x = 2 \).

---

## 5.1 Convergence Rate

| Method           | Convergence Type | Order of Convergence | Speed |
|------------------|------------------|-----------------------|--------|
| **Bisection**        | Linear          | 1                     | Slow   |
| **Newton–Raphson**   | Quadratic       | 2                     | Fast   |
| **Secant**           | Superlinear     | ≈1.618 (Golden Ratio) | Moderate |

- The **Bisection Method** converges linearly, meaning the number of accurate digits increases by roughly one per iteration.  
- The **Newton–Raphson Method** converges quadratically, rapidly doubling the number of accurate digits per iteration once near the root.  
- The **Secant Method** lies between the two — faster than Bisection but slightly slower than Newton–Raphson.

---

## 5.2 Stability and Robustness

| Method | Stability | Derivative Required | Guaranteed Convergence |
|:--|:--:|:--:|:--:|
| **Bisection** | ✅ High | ❌ No | ✅ Yes |
| **Newton–Raphson** | ⚠️ Medium | ✅ Yes | ❌ No |
| **Secant** | ⚠️ Medium | ❌ No | ❌ No |

- **Bisection** is the most **stable** method, as it always converges if \(f(a)f(b) < 0\).  
- **Newton–Raphson** is **sensitive** to the initial guess — it may diverge if the starting value is far from the true root or if \(f'(x)\) ≈ 0.  
- **Secant** removes the need for a derivative but sacrifices guaranteed convergence in exchange for speed.

---

## 5.3 Computational Effort

| Method | Function Evaluations per Iteration | Memory Usage | Implementation Complexity |
|:--|:--:|:--:|:--:|
| **Bisection** | 1 | Low | Easy |
| **Newton–Raphson** | 2 (f & f′) | Low | Moderate |
| **Secant** | 2 | Low | Easy |

- **Bisection** is computationally simple but may require more iterations.  
- **Newton–Raphson** demands derivative computation at each step, increasing effort but reducing total iterations.  
- **Secant** uses two function evaluations but avoids symbolic differentiation, making it efficient for non-analytic functions.

---

## 5.4 Error Behavior

The error \(E_n = |x_n - x_{true}|\) decreases differently for each method:

- **Bisection:** Error reduces linearly with interval halving:  
  \[
  E_n = \frac{b - a}{2^n}
  \]
- **Newton–Raphson:** Error decreases quadratically:  
  \[
  E_{n+1} \approx C \cdot E_n^2
  \]
- **Secant:** Error follows a superlinear relationship:  
  \[
  E_{n+1} \approx C \cdot E_n^{1.618}
  \]

Thus, Newton–Raphson achieves faster convergence if the derivative is well-behaved.

---

## 5.5 Overall Comparison

| Criterion | **Bisection** | **Newton–Raphson** | **Secant** |
|:--|:--:|:--:|:--:|
| Accuracy | High | Very High | High |
| Convergence Speed | Slow | Fast | Moderate |
| Stability | Excellent | Sensitive to initial guess | Sensitive to initial guesses |
| Requires Derivative | ❌ | ✅ | ❌ |
| Ease of Implementation | ✅ Easy | ⚙️ Moderate | ✅ Easy |
| Best Use Case | When guaranteed convergence is needed | When speed is crucial | When derivative is unavailable |

---

## 5.6 Discussion

The **Newton–Raphson Method** demonstrated the fastest convergence and highest precision among all three techniques.  
However, its dependence on the derivative and sensitivity to initial guesses can lead to divergence under poor conditions.

The **Bisection Method** remains the most reliable option, ensuring convergence as long as the initial interval brackets the root.  
The **Secant Method** offers an excellent balance — combining simplicity and efficiency without requiring a derivative.

Overall, the choice of method depends on the **nature of the function**, **availability of derivatives**, and **required precision**.  
In practical applications:
- Use **Bisection** for safety and guaranteed results.  
- Use **Newton–Raphson** when speed is essential and derivatives are known.  
- Use **Secant** when derivatives are difficult or impossible to compute.