---
dateCreated: 2025-05-25,16:35
---
## Familias exponenciales

>[!Remark]
>Sea $(\Omega_X, \mathcal{F}_X, \mu)$ un espacio de medida, con $\mu$ una medida $\sigma$-finita.
>Supongamos $\Omega_X \subseteq \mathbb{R}^m$ (y la medida $\mu$ puede ser la de contar para el caso discreto).

>[!Definition]
>Sea $T: (\Omega_X, \mathcal{F}_X) \to (\mathbb{R}^k, \mathcal{B}(\mathbb{R}^k))$ un estadístico tal que:
>$$ \int_{\Omega_X} e^{\eta^T T(x)} d\mu(x) < \infty \quad \forall \eta \in \mathbb{R}^k $$
>y sea $\mathcal{E} = \{\eta \in \mathbb{R}^k : \int_{\Omega_X} e^{\eta^T T} d\mu < \infty\}$ el **conjunto de parámetros**.
>Se define la medida de probabilidad:
>$$ P_\eta(B) = \frac{\int_B e^{\eta^T T} d\mu}{\int_{\Omega_X} e^{\eta^T T} d\mu} \quad \forall B \in \mathcal{F}_X, \eta \in \mathcal{E} $$
>y la familia $\{P_\eta : \eta \in \mathcal{E}\}$ se llama **familia exponencial**.
>Una reescritura de la medida de probabilidad es:
>$$ P_\eta(B) = \left( \int_B e^{\eta^T T} d\mu \right) \left( \int_{\Omega_X} e^{\eta^T T} d\mu \right)^{-1}= \int_B e^{\eta^T T - A(\eta)} d\mu $$
>con $A(\eta) = \log \int_{\Omega_X} e^{\eta^T T} d\mu$.

>[!Definition]
>Un estadístico $T: (\Omega_X, \mathcal{F}_X) \to (\mathbb{R}^k, \mathcal{B}(\mathbb{R}^k))$ se dice de **rango completo** con respecto a $\mu$ sobre $\mathcal{F}_X$ si para todo $a \in \mathbb{R}^k \setminus \{0\}$ y todo $c \in \mathbb{R}$, se cumple que:
>$$ \mu(\{x \in \Omega_X : a^T T(x) - c \ne 0\}) > 0 $$
>(O sea, la imagen de $T$ no se concentra en ningún espacio afín o hiperplano).

>[!Remark]
>Si $T$ es de rango completo y define una familia de exponenciales, entonces la familia exponencial se dice de **rango k**.

>[!Lemma]
>Sea $\{P_\eta \in \mathcal{E}_k(T, \mu) \mid \eta \in \mathcal{E}\}$ una familia exponencial de rango $k$.
>$T$ es de rango completo si y sólo si la parametrización es identificable (o sea, la función $\eta \mapsto P_\eta$ es inyectiva).
>>[!Proof]
>>$(\implies)$ Supongamos que $T$ es de rango completo. Supongamos que $P_\eta = P_\theta$ y queremos ver que $\eta = \theta$.
>>$P_\eta = P_\theta \implies P_\eta(B) = P_\theta(B)$ para todo $B \in \mathcal{F}_X$.
>>$$ \int_B e^{\eta^T T - A(\eta)} d\mu = \int_B e^{\theta^T T - A(\theta)} d\mu \quad \forall B \in \mathcal{F}_X $$
>>Esto implica que los integrandos deben ser iguales casi en todas partes con respecto a $\mu$:
>>$$ \mu(\{x: e^{\eta^T T - A(\eta)} \ne e^{\theta^T T - A(\theta)}\}) = 0 $$
>>Aplicando logaritmo:
>>$$ \mu(\{\eta^T T - A(\eta) \ne \theta^T T - A(\theta)\}) = 0 $$
>>$$ \mu(\{ (\eta - \theta)^T T - (A(\eta) - A(\theta)) \ne 0 \}) = 0 $$
>>Como $T$ es de rango completo, por la definición, el conjunto donde esta combinación lineal es cero debe tener medida nula, a menos que el vector de coeficientes sea cero.
>>Por lo tanto, $\eta - \theta = 0$, lo que implica $\eta = \theta$.
>>$(\impliedby)$ Supongamos que la parametrización es identificable y queremos ver que $T$ es de rango completo.
>>Supongamos por el absurdo que no se cumple la condición de rango completo. Es decir, existen $a \in \mathbb{R}^k \setminus \{0\}$ y $c \in \mathbb{R}$ tales que
>>$$ \mu(\{a^T T - c \ne 0\}) = 0 $$
>>Sean $\eta, \theta \in \mathcal{E}$ dos parámetros distintos. Podemos escribir
>>$$ a^T T - c = (\eta - \theta)^T T - c' $$
>>para algún $c'$. Esto implica que
>>$$ (\eta - \theta)^T T = c' \quad \text{c.s. } \mu $$
>>Ahora comparamos las medidas de probabilidad $P_\eta$ y $P_\theta$:
>>$$ P_\eta(B) = \int_B e^{\eta^T T - A(\eta)} d\mu = \int_B e^{(\eta-\theta)^T T + \theta^T T - A(\eta)} d\mu = \int_B e^{c' + \theta^T T - A(\eta)} d\mu $$
>>$$ = e^{c' - A(\eta) + A(\theta)} \int_B e^{\theta^T T - A(\theta)} d\mu = C \cdot P_\theta(B) $$
>>Como ambas son medidas de probabilidad, la constante $C$ debe ser 1.
>>Entonces $P_\eta = P_\theta$ para $\eta \ne \theta$, lo cual contradice la identificabilidad de la parametrización.
>>Por lo tanto, $T$ debe ser de rango completo.