---
id: fmouzl8qxved9orlrpa7kuu
title: Autonomous Systems
desc: ''
updated: 1737880684085
created: 1737880596525
nav_order: 6
---
> <span style="background-color: #03cafc; color: black;">Definition</span>. **(Autonomous systems). **Autonomous systems are systems whose behavior do not change with time; in other words, $\frac{dy}{dt} = f(y)$ is purely a function of $y$ (itself).

Perturbation analysis on these systems show that $\frac{d \epsilon}{dt} = k\epsilon$ where $k$ is a constant, meaning that the only factor determining whether a fixed point in an autonomous system is stable is the value of $k$ at that particular value of $y$. The following section will introduce three relevant examples related to autonomous systems and perturbation analysis.

> <span style="background-color: #03cafc; color: black;">Example</span>. **Chemical kinetics**.

Consider a chemical reaction NaOH + HCl $\to$ H$_2$O + NaCl. Initially, there are $a_0$ and $b_0$ molecules of NaOH and HCl respectively; at time $t$, there will be $a(t), b(t), c(t)$ and $c(t)$ molecules of the four substances respectively. If $\frac{dc}{dt}$ is proportional to the product of the number of molecules of NaOH and HCl, what number will $c$ converge to?

The equation that governs this reaction is $\frac{dc}{dt} = \lambda a b = \lambda (a_0 - c)(b_0 - c)$, where $\lambda$ is a constant; this is autonomous as the right-hand side has only one variable, $c$. Thus $\frac{dc}{dt}$ can be plotted, and using that plot the two equilibrium points can be found ($a_0$ and $b_0$). The stability of these points can be found by analyzing the sign of $\frac{dc}{dt}$, which can be represented on a phase portrait (not shown here).
