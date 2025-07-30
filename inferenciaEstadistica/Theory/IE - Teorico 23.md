**Métodos de estimación**

>[!Remark]
>Sea $\mathcal{P} = \{P_\theta \mid \theta \in \Theta\}$ una familia paramétrica e identificable.
>Tratamos de detectar el valor $\theta_0 \in \Theta$ (desconocido) tal que el vector aleatorio $X: \Omega \to \Omega_X$, cuya realización observamos, cumple que $X \sim P_{\theta_0}$. Queremos construir un estimador $\hat{\theta}(X)$ que se "relacione" con $\theta_0$.
>Supongamos que tomamos una función $\rho: \Omega_X \times \Theta \to \mathbb{R}$ y con ella definimos la **discrepancia** $D(\theta_0, \theta) = E_{\theta_0}[\rho(X, \theta)]$.
>(Esto es como tratar de medir en promedio la discrepancia por usar $X \sim P_{\theta_0}$ y comparar con cada $\theta$).
>La idea de una función de discrepancia debe ser que:
>$$ D(\theta_0, \theta_0) < D(\theta_0, \theta) \quad \forall \theta \ne \theta_0 $$
>Como $\theta_0$ es desconocido, no podemos calcular $E_{\theta_0}$. 
>Una forma de considerar el problema podría ser elegir un estimador $\hat{\theta}(X)$ que minimice $\rho(X, \theta)$ para la muestra observada.
>La función $\rho$ se dice **función de contraste**, y el estimador $\hat{\theta}(X)$ se dice **estimador de mínimo contraste**.
>$$ \hat{\theta}(X) = \arg\min_{\theta \in \Theta} \rho(X, \theta) $$
>

>[!Example]
>Sea $\theta \in \mathbb{R}$ y $X_1, \dots, X_n$ una muestra aleatoria. Entonces:
>- i) Una función de contraste conocida es: $$ \rho(X_1, \dots, X_n, \theta) = \frac{1}{n} \sum_{i=1}^n (X_i - \theta)^2 $$
>Derivamos con respecto a $\theta$ $$\rho'(\theta)=-\frac{2}{n}\left[\left(\sum^{n}_{i=1} X_{i}\right)-n\theta\right]$$
>Igualando derivada a 0 llegamos a que el estimador (llamado **estimador de cuadrados mínimos**) es:
>$$ \hat{\theta}(X) = \frac{1}{n} \sum_{i=1}^n X_i $$
>- ii) Otra función de contraste es:$$ \rho(X_1, \dots, X_n, \theta) = \frac{1}{n} \sum_{i=1}^n |X_i - \theta| $$
>y luego, el estimador es la **mediana muestral**:
>$$ \hat{\theta}(X) = \begin{cases} X_{(\frac{n+1}{2})} & \text{si } n \text{ es impar} \\ \frac{1}{2}(X_{(\frac{n}{2})} + X_{(\frac{n}{2}+1)}) & \text{si } n \text{ es par} \end{cases} $$

>[!Remark]
>Volvemos a la presentación general.
>Si tenemos $\Theta \subseteq \mathbb{R}^d$ y la función $\theta \mapsto D(\theta_0, \theta)$ es continua y diferenciable, entonces se debería cumplir que:
>$$ \nabla_\theta D(\theta_0, \theta) |_{\theta=\theta_0} = 0 $$
>Luego, el estimador de mínimo contraste debería verificar:
>$$ \nabla_\theta \rho(X, \theta) |_{\theta=\hat{\theta}(X)} = 0 $$
>Esta es la **ecuación de estimación**.

>[!Remark]
>En forma más general, podemos definir al estimador $\hat{\theta}(X)$ obtenido como la solución de $\Psi(X, \hat{\theta})=0$ (también llamada **ecuación de estimación**).
>Un caso particular importante de esta ecuación de estimación está dado por el metodo de los momentos

>[!Remark] Método de los Momentos
>Sea $X_1, \dots, X_n$ una muestra aleatoria tal que $X_1 \sim P_{\theta_0}$, con $\theta_0 \in \mathbb{R}^d$ (identificable).
>Supongamos que la distribución $P_\theta$ admite "$d$" momentos finitos, o sea:
>$$ \mu_j = \mu_j(\theta) = E_\theta(X_1^j) \in \mathbb{R} \quad \forall j \in \{1, \dots, d\} $$
>Osea tenemos $X_1 \sim P_{\theta}$ (y no conocemos el parámetro $\theta_0$).
>Sea $$F_n(x) = \frac{1}{n} \sum_{i=1}^n I_{(-\infty, x]}(X_i)$$la **función de distribución empírica**. (Notar aca $X_{i}$ son la muestra) 
>Esta función de distribución define una medida de probabilidad que asigna una masa de $1/n$ a cada observación $X_i$. 
>Es facil de ver por que 
>$$P_{F_{n}}(X=x)=F_{n}(x)-\lim\limits_{ a \to x^{-}  }F_{n}(a) $$
>Y esto es 0 en puntos que no sean de la muestra y en los puntos de la muestra $F_{n}(x)$ da justo un salto pero el limite por izquierda no llega a darlo entonces le resta lo acumulado dando $\frac{1}{n}$  
>Como $F_n$ es una f.d.a. del tipo discreto, el j-ésimo momento con respecto a esta distribución es:
>$$ \hat{\mu}_j = E_{F_n}(X^j) = \frac{1}{n} \sum_{i=1}^n x_i^j $$
>Este momento muestral cambia con la muestra, no con el parámetro.
>
>Supongamos que la función $\theta \mapsto (\mu_1(\theta), \mu_2(\theta), \dots, \mu_d(\theta))$ es inyectiva. Entonces, el método de los momentos provee una estimación para $\theta$ definiendo a $\hat{\theta}$ como la solución al sistema de ecuaciones:
>$$ E_{F_n}(X^j) = E_{\hat{\theta}(X)}(X^j) \quad \forall j \in \{1, \dots, d\} $$
>Esta es la **ecuación de estimación**. Esto es,
>$$ \hat{\mu}_j = \mu_j(\hat{\theta}(X)) \quad \forall j \in \{1, \dots, d\} $$
>El estimador $\hat{\theta}$ es el que produce la igualdad entre los **momentos poblacionales** (o teóricos) y los **momentos muestrales**.
>
>La ecuación de estimación puede escribirse en forma vectorial como $\Psi(X, \theta) = \mu(\theta) - \hat{\mu}(X) = 0$, donde:
>$$ \mu(\theta) = \begin{pmatrix} \mu_1(\theta) \\ \vdots \\ \mu_d(\theta) \end{pmatrix}, \quad \hat{\mu}(X) = \begin{pmatrix} \hat{\mu}_1 \\ \vdots \\ \hat{\mu}_d \end{pmatrix} $$

>[!Remark]
>Si tenemos una función $q: \Theta \to \mathbb{R}^k$ tal que $q(\theta) = h(\mu_1(\theta), \dots, \mu_d(\theta))$, se define el **estimador de los momentos** para $q(\theta)$ como:
>$$ \hat{q}(\theta) = h(\hat{\mu}_1, \dots, \hat{\mu}_d) $$

>[!Example] Ejemplo metodo momentos
>a) $X_1, \dots, X_n$ son una muestra aleatoria tal que $X_1 \sim \Gamma(\alpha, \lambda)$, con $\alpha > 0, \lambda > 0$.
>O sea, la función de densidad está dada por:
>$$ p(x; \alpha, \lambda) = \frac{\lambda^\alpha}{\Gamma(\alpha)} x^{\alpha-1} e^{-\lambda x} I_{(0, \infty)}(x) $$
>Se sabe que el m-ésimo momento es:
>$$ E(X_1^m) = \frac{\Gamma(\alpha+m)}{\Gamma(\alpha) \lambda^m} \quad \forall m \in \mathbb{N} $$
>En especial, los dos primeros momentos son:
>- $E(X_1) = \frac{\Gamma(\alpha+1)}{\Gamma(\alpha)\lambda} = \frac{\alpha \Gamma(\alpha)}{\Gamma(\alpha)\lambda} = \frac{\alpha}{\lambda}$ (por la propiedad de la función Gamma: $\Gamma(z+1) = z\Gamma(z)$)
>- $E(X_1^2) = \frac{\Gamma(\alpha+2)}{\Gamma(\alpha)\lambda^2} = \frac{(\alpha+1)\Gamma(\alpha+1)}{\Gamma(\alpha)\lambda^2} = \frac{(\alpha+1)\alpha\Gamma(\alpha)}{\Gamma(\alpha)\lambda^2} = \frac{\alpha(\alpha+1)}{\lambda^2}$
>La función $(\alpha, \lambda) \mapsto (\frac{\alpha}{\lambda}, \frac{\alpha(\alpha+1)}{\lambda^2})$ es inyectiva, luego planteamos el sistema de ecuaciones para el estimador de momentos (EM):
>$$ \begin{cases} \hat{\mu}_1 = \mu_1(\hat{\alpha}, \hat{\lambda}) = \frac{\hat{\alpha}}{\hat{\lambda}} \\ \hat{\mu}_2 = \mu_2(\hat{\alpha}, \hat{\lambda}) = \frac{\hat{\alpha}(\hat{\alpha}+1)}{\hat{\lambda}^2} \end{cases} $$
>De la primera ecuación, obtenemos $\hat{\alpha} = \hat{\lambda} \hat{\mu}_1$.
>Reemplazamos esta expresión en la segunda ecuación:
>$$ \hat{\mu}_2 = \frac{\hat{\lambda}\hat{\mu}_1(\hat{\lambda}\hat{\mu}_1+1)}{\hat{\lambda}^2} = \frac{\hat{\mu}_1(\hat{\lambda}\hat{\mu}_1+1)}{\hat{\lambda}} \implies \hat{\lambda}\hat{\mu}_2 = \hat{\lambda}\hat{\mu}_1^2 + \hat{\mu}_1 \implies \hat{\lambda}(\hat{\mu}_2 - \hat{\mu}_1^2) = \hat{\mu}_1 $$
>$$ \implies \hat{\lambda} = \frac{\hat{\mu}_1}{\hat{\mu}_2 - \hat{\mu}_1^2} $$
>El denominador es la varianza muestral, $\hat{V}_n(X) = \hat{\mu}_2 - \hat{\mu}_1^2$, que es siempre mayor que cero. Como el numerador, $\hat{\mu}_1$, es el promedio de variables positivas, también es positivo. Por lo tanto, $\hat{\lambda} > 0$.
>
>Entonces, los estimadores de momentos son:
>$$ \hat{\lambda} = \frac{\hat{\mu}_1}{\hat{\mu}_2 - \hat{\mu}_1^2} \in (0, \infty) \quad \text{y} \quad \hat{\alpha} = \hat{\lambda}\hat{\mu}_1 = \frac{\hat{\mu}_1^2}{\hat{\mu}_2 - \hat{\mu}_1^2} \in (0, \infty) $$
>donde $\hat{\mu}_1 = \frac{1}{n}\sum_{i=1}^n X_i$ y $\hat{\mu}_2 = \frac{1}{n}\sum_{i=1}^n X_i^2$.
>
>b) $X_1, \dots, X_n$ son una m.a. tal que $X_1 \sim U[0, \theta]$, con $\theta > 0$ desconocido.
>El EM para $\theta$ resulta de igualar el primer momento muestral al poblacional:
>$$ \frac{1}{n}\sum_{i=1}^n X_i = \hat{\mu}_1 = \mu_1(\theta) = \frac{\theta}{2} \implies \hat{\theta} = 2\hat{\mu}_1 $$
>(Recordar que si $Y \sim U[a,b]$, entonces $E(Y) = \frac{a+b}{2}$).
>c) $X_1, \dots, X_n$ son una v.a. con $P(X_1=j) = \lambda_j$ para $j \in \{1, \dots, k\}$, y $\lambda_1, \dots, \lambda_k$ desconocidos, con la restricción $\sum_{j=1}^k \lambda_j = 1$ y $0 < \lambda_j < 1$.
>El vector de parámetros es $\lambda = (\lambda_1, \dots, \lambda_k)$.
>El método de los momentos iguala los momentos muestrales a los poblacionales. Para $j \in \{0, 1, \dots, k-1\}$:
>$$ \frac{1}{n} \sum_{i=1}^n X_i^j = \hat{\mu}_j = \mu_j(\lambda) = E(X_1^j) = \sum_{i=1}^k i^j P(X_1=i) = \sum_{i=1}^k i^j \lambda_i $$
>Esto puede escribirse en forma matricial como:
>$$ \begin{pmatrix} \hat{\mu}_0 \\ \hat{\mu}_1 \\ \vdots \\ \hat{\mu}_{k-1} \end{pmatrix} = \begin{pmatrix} 1 & 1 & \dots & 1 \\ 1 & 2 & \dots & k \\ \vdots & \vdots & \ddots & \vdots \\ 1 & 2^{k-1} & \dots & k^{k-1} \end{pmatrix} \begin{pmatrix} \lambda_1 \\ \lambda_2 \\ \vdots \\ \lambda_k \end{pmatrix} = A \lambda $$
>donde $A$ es una matriz de Vandermonde. Como $\hat{\mu}_0=1$, y si $A$ es inversible, el EM es:
>$$ \hat{\lambda}_M = A^{-1} \hat{\mu} $$

>[!Remark]
>Otra forma de estimar en el ejemplo c.
>Habíamos visto que los estadísticos $T_j(X_1, \dots, X_n) = \sum_{i=1}^n I_{\{j\}}(X_i)$ para $j \in \{1, \dots, k\}$ (la cantidad de veces que aparece el valor $j$) siguen una distribución binomial:
>$$ T_j(X_1, \dots, X_n) \sim Bi(n, \lambda_j) \quad \text{con } \lambda_j = P(X_1=j) $$
>Podemos calcular su esperanza: $E(T_j) = n\lambda_j$. Luego, los estimadores $\frac{T_1}{n}, \dots, \frac{T_k}{n}$ son insesgados para $\lambda_1, \dots, \lambda_k$ respectivamente.
>Definimos $(\hat{\lambda}_1, \dots, \hat{\lambda}_k) = (\frac{T_1}{n}, \dots, \frac{T_k}{n})$ como el estimador de $(\lambda_1, \dots, \lambda_k)$. (Recordemos que $\sum_{j=1}^k T_j = n$). 
>Entonces ya tendriamos nuestra estimacion. La estimacion de $\hat{\lambda}_{1}$ seria la cantidad de veces que aparecio el $1$ en la muestra, etc
>

>[!Remark]
>Más en general, si tenemos una muestra aleatoria finita $X_1, \dots, X_n$ donde $P(X_1 = \nu_j) = \lambda_j$ para $j=1, \dots, k$ (con $\sum \lambda_j = 1$ y $0 < \lambda_j < 1$), y $\lambda_1, \dots, \lambda_k$ son desconocidos.
>En este caso $T_{j}(X_{1},\ldots,X_{n})=\sum^{n}_{i=1}I_{\{\nu_{j}\}}(X_{i})$ osea la cantidad de veces que aparece $\nu_{j}$ 
>Si queremos estimar $q(\lambda_1, \dots, \lambda_k)$, una función continua de los parámetros, entonces basta definir:
>$$ \hat{q}(\hat{\lambda}_1, \dots, \hat{\lambda}_k) = q(\hat{\lambda}_1, \dots, \hat{\lambda}_k) \quad \text{con } \hat{\lambda}_j = \frac{T_j}{n} $$
>Observamos que por la Ley Fuerte de los Grandes Números (Notando que $E(I_{j}(X_{i}))=j*P(X_{i}=j)=\lambda_{j}$ es una suma) ternemos que $$\frac{T_j}{n} \xrightarrow{c.s.} \lambda_j$$para todo $j \in \{1, \dots, k\}$. Entonces, por la continuidad de $q$:
>$$ \hat{q}(\hat{\lambda}_1, \dots, \hat{\lambda}_k) \xrightarrow{c.s.} q(\lambda_1, \dots, \lambda_k) $$

>[!Remark]
>Si una sucesión de estimadores $\{\hat{\theta}_n\}_{n \in \mathbb{N}}$ para una función $h(\theta)$ con $\Theta \subseteq \mathbb{R}^d$ cumple que $\hat{\theta}_n \xrightarrow{ae} h(\theta)$ si $X=(X_1, ..., X_n) \sim P_\theta$, entonces la sucesión $\{\hat{\theta}_n\}_{n \in \mathbb{N}}$ se dice **fuertemente consistente**.
>(Igualmente, si la convergencia es en probabilidad, se dice **débilmente consistente**).

>[!Definition] Estimadores Plug In
>Estimadores del tipo del ejemplo anterior, donde los parámetros desconocidos se reemplazan por estimadores dentro de una función conocida $q$, se denominan **estimadores de reemplazo o plug-in**.
>Supongamos que tenemos una clase de distribuciones o medidas de probabilidad $\mathcal{P}$, y tenemos $P \in \mathcal{P}$ distribucion subyacente y $q(P)$ un parametro de dicha distribucion que queremos estimar. Entonces si tomamos $\hat{P}$ un estimador de $P$ tenemos que $\hat{q}(P)=q(\hat{P})$ es un estimador de $q(P)$. Lo llamamos Plug In.
>Esto seria una version no parametrica, trabaja con distribuciones directamente.
>La version parametrica seria $\hat{q}(\theta)=q(\hat{\theta})$. Osea estimas el parametro $\theta$ de la distribucion con $\hat{\theta}$ y lo metes en la funcion $q$ 

>[!Example]
>Sea $X_1, \dots, X_n$ una muestra aleatoria con $X_1 \sim F$. Conocemos un estimador para $F$ dado por la función de distribución empírica.
>Un parámetro que ya conocimos es la **Función Cuantil**:
>$$ F_L^{-1}(\alpha) = \inf\{x \in \mathbb{R} \mid F(x) \ge \alpha\}, \quad \alpha \in (0,1) $$
>Una definición similar sería:
>$$ F_U^{-1}(\alpha) = \inf\{x \in \mathbb{R} \mid F(x) > \alpha\} $$
>Si $X \sim Bi(n,p)$, con $0 < p < 1$, calcular $F_L^{-1}(\alpha)$ y $F_U^{-1}(\alpha)$.
>>[!Proof]
>>1. Creo que aca se refiere a que podemos ver la funcion cuantil como que recibe una distribucion $$F_{n,L}^{-1}(\alpha )=\inf\{ x\in \mathbb{R}\ | \ F(x) \geq\alpha \}$$
>>2. Y tenemos que $F_{n}(x)=\frac{1}{n}\sum^{n}_{i=1}I_{(-\infty,x]}(X_{i})$ es estimador de la distribucion $X$
>>3. Con lo cual $F_{n,L}^{-1}(\alpha )=\inf\{ x\in \mathbb{R}\ | \ F_{n}(x)\geq\alpha  \}$ es un estimador del cuantil inferior $\alpha$ de la distribucion subyacente 
>>Esto seria como buscar el menor $x\in \mathbb{R}$ tal que la cantidad de muestras menores que $x$ dividido $n$ sea mayor que $\alpha$
>>4. Analogo con $F_{n,U}^{-1}$  

>[!Remark]
>Cuando definimos la **mediana muestral**:
>$$ \hat{m}_n(X_1, \dots, X_n) = \begin{cases} X_{(\frac{n+1}{2})} & \text{, n impar} \\ \frac{1}{2}(X_{(\frac{n}{2})} + X_{(\frac{n}{2}+1)}) & \text{, n par} \end{cases} $$
>Sea el parámetro $\nu_\alpha(F) = \frac{1}{2}(F_L^{-1}(\alpha) + F_U^{-1}(\alpha))$ al cual queremos estimar. Notar que si $\alpha = 0.5$ entonces $\nu_{0.5}(F)$ es la mediana.
>Ademas $F_L^{-1}$ y $F_U^{-1}$ son funciones de $F$. Para $F$ tenemos a $F_n$ como estimador (la función de distribución empírica), entonces el estimador plug-in es $\hat{\nu}_\alpha(F) = \nu_\alpha(F_n)$. Si ahora tomamos $\alpha =0.5$ entonces tenemos el estimador plug-in de la mediana que seria 
>$$ \hat{\nu}_{0.5}(F) = \nu_{0.5}(\hat{F}_n) $$
>Y podeoms notar que $\nu_{0.5}(\hat{F}_n) = \hat{m}_n$. Osea el estimador plug in de la mediana usando la funcion empirica es la mediana muestral

>[!Remark] Método de estimación por máxima verosimilitud (EMV)
>Sea $X$ un vector aleatorio en $\mathbb{R}^n$ y $x$ el vector observado, con $X \sim P_\theta$, $\theta \in \Theta \subseteq \mathbb{R}^d$.
>Supongamos que $X$ es discreta o absolutamente continua.
>Sea $p(x, \theta)$ la función de probabilidad puntual o de densidad conjunta.
>Llamemos $\mathcal{G} = \{f: \Theta \to [0, \infty)\}$.
>Llamamos **función de verosimilitud** a:
>$$ L: \Omega_X \to \mathcal{G}, \quad x \mapsto L_x(\cdot) = p(x, \cdot) $$
>
>La idea para estimar $\theta$ es que si hemos observado $x$, el $\theta$ que está subyacente debe ser el que le da la mayor chance de haber sido observado. O sea, buscamos $\hat{\theta}(X)$ como el valor que maximiza la verosimilitud:
>$$ L_x(\hat{\theta}(x)) = p(x, \hat{\theta}(x)) = \max_{\theta \in \Theta} p(x, \theta) $$
>
>Si no existe un $\hat{\theta}(x)$ que produzca el máximo, pero existe una sucesión $\{\hat{\theta}_m(x)\}_{m \in \mathbb{N}}$ convergente a $\hat{\theta}_L(x)$ y que cumple:
>$$ \lim_{m \to \infty} p(x, \hat{\theta}_m) = \sup_{\theta \in \Theta} p(x, \theta) $$
>entonces definimos el EMV como $\hat{\theta}(x) = \hat{\theta}_L(x)$.

>[!Example] Ejemplo de EMV
>a) $X_1, \dots, X_n$ es una m.a. con $X_1 \sim U[0, \theta]$, $\theta > 0$ desconocido.
>Encontrar el EMV para $\theta$.
>La densidad conjunta es:
> $$ p(x, \theta) = \frac{1}{\theta^n} \prod_{i=1}^n I_{[0, \theta]}(x_i) = \frac{1}{\theta^n} I_{[0, \infty)}(x_{(1)}) I_{[0, \theta]}(x_{(n)}) $$
>Para maximizar esta función con respecto a $\theta$, debemos hacer a $\theta$ lo más chico posible, pero tal que $\theta \ge x_{(n)}$. El valor que maximiza la verosimilitud es $\hat{\theta}(x) = x_{(n)}$.
>(No se pudo derivar en este ejemplo para encontrar el máximo).
>
>b) $X_1, \dots, X_n$ es una m.a. con $X_1 \sim N(\mu, \sigma^2)$, $\mu \in \mathbb{R}, \sigma > 0$ desconocidos.
>Mostrar que el EMV para $(\mu, \sigma^2)$ está dado por:
> $$ \hat{\mu}(X_1, \dots, X_n) = \frac{1}{n} \sum_{i=1}^n X_i = \bar{X}, \quad \hat{\sigma}^2(X_1, \dots, X_n) = \frac{1}{n} \sum_{i=1}^n (X_i - \bar{X})^2 $$
>
>c) El EMV no existe siempre.
>Sea $n > 2$, $X_1, \dots, X_n$ una m.a. donde la densidad de $X_1$ es de la forma:
>$$ f(x; \mu, \sigma^2) = \frac{9}{10} \frac{1}{\sigma} \varphi\left(\frac{x-\mu}{\sigma}\right) + \frac{1}{10} \varphi(x-\mu) $$
>donde $\varphi$ es la densidad de una normal estándar, y $\mu \in \mathbb{R}, \sigma > 0$ son desconocidos.
>Mostrar que se cumple que:
>$$ \sup_{0 < \sigma < \infty} p(y; \mu, \sigma) = \sup_{\mu \in \mathbb{R}, 0 < \sigma < \infty} p(y; \mu, \sigma) $$
>y que el supremo se alcanza cuando $\hat{\mu}$ iguala a alguno de los valores $x_1, \dots, x_n$.
>Deducir entonces que el EMV para $(\mu, \sigma^2)$ no existe.

>[!Remark]
>Supongamos que el soporte de la función de distribución no depende del parámetro que buscamos estimar.
>Llamemos **log-verosimilitud** a la función $l_x(\theta) = \log(L_x(\theta)) = \log(p(x, \theta))$.
>Como la función logaritmo es estrictamente creciente, entonces maximizar la verosimilitud $L_x(\theta)$ es equivalente a maximizar la log-verosimilitud $l_x(\theta)$, y esto a su vez es equivalente a minimizar $-l_x(\theta)$.
>Si $\Theta$ es un conjunto abierto, $l_x(\theta)$ es diferenciable y el estimador $\hat{\theta}(x)$ existe, entonces este debe resolver la **ecuación de verosimilitud**:
>$$ \nabla_\theta l_x(\theta)|_{\theta=\hat{\theta}} = 0 $$
>
>Si $X_1, \dots, X_n$ es una muestra aleatoria, la log-verosimilitud de la muestra es:
>$$ l_x(\theta) = \log(p(x, \theta)) = \log\left(\prod_{i=1}^n p_{X_1}(x_i, \theta)\right) = \sum_{i=1}^n \log(p_{X_1}(x_i, \theta)) $$
>Y la ecuación de verosimilitud se convierte en:
>$$ \nabla_\theta (l_x(\theta)) = \sum_{i=1}^n \nabla_\theta \log(p_{X_1}(x_i, \theta)) = 0 $$