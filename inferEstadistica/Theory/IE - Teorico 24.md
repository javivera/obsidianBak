## Test de hipótesis

>[!Remark]
>Sea $\mathcal{P}$ el conjunto de funciones de distribución del modelo estadístico. Tratemos de "descubrir" si la distribución desconocida subyacente $P_0$ pertenece a un subconjunto $\mathcal{P}_0$ o $\mathcal{P}_1$ de $\mathcal{P}$ tal que $\mathcal{P} = \mathcal{P}_0 \cup \mathcal{P}_1$ y $\mathcal{P}_0 \cap \mathcal{P}_1 = \emptyset$.
>(O equivalentemente, $\theta \in \Theta_0$ o $\theta \in \Theta_1$ si $\mathcal{P}$ es una familia paramétrica identificada por $\theta \in \Theta = \Theta_0 \cup \Theta_1$ (con $\Theta_0 \cap \Theta_1 = \emptyset$)).
>
>Como siempre, tenemos los espacios medibles $(\Omega, \mathcal{F})$ y $(\Omega_X, \mathcal{F}_X)$, y una variable aleatoria $X: \Omega \to \Omega_X$. Tenemos el conjunto de distribuciones $\mathcal{P}$ definido sobre $\mathcal{F}_X$ tal que $\mathcal{P} = \mathcal{P}_0 \cup \mathcal{P}_1$ y $\mathcal{P}_0 \cap \mathcal{P}_1 = \emptyset$.
>
>Queremos formular las hipótesis:
>- **Hipótesis nula** $H_0: P_0 \in \mathcal{P}_0$
>- **Hipótesis alternativa** $H_1: P_0 \in \mathcal{P}_1$
>
>Una idea posible para construir un test de hipótesis podría ser: "Si el vector observado $X$ es **improbable** de ocurrir bajo las distribuciones de $\mathcal{P}_0$, entonces se decide rechazar $H_0$ (que $P_0 \in \mathcal{P}_0$) y se acepta $H_1$."
>
>¿Qué tratamos de decir con "improbable"?
>Sea $C \in \mathcal{F}_X$ un conjunto tal que la probabilidad $Q(C)$ es "chica" para toda distribución $Q \in \mathcal{P}_0$. Si el dato $X$ cae en $C$, como tiene pocas chances de ocurrir bajo las distribuciones de $\mathcal{P}_0$, decidimos rechazar $H_0$ y aceptar $H_1$.
>
>- Entonces, la decisión de rechazar (o no) $H_0$ está asociada a encontrar una **región de rechazo** $C$ (o **región crítica**).
>- En general, llamaremos **región de rechazo** a un conjunto $C \in \mathcal{F}_X$ tal que se rechaza $H_0$ si $\underline{X} \in C$. Una regla de decisión así construida se suele denominar **test de no aleatoriedad**.
>
>Al tomar la decisión de rechazar $H_0$ podemos cometer dos tipos de error:
> - i) Rechazar $H_0$ siendo $H_0$ verdadera (**Error de Tipo I**).
> - ii) Aceptar $H_0$ siendo $H_0$ falsa (**Error de Tipo II**).
>
>Se nombran **error de tipo 1** y de **tipo 2** respectivamente.

>[!Definition] Nivel y Potencia del test
>Para un test no aleatorizado definido por una región de rechazo $C$, se denomina **nivel del test** a:
>$$ \alpha(C) = \sup_{P_X \in \mathcal{P}_0} P_X(C) $$
>donde $P_X(C) = P(X \in C)$.
>Se llama **potencia del test** para la distribución $P_X$ a la función:
>$$ \beta(P_X) = P_X(C) = P(X \in C) $$
>(Notar que $\beta(P) \le \alpha(C)$ para todo $P \in \mathcal{P}_0$).
>
>- La potencia $\beta(P)$ es la probabilidad de cometer un Error de Tipo I si la verdadera distribución es $P \in \mathcal{P}_0$.
>- Si la verdadera distribución es $P \in \mathcal{P}_1$, la potencia es:
>$$ \beta(P) = P_X(C) = 1 - P(X \notin C) = 1 - P(\text{Error de Tipo II}) $$
>O sea, que para distribuciones en la alternativa, tener un Error de Tipo II bajo es equivalente a tener una potencia alta.

![[Pasted image 20250726121442.png]]

>[!Remark]
>Una hipótesis en el mundo real no se puede confirmar en forma concluyente, pero se puede negar en forma concluyente.
>Por eso, en general, lo que se coloca como hipótesis nula es lo opuesto de lo que queremos comprobar. Basados en la evidencia provista por los datos es que vamos a rechazar $H_0$ y aceptar $H_1$.
>Luego, en general, $H_1$ contiene la hipótesis científica que queremos comprobar.

>[!Remark]
>No podemos minimizar simultáneamente ambos errores.

>[!Example]
>Sea $X \sim Bi(n, \theta)$, con $0 \le \theta \le 1$.
>Tomemos $n=2$. Las hipótesis son:
>$$H_0: \theta = 1/2 \quad vs \quad H_1: \theta = 1/6$$
>Las familias de distribuciones son:
>$$\mathcal{P}_0 = \{Bi(2, 1/2)\}\mathcal{P}_1 = \{Bi(2, 1/6)\}$$
>La función de probabilidad puntual es:
>$$ p(x; \theta) = \binom{n}{x} \theta^x (1-\theta)^{n-x}, \quad x \in \{0, 1, 2\} $$
>![[Pasted image 20250726121719.png]]
>¿Qué valores para $P(\text{ET I})$ y $P(\text{ET II})$ según diferentes elecciones de región de rechazo $C$? Regla: Rechazar $H_0$ si $x \in C$.
>![[Pasted image 20250726121754.png]]
>##Conclusión:** Del ejemplo surge que no podemos simultáneamente hacer tan pequeños como queramos ambos errores.
>Como dijimos, vamos a tratar de achicar la probabilidad de Error de Tipo I, atendiendo a la noción de test de hipótesis.

>[!Definition] Test
>Se llamará **test** a cualquier función $\varphi: (\Omega_X, \mathcal{F}_X) \to (, \mathcal{B})$ que sea medible. 
>El test se dice **aleatorizado** si existe $x \in \Omega_X$ tal que $0 < \varphi(x) < 1$. Y se dice **no aleatorizado** si $\varphi: \Omega_X \to \{0,1\}$.

>[!Remark]
>Si $C$ es una región de rechazo, y definimos $$\varphi(x) = \begin{cases} 1 & \text{si } x \in C \\ 0 & \text{si } x \notin C \end{cases}$$
>entonces este es un test no aleatorizado. 
>El nivel del test, en este contexto, se escribe como:
>$$ \alpha(C) = \sup_{P_X \in \mathcal{P}_0} P_X(C) = \sup_{P \in \mathcal{P}_0} E_P[\varphi(X)] $$
>Esto es porque la esperanza de una variable aleatoria que toma valores 0 y 1 es:
>$$E_P[\varphi(X)] = 1 \cdot P_P(X \in C) + 0 \cdot P_P(X \notin C) = P_P(X \in C)$$

>[!Definition] Nivel de significancion y tamaño del test
>Sea $\varphi$ una función test y un problema de hipótesis $$H_0: P_0 \in \mathcal{P}_0\ \text{ vs }\ H_1: P_0 \in \mathcal{P}_1$$
>Se dice que $\varphi$ tiene **nivel de significación** $\alpha$ si:
>$$ \sup_{P \in \mathcal{P}_0} E_P[\varphi(x)] \le \alpha $$
>A la cantidad $\sup_{P \in \mathcal{P}_0} E_P[\varphi(x)]$ se la denomina **tamaño del test**.

>[!Definition] Funcion potencia de test
>La función $\beta_\varphi: \mathcal{P} \to [0,1]$, donde $\mathcal{P} = \mathcal{P}_0 \cup \mathcal{P}_1$, dada por
>$$ \beta_\varphi(P) = E_P[\varphi(X)] $$
>se dice **función de potencia** del test.

>[!Remark]
>En general, se desea que la potencia sea lo más grande posible en las distribuciones de la alternativa.