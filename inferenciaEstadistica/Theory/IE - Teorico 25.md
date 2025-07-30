---
dateCreated: 2025-06-15,18:35
---
**TEST DE HIPÓTESIS (Demostraciones del día de la fecha)**

>[!Remark]
>Consideremos entonces el problema de testear
>$$ H_0: \mathcal{P}_0 = \{P_0\} \quad \text{vs.} \quad H_1: \mathcal{P}_1 = \{P_1\} $$
>
>**OBJETIVO:** Sea $0 \le \alpha \le 1$, encontrar un test $\varphi$ de tamaño $\alpha$ tal que su potencia en $P_1$ es mayor o igual a la potencia de cualquier otro test con nivel de significación $\alpha$.
>**NOTA:** Si la potencia es máxima entre todos los tests con nivel de significación $\alpha$, entonces tiene mínimo ETII entre todos los tests con nivel de significación $\alpha$. O sea que $1 - \beta_\varphi(P_1) \ge 1 - \beta_{\varphi'}(P_1)$.
>
>**NOTA:** Si $(\Omega_X, \mathcal{F}_X) = (\mathbb{R}^n, \mathcal{B}(\mathbb{R}^n))$ y si tenemos dos vectores aleatorios $X$ e $Y$ entonces entendemos las distribuciones $P_0$ y $P_1$ como las medidas que actuan en $\mathcal{B}(\mathbb{R}^n)$, $P_0(B) = P(X \in B)$ y $P_1(B) = P(Y \in B)$, $B \in \mathcal{B}(\mathbb{R}^n)$. Si $X$ e $Y$ son vectores discretos o continuos, entonces $P_0$ y $P_1$ tienen densidades, la función de probabilidad puntual en un caso y la función densidad propiamente en el caso continuo. Pero más en general, cuando $(\Omega_X, \mathcal{F}_X)$ es cualquiera y $P_0$ y $P_1$ son medidas sobre $\mathcal{F}_X$ cualquiera sea el caso, entonces se puede pensar que siempre están dominadas por una medida, esto es si tomamos la medida $\mu = P_0 + P_1$ resulta que $P_0 \ll P_0+P_1$ y $P_1 \ll P_0+P_1$, con lo cual admiten densidad respecto de la medida $\mu$ que domina.
>
>Entonces el siguiente lema nos dice como fabricar el test MP para el problema de hipótesis simples.

>[!Lemma] (de Neyman-Pearson I)
>Sean $f_0$ y $f_1$ las densidades de $P_0$ y $P_1$ respecto de una medida $\mu$. Entonces, para cada función $0 \le \gamma(x) \le 1$ y constante $k \ge 0$ se puede definir un test $\varphi: \Omega_X \to$ como
>$$ \varphi(x) = \begin{cases} 1 & \text{si } f_1(x) > k f_0(x) \\ \gamma(x) & \text{si } f_1(x) = k f_0(x) \\ 0 & \text{si } f_1(x) < k f_0(x) \end{cases} $$
>el cual resulta el MP de tamaño $\int \varphi f_0 d\mu$.
>>[!Proof]-
>>Si $\varphi'$ es otro test de nivel $\int \varphi' f_0 d\mu \le \int \varphi f_0 d\mu$, veamos que la potencia de $\varphi$ es mejor que la de $\varphi'$, esto es, $\int \varphi f_1 d\mu \ge \int \varphi' f_1 d\mu$. Como $\varphi'$ es un test, entonces por la definición de $\varphi$ resulta que
>>$$ [\varphi(x) - \varphi'(x)][f_1(x) - k f_0(x)] \ge 0 \text{ para todo } x. $$
>>Entonces
>>$$\begin{align*} 0 &\le \int [\varphi(x) - \varphi'(x)][f_1(x) - k f_0(x)] d\mu \\ &= \int (\varphi(x) - \varphi'(x)) f_1(x) d\mu - k \int (\varphi(x) - \varphi'(x)) f_0(x) d\mu \end{align*}$$
>>Como $\varphi'$ es de nivel $\alpha$, entonces $\int \varphi' f_0 d\mu \le \int \varphi f_0 d\mu$ y, $\int (\varphi(x) - \varphi'(x)) f_0(x) d\mu \ge 0$, por lo tanto $\int [\varphi(x) - \varphi'(x)] f_1(x) d\mu \ge 0$ y luego, se obtiene lo que se deseaba ver,
>>$$ \int \varphi'(x) f_1(x) d\mu \le \int \varphi(x) f_1(x) d\mu. $$

>[!Remark]
>Para deducir el test MP de cualquier tamaño deseado $\alpha$, enunciamos un resultado que se necesita que es una teorema del valor intermedio generalizado.

>[!Proposition]
>Supongamos que $\rho: \mathbb{R} \to \mathbb{R}$ es una función continua a derecha, decreciente y que satisface (i) $\lim_{x \to 0^-} \rho(x) = 1$ y (ii) $\lim_{x \to \infty} \rho(x) = 0$.
>Entonces para cualquier $0 < \alpha \le 1$ existe $k \in [0, \infty)$ tal que $\alpha \in [\rho(k), \rho(k^-)]$. (Sin Demostración)

>[!Lemma] de Neyman-Pearson II
>Para cualquier $0 < \alpha \le 1$ existe una test $\varphi$ de tamaño $\alpha$ de la forma dada en el Lema de Neyman-Pearson I, con $\gamma(x)=\gamma$, constante y $0 \le k < \infty$. Más aún, si $\varphi'$ es un test MP de tamaño $\alpha$. test MP de tamaño $\alpha$.
> $0 < \alpha \le 1$ entonces debe coincidir con el test de Neyman-Pearson salvo conjuntos de probabilidad 0 bajo $P_0$ y $P_1$, esto es,
> $$ P_0(\varphi \ne \varphi', f_1 \ne k f_0) = 0 \quad P_1(\varphi \ne \varphi', f_1 \ne k f_0) = 0 $$
>
> **NOTA:** La forma del test de Neyman-Pearson no especifica $\gamma(x)$, con lo cual si $\varphi = \varphi'$ en el conjunto $\{f_1 = k f_0\}$ entonces, por este último resultado, coinciden en todas partes salvo conjuntos de probabilidad 0.
>
>>[!Proof]
>>**(Existencia)** Veamos primero la existencia del test $\varphi$ con las propiedades enunciadas. Sea un test $\varphi$ con la forma del lema de Neyman-Pearson con $\gamma(x) = \gamma$, constante, entonces el tamaño resulta
>>$$ \int \varphi f_0 d\mu = P_0(f_1 > k f_0) + \gamma P_0(f_1 = k f_0). $$
>> Notemos que
>>$$ P_0(f_1 > k f_0) = \int_{\{f_1 > k f_0\}} f_0 d\mu = \int f_0 1_{\{f_1 > k f_0\}} d\mu = P_0(f_1 > k f_0 \cap f_0 > 0) $$
>>Fijemos $0 < \alpha \le 1$, y definamos
>>$$ \rho(k) = P_0(f_1 > k f_0) = P_0(f_1/f_0 > k \cap f_0 > 0). $$
>>Entonces $\rho(\cdot)$ es decreciente, continua por la derecha con las siguientes propiedades
>>$$ \rho(k^-) = \lim_{x \to k^-} \rho(x) = P_0(f_1 \ge k f_0), \quad \rho(0^-) = 1, \quad \rho(0) = P_0(f_1>0), \quad \lim_{k \to \infty} \rho(k) = 0. $$
>>Por lo tanto $(0,1] \subset \cup \{[\rho(k), \rho(k^-)]: 0 \le k < \infty \}$. Luego, para cualquier $0 < \alpha \le 1$ existe $0 \le k_0 < \infty$ tal que
>>$$ P_0(f_1 > k_0 f_0) \le \alpha \le P_0(f_1 \ge k_0 f_0), $$
>>con lo cual, usando $k=k_0$, para resolver la ecuación $\alpha = \int \varphi f_0 d\mu = P_0(f_1 > k f_0) + \gamma P_0(f_1 = k f_0)$, se debe tomar la constante $\gamma$ como
>>$$ \gamma = \begin{cases} \frac{\alpha - P_0(f_1 > k f_0)}{P_0(f_1=k f_0)} & \text{si } P_0(f_1 = k f_0) \ne 0 \\ 0 & \text{si } P_0(f_1 = k f_0) = 0 \end{cases}. $$
>>Luego, el test queda
>>$$ \varphi(x) = \begin{cases} 1 & \text{si } f_1(x) > k f_0(x) \\ \gamma & \text{si } f_1(x) = k f_0(x) \\ 0 & \text{si } f_1(x) < k f_0(x) \end{cases}. \quad (1) $$
>>**(Unicidad)** Sea $0 < \alpha \le 1$, sea $\varphi$ el test recién construido de tamaño $\alpha$, y sea $\varphi'$ otro test MP de tamaño $\alpha$, o sea que
>>$$ \int \varphi f_j d\mu = \int \varphi' f_j d\mu \text{ para } j=0,1 $$
>>Entonces,
>>$$ \int (\varphi - \varphi')(f_1 - k f_0) d\mu = \int (\varphi - \varphi') f_1 d\mu - k \int (\varphi - \varphi') f_0 d\mu = 0. $$
>>Como $(\varphi - \varphi')(f_1 - k f_0) \ge 0$ entonces $\mu((\varphi-\varphi')(f_1 - k f_0)=0)=1$. Entonces
>>$$ 1 = \mu((\varphi-\varphi')(f_1 - k f_0)=0), $$
>>$$ 0 = \mu((\varphi-\varphi') \ne 0, (f_1 - k f_0) \ne 0) $$
>>Como $P_0 \ll \mu$ y $P_1 \ll \mu$, entonces
>>$$ 0 = P_0((\varphi-\varphi') \ne 0, (f_1 - k f_0) \ne 0) $$
>>y sale el resultado deseado.
>>**NOTA:** Si $\alpha=0$ también se puede encontrar el test más potente que resulta de la forma $\varphi(x) = 1_{\{f_0(x)=0\}}(x)$ (es intuitivamente claro que para tener tamaño 0 debe rechazar siempre, que es lo que hace, no haremos la derivación).

## Tests uniformemente más potentes (UMP) para hipótesis unilaterales

>[!Lemma]
>Sea $\Theta \subset \mathbb{R}$. Supongamos que la familia de densidades $\{f_\theta(x) : \theta \in \Theta\}$ respecto de la medida $\mu$ cumple la propiedad de CVM creciente en $T(x)$. Si además el test $\varphi$ es una función creciente [decreciente] en $T$ entonces la función potencia $\beta_\varphi(\theta) = E_\theta \varphi = \int \varphi f_\theta d\mu$ es creciente [decreciente] en $\theta$.
>>[!Proof]
>>Sean $\theta_1 < \theta_2$ y sean los conjuntos
>>$A = \{x : f_{\theta_2}(x) < f_{\theta_1}(x)\} \text{ y } B = \{x : f_{\theta_1}(x) < f_{\theta_2}(x)\}$
>>Por definicion, si $a \in A$ y $b \in B$ entonces $L(a) < 1 < L(b)$. Por la definición de CVM y ser creciente en T resulta que $T(a) < T(b)$, como $\varphi$ es por hipótesis creciente en $T$, $\varphi(a) \le \varphi(b)$ para todo $a \in A$ y $b \in B$, por lo cual también se cumple que $\sup_{a \in A} \varphi(a) \le \inf_{b \in B} \varphi(b)$. Usando esto y el hecho que $\int_A (f_{\theta_2} - f_{\theta_1}) d\mu \le 0$ podremos comprobar el resultado del lema:
>>$$\begin{align*} \beta_\varphi(\theta_2) - \beta_\varphi(\theta_1) &= \int \varphi(f_{\theta_2} - f_{\theta_1}) d\mu = \int_A \varphi(f_{\theta_2} - f_{\theta_1}) d\mu + \int_B \varphi(f_{\theta_2} - f_{\theta_1}) d\mu \\ &\ge \sup_{a \in A} \varphi(a) \int_A (f_{\theta_2} - f_{\theta_1}) d\mu + \inf_{b \in B} \varphi(b) \int_B (f_{\theta_2} - f_{\theta_1}) d\mu \\ &\ge \inf_{b \in B} \varphi(b) \int_A (f_{\theta_2} - f_{\theta_1}) d\mu + \inf_{b \in B} \varphi(b) \int_B (f_{\theta_2} - f_{\theta_1}) d\mu \\ &\ge \inf_{b \in B} \varphi(b) \left( \int_A (f_{\theta_2} - f_{\theta_1}) d\mu + \int_B (f_{\theta_2} - f_{\theta_1}) d\mu \right) = \inf_{b \in B} \varphi(b) \int (f_{\theta_2} - f_{\theta_1}) d\mu = 0 \end{align*}$$
>>y $\beta_\varphi(\theta)$ es creciente en $\theta$ como se quería ver. El caso $\varphi$ decreciente en $T$ sale porque $1-\varphi$ es creciente en $T$, $\beta_{1-\varphi}(\theta) = 1-\beta_\varphi(\theta)$ es creciente en $\theta$ y por lo tanto $\beta_\varphi(\theta)$ es decreciente en $\theta$.
>>Con este resultado ya puede enunciarse como van a resultar los tests UMP-$\alpha$ en el problema de hipótesis unilaterales.

>[!Theorem]
>Supongamos que la familia de densidades $\{f_\theta: \theta \in \Theta\}$ cumple la propiedad de CVM creciente en un estadístico $T$. Sea $0 < \alpha < 1$. Sea $\theta_0 \in \Theta$ y $P_0(B) = \int_B f_{\theta_0} d\mu$.
>- (a) Sea el problema de hipótesis $H_0: \theta \le \theta_0$ vs $H_0: \theta > \theta_0$. Entonces el test $\varphi$ definido como
>$$ \varphi(x) = \begin{cases} 1 & \text{si } T(x) > k \\ \gamma & \text{si } T(x) = k \\ 0 & \text{si } T(x) < k \end{cases} \quad (2) $$
>donde $k \in [0, \infty)$ y $\gamma \in$ satisfacen
>$$ P_0(T>k) \le \alpha \le P_0(T \ge k) $$
>$$ \alpha = P_0(T>k) + \gamma P_0(T=k). $$
>es un test UMP-$\alpha$ para el problema de hipótesis.
>- (b) Sea el problema de hipótesis $H_0: \theta \ge \theta_0$ vs $H_0: \theta < \theta_0$. Entonces el test $\varphi'$ definido como
>$$ \varphi'(x) = \begin{cases} 1 & \text{si } T(x) < k' \\ \gamma' & \text{si } T(x) = k' \\ 0 & \text{si } T(x) > k' \end{cases} $$
>donde $k' \in [0, \infty)$ y $\gamma \in$ satisfacen
>$$ P_0(T < k') \le \alpha \le P_0(T \le k') $$
>$$ \alpha = P_0(T < k') + \gamma' P_0(T=k') $$
>es un test UMP-$\alpha$ para el problema de hipótesis.
>>[!Proof]-
>>(a) Como se ha hecho con los ejemplos en la clase pasada, consideremos primero el problema de hipótesis $H_0: \theta = \theta_0$ vs. $H_1: \theta = \theta_1$, que toma la forma
>>$$ \eta(x) = \begin{cases} 1 & \text{si } f_{\theta_1}(x) > k_1 f_{\theta_0}(x) \\ \gamma & \text{si } f_{\theta_1}(x) = k_1 f_{\theta_0}(x) \\ 0 & \text{si } f_{\theta_1}(x) < k_1 f_{\theta_0}(x) \end{cases} $$
>>$k_1 \ge 0$ y $\gamma \in$. Sea $L(x)$ definida en la propiedad de CVM como
>>$$ L(x) = \begin{cases} \frac{f_{\theta_1}(x)}{f_{\theta_0}(x)} & \text{si } f_{\theta_0}(x)>0 \\ \infty & \text{si } f_{\theta_0}(x)=0 \text{ y } f_{\theta_1}(x)>0 \end{cases}. $$
>>Por hipótesis $L(x) = L_{01}(T(x))$, con $L_{01}$ función creciente. Entonces, dado $k \in (-\infty, \infty)$ se cumplen las inclusiones,
>>$$ \{x: T(x) \le k\} \subset \{x: L_{01}(T(x)) \le L_{01}(k)\}, $$
>>$$ \{x: T(x) \ge k\} \subset \{x: L_{01}(T(x)) \ge L_{01}(k)\}, $$
>>o equivalentemente
>>$$ \{x: L_{01}(T(x)) > L_{01}(k)\} \subset \{x: T(x) > k\}, $$
>>$$ \{x: L_{01}(T(x)) < L_{01}(k)\} \subset \{x: T(x) < k\}, $$
>>con lo cual se tiene
>>$$ \{x: f_{\theta_1}(x) > L_{01}(k) f_{\theta_0}(x)\} \subset \{x: T(x) > k\} $$
>>$$ \{x: f_{\theta_1}(x) < L_{01}(k) f_{\theta_0}(x)\} \subset \{x: T(x) < k\}, $$
>>para todo $\theta_1 > \theta_0$. Sea $\varphi$ el test del enunciado del teorema
>>$$ \varphi(x) = \begin{cases} 1 & \text{si } T(x) > k \\ \gamma & \text{si } T(x) = k \\ 0 & \text{si } T(x) < k \end{cases} $$
>>Para poder asegurar que el test $\varphi$ tiene mejor potencia que otro test $\phi$ de nivel $\int \phi f_{\theta_0} d\mu$ (o sea, $\int \phi f_{\theta_0} d\mu \le \int \varphi f_{\theta_0} d\mu$), se debe analizar el signo de $f_1(x) - L_{01}(k)f_0(x)$ y el de $\varphi(x)-\phi(x)$: si $f_1(x) - L_{01}(k)f_0(x) > 0$ entonces $T(x)>k$ y $\varphi(x)-\phi(x) = 1-\phi(x) \ge 0$; si $f_1(x)-L_{01}(k)f_0(x)<0$ entonces $T(x)<k$ y $\varphi(x)-\phi(x)=-\phi(x) \le 0$. Con lo cual se puede concluir que
>>$$ [\varphi(x)-\phi(x)][f_{\theta_1}(x) - L_{01}(k)f_{\theta_0}(x)] \ge 0 \text{ para todo } x $$
>>y por lo tanto, como $\int[\varphi(x)-\phi(x)]f_{\theta_0}(x) d\mu \ge 0$ entonces $\int[\varphi(x)-\phi(x)]f_{\theta_1}(x)d\mu \ge 0$ cualquiera sea el test $\phi$ tal que $\int \phi f_{\theta_0} d\mu \le \int \varphi f_{\theta_0} d\mu$.
>>Entonces, eligiendo k y $\gamma$ tal que
>>$$ P_0(T(X)>k) \le \alpha \le P_0(T(X)>k) $$
>>$$ \alpha = P_0(T(X)>k) + \gamma P_0(T(X)=k) $$
>>tenemos un test UMP-$\alpha$ para $H_0: \theta = \theta_0$ vs $H_1: \theta > \theta_0$, pero el Lema 1 dice que $\beta_\varphi(\theta)$ es creciente, por lo tanto $\beta_\varphi(\theta') \le \beta_\varphi(\theta_0)$ para todo $\theta' \le \theta_0$ y $\varphi$ resulta el UMP-$\alpha$ para el problema $H_0: \theta \le \theta_0$ vs $H_1: \theta > \theta_0$.
>>(b) Sea $\psi$ el test UMP-($1-\alpha$) encontrado en (a) para el problema de hipótesis $H_0: \theta \le \theta_0$ vs $H_1: \theta > \theta_0$. Entonces el test $\varphi' = 1-\psi$ es un test UMP-$\alpha$ para el problema de hipótesis $H_0: \theta \ge \theta_0$ vs $H_1: \theta < \theta_0$.
