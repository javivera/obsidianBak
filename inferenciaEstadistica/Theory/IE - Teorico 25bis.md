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
>- i) $\beta_\varphi(P_0) = \alpha$ (El tamaño del test es exactamente $\alpha$).
>- ii) Para todo test $\varphi'$ tal que $\beta_{\varphi'}(P_0) \le \alpha$, se tiene que $\beta_{\varphi'}(P_1) \le \beta_\varphi(P_1)$.

>[!Remark]
>La respuesta a cómo conseguir un test MP está dada por los siguientes resultados.

>[!Lemma] Neyman-Pearson I
>Sea el problema de hipótesis simples planteado arriba, y sean $f_0, f_1$ las densidades de $P_0$ y $P_1$ respecto a una medida $\mu_0$.
>Entonces, para cada función $0 \le \gamma(x) \le 1$ y constante $k \ge 0$, el test
>$\varphi: \Omega_X \to[0,1]$ definido como
>$$ \varphi(x) = \begin{cases} 1 & \text{si } f_1(x) > k f_0(x) \\ \gamma(x) & \text{si } f_1(x) = k f_0(x) \\ 0 & \text{si } f_1(x) < k f_0(x) \end{cases} $$
>es el test más potente (MP) de tamaño $\int \varphi f_0 d\mu = \beta_\varphi(P_0)$.

>[!Remark]
>Al cambiar $\gamma$ y $k$ siempre obtenemos un test MP, pero de tamaño $\int \varphi f_0 d\mu$.
>La intuición de lo que hace el test es clara en el caso discreto: el test toma el valor 1 (o sea, rechaza $H_0$) cuando la probabilidad de observar $x$ bajo la alternativa ($f_1(x)$) es $k$ veces mayor que la probabilidad de observar $x$ bajo la nula $H_0(f_0(x))$.

>[!Remark]
>¿Pero cómo hacemos para deducir el MP de tamaño $\alpha$ deseado?

>[!Lemma] (de Neyman-Pearson II)
>Para cualquier $0 < \alpha < 1$, existe un test $\varphi: \Omega_X \to$ de tamaño $\alpha$ de la forma dada en (1), con $\gamma(x) = \gamma$ (constante) y $k \in [0, \infty)$, satisfaciendo:
>$$ P_0(f_1 > k f_0) \le \alpha \le P_0(f_1 \ge k f_0) $$
>$$ \alpha = \int \varphi f_0 d\mu = P_0(f_1 > k f_0) + \gamma P_0(f_1 = k f_0) $$
>Más aún, si $\varphi'$ es un test MP de tamaño $0 < \alpha \le 1$, entonces debe coincidir con el test $\varphi$ de Neyman-Pearson salvo conjuntos de probabilidad cero, o sea:
>$$ P_0(\varphi \ne \varphi', f_1 \ne k f_0) = 0 $$
>$$ P_1(\varphi \ne \varphi', f_1 \ne k f_0) = 0 $$

>[!Remark]
>Neyman-Pearson no especifica $\gamma(x)$, y si $\varphi = \varphi'$ en el conjunto $\{f_1 = k f_0\}$, realmente coinciden en todas partes salvo conjuntos de probabilidad cero.

## Tests uniformemente más potentes (UMP) para hipótesis unilaterales

>[!Remark]
>El problema al cual nos vamos a abocar es en el caso de familias paramétricas con $\Theta \subseteq \mathbb{R}$.
>$$\Theta = \Theta_0 \cup \Theta_1\quad\Theta_0 = (-\infty, \theta_0]\quad \Theta_1 = (\theta_0, \infty)$$
>o viceversa
>$$\Theta_0 = [\theta_0, \infty)\quad\Theta_1 = (-\infty, \theta_0)$$
>Con lo cual, el problema de hipótesis sería de tipo:
>$H_0: \theta \le \theta_0$ vs $H_1: \theta > \theta_0$
>($H_0: \theta \ge \theta_0$ vs $H_1: \theta < \theta_0$)
>(Esto es lo que llamamos **hipótesis unilaterales**).

>[!Definition]
>Para un problema de hipótesis $H_0: P \in \mathcal{P}_0$ vs $H_1: P \in \mathcal{P}_1$, con $\mathcal{P} = \mathcal{P}_0 \cup \mathcal{P}_1$ y $\mathcal{P}_0 \cap \mathcal{P}_1 = \emptyset$. Un test $\varphi: \Omega_X \to$ de tamaño $\alpha$ (es decir, $\sup_{P \in \mathcal{P}_0} \beta_\varphi(P) = \alpha$) se dice **test uniformemente más potente de tamaño $\alpha$ (UMP-$\alpha$)** si para cualquier otro test $\varphi'$ de nivel $\alpha$ ($\sup_{P \in \mathcal{P}_0} \beta_{\varphi'}(P) \le \alpha$) cumple que: 
>$$ \beta_{\varphi'}(P) \le \beta_\varphi(P) \quad \forall P \in \mathcal{P}_1 $$

>[!Remark]
>Volvamos a nuestro problema unilateral:
>$H_0: \theta \le \theta_0$ vs $H_1: \theta > \theta_0$.
>
>Si ponemos
>$H_0: \theta = \theta_0$ vs $H_1: \theta = \theta_1$
>con $\theta_1 > \theta_0$, sabemos encontrar el test MP.

>[!Example]
>Sea $X \sim Bi(n, \theta)$, con $0 < \theta < 1$.
>El problema de hipótesis es
>$H_0: \theta = \theta_0$ vs $H_1: \theta = \theta_1$, con $\theta_1 > \theta_0$.
>Si aplicamos el test de Neyman-Pearson:
>$$ \varphi(x) = \begin{cases} 1 & \text{si } f_1(x) > k f_0(x) \\ \gamma & \text{si } f_1(x) = k f_0(x) \\ 0 & \text{si } f_1(x) < k f_0(x) \end{cases} $$
>donde el cociente de verosimilitudes es:
>$$ L(x) = \frac{f_1(x)}{f_0(x)} = \frac{\binom{n}{x} \theta_1^x (1-\theta_1)^{n-x}}{\binom{n}{x} \theta_0^x (1-\theta_0)^{n-x}} = \left(\frac{\theta_1}{\theta_0}\right)^x \left(\frac{1-\theta_1}{1-\theta_0}\right)^{n-x} $$
>Como $\theta_1 > \theta_0$, tenemos que $a = \frac{\theta_1}{\theta_0} > 1$ y $b = \frac{1-\theta_1}{1-\theta_0} < 1$.
>
>O sea, el test se puede escribir como:
>$$ \varphi(x) = \begin{cases} 1 & \text{si } L(x) > k \\ \gamma & \text{si } L(x) = k \\ 0 & \text{si } L(x) < k \end{cases} $$
>$k$ se determina por la condición de nivel:
>$P_0(L(x) > k) \le \alpha \le P_0(L(x) \ge k)$
>y $\gamma$ por la ecuación
>$\alpha = P_0(L > k) + \gamma P_0(L=k)$.
>Trabajemos la región $L > k$:
>$L > k \iff \log L > \log k$
>$$ x \log a + (n-x) \log b > \log k $$
>$$ x(\log a - \log b) > \log k - n \log b $$
>Como $\log a > 0$ y $\log b < 0$, entonces $\log a - \log b > 0$, y la desigualdad se mantiene:
>$$ x > \frac{\log k - n \log b}{\log a - \log b} =: m $$
>
>$P(L > k) = P(X > m)$. Luego el test $\varphi$ toma la forma:
>$$ \varphi(x) = \begin{cases} 1 & \text{si } x > m \\ \gamma & \text{si } x = m \\ 0 & \text{si } x < m \end{cases} $$
>donde $m$ y $\gamma$ satisfacen:
>$P_0(X > m) \le \alpha \le P_0(X \ge m)$
>$\alpha = P_0(X > m) + \gamma P_0(X=m)$
>Luego, el test obtenido sólo depende de $\theta_0$ y no depende de $\theta_1$, con lo cual resulta el test más potente (MP) para cualquiera sea la alternativa $\theta_1 > \theta_0$. Luego, es el **test uniformemente más potente de tamaño $\alpha$ (UMP-$\alpha$)** para el problema de hipótesis:
>$H_0: \theta = \theta_0$ vs $H_1: \theta > \theta_0$.

>[!Example]
>Sea $X_1, \dots, X_n$ una muestra aleatoria i.i.d. tal que $X_1 \sim N(\theta, 1)$.
>Sea el problema de hipótesis $H_0: \theta = \theta_0$ vs $H_1: \theta > \theta_0$.
>Ver que el test UMP-$\alpha$ es de la forma:
>$$ \varphi(X_1, \dots, X_n) = \begin{cases} 1 & \text{si } \frac{\sum X_i}{n} > m \\ 0 & \text{si } \frac{\sum X_i}{n} \le m \end{cases} $$
>donde $m$ cumple:
>$P_0(\bar{X}_n > m) \le \alpha \le P_0(\bar{X}_n \ge m)$
>$\alpha = P_0(\bar{X}_n > m)$.
>
>Esto que se ve en los ejemplos, puede ser generalizado a través de la propiedad siguiente:

>[!Definition]
>Sea la familia de distribuciones $\mathcal{P} = \{P_\theta : \theta \in \Theta \subseteq \mathbb{R}\}$ dominadas por una medida $\mu$, y sean $f_\theta$ sus densidades.
>La familia de densidades $\{f_\theta : \theta \in \Theta\}$ se dice que tiene **cociente de verosimilitud monótono (CVM)** en un estadístico $T: \Omega_X \to \mathbb{R}$ si para todo $\theta_1 < \theta_2$, con $\theta_1, \theta_2 \in \Theta$. El cociente de verosimilitud:
>$$ L(x) = \begin{cases} \frac{f_{\theta_2}(x)}{f_{\theta_1}(x)} & \text{si } f_{\theta_1}(x) > 0 \\ \infty & \text{si } f_{\theta_1}(x) = 0 \text{ y } f_{\theta_2}(x) > 0 \end{cases} $$
>es una función monótona (creciente o decreciente) en $T(x)$.
>(El cociente de verosimilitud no se define si $f_{\theta_1}(x) = 0 = f_{\theta_2}(x)$).

>[!Example]
>Sea $X_1, \dots, X_n$ una muestra aleatoria i.i.d. con $X_1 \sim U(0, \theta)$.
>En este caso, el espacio paramétrico es $\Theta = (0, \infty)$.
>La densidad conjunta es:
>$$ f_\theta(x_1, \dots, x_n) = \frac{1}{\theta^n} I_{(0, \infty)}(\min x_i) I_{[0, \theta]}(\max x_i) $$
>¿Es esta familia de CVM?
>Sean $0 < \theta_1 < \theta_2$. El cociente de verosimilitud es:
>$$ \frac{\frac{1}{\theta_2^n} I_{[0, \theta_2]}(\max x_i)}{\frac{1}{\theta_1^n} I_{[0, \theta_1]}(\max x_i)} = \begin{cases} 0 & \text{si } \max x_i > \theta_2 \\ (\frac{\theta_1}{\theta_2})^n & \text{si } \max x_i \le \theta_1 \\ \infty & \text{si } \theta_1 < \max x_i < \theta_2 \end{cases} $$
>
>Luego, tiene CVM en el estadístico $T(X_1, \dots, X_n) = X_{(n)}$.

>[!Remark]
>A continuación vamos a enunciar un lema, que va a permitirnos después obtener el test UMP-$\alpha$ en el problema de hipótesis unilaterales.

>[!Lemma]
>Sea $\Theta \subseteq \mathbb{R}$ y supongamos que tenemos la familia de densidades $\{f_\theta : \theta \in \Theta\}$ respecto de la medida $\mu$, que cumple la propiedad de CVM en el estadístico $T(x)$. Sea además el test $\varphi$ de Neyman-Pearson II, que depende del cociente de verosimilitud. Si esta es una función creciente (decreciente) en $T$, entonces se cumple que la función potencia
>$$ \beta_\varphi(\theta) = E_\theta(\varphi) = \int \varphi f_\theta d\mu $$
>es creciente (decreciente).

>[!Remark]
>Ahora llegamos al enunciado del teorema que nos dará los test UMP-$\alpha$ en el problema unilateral.

>[!Theorem]
>Sea la familia de densidades $\{f_\theta : \theta \in \Theta \subseteq \mathbb{R}\}$ con CVM creciente en el estadístico $T$. Sea $0 < \alpha < 1$, $\theta_0 \in \Theta$, y $P_0(B) = \int_B f_{\theta_0} d\mu$.
>- a) Sea el problema de hipótesis
>$H_0: \theta \le \theta_0$ vs $H_1: \theta > \theta_0$.
>Entonces el test definido como
>$$ \varphi(x) = \begin{cases} 1 & \text{si } T(x) > k \\ \gamma & \text{si } T(x) = k \\ 0 & \text{si } T(x) < k \end{cases} $$
>donde $k, \gamma \in$ satisfacen que
>$P_0(T>k) \le \alpha \le P_0(T \ge k)$
>$\alpha = P_0(T>k) + \gamma P_0(T=k)$
>es un test UMP-$\alpha$ para el problema de hipótesis.
>
>- b) Sea el problema de hipótesis
>$H_0: \theta \ge \theta_0$ vs $H_1: \theta < \theta_0$.
>Entonces el test definido como
>$$ \varphi'(x) = \begin{cases} 1 & \text{si } T(x) < k' \\ \gamma' & \text{si } T(x) = k' \\ 0 & \text{si } T(x) > k' \end{cases} $$
>donde $k', \gamma' \in$ satisfacen que
>$P_0(T < k') \le \alpha \le P_0(T \le k')$
>$\alpha = P_0(T < k') + \gamma' P_0(T=k')$
>es un test UMP-$\alpha$ para el problema de hipótesis.

>[!Remark]
>¿Es posible encontrar un test UMP-$\alpha$ para problemas de hipótesis del tipo $H_0: \theta = \theta_0$ vs $H_1: \theta \ne \theta_0$?
>(Problema de **hipótesis bilateral**).

>[!Example]
>Sea $X \sim Bi(n, \theta)$, con $0 < \theta < 1$.
>Y tenemos el problema de hipótesis:
>$H_0: \theta = 0.5$ vs $H_1: \theta \ne 0.5$.
>¿Podemos encontrar un test UMP-$\alpha$ para este problema?
>Si uno plantea el problema unilateral:
>$H_0: \theta=0.5$ vs $H_1^+: \theta > 0.5$.
>Para este problema sabemos encontrar el test UMP-$\alpha$, que es de la forma:
>$$ \varphi^+(x) = \begin{cases} 1 & \text{si } x > k^+ \\ \gamma^+ & \text{si } x = k^+ \\ 0 & \text{si } x < k^+ \end{cases} $$
>donde $k^+$ y $\gamma^+$ se determinan para asegurar que $\alpha = E_{0.5}[\varphi^+(X)]$.
>
>Si uno considera el problema:
>$H_0: \theta=0.5$ vs $H_1^-: \theta < 0.5$.
>![[Pasted image 20250726170614.png]]
>El test MP para $H_0$ vs $H_1^-$ es de la forma:
>$$ \varphi^-(x) = \begin{cases} 1 & \text{si } x < k^- \\ \gamma^- & \text{si } x = k^- \\ 0 & \text{si } x > k^- \end{cases} $$
>donde $\gamma^-$ y $k^-$ se eligen de forma tal que $\alpha = E_{0.5}[\varphi^-(X)]$.
>
>Supongamos que tenemos el test UMP-$\alpha$ para el problema bilateral, y lo llamamos $\varphi^0$.
>Entonces, $\varphi^0$ es el más potente para el problema de hipótesis $H_0: \theta=0.5$ vs $H_1^+: \theta > 0.5$.
>Esto implica que las funciones de potencia deben ser iguales:
>$$ \beta_{\varphi^0}(\theta) = \beta_{\varphi^+}(\theta) \quad \forall \theta \ge 0.5 $$
>$$ \implies E_\theta[\varphi^0(X)] = E_\theta[\varphi^+(X)] \quad \forall \theta \ge 0.5 $$
>
>Sea $g^+(x) = \varphi^0(x) - \varphi^+(x)$. Entonces:
>$$ 0 = E_\theta[g^+(X)] = \sum_{j=0}^n g^+(j) \binom{n}{j} \theta^j (1-\theta)^{n-j} \quad \forall \theta \ge 0.5 $$
>$$ 0 = (1-\theta)^n \sum_{j=0}^n g^+(j) \binom{n}{j} \left(\frac{\theta}{1-\theta}\right)^j $$
>
>Si $\theta \in [0.5, 1)$, entonces $\eta = \frac{\theta}{1-\theta} \in [1, \infty)$.
>Luego, tenemos un polinomio de grado $n$ en $\eta$ que sobre la semirrecta $[1, \infty)$ se anula. 
>...es el polinomio nulo, lo que implica que sus coeficientes son cero:
>$$ g^+(j) = 0 \quad \forall j \in \{0, \dots, n\} $$
>$$ \implies \varphi^0(j) = \varphi^+(j) \quad \forall j \in \{0, \dots, n\} $$
>
>Ahora, si consideramos el problema $H_0: \theta=0.5$ vs $H_1^-: \theta < 0.5$ y definimos $g^-(j) = \varphi^0(j) - \varphi^-(j)$, de la misma forma concluimos que
>$$ \varphi^0(j) = \varphi^-(j) \quad \forall j \in \{0, \dots, n\} $$
>
>Juntando ambos resultados, tendríamos $\varphi^-(j) = \varphi^+(j)$ para todo $j$.
>Lo cual es imposible, porque sabemos la forma de los tests $\varphi^+$ y $\varphi^-$.
>
>$\implies$ **NO existe el test UMP-$\alpha$ para el problema bilateral.**
>
>Como no podemos plantear procedimientos óptimos, ¿qué podemos hacer?

