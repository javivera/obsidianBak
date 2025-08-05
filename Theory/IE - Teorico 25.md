>[!Remark]
>Entonces la convención es mantener el ET I bajo control, por lo tanto como se eligen las hip. nula y alternativa en el problema particular que estemos analizando. Es una decisión en términos de lo que se considere el interés en el fenómeno bajo estudio. Veamos el siguiente ejemplo.

>[!Example]
>Supongamos que estudiamos una nueva droga que deseamos saber si aumenta la tasa de recuperación resp. de tratamientos anteriores. Supongamos que de la experiencia con las drogas anteriores, la tasa de recuperación es $\theta_0 = 0.3$.
>El científico que descubre la nueva droga quiere minimizar el error de decir que la nueva droga es mejor cuando eso no ocurre (1) .
>Hay dos posibles errores que uno puede cometer:
>- "Decir que la nueva droga es mejor que la anterior cuando esto no ocurre"
>- "Decir que la nueva droga es igual que las anteriores cuando esto no ocurre"
>
>Equivalentemente:
>- Decir que $\theta > 0.3$ cuando $\theta = 0.3$ (2)
>- Decir que $\theta = 0.3$ cuando $\theta > 0.3$
>
>En términos del interés del científico (1) , entonces lo que planteamos como problema de hipótesis es:
>$$H_0: \theta=0.3\ \text{ vs }\ H_1: \theta>0.3$$
>que es equivalente a rechazar $H_0$ (decir que $\theta > 0.3$) siendo $H_0$ verdadera (2) (o sea cdo la nueva droga no es más eficiente).
>
>Se realiza entonces una experiencia donde se toma una muestra aleatoria de la población enferma, donde se administra la nueva droga. Se obtiene una muestra $X=(X_1, \dots, X_n)^t$ donde $X_i \sim Bi(1, \theta)$, $i=1, \dots, n$ independientes. Sea $S = \sum_{i=1}^n X_i$ el número de pacientes recuperados con la nueva droga, $S \sim Bi(n, \theta)$. 
>Para plantear una región de rechazo para construir el test, observamos que la f.d.a de $S$, $P_\theta(S \le k) = F_\theta(k)$ es decreciente en $\theta \in (0,1)$ para cada $k$ fijado. (es un resultado que se puede probar).
>Luego, $S$ tiende a producir valores más grandes a medida que $\theta$ crece, con lo cual podríamos decir: Rechazar $H_0$ si $S$ es más "grande" de lo que hubieramos esperado por azar si $H_0: \theta=0.3$ es verdadera. Entonces la región de rechazo resultaría: $$C = \{x\in \Omega_{X}: S(x) > k\}$$, con $k$ a determinar, y el test resultaría:
>$$ \varphi(x) = I_{\{k, k+1, \dots, n\}}(S)= \begin{cases} 1 & \text{si } x \in C \\ 0 & \text{si } x \notin C \end{cases} $$
>$k$ se determina usando la condición de nivel $\alpha$:
>$$ \beta_\varphi(\theta_0) =\sup_{P\in \mathcal{P}_{0}}E_{P}(\varphi(x))= E_{\theta_0}[\varphi] = P_{\theta_0}(S > k) \le \alpha $$
>(supremo se simplifica por que hay un solo elemento en el conjunto $\mathcal{P}_{0}$) 
>La idea es determinar "$k$" de forma que $P_{\theta_0}(S > k)$ sea "chico" (porque entonces es "chico" el ETI que queremos controlar).
>
>Para fijar ideas, supongamos en nuestro caso que $n=10$ y $\theta_0=0.3$
>Al buscar en tablas o con un paquete estadístico vemos por ejemplo que
>Tomando $k=5$ resulta que
>$$ P_{0.3}(S > 5) = 0.0473 $$
>En este caso, como $\mathcal{P}_0 = \{P_{0.3}\}$, el supremo se alcanza en el único elemento del conjunto:
>$$ \sup_{P \in \mathcal{P}_0} E_P[\varphi(X)] = E_{0.3}[\varphi(\underline{X})] = P_{0.3}(S > 5) $$
>"$k$" recibe el nombre de **valor crítico**. Luego, el test es definido por
>$$ \varphi(X_1, \dots, X_n) = \begin{cases} 1 & \text{si } S > 5 \\ 0 & \text{si } S \le 5 \end{cases} $$
>y $\{S > 5\}$ es la **región crítica**, produce un test de tamaño $0.0473$.
>
>Ademas Notar
>![[Pasted image 20250726164154.png]]
>Que la función de potencia $\beta_\varphi(\theta)$ tienda a 1 a medida que $\theta$ crece a 1 es una buena propiedad del test.
>Si nos fijamos en nuestro ejemplo, el test construido se basó en el estadístico $S$, el cual recibe el nombre de **estadístico del test**.

>[!Remark]
>Vayamos ahora al caso más sencillo posible de plantear:
>$$ H_0: \mathcal{P}_0 = \{P_0\} \quad \text{vs} \quad H_1: \mathcal{P}_1 = \{P_1\} $$
>(el caso de **"hipótesis simples"**).
>
>La pregunta que queremos resolver es:
>Dado $\alpha < 1$, ¿podemos encontrar un test $\varphi$ de tamaño $\alpha$ tal que su potencia en $P_1$ sea mayor o igual que la potencia de cualquier otro test con nivel de significación $\alpha$?

>[!Definition] Test MP
>Un test $\varphi$ para el problema $H_0: \mathcal{P}_0=\{P_0\}$ vs $H_1: \mathcal{P}_1=\{P_1\}$ se dice **más potente (MP)** de tamaño $\alpha$ si
>- i) $\beta_\varphi(P_0) = \alpha$ 
>- ii) Para todo test $\varphi'$ tal que $\beta_{\varphi'}(P_0) \le \alpha$, se tiene que $\beta_{\varphi'}(P_1) \le \beta_\varphi(P_1)$.
>Osea es de tamaño $\alpha$ (por que es supremo de un conjunto de un solo elemento) y es el de mayor potencia en distribuciones alternativas entre todos los test de tamaño menores o iguales a $\alpha$ 

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

>[!Lemma] Neyman-Pearson I
>Sean $f_0$ y $f_1$ las densidades de $P_0$ y $P_1$ respecto de una medida $\mu$. Entonces, para cada función $0 \le \gamma(x) \le 1$ y constante $k \ge 0$ se puede definir un test $\varphi: \Omega_X \to$ como
>$$ \varphi(x) = \begin{cases} 1 & \text{si } f_1(x) > k f_0(x) \\ \gamma(x) & \text{si } f_1(x) = k f_0(x) \\ 0 & \text{si } f_1(x) < k f_0(x) \end{cases} $$
>el cual resulta el MP de tamaño $\int \varphi f_0 d\mu$.
>>[!Proof]-
>>1. Si $\varphi'$ es otro test de nivel $\int \varphi' f_0 d\mu \le \int \varphi f_0 d\mu$, veamos que la potencia de $\varphi$ es mejor que la de $\varphi'$, esto es, $\int \varphi f_1 d\mu \ge \int \varphi' f_1 d\mu$. Como $\varphi'$ es un test, entonces por la definición de $\varphi$ resulta que
>>$$ [\varphi(x) - \varphi'(x)][f_1(x) - k f_0(x)] \ge 0 \text{ para todo } x. $$
>>2.  Entonces
>>$$\begin{align*} 0 &\le \int [\varphi(x) - \varphi'(x)][f_1(x) - k f_0(x)] d\mu \\ &= \int (\varphi(x) - \varphi'(x)) f_1(x) d\mu - k \int (\varphi(x) - \varphi'(x)) f_0(x) d\mu \end{align*}$$
>>3. Como $\varphi'$ es de nivel $\alpha$, entonces $\int \varphi' f_0 d\mu \le \int \varphi f_0 d\mu$ y, $\int (\varphi(x) - \varphi'(x)) f_0(x) d\mu \ge 0$, 
>>4. por lo tanto $\int [\varphi(x) - \varphi'(x)] f_1(x) d\mu \ge 0$ y luego, se obtiene lo que se deseaba ver,
>>$$ \int \varphi'(x) f_1(x) d\mu \le \int \varphi(x) f_1(x) d\mu. $$

^e3d94e

>[!Remark]
>Al cambiar $\gamma$ y $k$ siempre obtenemos un test MP, pero de tamaño $\int \varphi f_0 d\mu$.
>La intuición de lo que hace el test es clara en el caso discreto: el test toma el valor 1 (o sea, rechaza $H_0$) cuando la probabilidad de observar $x$ bajo la alternativa $H_{1}$  ($f_1(x)$) es $k$ veces mayor que la probabilidad de observar $x$ bajo la nula $H_0$ $(f_0(x))$.

>[!Remark]
>¿Pero cómo hacemos para deducir el MP de tamaño $\alpha$ deseado?
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
>>[!Proof]-
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

>[!Lemma] Neyman-Pearson II
>Para cualquier $0 < \alpha < 1$, existe un test $\varphi: \Omega_X \to$ de tamaño $\alpha$ de la forma dada en (1), con $\gamma(x) = \gamma$ (constante) y $k \in [0, \infty)$, satisfaciendo:
>$$ P_0(f_1 > k f_0) \le \alpha \le P_0(f_1 \ge k f_0) $$
>$$ \alpha =E_{P_{0}}(\varphi(X))= \int \varphi f_0 d\mu = P_0(f_1 > k f_0) + \gamma P_0(f_1 = k f_0) $$
>Más aún, si $\varphi'$ es un test MP de tamaño $0 < \alpha \le 1$, entonces debe coincidir (a exepcion de en el borde $f_{1}(x)=kf_{0}(x)$, es como si en ese borde fuera inconcluso si rechazar o no y cualquier estartegia serviria para un test de optimalidad) con el test $\varphi$ de Neyman-Pearson salvo conjuntos de probabilidad cero, o sea:
>$$ P_0(\varphi \ne \varphi', f_1 \ne k f_0) = 0 $$
>$$ P_1(\varphi \ne \varphi', f_1 \ne k f_0) = 0 $$

^2f1e3c

>[!Remark]
>Neyman-Pearson no especifica $\gamma(x)$, y si $\varphi = \varphi'$ en el conjunto $\{f_1 = k f_0\}$, realmente coinciden en todas partes salvo conjuntos de probabilidad cero.
