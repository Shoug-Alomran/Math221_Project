# Conclusion

This project explored and implemented three fundamental numerical techniques — **Bisection**, **Newton–Raphson**, and **Secant Methods** — to solve nonlinear equations that cannot be expressed or solved analytically.  
Through careful computational experiments and visual analysis, the performance, accuracy, and convergence rate of each method were systematically compared.

---

## 6.1 Summary of Findings

- All three methods successfully found the root of the test function \( f(x) = x^2 - 4 \) at **x = 2**.  
- The **Bisection Method** was the most reliable, as it guarantees convergence when the initial interval is properly chosen.  
- The **Newton–Raphson Method** demonstrated the fastest convergence rate, achieving the root within a few iterations.  
- The **Secant Method** offered a good compromise between efficiency and simplicity, performing well without requiring derivative computation.

These results confirm the theoretical expectations of convergence order and demonstrate how initial guesses, tolerance levels, and computational precision affect numerical accuracy.

---

## 6.2 Reflection

This project enhanced the understanding of:
- How iterative numerical techniques approach a root through successive approximations.  
- The trade-offs between **stability**, **speed**, and **accuracy** when applying each method.  
- The importance of algorithm design in ensuring that numerical computations remain efficient and error-tolerant.

The hands-on implementation using **GNU Octave** (and MATLAB-compatible syntax) reinforced both **mathematical theory** and **computational practice**, bridging the gap between analytical equations and digital problem-solving.

---

## 6.3 Future Work

For further enhancement, the following directions are recommended:
- Implementing **adaptive step-size control** to improve convergence reliability.  
- Extending the project to handle **systems of nonlinear equations**.  
- Integrating **graphical user interfaces (GUIs)** for better visualization of iterations.  
- Comparing these methods with advanced algorithms like **Fixed Point Iteration**, **Hybrid Methods**, or **Brent’s Method** for broader insight.

---

## 6.4 Final Thoughts

The exploration of numerical root-finding methods demonstrates their critical role in modern computational mathematics.  
From simple academic exercises to large-scale engineering applications, these techniques remain essential tools for scientists, engineers, and developers worldwide.  
Their enduring relevance lies in their adaptability — balancing mathematical rigor with computational practicality.