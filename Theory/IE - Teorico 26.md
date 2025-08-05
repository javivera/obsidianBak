>[!Remark]
>¿Cuando no podemos plantear procedimientos óptimos, qué podemos hacer?
>Sea $X=(X_1, ..., X_n)^{T}$ el vector aleatorio con densidad o probabilidad puntual $p(x, \theta)$ y se desea testear
>$$ H_0: \theta \in \Theta_0 \quad \text{vs} \quad H_1: \theta \in \Theta_1 $$
>donde $\Theta = \Theta_0 \cup \Theta_1$, $\Theta_0 \cap \Theta_1 = \emptyset$ y $\Theta \subseteq \mathbb{R}^k$.
>Tomando la idea de lo que hace el test de Neyman-Pearson, se toma el **cociente de verosimilitud**:
>$$ L(x) = \frac{\sup\{p(x, \theta) : \theta \in \Theta_1\}}{\sup\{p(x, \theta) : \theta \in \Theta_0\}} $$
>La idea es que si $\sup_{\theta \in \Theta_1} \{p(x,\theta)\}$ es "grande" respecto de $\sup_{\theta \in \Theta_0} \{p(x,\theta)\}$, entonces la muestra $x$ está mejor explicada por algún $\theta \in \Theta_1$, y entonces rechazamos $H_0$.
>Entonces se llama **test de cociente de verosimilitud** a un test de la forma:
>$$ \varphi(x) = \begin{cases} 1 & \text{si } L(x) > k \\ \gamma & \text{si } L(x) = k \\ 0 & \text{si } L(x) < k \end{cases} $$
>donde $\gamma$ y $k$ se determinan por el nivel de significación deseado $\alpha$:
>$$ \alpha = \sup_{\theta \in \Theta_0} E_\theta[\varphi(X)] $$
>Supongamos que planteamos una idea relacionada, que es comparar la máxima verosimilitud en todo el espacio de parámetros con la máxima verosimilitud bajo la hipótesis nula. Definimos el estadístico:
>$$ \lambda(x) = \frac{\sup_{\theta \in \Theta} \{p(x,\theta)\}}{\sup_{\theta \in \Theta_0} \{p(x,\theta)\}} $$
>Podemos reescribir el numerador, ya que $\Theta = \Theta_0 \cup \Theta_1$:
>$$ \sup_{\theta \in \Theta} \{p(x,\theta)\} = \max \left( \sup_{\theta \in \Theta_0} \{p(x,\theta)\}, \sup_{\theta \in \Theta_1} \{p(x,\theta)\} \right) $$
>Sustituyendo en la expresión de $\lambda(x)$:
>$$\begin{align*} \lambda(x) &= \frac{\max \left( \sup_{\theta \in \Theta_0} \{p(x,\theta)\}, \sup_{\theta \in \Theta_1} \{p(x,\theta)\} \right)}{\sup_{\theta \in \Theta_0} \{p(x,\theta)\}} \\ &= \max \left( \frac{\sup_{\theta \in \Theta_0} \{p(x,\theta)\}}{\sup_{\theta \in \Theta_0} \{p(x,\theta)\}}, \frac{\sup_{\theta \in \Theta_1} \{p(x,\theta)\}}{\sup_{\theta \in \Theta_0} \{p(x,\theta)\}} \right) \\ &= \max(1, L(x)) \end{align*}$$

>[!Remark]
>Como muchas veces es más sencillo buscar el sup en todo el conjunto de parámetros $\Theta$ que en $\Theta_1$, entonces se usa esta modificación del cociente de verosimilitud, y con eso construir los tests de cociente de verosimilitud. A partir de ahora trabajaremos en esta modificación y para construir el test operamos del siguiente modo.
>
> **PASOS PARA CONSTRUIR TEST de C.V.**
> - a) Construir el EMV $\hat{\theta}$ de $\theta \in \Theta$.
> - b) Construir el EMV $\hat{\theta}_0$ de $\theta \in \Theta_0$.
> - c) Calcular $\lambda(x) = \frac{p(x, \hat{\theta})}{p(x, \hat{\theta}_0)}$.
> - d) Encontrar una función $h$ estrictamente creciente sobre la imagen de $\lambda$ tal que $h(\lambda(X))$ tiene una distribución reconocible bajo $H_0$ y poder armar la regla de rechazo: rechazar $H_0$ si $h(\lambda(X)) > d_0$, donde $d_0$ se elige tal que $P(h(\lambda(X)) > d_0) = \alpha$ para poder lograr el tamaño deseado $\alpha$.

>[!Example]
>Sea $X_1, ..., X_n$ una muestra aleatoria i.i.d. tal que $X_i \sim N(\mu, \sigma^2)$, con $\mu, \sigma^2$ desconocidos. El parámetro es $\theta = (\mu, \sigma^2)$. La densidad conjunta es:
> $$ p(x, \theta) = \frac{1}{(2\pi\sigma^2)^{n/2}} \exp\left(-\frac{1}{2} \sum_{i=1}^n \left(\frac{x_i - \mu}{\sigma}\right)^2\right) $$
> Supongamos que queremos testear el problema:
> $$ H_0: \mu = \mu_0 \quad \text{vs} \quad H_1: \mu \ne \mu_0 $$
>Los espacios de parámetros son:
> $$ \Theta = \{(\mu, \sigma^2): \mu \in \mathbb{R}, \sigma > 0\} $$
> $$ \Theta_0 = \{(\mu, \sigma^2): \mu=\mu_0, \sigma > 0\} $$
> - a) En $\Theta$, el EMV para $\theta = (\mu, \sigma^2)$ es $\hat{\theta} = (\hat{\mu}, \hat{\sigma}^2)$, donde:
> $$ \hat{\mu} = \frac{1}{n} \sum_{i=1}^n X_i = \bar{X} \quad \text{y} \quad \hat{\sigma}^2 = \frac{1}{n} \sum_{i=1}^n (X_i - \bar{X})^2 $$
> - b) En $\Theta_0$, el EMV para $\sigma^2$ resulta:
> $$ \hat{\sigma}_0^2 = \frac{1}{n} \sum_{i=1}^n (X_i - \mu_0)^2 $$
> - c) El cociente de verosimilitud generalizado es:
> $$ \hat{\lambda}(x) = \frac{p(x, \hat{\theta})}{p(x, \hat{\theta}_0)} = \frac{\frac{1}{(2\pi\hat{\sigma}^2)^{n/2}} \exp\left(-\frac{1}{2\hat{\sigma}^2} \sum_{i=1}^n (x_i - \overline{X} )^2\right)}{\frac{1}{(2\pi\hat{\sigma}_0^2)^{n/2}} \exp\left(-\frac{1}{2\hat{\sigma}_0^2} \sum_{i=1}^n (x_i - \mu_0)^2\right)} $$
> Como $\sum(x_i-\overline{X})^2 = n\hat{\sigma}^2$ y $\sum(x_i-\mu_0)^2 = n\hat{\sigma}_0^2$, los términos exponenciales se simplifican a $e^{-n/2}$, y queda:
> $$ \hat{\lambda}(x) = \left( \frac{\hat{\sigma}_0^2}{\hat{\sigma}^2} \right)^{n/2} $$
> - d) Este paso pide reconocer una función $h$ tal que $h(\lambda(X))$ tenga una distribución reconocible bajo $H_0$. Tomemos el logaritmo de $\lambda(X)$:
> $$ \log(\lambda(X)) = \frac{n}{2} \log\left(\frac{\hat{\sigma}_0^2}{\hat{\sigma}^2}\right) $$
>Luego $$\begin{align*} \hat{\sigma}^2 &= \frac{1}{n} \sum_{i=1}^n (X_i - \mu_0)^2 = \frac{1}{n} \sum_{i=1}^n (X_i - \mu _{0}+\mu _{0} - \overline{X_{n}} )^2 \\ &= \frac{1}{n} \sum_{i=1}^n (X_i - \mu _{0})^2 + 2(\mu_0-\overline{X}_{n} )\frac{1}{n}\sum_{i=1}^n(X_i-\mu_{0}) + (\mu_0-\overline{X_{n}} )^2 \\ &= \hat{\sigma}^2  - (\mu_0-\overline{X}_{n} )^2 \end{align*}$$
>$$\begin{align}\hat{\sigma}_{0}^2 &=\frac{1}{n} \sum_{i=1}^n (X_i - \bar{X} + \bar{X} - \mu_0)^2 \\ & = \frac{1}{n} \sum_{i=1}^n [(X_i - \bar{X})^2 + 2(X_i - \bar{X})(\bar{X} - \mu_0) + (\bar{X} - \mu_0)^2] \\&= \frac{1}{n} \sum_{i=1}^n (X_i - \bar{X})^2 + 2(\bar{X} - \mu_0)\frac{1}{n}\sum_{i=1}^n(X_i - \bar{X}) + (\bar{X} - \mu_0)^2\\&=\frac{1}{n} \sum_{i=1}^n (X_i - \bar{X})^2 +  (\bar{X} - \mu_0)^2\\&=\hat{\sigma}^{2}+(\overline{X} -\mu _{0})^{2}\end{align}$$  
>Entonces $$ \frac{\hat{\sigma}_0^2}{\hat{\sigma}^2} = 1 + \frac{(\overline{X} -\mu_0)^{2} }{\hat{\sigma}^2}$$
> ¿El término $\frac{(\bar{X}-\mu_0)^2}{\hat{\sigma}^2}$ está relacionado con una distribución conocida bajo $H_0$? ¡Sí!
>Bajo $H_0$, $E[X_i]=\mu_0$, entonces:
>$$ \frac{n(\bar{X}_n - \mu_0)^2}{S^2} \sim F_{1, n-1} $$
>donde $S^2 = \frac{1}{n-1}\sum_{i=1}^n(X_i - \bar{X})^2$.
>Si denotamos $f_{m_1, m_2, 1-\alpha}$ al valor tal que $P(W \ge f_{m_1, m_2, 1-\alpha}) = \alpha$ cuando $W \sim F_{m_1, m_2}$.
>El estadístico del cociente de verosimilitud $\hat{\lambda}$ es una función estrictamente creciente del estadístico F:
>$$\hat{\lambda} = \left(\frac{\hat{\sigma}_0^2}{\hat{\sigma}^2}\right)^{n/2} = \left(1 + \frac{(\bar{X}_n-\mu_0)^2}{\hat{\sigma}^2}\right)^{n/2} = \left(1 + \frac{n-1}{n} \frac{n(\bar{X}_n-\mu_0)^2}{S^2}\right)^{n/2} $$
>Luego, el test resulta:
>$$ \varphi_1(X) = \begin{cases} 1 & \text{si } \lambda(X) > \tilde{\lambda} \\ 0 & \text{si } \lambda(X) \le \tilde{\lambda} \end{cases} $$
>(El renglón del caso de igualdad se puede pasar al de no rechazo porque tenemos una distribución continua).
>Y esto es equivalente a:
>$$ \varphi(X) = \begin{cases} 1 & \text{si } \frac{n(\bar{X}_n-\mu_0)^2}{S^2} > f_{1, n-1, 1-\alpha} \\ 0 & \text{si } \frac{n(\bar{X}_n-\mu_0)^2}{S^2} \le f_{1, n-1, 1-\alpha} \end{cases} $$

>[!Example]
>Calcular el test de cociente de verosimilitud para el caso en que $\sigma^2$ es conocido para el problema:
>$H_0: \mu = \mu_0 \quad \text{vs} \quad H_1: \mu \ne \mu_0$.
>Concluir que el test es equivalente a:
>$$ \varphi(X_1, ..., X_n) = \begin{cases} 1 & \text{si } \left|\frac{\sqrt{n}(\bar{X}_n - \mu_0)}{\sigma}\right| > z_{1-\alpha/2} \\ 0 & \text{en caso contrario} \end{cases} $$
>donde $z_\gamma$ es el cuantil de orden $\gamma$ de la distribución normal estándar, es decir, $P(Z \le z_\gamma)=\gamma$ si $Z \sim N(0,1)$.
>Por la simetría de la normal, se cumple que $-z_{1-\alpha/2} = z_{\alpha/2}$.
>Entonces, la región de rechazo también se puede escribir como:
>$$ \frac{\sqrt{n}(\bar{X}_n - \mu_0)}{\sigma} < z_{\alpha/2} \quad \text{o} \quad \frac{\sqrt{n}(\bar{X}_n - \mu_0)}{\sigma} > z_{1-\alpha/2} $$
>(O sea, lo que estamos diciendo es que rechazamos $H_0$ si la media muestral estandarizada toma valores muy grandes, ya sea negativa o positivamente).

>[!Example]
>Para el caso de $\sigma^2$ conocido, calcular la función de potencia y comprobar que:
>La función de potencia es:
>$$\beta_\varphi(\mu) = E_\mu[\varphi] = P_\mu\left(\left|\frac{\sqrt{n}(\bar{X}_n - \mu_0)}{\sigma}\right| > z_{1-\alpha/2}\right) $$
>Si $\mu=\mu_0, \quad \beta_\varphi(\mu_0) = \alpha$ y si $\mu \ne \mu_0$ comprobar que $$\beta_\varphi(\mu) = \Phi\left(z_{\alpha/2} - \frac{\sqrt{n}(\mu-\mu_0)}{\sigma}\right) + \Phi\left(-z_{\alpha/2} - \frac{\sqrt{n}(\mu-\mu_0)}{\sigma}\right)$$
> - Si $\mu < \mu_0$, $\beta_\varphi(\mu)$ es decreciente.
> - Si $\mu > \mu_0$, $\beta_\varphi(\mu)$ es creciente.
>Luego $$ \lim_{\mu \to \infty} \beta_\varphi(\mu) = 1 = \lim_{\mu \to -\infty} \beta_\varphi(\mu) $$
>
>Esto se puede visualizar en el siguiente gráfico, donde se muestra la función de potencia $\beta_\varphi(\mu)$ y el error de tipo II, $ETII(\mu) = 1 - \beta_\varphi(\mu)$.
>![[Pasted image 20250802222214.png]]
>Aunque veamos que el Error de Tipo II es alto para valores de $\mu$ cercanos a $\mu_0$, en este mismo ejemplo podemos comprobar que si tomamos un tamaño muestral $n$ suficientemente grande, para una hipótesis alternativa particular, podemos controlar el Error de Tipo II.
>Tomemos un valor de potencia deseado $\beta \in (\alpha, 1)$ y fijemos una hipótesis alternativa $\mu = \mu_1 \ne \mu_0$.
>Si $\beta > \alpha$ entonces $\beta - \frac{\alpha}{2} > \frac{\alpha}{2}$ luego como la f.d.a. $\Phi$ de la normal estándar es estrictamente creciente, su inversa $\Phi^{-1}$ también lo es, por lo tanto:
>$$ \Phi^{-1}\left(\beta - \frac{\alpha}{2}\right) > \Phi^{-1}\left(\frac{\alpha}{2}\right) = z_{\alpha/2} $$
>¿Podemos elegir un tamaño de muestra $n$ tal que la potencia en $\mu_1$ sea al menos $\beta$, es decir, $\beta_\varphi(\mu_1) \ge \beta$? (y por lo tanto tendriamos ETII chico)
>
>La inecuación a resolver es:
>$$ \begin{align}\beta \le \beta_\varphi(\mu_1) &= \Phi\left(z_{\alpha/2} - \frac{\sqrt{n}(\mu_1-\mu_0)}{\sigma}\right) + \Phi\left(z_{\alpha/2} - \frac{\sqrt{n}(\mu_1-\mu_0)}{\sigma}\right) \\ &=  \begin{cases}\Phi(z_{\alpha /2})+\Phi\left(z_{\alpha/2} - \frac{\sqrt{n}(\mu_1-\mu_0)}{\sigma}\right) & \text{si } \mu_1 <\mu_0 \\ \Phi(z_{\alpha /2})+ \Phi\left(z_{\alpha/2} +\frac{\sqrt{n}(\mu_1-\mu_0)}{\sigma}\right) & \text{si } \mu_1 > \mu_0 \end{cases} \end{align}$$
>Si despejamos $n$ en la desigualdad que hemos obtenido, podemos derivar que:
>$$ n \ge \left( \frac{\Phi^{-1}\left (\beta-\alpha/2)\right) - z_{\alpha/2}}{\frac{|\mu_1 - \mu_0|}{\sigma}} \right)^2 $$
>Con este tamaño muestral, en una alternativa particular $\mu_1$, controlamos el Error de Tipo II.

>[!Remark] P-valor o probabilidad de significancia
>Un concepto más, el **p-valor** o **probabilidad de significancia** del test.
>Supongamos que en el problema de hipótesis planteado
>$$ H_0: \theta \in \Theta_0 \quad \text{vs} \quad H_1: \theta \in \Theta_1 $$
>obtenemos un test del tipo:
>$$ \varphi(x) = \begin{cases} 1 & \text{si } T(x) \ge c \\ 0 & \text{si } T(x) < c \end{cases} $$
>Con $x=(x_{1},\ldots,x_{n})$ muestra. 
>El tamaño del test se definía como:
>$$ \alpha(c) = \sup_{\theta \in \Theta_0} P_\theta(T(X) \ge c) \quad \text{(decreciente en c)} $$
>Vamos a definir como **p-valor** al menor nivel de significación para el cual un experimentador, usando el estadístico $T$ para el problema de hipótesis planteado, rechazaría $H_0$ sobre la base del resultado observado $x$.
>O sea, observamos $T(x)$ rechazamos $H_0$ si y sólo si $c \le T(x)$ entonces ¿Hasta dónde podríamos agrandar el valor crítico $c$ para rechazar $H_0$? Hasta $T(x)$.
>$$\alpha(T(x))=\sup_{\theta\in \Theta_{0}}P_{\theta}(T(x)\geq T(x))$$
>(Es el valor más pequeño de $\alpha$ para el cual rechazaríamos $H_0$ habiendo observado $T(x)$).
>El p-valor depende del valor de $T(x)$, por lo tanto, es aleatorio y puede cambiar con el valor observado. 
>¿Se puede decir algo de la distribución del p-valor? la respuesta es sí

>[!Lemma]
>Si $H_0: \theta = \theta_0$ y el estadístico $T(X)$ tiene una distribución continua con densidad entonces el p-valor $\alpha(T(X))$ sigue una distribución uniforme
>$$ \alpha(T(X)) \sim \mathcal{U}(0,1) $$

## Intervalos, regiones y cotas de confianza

>[!Remark]
>Supongamos que tenemos el parámetro $\nu = \nu(P) \in \mathbb{R}$, y $P \in \mathcal{P}$.
>Si $X \sim P$ y $X \in \mathbb{R}^q$ es un vector aleatorio, quisiéramos "atrapar" el parámetro con alta probabilidad.

>[!Definition]
>Un estadístico $\underline{\nu}(X)$ se dice una **cota de confianza inferior** para $\nu$ de **nivel $1-\alpha$** si para todo $P \in \mathcal{P}$ se cumple:
>$$ P(\underline{\nu}(X) \le \nu(P)) \ge 1-\alpha $$
>o bien,
>$$ P\left(\nu(P) \in [\ \underline{\nu}(X), \infty)\right) \ge 1-\alpha $$
>
>Igualmente, si tenemos el estadístico $\bar{\nu}(X)$, se dice una **cota de confianza superior** para $\nu(P)$ de nivel $1-\alpha$ si para todo $P \in \mathcal{P}$ se cumple:
>$$ P(\bar{\nu}(X) \ge \nu(P)) \ge 1-\alpha $$
>o bien,
>$$ P\big(\nu(P) \in (-\infty, \bar{\nu}(X)]\big) \ge 1-\alpha $$
>Un intervalo aleatorio $[\underline{\nu}(X), \bar{\nu}(X)]$ es un **intervalo de confianza** para $\nu$ de **nivel $1-\alpha$** si para todo $P \in \mathcal{P}$ se cumple que:
>$$ P(\underline{\nu}(X) \le \nu(P) \le \bar{\nu}(X)) \ge 1-\alpha $$
>Esta es la **probabilidad de cubrimiento**. Ademas $1-\alpha$ es el **nivel de confianza**.
>Como cualquier valor por debajo de $1-\alpha$ es un nivel de confianza, se define el **coeficiente de confianza** como:
>$$ \inf_{P \in \mathcal{P}} P(\underline{\nu}(X) \le \nu(P) \le \bar{\nu}(X)) $$
>(O sea, el nivel de confianza más grande posible).

>[!Example]
>Sea $X_1, \dots, X_n$ una muestra aleatoria i.i.d. de $N(\mu, \sigma^2)$, con $(\mu, \sigma^2)$ desconocidos.
>Si $$S = \sqrt{\frac{1}{n-1}\sum_{i=1}^n(X_i-\bar{X})^2}$$ (la desviación estándar muestral)
>$$ T_n = \frac{\sqrt{n}(\bar{X}_n - \mu)}{S} \sim t_{n-1} $$
>$$ C_n = \frac{\sum_{i=1}^n (X_i - \bar{X})^2}{\sigma^2} = \frac{(n-1)S^2}{\sigma^2} \sim \chi^2_{n-1} $$
>
>$T_n$ y $C_n$ dependen de la muestra y de los parámetros, pero sus distribuciones **no dependen de parámetros desconocidos**.
>Tales funciones se denominan **pivotes**.
>
>Si $T \sim t_m$, denotamos $t_{m,\gamma}$ al valor tal que $P(T \le t_{m,\gamma}) = \gamma$.
>Si $C \sim \chi^2_m$, denotamos $\chi^2_{m,\gamma}$ al valor tal que $P(C \le \chi^2_{m,\gamma}) = \gamma$.
>Si $W \sim F_{n,m}$, denotamos $f_{n,m,\gamma}$ al valor tal que $P(W \le f_{n,m,\gamma}) = \gamma$.
>
>(Los valores $t_{m,\gamma}, \chi^2_{m,\gamma}, f_{n,m,\gamma}$ se denominan **percentiles** de la distribución correspondiente).
>![[Pasted image 20250802231758.png]]
>$$P(t_{n-1,\gamma}\leq T_{n}\leq t_{n-1,1-\beta })=1-\alpha \quad (*)$$
>![[Pasted image 20250802231909.png]]
>$$ P(\chi^2_{n-1, \alpha/2} \le C_n \le \chi^2_{n-1, 1-\beta }) = 1-\alpha \quad (**)$$
>Luego 
>$$\begin{align}[t_{n-1, \alpha/2} \le T_n \le t_{n-1, 1-\alpha/2}]&\iff t_{n-1,\gamma}\leq \frac{\sqrt{ n }(T_{n}-\mu )}{S}\leq t_{n-1,1-\beta }\\&\iff \overline{X_{n}} -\frac{S}{\sqrt{ n }}t_{n-1,1-\beta }\leq \mu\leq \overline{X_{n}} +\frac{S}{\sqrt{ n }}t_{n-1,\gamma}\end{align}$$
>Entonces $$1-\alpha =P\left( \mu \in \left[ \overline{X_{n}}-\frac{S}{\sqrt{ n }} t_{n-1,1-\beta},\overline{X_{n}}-\frac{S}{\sqrt{ n }}t_{n-1,\gamma}\right] \right)$$
>
>Para el caso de $\sigma^2$, despejamos igualmente en $(**)$ obtenemos el intervalo de confianza:
>$$ 1-\alpha = P\left( \sigma^2 \in \left[ \frac{\sum_{i=1}^n(X_i-\bar{X})^2}{\chi^2_{n-1, 1-\beta}}, \frac{\sum_{i=1}^n(X_i-\bar{X})^2}{\chi^2_{n-1, \gamma}} \right] \right) $$
>Si tomamos $\gamma = \beta = \alpha/2$ (dejando la misma área en cada lado y usando la simetria de $t_{n-1}$
>![[Pasted image 20250803121045.png]]
>$$\begin{align}1-\alpha & = P\left(\mu \in \left[\bar{X}_n - \frac{S}{\sqrt{n}}t_{n-1, 1-\alpha/2}, \bar{X}_n - \frac{S}{\sqrt{n}}t_{n-1, \alpha/2}\right]\right) \\&= P\left(\mu \in \left[\bar{X}_n - \frac{S}{\sqrt{n}}t_{n-1, 1-\alpha/2}, \bar{X}_n + \frac{S}{\sqrt{n}}t_{n-1, 1-\alpha/2}\right]\right)\end{align} $$
>El ulitmo igual es por que la distribución t de Student es simétrica, $t_{n-1, \alpha/2} = -t_{n-1, 1-\alpha/2}$, entonces:
>Podemos definir entonces la **longitud del intervalo** como la diferencia de sus extremos. En el caso del intervalo de confianza para $\mu$:
>$$ L(IC) = \frac{S}{\sqrt{n}}(t_{n-1, 1-\beta} - t_{n-1, \gamma}) $$
>¿Se pueden elegir $\beta$ y $\gamma$ de forma que la longitud esperada del intervalo de confianza, $E[L(IC)]=k(t_{n-1,1-\beta}-t_{n-1,\gamma})$, sea mínima?
>**Respuesta:** Sí, tomando $\beta = \gamma = \alpha/2$.

>[!Example] ejercicio
>Comprobar la respuesta.

>[!Example]
>(Donde obtenemos Intervalos de Confianza "aproximados")
>Sean $X_1, ..., X_n$ una muestra aleatoria i.i.d. tal que $X_i \sim Bi(1, \theta)$.
>Entonces $\sum_{i=1}^n X_i \sim Bi(n, \theta)$. El estimador de máxima verosimilitud de $\theta$ es $\bar{X}_n = \frac{1}{n} \sum_{i=1}^n X_i$.
>No sabemos reconocer pivotes como en el ejemplo anterior. Usando el Teorema Central del Límite (TCL):
>$$ \frac{\sqrt{n}(\bar{X}_n - \theta)}{\sqrt{\theta(1-\theta)}} \xrightarrow{\mathcal{D}} N(0,1) $$
>o sea,
>$$ P\left(\frac{\sqrt{n}(\bar{X}_n - \theta)}{\sqrt{\theta(1-\theta)}} \le t\right) \xrightarrow[n \to \infty]{} \Phi(t) \quad \forall t \in \mathbb{R} $$
>Como la distribución límite NO depende del parámetro desconocido, vamos a usar este **pivote** aproximado. Entonces podemos decir
>$$P\left( z_{\alpha /2}\leq \sqrt{ n }\frac{\overline{X_{n}} -\theta}{\sqrt{ \theta(1-\theta) }} \leq z_{1-\alpha /2}\right)\approx 1-\alpha $$
>y notar $z_{\alpha /2}=-z_{1-\alpha /2}$ por simetria de la $N(0,1)$
>Si $n$ es suficientemente grande, usando el TCL. Vamos a despejar $\theta$ para poder encontrar un $IC$ de nivel "aproximado" $1-\alpha$, por que usamos el TC
>Vamos a despejar $\theta$ de la desigualdad. Elevando al cuadrado:
>$$\begin{align}\left|\sqrt{ n }\frac{(\overline{X_{n}} -\theta)}{\sqrt{ \theta(1-\theta) }}\right|^{2}\leq z^{2}& \iff n(\bar{X}_n - \theta)^2 \le z^2 \theta(1-\theta) \\ &\iff \left(1 + \frac{z^2}{n}\right)\theta^2 - \left(2\bar{X}_n + \frac{z^2}{n}\right)\theta + \bar{X}_n^2 \le 0 \\& \iff  \theta \in [\underline{\theta}(X), \bar{\theta}(X)] \end{align}$$
>![[Pasted image 20250803123520.png]]
>Encontrar entonces las raíces del polinomio nos da el intervalo de confianza:
>$$ P(\theta \in [\underline{\theta}(X), \bar{\theta}(X)]) \approx 1-\alpha $$
>si $n$ es suficientemente grande (por el TCL).
>(Se dice un **Intervalo de Confianza para $\theta$ de nivel aproximado $1-\alpha$**).

## Dualidad entre regiones de confianza y tests

>[!Remark]
>Sea $X \in \Omega_X \subseteq \mathbb{R}^q$ un vector aleatorio, $X \sim P \in \mathcal{P}$. 
>$\mathcal{P} = \{P_\nu\}_{\nu \in \Gamma}$, y queremos estimar el parámetro $\nu: \mathcal{P} \to \mathcal{V}$.
>Tomemos una función $S: \Omega_X \to \mathcal{P}(\mathcal{V})$ que a cada muestra le asigna un subconjunto del espacio de parámetros.
>Decimos que $S=S(X)$ es una **región de confianza de nivel $1-\alpha$** si:
>$$ \inf_{\nu \in \Gamma} P_\nu(\nu \in S(X)) \ge 1-\alpha $$
>Supongamos que planteamos testear si un valor determinado del parámetro $\nu$ corresponde a la verdadera distribución de los datos. Entonces, el problema de hipótesis es:
>$$ H_0:P=P_{\nu_0} \quad \text{vs} \quad H_1:  P \ne P_{\nu_0}\quad(1) $$
>Sea el test aleatorizado de nivel $\alpha$:
>$$ \varphi(X, \nu) = \begin{cases} 1 & \text{si } X \in R_{\nu} \\ 0 & \text{si } X \notin R_{\nu} \end{cases} $$
>$R_{\nu}$ es la región de rechazo del test. $P_{\nu}(X \in R_{\nu}) \le \alpha$.
>Hallamos
>$$ A(\nu) = \{x \in \Omega_X : \varphi(x, \nu) = 0\} $$

>[!Theorem]
>El test $\varphi(X,\nu)$ es un test de nivel $\alpha$ para el problema de hipótesis $(1)$ para todo $\nu \in \Gamma$ si y sólo si la región
>$$ S(X) = \{\nu \in \Gamma : X \in A(\nu)\} $$
>es una región de confianza de nivel $1-\alpha$.
>>[!Proof]-
>>$(\implies)$ Dado el test $\varphi(X,\nu)$, la región $A(\nu)$ es su región de aceptación (o no rechazo) 
>> Por definición de test de nivel $\alpha$, tenemos que $P_\nu(X \notin A(\nu)) = P_\nu(X \in R_\nu) \le \alpha$, lo que es equivalente a:
>> $$ P_\nu(X \in A(\nu)) \ge 1-\alpha $$
>>El conjunto de todos los parámetros que generan una zona de aceptación que contiene al $x$ observado es el conjunto aleatori0
>> $$S(X)=\{ \nu\in \Gamma:X\in A(\nu) \}$$
>> Dado que $P_\nu(X \in R_\nu) \le \alpha$ para todo $\nu \in \Gamma$, se tiene que:
>> $$ 1-\alpha \le P_\nu(X \notin R_\nu) = P(X \in A(\nu))=  P_\nu(\nu \in S(X)) \quad \forall \nu \in \Gamma $$
>>el ultimo igual por la definición de $S(X)$, 
>>Entonces $S(X)$ es una región de confianza de nivel $1-\alpha$.
>>$(\impliedby)$ Si $S(X)$ es una región de confianza de nivel $1-\alpha$, tomemos el test para el problema (1):
> $$ \varphi(X, \nu) = \begin{cases} 1 & \text{si } \nu \notin S(X) \\ 0 & \text{si } \nu \in S(X) \end{cases} $$
> Como $P_\nu(\nu \in S(X)) \ge 1-\alpha$, entonces:
> $$ P_\nu(\nu \notin S(X)) \le \alpha $$
> La región de rechazo del test es $\{x: \nu \notin S(x)\}$, y por lo tanto, la probabilidad de rechazar $H_0$ cuando es verdadera es menor o igual a $\alpha$. Mostrando que el test tiene el nivel deseado.

>[!Remark]
>Veamos un resultado que permite obtener Intervalos de Confianza en familias de distribuciones con Cociente de Verosimilitud Monótono (CVM).

>[!Theorem]
>Supongamos que $X \sim P_\theta$ (X vectorial).
>- (i) $\{P_\theta : \theta \in \Theta\}$ es de CVM en $T(X)$.
>- (ii) $T \sim F(\cdot, \theta)$ donde $F(t, \theta)$ es continua en cada variable cuando la otra está fija.
>
>Entonces se cumple que:
>- (a) Si la ecuación $F(t, \theta) = 1-\alpha$ tiene una solución $\underline{\theta_\alpha}(t) \in \Theta$, entonces $\underline{\theta_{\alpha }}(T)$ es una **cota inferior de confianza** para $\theta$ de nivel $1-\alpha$.
>- (b) Si la ecuación $F(t, \theta) = \alpha$ tiene una solución $\overline{\theta_{\alpha }}\in \Theta$ entonces $\overline{\theta_{\alpha}}(T)$ es una **cota superior de confianza** para $\theta$ de nivel $1-\alpha$.
>- (c) Si $\alpha_1 + \alpha_2 \le 1$, entonces el intervalo $[\underline{\theta_{\alpha _{1}}}(T), \overline{\theta_{\alpha _{2}}}(T)]$ es un **Intervalo de Confianza** para $\theta$ de nivel $1 - (\alpha_1 + \alpha_2)$.


