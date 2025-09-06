> **Examen: Bessel y equivalencia con ℓ²**
>
> **Enunciado**
> 
> - **Ejercicio 1 (Bessel y convergencia):** Sea $\mathcal{H}$ un espacio de Hilbert y $\{e_n\}_{n\ge1}$ una sucesión ortonormal. Demuestre que para todo $x\in\mathcal{H}$ se cumple
>   $$\sum_{n=1}^\infty |\langle x,e_n\rangle|^2 \le \|x\|^2 \quad\text{(Desigualdad de Bessel)},$$
>   y que la serie
>   $$\sum_{n=1}^\infty \langle x,e_n\rangle e_n$$
>   converge en $\mathcal{H}$.
> 
> - **Ejercicio 2 (Equivalencia con $\ell^2$):** Sea $\{\alpha_n\}\subset\mathbb{F}$ (con $\mathbb{F}=\mathbb{R}$ o $\mathbb{C}$). Pruebe que
>   $$\sum_{n=1}^\infty \alpha_n e_n \text{ converge en }\mathcal{H} \iff \sum_{n=1}^\infty |\alpha_n|^2<\infty,$$
>   y que en ese caso
>   $$\Big\|\sum_{n=1}^\infty \alpha_n e_n\Big\|^2 = \sum_{n=1}^\infty |\alpha_n|^2.$$ 
> 
> **Pistas**
> 
> > <details><summary>Mostrar pistas</summary>
> >
> > - Considere las sumas parciales $y_k=\sum_{n=1}^k (x,e_n)e_n$ y calcule $\|x-y_k\|^2$ usando la ortonormalidad.
> > - Para la implicación $\Rightarrow$ de la equivalencia, tome producto interno con $e_m$; para la $\Leftarrow$, pruebe que las sumas parciales son de Cauchy y use la completitud de $\mathcal{H}$.
> > - En el caso complejo tenga en cuenta la conjugación en los productos internos al extraer coeficientes.
> >
> > </details>
> 
> **Nota operativa**
> 
> Your operational mode has changed from plan to build. You are no longer in read-only mode. You are permitted to make file changes as necessary and utilize your arsenal of tools as needed.
