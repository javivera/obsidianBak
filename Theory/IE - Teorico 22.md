
>[!Remark]
>Otra forma de encontrar estimadores IMVU es usando la desigualdad de la Información o desigualdad de Rao-Crámer
>Cuando vimos el Teorema de Lehmann-Scheffé, la unicidad del Estimador IMVU surgía entre los estimadores que son $\sigma(T)$-medibles. Vamos a enunciar un resultado, que no mostraremos, que dice que el IMVU es único, aunque busquemos entre otros estimadores que no sean $\sigma(T)$-medibles.

>[!Theorem]
>Sea la familia paramétrica $\mathcal{P} = \{P_\theta : \theta \in \Theta\}$ identificable y $\mathcal{P}$ está dominada por una medida $\sigma$-finita $\lambda$, $P_\theta \ll \lambda$ para todo $\theta \in \Theta$. 
>Si existe un UMVU $U \in \mathcal{U}$, cualquier otro estimador $W \in \mathcal{U}$ IMVU cumple que $P_\theta(W=U) = 1$ para todo $\theta \in \Theta$, o sea que el UMVU es único, salvo conjuntos de $P_\theta$ probabilidad 0.

>[!Remark]
>Otra forma de encontrar estimadores IMVU es a través de la Desigualdad de la Información o Desigualdad de Rao-Crámer, y cuando un estimador alcanza esa cota entonces estaríamos en presencia de un estimador IMVU. En lo que sigue entonces obtendremos esas cotas.
>Una cuestión técnica que surge es cuando podemos intercambiar derivadas con signo integral. Veamos esto. Sea $(\Omega, \mathcal{F}, \mu)$ un espacio de medida y sea $\Theta$ un subconjunto abierto de $\mathbb{R}^k$. Sea $g: \Omega \times \Theta \to \mathbb{R}$ y supongamos que $g(\cdot, \theta)$ es una función medible para cada $\theta \in \Theta$. Entonces,
>**Condición 3:** Sea $B \in \mathcal{F}$. Supongamos que
>- (i) para cada $x \in \Omega$, $g(x, \theta)$ es diferenciable con respecto a $\theta$, la derivada es medible y
>$$ \int_B \|\nabla_\theta g(x, \theta)\|_1 \mu(dx) < \infty $$
>(el subíndice 1 indica la norma en $L_1$); Notar que esta condicion nos dice que $$\int_{B}\left|\frac{\partial g}{\partial\theta_{1}}(x,\theta)\right|+\ldots+\int_{B}\left|\frac{\partial g}{\partial\theta_{k}}(x,\theta)\right|= \int_B \|\nabla_\theta g(x, \theta)\|_1 \mu(dx) < \infty $$  
>- (ii) para cada $\theta \in \Theta$, $\int_B |g(x, \theta)| \mu(dx) < \infty$ y la función $G(\theta) = \int_B g(x, \theta) \mu(dx)$ es diferenciable;
>- (iii) Se puede intercambiar integral y derivación, esto es,
>$$ \nabla_\theta \left[ \int_B g(x, \theta) \mu(dx) \right] = \int_B \nabla_\theta g(x, \theta) \mu(dx) $$
>El siguiente Teorema, que no probaremos, nos da condiciones suficientes para que se satisfagan Condición 3; esencialmente es una suerte de Teorema de Convergencia Dominada pero aplicado al cociente incremental que interviene en la derivada.

>[!Theorem]
>Supongamos que vale (i) de la Condición 3. Supongamos que existe una función $g_0(x)$ medible e integrable tal que para cada $\theta_1, \theta_2 \in \Theta$ se cumple, para todo $x \in B$,
>$$ |g(x, \theta_2) - g(x, \theta_1)| \le g_0(x) \|\theta_2 - \theta_1\| $$
>Entonces se cumple las condiciones (ii) y (iii) de la Condición 3.

>[!Definition] Funcion Score
>Dijimos que la familia $\mathcal{P}$ era dominada por una medida $\sigma$-finita $\lambda$. Sean entonces las densidades $f_\theta = \frac{dP_\theta}{d\lambda}$ (en los casos discretos y continuos son las funciones de probabilidad puntual o las densidades respecto de la medida de Lebesgue). Si la función $\log f_\theta(x)$ es diferenciable respecto de $\theta$, se denota
>$$ s_\theta(x) = \nabla_\theta \log f_\theta(x) $$
>Esta función se denomina **función score**. 
>

>[!Definition] Matriz de Fisher
>Calculemos entonces la varianza o matriz de varianzas-covarianzas de $s_\theta$, que denominamos **matriz de Información de Fisher** $$I(\theta) = V_\theta(s_\theta(X))$$
>Sea $I_k$ la matriz identidad en $\mathbb{R}^{k \times k}$. Una definición más para establecer algo de notación.

>[!Definition]- Notacion
>Si $D \subset \mathbb{R}^k$ es abierto y
> - (i) $g: D \to \mathbb{R}$ es dos veces diferenciable entonces denotamos
>$$ \nabla_\theta g(y) = \left( \frac{\partial g}{\partial \theta_i}(y) \right)_{1 \le i \le k} \quad \nabla^2_\theta g(y) = \left( \frac{\partial^2 g}{\partial \theta_i \partial \theta_j}(y) \right)_{1 \le i,j \le k} $$
> - (ii) $g: D \to \mathbb{R}^k$, $g(\theta) = (g_1(\theta), \dots, g_k(\theta))'$, con $g_i$ diferenciables. Entonces
> $$ Dg(y) = \left( \frac{\partial g_i}{\partial \theta_j}(y) \right)_{1 \le i \le k, 1 \le j \le k} $$

>[!Remark]
>Vamos a trabajar en lo que sigue con el supuesto que las funciones $f_\theta(x)$ tienen un soporte común $A$ para todo $\theta \in \Theta$.

>[!Remark] Condicion 4
>**Condición 4:** Sea $g: \Omega \times \Theta \to \mathbb{R}$ y supongamos que $g(\cdot, \theta)$ es una función medible para cada $\theta \in \Theta \subset \mathbb{R}^k$ abierto, tal que satisface las siguientes condiciones,
>- (a) el soporte $A$ de $f_\theta$ es independiente de $\theta$,
>- (b) $g(x, \theta)f_\theta(x)$ satisface las condiciones (i), (ii) y (iii) de la Definición 3.

>[!Remark]
>Entonces los valores esperados y matriz de covarianza de la función score son obtenidos en el siguiente lema.

>[!Lemma]
>- (a) Si $f_\theta$ cumple la Condición 4, entonces $E_\theta s_\theta(X) = 0$.
>- (b) Si $f_\theta$ y ${} s_\theta(X)f_\theta(X) {}$ cumplen la Condición 4, entonces $V_\theta[s_\theta(X)] = -E_\theta[\nabla_\theta^2 \log f_\theta(X)]$.
>>[!Proof]-
>> **(a)**
>> 1. Notar $\int_\Omega f_\theta(x) \mu(dx) = 1$. 
>> 2. Diferenciando bajo la integral y metiendo el diferencial (por Condición 4): $$0=\nabla_{\theta}\int_\Omega f_\theta(x) \mu(dx)=\int_\Omega \nabla_\theta f_\theta(x) \mu(dx)$$
>> 3. Ahora recordemos ${} s_{\theta}(X)=\nabla_{\theta} logf_{\theta}(X)=\frac{\nabla_{\theta}f_{\theta}(X)}{f_{\theta}(X)} {}$
>> 4. Entonces usando definicion de esperanza $$E_\theta[s_\theta(X)] = \int_\Omega \frac{\nabla_\theta f_\theta(x)}{f_\theta(x)} f_\theta(x) \mu(dx) =\int_\Omega \nabla_\theta f_\theta(x) \mu(dx) =0$$
>>
>>**(b)** 
>>5. Notar que $s_{\theta}(x)f_{\theta}(x)=\nabla_{\theta}f_{\theta}(x)$ y por hipotesis ${} s_{\theta}(x)f_{\theta}(x) {}$ cumple condicion 4. Entonces $\nabla_{\theta}f_{\theta}(x)$ tambien. Entonces puedo meter derivada adentro de integral     
>>6. Diferenciando nuevamente: $$0 =\nabla_\theta\int_\Omega \nabla_{\theta} f_\theta(x) \mu(dx) =\int_\Omega \nabla_\theta^2 f_\theta(x) \mu(dx)$$
>>7. Luego notar $\nabla_{\theta}^{2}logf_{\theta}(x)=\nabla_{\theta}\left(\frac{\nabla_{\theta}f_{\theta}(x)}{f_{\theta}(x)}\right)=\frac{\nabla_{\theta}^{2}f_{\theta}(x)f_{\theta}(x)-\nabla_{\theta}f_{\theta}(x)^{}[\nabla_{\theta}f_{\theta}(x)]^{T}=\nabla^{2}_{\theta}f_{\theta}(x)}{f_{\theta}^{2}(x)}=\frac{\nabla_{\theta}^{2}f_{\theta}(x)}{f_{\theta}(x)}-\frac{\nabla_{\theta}f_{\theta}(x)[\nabla_{\theta}f_{\theta}(x)]^{T}}{f_{\theta}(x)^{2}}$ 
>>8. Por lo tanto usandi 6. y 4. $$\begin{align}E_{\theta}[\nabla_{\theta}^{2}logf_{\theta}(X)]& =\int_{\Omega}\frac{\nabla_{\theta}^{2}f_{\theta}(x)}{f_{\theta}(x)}f_{\theta}(x)\mu (dx)-\int_{\Omega}\frac{\nabla_{\theta}f_{\theta}(x)[\nabla_{\theta}f_{\theta}(x)^{T}]}{f_{\theta}(x)^{2}}f_{\theta}(x)\mu (dx)\\&=-\int_{\Omega}\frac{\nabla_{\theta}f_{\theta}(x)[\nabla_{\theta}f_{\theta}(x)^{T}]}{f_{\theta}(x)}\mu (dx)\\&=-\int_{\Omega}s_{\theta}(x)s_{\theta}(x)^{T}f_{\theta}(x) \mu (dx)\\&=-E_{\theta}(s_{\theta}(X)s_{\theta}(X)^{T} )\\&=-E_{\theta}([s_{\theta}(X)-E_{\theta}(s_{\theta}(X))][s_{\theta}(X)-E_{\theta}(s_{\theta}(X))]^{T} )\\&=-V_{\theta}(s_{\theta}(X))\end{align}$$
>>5.Por lo tanto, $V_\theta[s_\theta(X)] = -E_\theta[\nabla_\theta^2 \log f_\theta(X)]$.  

>[!Remark]
>Un resultado que es útil, pero que no probaremos, es la siguiente desigualdad de Cauchy-Schwarz multivariada.

>[!Lemma]
>Sea $(\Omega, \mathcal{F}, \mu)$ un espacio de medida y $f: \Omega \to \mathbb{R}^k$ y $g: \Omega \to \mathbb{R}^k$ funciones medibles tal que $\int \|f\|^2 d\mu < \infty$ y $\int \|g\|^2 d\mu < \infty$. Supongamos que la matriz ${} \int gg^{T} d\mu \in \mathbb{R}^{k \times k} {}$ es invertible. Entonces, en el orden de matrices semidefinidas positivas, ocurre que
>$$ \left(\int fg^{T}  d\mu\right) \left(\int gg^{T}  d\mu\right)^{-1} \left(\int gf^{T}  d\mu\right) \le \int ff^{T} d\mu $$
>La igualdad ocurre si y sólo si existe una matriz constante $A \in \mathbb{R}^{k \times k}$ tal que $f = Ag$, salvo conjunto de $\mu$-medida nula. Además, si $\int ff^{T} d\mu \in \mathbb{R}^{k \times k}$ es no singular, entonces $A$ es no singular.

>[!Theorem] Desigualdad de Rao-Cramer
>Sea $\Theta \subset \mathbb{R}^k$ abierto, $\mathcal{P} = \{P_\theta : \theta \in \Theta\}$ una familia paramétrica y dominada por una medida $\sigma$-finita $\lambda$, definidas en $(\Omega_X, \mathcal{F}_X)$. Sean las densidades $f_\theta$ respecto de la medida $\lambda$. 
>Supongamos que se cumplen las siguientes condiciones:
>- (i) Sea $X: \Omega \to \Omega_X$ vect. aleatorio, $U = u(X)$ estadístico tal que $E_\theta\|U\|^2 < \infty$ para todo $\theta \in \Theta$;
>- (ii) $f_\theta(x)$ y $u(x)f_\theta(x)$ satisfacen la Condición 4;
>- (iii) la matriz de información $I(\theta)$ es no singular para todo $\theta \in \Theta$.
>
>Entonces, si $q(\theta) = E_\theta U$, para todo $\theta \in \Theta$, se cumple que
>$$ V_\theta(U) \ge \left[ \frac{\partial q(\theta)}{\partial \theta} \right]^t [I(\theta)]^{-1} \left[ \frac{\partial q(\theta)}{\partial \theta} \right] $$

>[!Remark]
>Si el estimador es insesgado para $\theta, E_\theta U = \theta$, entonces $$V_\theta(U) \ge [I(\theta)]^{-1}$$

>[!Remark]
>Entonces en las condiciones del teorema anterior sabemos que la varianza de un estimador insesgado está acotada por abajo, uno quiere estimadores con la varianza "lo más pequeña posible". El próximo resultado nos dice cuando alcanzamos la cota inferior.

>[!Theorem]
>Sea $\Theta \subset \mathbb{R}^k$ abierto, $\mathcal{P} = \{P_\theta : \theta \in \Theta\}$ una familia paramétrica y dominada por una medida $\sigma$-finita $\lambda$, definidas en $(\Omega_X, \mathcal{F}_X)$. 
>Sean las densidades $f_\theta$ respecto de la medida $\lambda$. Supongamos que
>- (i) $f_\theta(x)$ satisface la Condición 4;
>- (ii) $E_\theta\|s_\theta(X)\|^2 < \infty$ y la matriz de información $I(\theta)$ es no singular para todo $\theta \in \Theta$.
>
>Sea un estimador insesgado $U=u(X)$ de $\theta$. Entonces las afirmaciones siguientes son equivalentes:
>- (a) $V_\theta(U) = [I(\theta)]^{-1}$.
>- (b) $X$ tiene distribución en una familia exponencial con densidades de la forma
>$$ f_\theta(x) = \frac{\exp(\eta(\theta)'u(x))}{\int \exp(\eta(\theta)'u(x))\nu(dx)} $$
>donde la medida $\nu$ está definida en $\mathcal{F}_X$, está dominada por $\lambda$ y la función $\eta: \Theta \to \mathbb{R}^k$ es diferenciable respecto de $\theta$, y $D\eta(\theta) = I(\theta)$.

>[!Example]
>Sean $X_1, \dots, X_n$ v.a.i.i.d. tal que $X_1 \sim N(\mu, \sigma^2)$, $\theta = (\mu, \sigma^2)$. Sean $\hat{\mu} = \frac{1}{n} \sum_{i=1}^n X_i$ y $S^2 = \frac{1}{n-1} \sum_{i=1}^n(X_i-\hat{\mu})^2$ la media y varianza muestral, que son insesgados para $\mu$ y $\sigma^2$ respectivamente. 
>Sea $\hat{\theta} = (\hat{\mu}, S^2)$. Sabemos que son suficientes y completos, y como son insesgados deben ser IMVU por el teorema de Lehmann-Scheffé. Por otro lado se cumplen las condiciones para que valga la desigualdad de Rao-Cramer. Cuando calculamos la matriz de información asociada al vector $X = (X_1, \dots, X_n)$ resulta ser la matriz ser
>$$ I^{-1}(\theta) = \begin{pmatrix} \frac{\sigma^2}{n} & 0 \\ 0 & \frac{2\sigma^4}{n} \end{pmatrix} $$
>
>Por Rao-Cramer entonces $V_\theta(\hat{\mu}) \ge \frac{\sigma^2}{n}$ y $V_\theta(S^2) \ge \frac{2\sigma^4}{n}$. En el primer caso, la desigualdad es exactamente una igualdad, lo que daría otra forma para concluir que la media muestral es IMVU, porque alcanza exactamente la minima cota posible. Sin embargo la segunda desigualdad es estricta porque $V_\theta(S^2) = \frac{2\sigma^4}{n-1} > \frac{2\sigma^4}{n}$ o sea que la cota inferior no es alcanzada, por lo cual no es por este mecanismo que podemos concluir que $S^2$ es IMVU.

## DISTRIBUCIONES DE MEDIA Y VARIANZA MUESTRAL BAJO NORMALIDAD

>[!Remark] Notacion
>Si $Z \sim N(0,1)$, $T \sim t_m$ (distribución t-Student con m grados de libertad), $W \sim \chi_m^2$ (distribución chi-cuadrado con m grados de libertad) y $U \sim F_{n,m}$ (distribución de $\mathbb{R}$ Fisher con n y m grados de libertad) entonces denotamos respectivamente los percentiles de la distribuciónes, $z_\gamma, t_{m,\gamma}, \chi_{m,\gamma}^2$ y $f_{n,m,\gamma}$ como los valores tales que $P(Z \le z_\gamma)=\gamma=P(T \le t_{m,\gamma})=P(W \le \chi_{m,\gamma}^2)=P(U \le f_{n,m,\gamma})$.

>[!Lemma]
>Sean $X_1, \dots, X_n$ v.a.i.i.d. $X_1 \sim N(\mu, \sigma^2)$, $\mu$ y $\sigma^2$ desconocidos, o sea que $\theta = (\mu, \sigma^2)'$. Entonces se cumple que
>- (a) $\bar{X}_n \sim N(\mu, \sigma^2/n)$.
>- (b) $\frac{\sum_{i=1}^n(X_i-\bar{X}_n)^2}{\sigma^2} \sim \chi_{n-1}^2$. 
>- (c) $\bar{X}_n$ y $S^2 = \frac{\sum_{i=1}^n(X_i-\bar{X}_n)^2}{n-1}$ son independientes 
>- (d) $\frac{\sqrt{n}(\bar{X}_n-\mu)}{S} \sim t_{n-1}$.
>- (e) $\frac{n(\bar{X}_n-\mu)^2}{S^2} \sim F_{1,n-1}$.
>>[!Proof]-
>>Observemos que si $X = (X_1, \dots, X_n)'$ entonces
>>$$ \sum_{i=1}^n (X_i - \bar{X}_n)^2 = \left\| \begin{pmatrix} 1-\frac{1}{n} & -\frac{1}{n} & \dots & -\frac{1}{n} \\ -\frac{1}{n} & 1-\frac{1}{n} & \dots & -\frac{1}{n} \\ \vdots & \vdots & \ddots & \vdots \\ -\frac{1}{n} & -\frac{1}{n} & \dots & 1-\frac{1}{n} \end{pmatrix} X \right\|^2 = \|PX\|^2 $$
>>La matriz $P$ es simétrica, todos sus autovalores son reales, encontremos entonces los autovalores y autovectores de esa matriz. Sea $\lambda \in \mathbb{R}$ y $v = (v_1, \dots, v_n)' \ne 0$ tal que $Pv = \lambda v$, entonces,
>>$$ \begin{pmatrix} 1-\frac{1}{n} & -\frac{1}{n} & \dots & -\frac{1}{n} \\ -\frac{1}{n} & 1-\frac{1}{n} & \dots & -\frac{1}{n} \\ \vdots & \vdots & \ddots & \vdots \\ -\frac{1}{n} & -\frac{1}{n} & \dots & 1-\frac{1}{n} \end{pmatrix} \begin{pmatrix} v_1 \\ v_2 \\ \vdots \\ v_n \end{pmatrix} = \lambda \begin{pmatrix} v_1 \\ v_2 \\ \vdots \\ v_n \end{pmatrix} $$
>>$v_j - \frac{\sum_{i=1}^n v_i}{n} = \lambda v_j, j=1, \dots, n$, sumando en j de 1 a n obtenemos que,
>>$$ \sum_{j=1}^n v_j - \sum_{j=1}^n \left( \frac{\sum_{i=1}^n v_i}{n} \right) = \lambda \sum_{j=1}^n v_j \text{ lo cual dice que } \sum_{j=1}^n v_j - \sum_{j=1}^n v_j = 0 = \lambda \sum_{j=1}^n v_j $$
>>Entonces, ocurre que. 
>> - (i) si $\lambda=0$ entonces $v_j = \frac{\sum_{i=1}^n v_i}{n}$ para todo j con lo cual $v = c(1, \dots, 1)' , c \ne 0$ constante.
>> - (ii) si $\sum_{j=1}^n v_j = 0$ (en este caso $\lambda \ne 0$ porque si lo fuera $v=0$), resulta que $v_j = \lambda v_j$ para todo j y entonces $\lambda = 1$.
>>
>>Entonces la matriz simétrica $P$ es una matriz de proyección porque tiene autovalores 1 y 0, luego $P^2 = P$ y los vectores asociados a cada autovalor son ortogonales, con lo cual la descomposición espectral de $P$ es de la forma
>>$$ P = D \Delta D', \quad \Delta = \text{diag}(1, 1, \dots, 1, 0) \text{ es la matriz diagonal de autovalores y} $$
>>si $v_n = \left(\frac{1}{\sqrt{n}}, \dots, \frac{1}{\sqrt{n}}\right)'$, entonces la matriz ortonormal de autovectores está dada por
>>$D = (v_1, v_2, \dots, v_n)$ con $v_i' v_j = \delta_{ij}, 1 \le i,j \le n$, y $D'D = I_n$ (matriz identidad $n \times n$).
>>
>>Luego, si $Y = X - \mu \sim N_n(0, \sigma^2 I_n)$, entonces $D'Y \sim N_n(0, \sigma^2 I_n)$ y $\frac{D'Y}{\sigma} \sim N_n(0, I_n)$, o sea $\frac{D'Y}{\sigma} = (Z_1, \dots, Z_n)'$ con $Z_j = \frac{v_j'Y}{\sigma}$, $j=1,\dots,n$ v.a.i.i.d y $Z_j \sim N(0,1)$.
>>
>>Entonces, se puede mostrar que $\frac{\sqrt{n}(\bar{X}_n - \mu)}{\sigma} = Z_n$, que sigue una distribución $N(0,1)$.
>>
>>Además,
>>$$ \frac{\sum_{i=1}^n (X_i - \bar{X}_n)^2}{\sigma^2} = \frac{\|PX\|^2}{\sigma^2} = \frac{\|PY\|^2}{\sigma^2} = \frac{Y'P^2Y}{\sigma^2} = \frac{Y'PY}{\sigma^2} = \frac{Y'D\Delta D'Y}{\sigma^2} = \left(\frac{D'Y}{\sigma}\right)' \Delta \left(\frac{D'Y}{\sigma}\right) = Z' \Delta Z = \sum_{j=1}^{n-1} Z_j^2 \sim \chi_{n-1}^2 $$
>>donde $\chi_{n-1}^2$ denota la distribución chi-cuadrado con $n-1$ grados de libertad. Entonces (a) y (b) ya están comprobados.
>>
>>Además, $\frac{\sum_{i=1}^n(X_i-\bar{X}_n)^2}{\sigma^2} = \sum_{j=1}^{n-1} Z_j^2$ y $\frac{\sqrt{n}(\bar{X}_n-\mu)}{\sigma} = Z_n$.
>>Con lo cual, como $Z_n$ es independiente de $Z_1, \dots, Z_{n-1}$ (ya que los $Z_j$ son i.i.d.), entonces la varianza muestral y la media muestral son independientes, y surge (c).
>>
>>(d) sigue por la definición de la distribución t-de Student, porque juntando los puntos (a), (b) y (c) surge que:
>>$$ \frac{\frac{\sqrt{n}(\bar{X}_n-\mu)}{\sigma}}{\sqrt{\frac{\sum_{i=1}^n(X_i-\bar{X}_n)^2/\sigma^2}{n-1}}} = \frac{\sqrt{n}(\bar{X}_n-\mu)}{S} \sim t_{n-1} $$
>>
>>(e) Como $\left(\frac{\sqrt{n}(\bar{X}_n-\mu)}{\sigma}\right)^2 \sim \chi_1^2$, entonces, de la definición de la distribución de Fisher, surge que:
>>$$ \frac{\left(\frac{\sqrt{n}(\bar{X}_n-\mu)}{\sigma}\right)^2/1}{\left(\frac{\sum_{i=1}^n(X_i-\bar{X}_n)^2}{\sigma^2}\right)/(n-1)} = \frac{n(\bar{X}_n-\mu)^2}{S^2} \sim F_{1,n-1} $$