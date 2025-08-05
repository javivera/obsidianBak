## Tests uniformemente más potentes (UMP) para hipótesis unilaterales

>[!Remark]
>El problema al cual nos vamos a abocar es en el caso de familias paramétricas con $\Theta \subseteq \mathbb{R}$.
>$$\Theta = \Theta_0 \cup \Theta_1\quad\Theta_0 = (-\infty, \theta_0]\quad \Theta_1 = (\theta_0, \infty)$$
>o viceversa
>$$\Theta_0 = [\theta_0, \infty)\quad\Theta_1 = (-\infty, \theta_0)$$
>Con lo cual, el problema de hipótesis sería de tipo:
>$$H_0: \theta \le \theta_0\ \text{ vs }\ H_1: \theta > \theta_0\quad (H_0: \theta \ge \theta_0\ \text{ vs }\ H_1: \theta < \theta_0)$$
>(Esto es lo que llamamos **hipótesis unilaterales**).

>[!Definition] Test UMP-$\alpha$ 
>Para un problema de hipótesis $$H_0: P \in \mathcal{P}_0\ \text{ vs } \ H_1: P \in \mathcal{P}_1$$con $\mathcal{P} = \mathcal{P}_0 \cup \mathcal{P}_1$ y $\mathcal{P}_0 \cap \mathcal{P}_1 = \emptyset$. 
>Un test $\varphi: \Omega_X \to$ de tamaño $\alpha$ (es decir, $\sup_{P \in \mathcal{P}_0} \beta_\varphi(P) = \alpha$) se dice **test uniformemente más potente de tamaño $\alpha$ (UMP-$\alpha$)** si para cualquier otro test $\varphi'$ de nivel $\alpha$ ($\sup_{P \in \mathcal{P}_0} \beta_{\varphi'}(P) \le \alpha$) cumple que: 
>$$ \beta_{\varphi'}(P) \le \beta_\varphi(P) \quad \forall P \in \mathcal{P}_1 $$

>[!Remark]
>Volvamos a nuestro problema unilateral:
>$$H_0: \theta \le \theta_0\ \text{ vs }\ H_1: \theta > \theta_0$$
>Si ponemos
>$$H_0: \theta = \theta_0\ \text{ vs }\ H_1: \theta = \theta_1$$
>con $\theta_1 > \theta_0$, sabemos encontrar el test MP.

>[!Example]
>Sea $X \sim Bi(n, \theta)$, con $0 < \theta < 1$. El problema de hipótesis es
>$$H_0: \theta = \theta_0\ \text{ vs }\ H_1: \theta = \theta_1$$
>con $\theta_1 > \theta_0$.
>Si aplicamos el test de Neyman-Pearson:
>$$ \varphi(x) = \begin{cases} 1 & \text{si } f_1(x) > k f_0(x) \\ \gamma & \text{si } f_1(x) = k f_0(x) \\ 0 & \text{si } f_1(x) < k f_0(x) \end{cases} $$
>donde el cociente de verosimilitudes es:
>$$ L(x) = \frac{f_1(x)}{f_0(x)} = \frac{\binom{n}{x} \theta_1^x (1-\theta_1)^{n-x}}{\binom{n}{x} \theta_0^x (1-\theta_0)^{n-x}} = \left(\frac{\theta_1}{\theta_0}\right)^x \left(\frac{1-\theta_1}{1-\theta_0}\right)^{n-x} $$
>Como $\theta_1 > \theta_0$, tenemos que $a = \frac{\theta_1}{\theta_0} > 1$ y $b = \frac{1-\theta_1}{1-\theta_0} < 1$.
>O sea, el test se puede escribir como:
>$$ \varphi(x) = \begin{cases} 1 & \text{si } L(x) > k \\ \gamma & \text{si } L(x) = k \\ 0 & \text{si } L(x) < k \end{cases} $$
>Y dicho test seria MP por [[IE - Teorico 25#^e3d94e]]
>Supongamos ademas queremos que el nivel del test sea un $\alpha$ predeterminado. Entonces por [[IE - Teorico 25#^2f1e3c]] sabemos que existe dicho test y que tiene que cumplir
>$$P_0(L(x) > k) \le \alpha \le P_0(L(x) \ge k)$$
> y pedimos $\gamma$ tal que $$\alpha = P_0(L > k) + \gamma P_0(L=k)$$
>Esto nos determinaria $k$. Ademas trabajemos la región $L > k$:
>$$\begin{align} L(x) > k & \iff \log L(x) > \log k \\& \iff  x \log a + (n-x) \log b > \log k \\&\iff  x(\log a - \log b) > \log k - n \log b \end{align}$$
>Como $\log a > 0$ y $\log b < 0$, entonces $\log a - \log b > 0$, y la desigualdad se mantiene:
>$$ x > \frac{\log k - n \log b}{\log a - \log b} =: m $$
>
>Por lo tanto sucede $P(L > k) = P(X > m)$. 
>Luego el test $\varphi$ toma la forma:
>$$ \varphi(x) = \begin{cases} 1 & \text{si } x > m \\ \gamma & \text{si } x = m \\ 0 & \text{si } x < m \end{cases} $$
>donde $m$ y $\gamma$ satisfacen:
>$$P_0(X > m) \le \alpha \le P_0(X \ge m)\quad \land\quad\alpha = P_0(X > m) + \gamma P_0(X=m)$$
>Luego, dado un tamaño $\alpha$ y $\theta_{0}$ (osea $P_{0}$) fijos tenemos el test y no depende de $\theta_1$, digamos si cambiara $\theta_{1}$ como el $m$ esta fijado por $\alpha,\theta_{0}$ entonces el $log(k)$ se adaptaría. Con lo cual resulta el test más potente (MP) para cualquiera sea la alternativa $\theta_1 > \theta_0$. 
> Luego, es el **test uniformemente más potente de tamaño $\alpha$ (UMP-$\alpha$)** para el problema de hipótesis:
>$$H_0: \theta = \theta_0\ \text{ vs }\ H_1: \theta > \theta_0$$
>
>

>[!Example] ejercicio
>Sea $X_1, \dots, X_n$ una muestra aleatoria i.i.d. tal que $X_1 \sim N(\theta, 1)$.
>Sea el problema de hipótesis $$H_0: \theta = \theta_0\ \text{ vs }\ H_1: \theta > \theta_0$$
>Ver que el test UMP-$\alpha$ es de la forma:
>$$ \varphi(X_1, \dots, X_n) = \begin{cases} 1 & \text{si } \frac{\sum X_i}{n} > m \\ 0 & \text{si } \frac{\sum X_i}{n} \le m \end{cases} $$
>donde $m$ cumple:
>$$P_0(\bar{X}_n > m) \le \alpha \le P_0(\bar{X}_n \ge m)\quad\land\quad\alpha = P_0(\bar{X}_n > m)$$
>Esto que se ve en los ejemplos, puede ser generalizado a través de la propiedad siguiente:

>[!Definition] CMV
>Sea la familia de distribuciones $\mathcal{P} = \{P_\theta : \theta \in \Theta \subseteq \mathbb{R}\}$ dominadas por una medida $\mu$, y sean $f_\theta$ sus densidades.
>La familia de densidades $\{f_\theta : \theta \in \Theta\}$ se dice que tiene **cociente de verosimilitud monótono (CVM)** en un estadístico $T: \Omega_X \to \mathbb{R}$ si para todo $\theta_1 < \theta_2$, con $\theta_1, \theta_2 \in \Theta$. El cociente de verosimilitud:
>$$ L(x) = \begin{cases} \frac{f_{\theta_2}(x)}{f_{\theta_1}(x)} & \text{si } f_{\theta_1}(x) > 0 \\ \infty & \text{si } f_{\theta_1}(x) = 0 \text{ y } f_{\theta_2}(x) > 0 \end{cases} $$
>es una función monótona (creciente o decreciente) en $T(x)$. (El cociente de verosimilitud no se define si $f_{\theta_1}(x) = 0 = f_{\theta_2}(x)$).

^65bcdd

>[!Example] CMV
>Sea $X_1, \dots, X_n$ una muestra aleatoria i.i.d. con $X_1 \sim U(0, \theta)$. En este caso, el espacio paramétrico es $\Theta = (0, \infty)$. La densidad conjunta es:
>$$ f_\theta(x_1, \dots, x_n) = \frac{1}{\theta^n} I_{(0, \infty)}(\min x_i) I_{[0, \theta]}(\max x_i) $$
>¿Es esta familia de CVM? Sean $0 < \theta_1 < \theta_2$. El cociente de verosimilitud es:
>$$ \frac{\frac{1}{\theta_2^n} I_{[0, \theta_2]}(\max x_i)}{\frac{1}{\theta_1^n} I_{[0, \theta_1]}(\max x_i)} = \begin{cases} 0 & \text{si } \max x_i > \theta_2 \\ (\frac{\theta_1}{\theta_2})^n & \text{si } \max x_i \le \theta_1 \\ \infty & \text{si } \theta_1 < \max x_i < \theta_2 \end{cases} $$
>
>Luego, tiene CVM en el estadístico $T(X_1, \dots, X_n) = X_{(n)}$.

>[!Remark]
>A continuación vamos a enunciar un lema, que va a permitirnos después obtener el test UMP-$\alpha$ en el problema de hipótesis unilaterales.

>[!Lemma] CMV implica potencia creciente (decreciente) 
>Sea $\Theta \subseteq \mathbb{R}$ y supongamos que tenemos la familia de densidades $\{f_\theta : \theta \in \Theta\}$ respecto de la medida $\mu$, que cumple la propiedad de CVM en el estadístico $T(x)$. Sea además el test $\varphi$ de Neyman-Pearson II, que depende del cociente de verosimilitud. Si esta es una función creciente (decreciente) en $T$, entonces se cumple que la función potencia
>$$ \beta_\varphi(\theta) = E_\theta(\varphi) = \int \varphi f_\theta d\mu $$
>es creciente (decreciente).

^5543e6

>[!Lemma] CMV implica potencia creciente (decreciente) 
>Sea $\Theta \subseteq \mathbb{R}$ y supongamos que tenemos la familia de densidades $\{f_\theta : \theta \in \Theta\}$ respecto de la medida $\mu$, que cumple la propiedad de CVM en el estadístico $T(x)$, luego es creciente (decreciente) en $T(x)$. Sea además el test $\varphi$ de Neyman-Pearson II, que depende del cociente de verosimilitud. Entonces se cumple que la función potencia
>$$ \beta_\varphi(\theta) = E_\theta(\varphi) = \int \varphi f_\theta d\mu $$
>es creciente (decreciente).
>>[!Proof]-
>>Sean $\theta_1 < \theta_2$ y sean los conjuntos
>>$A = \{x : f_{\theta_2}(x) < f_{\theta_1}(x)\} \text{ y } B = \{x : f_{\theta_1}(x) < f_{\theta_2}(x)\}$
>>Por definicion, si $a \in A$ y $b \in B$ entonces $L(a) < 1 < L(b)$. Por la definición de CVM y ser creciente en T resulta que $T(a) < T(b)$, como $\varphi$ es por hipótesis creciente en $T$, $\varphi(a) \le \varphi(b)$ para todo $a \in A$ y $b \in B$, por lo cual también se cumple que $\sup_{a \in A} \varphi(a) \le \inf_{b \in B} \varphi(b)$. Usando esto y el hecho que $\int_A (f_{\theta_2} - f_{\theta_1}) d\mu \le 0$ podremos comprobar el resultado del lema:
>>$$\begin{align*} \beta_\varphi(\theta_2) - \beta_\varphi(\theta_1) &= \int \varphi(f_{\theta_2} - f_{\theta_1}) d\mu = \int_A \varphi(f_{\theta_2} - f_{\theta_1}) d\mu + \int_B \varphi(f_{\theta_2} - f_{\theta_1}) d\mu \\ &\ge \sup_{a \in A} \varphi(a) \int_A (f_{\theta_2} - f_{\theta_1}) d\mu + \inf_{b \in B} \varphi(b) \int_B (f_{\theta_2} - f_{\theta_1}) d\mu \\ &\ge \inf_{b \in B} \varphi(b) \int_A (f_{\theta_2} - f_{\theta_1}) d\mu + \inf_{b \in B} \varphi(b) \int_B (f_{\theta_2} - f_{\theta_1}) d\mu \\ &\ge \inf_{b \in B} \varphi(b) \left( \int_A (f_{\theta_2} - f_{\theta_1}) d\mu + \int_B (f_{\theta_2} - f_{\theta_1}) d\mu \right) = \inf_{b \in B} \varphi(b) \int (f_{\theta_2} - f_{\theta_1}) d\mu = 0 \end{align*}$$
>>y $\beta_\varphi(\theta)$ es creciente en $\theta$ como se quería ver. El caso $\varphi$ decreciente en $T$ sale porque $1-\varphi$ es creciente en $T$, $\beta_{1-\varphi}(\theta) = 1-\beta_\varphi(\theta)$ es creciente en $\theta$ y por lo tanto $\beta_\varphi(\theta)$ es decreciente en $\theta$.
>>Con este resultado ya puede enunciarse como van a resultar los tests UMP-$\alpha$ en el problema de hipótesis unilaterales.

^710754

>[!Remark]
>Ahora llegamos al enunciado del teorema que nos dará los test UMP-$\alpha$ en el problema unilateral.

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

>[!Remark]
>¿Es posible encontrar un test UMP-$\alpha$ para problemas de hipótesis del tipo $H_0: \theta = \theta_0$ vs $H_1: \theta \ne \theta_0$?
>(Problema de **hipótesis bilateral**).

 >[!Example]
>Sea $X \sim Bi(n, \theta)$, con $0 < \theta < 1$. (ósea el experimento de fondo sigue una $X\sim Ber(\theta)$ entonces las muestras que tomemos serán binomiales) Y tenemos el problema de hipótesis:
>$$H_0: \theta = 0.5\ \text{ vs }\ H_1: \theta \ne 0.5$$
>¿Podemos encontrar un test UMP-$\alpha$ para este problema?. Si uno plantea el problema unilateral:
>$$H_0: \theta=0.5\ \text{ vs }\ H_1^+: \theta > 0.5$$
>Para este problema sabemos encontrar el test UMP-$\alpha$, que es de la forma:
>$$ \varphi^+(x) = \begin{cases} 1 & \text{si } x > k^+ \\ \gamma^+ & \text{si } x = k^+ \\ 0 & \text{si } x < k^+ \end{cases} $$
>donde $k^+$ y $\gamma^+$ se determinan para asegurar que $\alpha = E_{0.5}[\varphi^+(X)]$.
>
>Si uno considera el problema:
>$$H_0: \theta=0.5\ \text{ vs }\ H_1^-: \theta < 0.5$$
>El test MP para $H_0$ vs $H_1^-$ es de la forma:
>$$ \varphi^-(x) = \begin{cases} 1 & \text{si } x < k^- \\ \gamma^- & \text{si } x = k^- \\ 0 & \text{si } x > k^- \end{cases} $$
>donde $\gamma^-$ y $k^-$ se eligen de forma tal que $\alpha = E_{0.5}[\varphi^-(X)]$.
>
>Supongamos que tenemos el test UMP-$\alpha$ para el problema bilateral, y lo llamamos $\varphi^0$.
>Entonces, $\varphi^0$ es el más potente para el problema de hipótesis $$H_0: \theta=0.5\ \text{ vs }\ H_1^+: \theta > 0.5$$
>Esto implica que las funciones de potencia deben ser iguales:
>$$ \beta_{\varphi^0}(\theta) = \beta_{\varphi^+}(\theta) \quad \forall \theta \ge 0.5 $$
>$$ E_\theta[\varphi^0(X)] =\beta_{\varphi^0}(\theta) = \beta_{\varphi^+}(\theta) = E_\theta[\varphi^+(X)] \quad \forall \theta \ge 0.5 $$
>
>Sea $g^+(x) = \varphi^0(x) - \varphi^+(x)$. Entonces:
>$$ 0 = E_\theta[g^+(X)] = \sum_{j=0}^n g^+(j) \binom{n}{j} \theta^j (1-\theta)^{n-j} \quad \forall \theta \ge 0.5 $$
>$$ 0 = (1-\theta)^n \sum_{j=0}^n g^+(j) \binom{n}{j} \left(\frac{\theta}{1-\theta}\right)^j $$
>
>Si $\theta \in [0.5, 1)$, entonces $\eta = \frac{\theta}{1-\theta} \in [1, \infty)$.
>Luego, tenemos un polinomio de grado $n$ en $\eta$ sobre la semirrecta $[1, \infty)$.
>Que es igual a $0$ , el polinomio nulo, lo que implica que sus coeficientes son cero:
>$$ g^+(j) = 0 \quad \forall j \in \{0, \dots, n\} $$
>Luego $$ \varphi^0(j) = \varphi^+(j) \quad \forall j \in \{0, \dots, n\}$$
>Ahora, si consideramos el problema $H_0: \theta=0.5$ vs $H_1^-: \theta < 0.5$ y definimos $g^-(j) = \varphi^0(j) - \varphi^-(j)$, de la misma forma concluimos que
>$$ \varphi^0(j) = \varphi^-(j) \quad \forall j \in \{0, \dots, n\} $$
>
>Juntando ambos resultados, tendríamos $\varphi^-(j) = \varphi^+(j)$ para todo $j$. Lo cual es imposible por definicion de ambas. Concluimos entonces que no existe el test UMP-$\alpha$ para el problema bilateral
>Intuición gráfica de por que no es posible que sean iguales ![[Pasted image 20250726170614.png]]

>[!Remark]
>Como no podemos plantear procedimientos óptimos, ¿qué podemos hacer? (Siguiente teorico) 

