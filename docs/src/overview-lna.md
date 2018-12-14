# [LNA Overview](@id lna-overview)

The LNA approximates the Chemical Master Equation (CME) by decomposing the stochastic process into two ordinary differential equations (ODEs); one describing the evolution of the mean of the trajectories and the other describing the evolution of the covaraince of the trajectories.

In other words the LNA approximates the stochastic process by looking at the mean and the covariance of the trajectories $\textbf{x}(t)$, whose evolution is described by a system of ODEs which can be seen below:

```math
\begin{align}
\frac{d\varphi}{dt}&=\mathcal{S}\textbf{f}(\boldsymbol\varphi) \label{mean} \\
\frac{d\Sigma}{dt}&=\mathcal{A} \, \Sigma + \Sigma \, \mathcal{A}^T + \frac{1}{\sqrt{\Omega}} \, \mathcal{S} \, \text{diag}(\textbf{f}(\boldsymbol\varphi)) \, \mathcal{S}^T \label{covar}
\end{align}
```

Here $\mathcal{S}$ is the stoichometry matrix of the system, $\textbf{f}$ is the reaction rates.

The matrix $\mathcal{A}(t) = \mathcal{S}\mathcal{D}$ and $\mathcal{D}$ is the Jacobian of the reaction rates: $\{\mathcal{D} \}_{i,k} = \frac{\partial f_i(\boldsymbol\varphi)}{\partial \phi_k}$

These can be solved by numerical methods to describe how $\boldsymbol\varphi$ (the mean) and $\Sigma$ (the covariance) evolve with time.
