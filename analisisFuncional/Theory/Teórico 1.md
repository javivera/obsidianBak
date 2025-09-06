---
dateCreated: 2024-09-21,00:32
tags:
  - Riesz
  - FunctionalAnalysis
  - normEquivalences
  - banachSpace
  - vectorSpace
---
>[!Definition] Espacio Normado
> X e.v.s sobre $\mathbb{F}$ ($\mathbb{R}$ o $\mathbb{C}$). Una norma en $X$ es una función $\|\cdot\|: X \to \mathbb{R}$ / $\forall x,y \in X$ y $\forall \alpha \in \mathbb{F}$. Se tiene:
> - (1) $\|x\| > 0$
> - (2) $\|x\| = 0 \iff x=0$
> - (3) $\|\alpha x\| = |\alpha| \|x\|$ 
> - (4) $\|x+y\| \le \|x\| + \|y\|$

^cffc55

## Ejemplos de normas

>[!Example]
>La función $\|\cdot\|: \mathbb{F}^n \to \mathbb{R}$. Dada por $$\|(x_1,\ldots,x_n)\| = (\sum |x_j|^2)^{1/2}$$ es una norma en $\mathbb{F}^n$ y se dice norma estándar en $\mathbb{F}^n$. 

>[!Example] Algunas normas
>- (1) Sea $X$ un e.v. de dim finita sobre $\mathbb{F}$ con base {$e_1, \dots, e_n$}. Todo $x \in X$ se puede escribir como $x=\sum \lambda_j e_j$ con $\lambda_j \in \mathbb{F}$ únicos.  La función $\|\cdot\|: X \to \mathbb{R}$ toda por $\|x\| = (\sum |\lambda_j|^2)^{1/2}$ es una norma en $X$. En efecto es fácil ver que valen (1)-(3) (ej). 
>Para ver (4) sean $x = \sum \lambda_j e_j$ $y=\sum \mu_j e_j$ entonces $$\begin{align}\|x+y\|^2 = \sum|\lambda_j+\mu_j|^2 & = \sum (|\lambda_j|^2 + 2\text{Re}(\lambda_j\bar{\mu_j}) + |\mu_j|^2) \\&\le \sum |\lambda_j|^2 + 2|\lambda_j||\mu_j| + |\mu_j|^2 \\& \le \sum |\lambda_j|^2 + 2(\sum |\lambda_j|^2)^{1/2}(\sum |\mu_j|^2)^{1/2} + \sum |\mu_j|^2 \\& = \|x\|^2 + 2\|x\|\|y\| + \|y\|^2\\&= (\|x\|+\|y\|)^2\end{align}$$
>(Recordar Holder $\sum|x_j||y_j| \le (\sum|x_j|^p)^{1/p}(\sum|y_j|^q)^{1/q}\quad\text{con }\frac{1}{p}+\frac{1}{q}=1$)
>-  (3) Sea M un esp métrico compacto y $C_{\mathbb{F}}(M)$ el ev de.. sigue y no copie
>- (4) Sea $(X, \Sigma, \mu)$ esp medida y consideremos $L_p(X)$, con $1 \le p \le \infty$
> 	- (a) si $1 \le p < \infty$, $\|f\|_p = (\int|f|^p)^{1/p}$ es norma
> 	- (b) si $p=\infty$ $\|f\|_\infty = \text{sup ess } |f|$ es norma ($L^\infty(X)$) (ej) p35 young
>- (5) Si tenemos caso particular de (4) $(\mathbb{N}, P(\mathbb{N}), \mu_c)$ la medida de contar (i.e. la cantidad de elementos de $S$). Recordar toda funcion $f:\mathbb{N} \to \mathbb{F}$ puede verse como una sucesión $$\{a_n\}_{n\in \mathbb{N} }\quad \text{sugiere }\quad a_n=f(n)$$
> Entonces sucede que $$f\text{ integrable resp de }\mu_c\iff\sum_{n=1}^\infty |a_n|<\infty$$ Y sucede $$\int_\mathbb{N} f d\mu_c = \sum_{n=1}^\infty a_n$$ Sea $\ell^p(\mathbb{N}) = \ell^p$ el conj de todas las suc $$\{ x_{n} \}\subset \mathbb{F} \quad\text{ tal que }\quad\sum x_n < \infty \quad (1 \le p < \infty)$$. Definimos $\ell^{\infty}$ como el conj de sucesiones acotadas. Luego  $$\|{x_n}\|_p = (\sum|x_n|^p)^{1/p}\quad\quad\|{x_n}\|_\infty = \sup|x_n|$$
>son normas.
>Nota: que hölder (vale para infinito) $$\begin{align}\|x_{n}y_{n}\|_1 & =\sum^{\infty}_{n=1}|x_{n}y_{n}|\\& = \int_N |fg| \\&= \int|f||g| \\&\le \left( \int|f|^p \right)^{1/p}\left( \int|g|^q \right)^{1/q} = \|x_{n}\|_p\|y_{n}\|_q\end{align}$$ 
>$\equiv \sum_{n=1}^\infty |X_n Y_n| = \|X_n Y_n\| \le \|f\|_p \|g\|_q = (\sum_{n=1}^N |X_n|^p)^{1/p}(\sum_{n=1}^N |y_n|^q)^{1/q}$
>- (6) Si $X$ es un ev con $\|\cdot\|$ y $S$ es un ev ent $\|\cdot\|_S$ dede por restricción de $\|\cdot\|$ en $X$ es una norma en $S$
>- (7) Si $X,Y$ son norm. con $\|\cdot\|_1, \|\cdot\|_2$ respect $\Rightarrow Z=X \times Y$ es normado con $\|(x,y)\|_z = \|x\|_1 + \|y\|_2$ (ej)

>[!Remark]
>Un espacio vectorial en el que hay una norma se dice espacio vectorial normado y $x \in X$ / $\|x\|=1$ se dice unitario.

>[!Lemma] Todo normado es metrico
>Sea $X$ espacio vectorial con norma $\lVert \cdot \rVert_{}$. Sea $$d:X\times X\rightarrow \mathbb{R} \quad \text{ donde }\quad d(x,y)=\lVert x-y \rVert_{}$$entonces
>$$(X,d)\text{ es metrico}$$ 
>(Equivalentemente todo $X$ espacio vectorial normado es metrico con la metrica estandar)
>>[!Proof]-
>>1. $d(x,x)=||0||=0$
>>2. $d(x,y)=||x-y||\geq 0$ so $x\neq y$  
>>3. $d(x,y)=||x-y||=||-(y-x)||=||y-x||=d(y,x)$
>>4. $d(x,z)=||x-y+y-z||\leq ||x-y||+||y-z|| = d(x,y)+d(y,z)$ 
>>5. Entonces $d$ es metrica entonces $(X,d)$ es espacio metrico 

^59c764

>[!Remark] Metrica no necesariamente induce norma
>Si X es un ev con una métrica d en gral no es cierto que exista una norma tal que $d(x,y)=\|x-y\|$ 
>(ejemplo $d$ acotada $d(x,y)\le M$ ent no vale $(3)$ (definicion norma) 
>

^8f0ed9

>[!Remark] Caso donde metrica induce norma
>Si una métrica es:
>- Homogénea $$d(\alpha x, \alpha y) = |\alpha|d(x,y)$$
>- Invariante por translación: $$d(x,y) = d(x+z, y+z)$$
>Entonces existe una norma tal que $d(x,y)=||x-y||$ 
>>[!Proof]-
>>1. Definimos $d(x,y)=||x-y||$  
>>2. Por ser $d$ homogénea $||\cdot||$ cumple $(3)$ 
>>3. Luego usando invarianza de $d$  $$\begin{align}\|x+y\|&=d(x+y,0)\le d(x+y,x)+d(x,0) \\&  \leq d(y,0)+d(x,0)\quad (\text{invarianza})\\&= \|y\|+\|x\|\end{align}$$
>>entonces $||\cdot||$ cumple $(4)$
>>4. $(1)$ Y $(2)$ trivial por def
>>5. Entonces $||\cdot||$ es norma

^4446de

> [!theorem] Continuidad de norma, suma y producto
>Sea $X$ espacio vectorial con norma $\lVert \cdot \rVert_{}$. Sea $x_{n}\rightarrow x$, $y_{n}\rightarrow y$ con $\{ \alpha_{n} \}\subseteq \mathbb{F}$ y $\alpha_{n}\rightarrow\alpha$ entonces:
>1. $\big\lvert \lVert x \rVert_{} -\lVert y \rVert_{}\big\rvert\leq \lVert x-y \rVert_{}$
>2. $\lim_{ n \to \infty }\lVert x_{n} \rVert_{}=\lVert x \rVert_{}$
>3. $\lim_{ n \to \infty }x_{n}+y_{n}=x+y$
>4. $\lim_{ n \to \infty }\alpha_{n} x_{n}=\alpha x$
>>[!Proof]-
>> 1. Sale usando $\lVert x \rVert\leq \lVert x-y \rVert+\lVert y \rVert$
>> 2. Sale usando 1
>> 3. $\|x_{n} + y_{n}- (x+y)\|\leq \|x_{n}-x\|+\|y_{n}-y\|\rightarrow 0$ 
>> 4. $\|\alpha_{n} x_{n}-\alpha x\|= \|\alpha_{n} (x_{n}-x)+(\alpha_{n}-\alpha) x\|\leq |\alpha_{n}|\|x_{n}-x\|+|\alpha_{n}-\alpha |\|x\|\rightarrow 0$  

^650441

>[!Remark]
>Esto nos dice que en un espacio vectorial normado, la norma, la suma y producto por escalar son continuas.

>[!Definition] Equivalencia de normas
>Sea $X$ espacio vectorial y  $\lVert \cdot \rVert_{1},\lVert \cdot \rVert_{2}$ normas en  $X$ decimos que son equivalentes si $$\exists\ m,M>0\quad /\quad m\lVert x \rVert _{1}\leq \lVert x \rVert _{2}\leq M\lVert x \rVert_{1} $$

^b51eea

>[!Remark] Equivalencia de normas es una relacion de equivalencia
>La equivalencia de normas es una relacion de equivalencia
>>[!Proof]-
>>1. Reflexividad. Una norma es equivalente con si misma usando $m=M=1$ 
>>2. Simetria. Por definición de equivalencia 
>>3. Transitividad: 
>>	- Como norma 1 es equivalente a norma 2 $m_{1,2}\|x\|_{1}\leq \|x\|_{2}\leq M_{1,2}\|x\|_{1}$ 
>>	- Como norma 2 es equivalente a norma 3 $m_{2,3}\|x\|_{2}\leq \|x\|_{3}\leq M_{2,3}\|x\|_{2}$ 
>>	- Entonces $$m_{1,2}m_{2,3}\|x\|_{1}\leq m_{2,3}\|x\|_{2}\leq \|x\|_{3}\leq M_{2,3}\|x\|_{2}\leq M_{2,3}M_{1,2}\|x\|_{1}$$

^2230e0

>[!Corollary] propiedades de normas equivalentes
>Sea $X$ espacio vectorial $\lVert \cdot \rVert_{}$ y $\lVert \cdot \rVert_{1}$ normas equivalentes en $X$ con $d,d_1$ metricas asociadas. Sea $\{ x_{n} \}\subseteq X$ entonces:
>1.$\quad x_{n}\rightarrow x$ en $(X,d)\iff x_{n}\rightarrow x$ en $(X,d_{1})$
>2.$\quad \{ x_{n} \}$ es de cauchy en $(X,d)\iff \{ x_{n} \}$ es de cauchy en $(X,d_{1})$ 
>3.$\quad (X,d)$  es completo $\iff (X,d_{1})$ es completo   
>>[!Proof]-
>>Usando [[#^650441]] y que equivalencia de normas

^cd6dc0

>[!Theorem] Continua en compacto tiene maximo y minimo
>Sea $(X,d)$ metrico compacto y $f:M\rightarrow \mathbb{F}$ continua entonces $\exists c>0 \ / \ \lvert f(x) \rvert\quad\forall x \in M$ ($f$ acotada)
>En particular si $\mathbb{F}=\mathbb{R}$ los numeros
>$$a = \sup\{ \lvert f(x) \rvert :x \in M\}$$
>$$b = \inf\{ \lvert f(x) \rvert :x \in M\}$$
>Existen y son finitos. Mas aun 
>$$\exists \ x,y \in M \ f(x)=a \ \ \land f(y)=b$$

^8b9dd8

>[!Theorem] Equivalencia de normas finitas a norma coeficiente
>Sea $X$ espacio vectorial normado de dim finita con norma $\lVert \cdot \rVert$. Sea $\{ e_{1},\ldots,e_{n} \}$ base para $x=\sum\alpha_{j}e_{j}$ y sea $\lVert x \rVert_{c}=\left( \sum|\alpha_{j}|^{2} \right)^{\frac{1}{2}}$ entonces $\lVert \cdot \rVert_{c}$ y $\lVert \cdot \rVert$ son equivalentes
>>[!proof]-
>>1. $M=(\sum \lVert e_{j} \rVert^2)^{\frac{1}{2}}>0$
>>2. Usando Hölder vemos que $$\lVert x \rVert=\left\lVert  \sum\alpha_{j}e_{j}  \right\rVert\leq \sum \lVert \alpha_{j}e_{j} \rVert=\sum\bigg||\alpha_{j}|\lVert e_{j} \rVert\bigg| \leq \big( \sum|\alpha_{j}|^2\big)^{\frac{1}{2}} \big(\sum\lVert e_{j} \rVert^2\big)^{\frac{1}{2}} = \lVert x \rVert_{c}M$$ por lo tanto ya tenemos una desigualdad
>>3. Sea $f:\mathbb{F}^{n}\rightarrow \mathbb{R}\quad f(\alpha_{1},\ldots,\alpha_{n})=\left\lVert  \sum\alpha_{j}e_{j}\right\rVert =\lVert x \rVert$
>>4. Podemos ver que es continua $$\biggl\lvert \left\lVert  \sum\alpha_{j}e_{j}  \right\rVert-\left\lVert  \sum\beta_{j}e_{j} \right\rVert \biggl\rvert \leq\|\sum\alpha_{j}e_{j}- \sum \beta_{j}e_{n}\|=\|\sum(\alpha_{j}-\beta_{j})e_{j}\|\leq \sum|\alpha_{j}-\beta_{j}|\|e_{j}\|\leq ( \sum|\alpha_{j}-\beta_{j}|^2)^{\frac{1}{2}} (\sum\lVert e_{j} \rVert^2)^{\frac{1}{2}}\leq \|\alpha_{j}-\beta_{j}\|_{2}M$$ 
>>(Asumimos aca $(\mathbb{F}^{n},\|\cdot\|_{2})$) 
>>5. $S=\left\{  (\alpha_{1},\dots,\alpha_{n}):\sum|\alpha_{j}|^2 = 1  \right\}$ es compacto. 
>>	- Cerrado: Sea $g:\mathbb{F}^{n}\rightarrow\mathbb{R}$ dada por $g(\alpha_{1},\ldots,\alpha_{n})=\sum^{n}_{i=1}|\alpha_{j}|^{2}$ es continua por que suma producto y modulo son continuas. Luego como $\{ 1 \}$ es cerrado en $\mathbb{R}$ entonces $g^{-1}(\{ 1 \})=S$ es cerrado
>>	- Acotada: Sea $\alpha \in S$ entonces $\|\alpha \|_{2}=\sum(|\alpha_{j}|^{2})^{1/2}=1$ entonces $\alpha \in \overline{B}(0,1)$ mostrando que $S\subseteq \overline{B}(0,1)$  
>>6. Entonces existe $m = f(u_{1},\dots,u_{n})$ minimo (en el compacto) porque $\mathrm{Im}f =\mathbb{R}$ [[#^8b9dd8]]
>>7. $m >0$ porque si fuese $0$ entonces $\sum^{n}_{i=1}u_{j}e_{j}=0$ y como $\{ e_{j} \}$ es base entonces $u_{i}=0$ por lo tanto $(u_{1},\ldots,u_{n})\not\in S$ absurdo porque $m$ es minimo del compacto, osea pertenece al compacto 
>>8. Si $\lVert x \rVert_{c}=1 \iff \sum|\alpha_{j}|^2=1 \Rightarrow(\alpha_{1},\dots,\alpha_{n})\in S$ 
>>9. Entonces como estamos en el compacto $m\lVert x \rVert_{c} = m\leq f(\alpha_{1},\dots,\alpha_{n})=\lVert x \rVert$ por ser m minimo
>>10. Si no $\left\lVert  \frac{x}{\lVert x \rVert}_{c}  \right\rVert=1$ luego $m \leq \left\lVert  \frac{x}{\lVert x \rVert}_{c}  \right\rVert$ por el caso de arriba

^a9c775

>[!Corollary] Normas son equivalentes en dim finita
>En dimension finita todas las normas son equivalentes
>>[!Proof]-
>> Equivalencia de normas es relacion de equivalencia entonces es transitiva y [[Teórico 1#^a9c775]]

^fd2535

> [!remark] Contraejemplo a equivalencia de normas en dim infinta
>Esto no vale en dimension infinita $X=C^1[0,\pi]$ tenemos dos normas no equivalentes 
>$$\lVert \cdot \rVert_{\infty} \quad \text{ y }\quad \lVert u \rVert =\lVert u \rVert_{\infty}+\left\lVert  u'  \right\rVert_{\infty}$$
>Considerando la funcion $u_{n}(x)=sen(nx)$ se puede ver facilmetend
>

^5fe893

>[!Lemma] $d_{1}$ es completo
> X espacio vectorial de dim finita y $\lVert \cdot \rVert_{c} =\left( \sum \lvert \alpha_{j} \rvert^2 \right)^{\frac{1}{2}}$ y $d_{1}$ la metrica asociada, entonces $(X,d_{c})$ es completo (Banach)
>>[!Proof]-
>> 1. Ya sabemos que es metrico, por ser normado, lo suponemos de dimension finita $N$
>> 2. Sea $\{ x^{n} \}\subseteq X$ suc de cauchy con $$x^{n}\in X\quad x^{n}=\sum_{j}^{N}\alpha_{j}^n e_{j}\quad \alpha_{j}^n\in \mathbb{F}$$
>> 3. Luego $\exists m_{0}\in \mathbb{N}$ tq $$\sum \lvert \alpha_{j}^k-\alpha_{j}^m \rvert^{2}=\lVert x^{k}-x^{m} \rVert_{c}^{2}\leq \epsilon^2$$
>> 4. Fijando $j\in \mathbb{N}$ tenemos $\lvert \alpha_{j}^k-\alpha_{j}^m \rvert\leq\epsilon^2\quad \forall k,m\geq m_{0}$
>> 5. $\{ \alpha_{j}^n \}_{n\in \mathbb{N}}$ es de cauchy en un completo $\mathbb{F}$ entonces tiene limite $\alpha_{j}$ (vale para cada $j$)
>> 6. $\exists n_{j}\in \mathbb{N}$ tq $\lvert \alpha_{j}^n -\alpha_{j} \rvert < \frac{\epsilon^2}{N} \quad\forall n\geq n_{j}$ 
>> 7.  Definimos $\tilde{n}=max\{ n_{0},\dots,n_{N} \}$ y proponemos $x=\sum^{N}_{j=1}\alpha_{j}e_{j}$ como límite de $x_{n}$ 
>> 8. Por definición $x\in X$ , por ser combinacion lineal de elementos de la base
>> 9. para $m\geq \tilde{n}$ sucede $$\lVert x^{n}-x \rVert_{c}^2=\sum_{j}^N\lvert \alpha _{j}^n-\alpha_{j} \rvert^2\leq \epsilon^2$$ Mostrando que $\{ x^{n} \}$ converge a $x$ 
>> 10. Por lo tanto $X$ es de completo

^910368

>[!Corollary] Todo EV de dim finita es completo
>Todo espacio vectorial de dim finita es completo con la metrica asociada a cualquier norma
>>[!Proof]-
>>1. Todas las normas son equivalentes a $||\cdot||_{c}$ por [[#^a9c775]]
>>2. Entonces $(X,d)$ completo$\iff(X,d_{c})$ completo por [[#^cd6dc0]] 
>>3. Finalmente [[#^910368]]

^26042d

>[!Theorem] Resultados en métricos
> Sea $(M,d)$ metrico y $A\subseteq M$ entonces:
> 1. $A$ completo $\Rightarrow A$ cerrado
> 2.  $M$ completo $\Rightarrow$ ($A$ completo $\iff A$ cerrado)
> 3. Si $A$ es compacto $\Rightarrow$ $A$ es cerrado y acotado
> 4. Cerrado y acotado en $\mathbb{F}^n \Rightarrow$ compacto
>>[!Proof]
>>1. Probar Searcoid metric spaces o topology munkress 
^83c633

>[!Corollary] Todo sub ev de dim finita es cerrado
>Si $Y$ subespacio vectorial de dim finita $\Rightarrow$ $Y$ es cerrado
>>[!Proof]-
>>2. Por ser $Y$ espacio vectorial de dim finita, es normado (norma estandar) por ser espacio vectorial normado es metrico [[#^59c764]]
>>3. Por dim finita es completo [[#^26042d]]
>>4. Cerrado por 1. [[#^83c633]]
^3196e0

> [!remark] Contraejemplo en dim infinita a $Y$ subespacio vectorial implica $Y$ cerrado 
> [[#^3196e0]] no es cierto si la dimension es infinita
>>[!Proof]-
>>4. $S=\bigg\{ \{ x_{n} \} \subseteq\ell^{\infty}:\exists n_{0}\in \mathbb{N} \ / \ x_{n}=0 \ \forall n\leq n_{0} \bigg\}$
>>5. S subespacio de dim infinita de $\ell^{\infty}$
>>6. $x_{n} = (1, \frac{1}{2},\dots, \frac{1}{n},0,\dots,0,\ldots) \in S$
>>7. Sea $x=\left( 1, \frac{1}{2},\dots, \frac{1}{n}, \frac{1}{n+1},\dots \right)\in (\ell^{\infty}\setminus S)$ 
>>8. $\lVert x-x_{n} \rVert_{\infty} = \frac{1}{n+1}\rightarrow 0$ o lo mismo $\lim_{ n \to \infty }x_{n}=x$
>>9. $S$ no es cerrado

^0676dc

>[!Lemma] Clausura de sub espacio es subespacio
> $X$ espacio vectorial normado, $S$ subespacio de $X$ entonces $\overline{S}$ es subespacio vectorial de $X$
>>[!Proof]-
>>1. $x,y\in \overline{S},\ \alpha \in \mathbb{F}$
>>2. Por ser clausura existen $x_{n}\rightarrow x, \ y_{n}\rightarrow y$ en $S$
>>3. $S$ es subespacio entonces $x_{n}+y_{n}\in S$
>>4. Además $x_{n}+y_{n}\rightarrow x+y$ por [[#^650441]]
>>5. entonces $x+y\in\overline{S}$
>>6. Analogo $\alpha x_{n}$

^4c773a

>[!Definition] Span
> $E\subseteq X$ normado:
> $$Sp(E) = \{ \text{Todas las combinaciones lineales finitas de elmentos de } E\}$$
> $$\overline{Sp}(E)=\{\text{Todas las intersecciones de subespacios cerrados que contienen a }E \}$$

^f2fb50

>[!Lemma] Propiedades del span
>$X$ espacio vectorial normado $\emptyset\neq E \subseteq X$ entonces: 
>(a) $\overline{Sp}(E)$ es un cerrado de $X$ que contiene a $E$
>(b) $\overline{Sp}(E) = \overline{Sp(E)}$
>>[!Proof]-
>>(a)
>>1. Intersección de cerrados es cerrado e interseccion de subespacios es subespacio
>>
>>(b) 
>>2. Como $Sp(E)$ es sub espacio $\overline{Sp(E)}$ es subespacio por [[#^4c773a]]. Además cerrado y contiene a $E$ por def
>>	- ($\subseteq$) $\overline{Sp(E)}$ es subespacio cerrado que contiene a $E$ entonces por definición $\overline{Sp}(E)\subseteq\overline{Sp(E)}$
>>	- ($\supseteq$) Notar $\overline{Sp}(E)$ es cerrado y contiene a $Sp(E)$ por que si $M$ subesp que contiene a $E$ por linealidad contiene toda combinación lineal finita entonces $Sp(E)\subseteq M$. En particular vale para subespacios $M$ cerrados entonces $Sp(E)$ está en todos los elementos que componen la intersección que genera $\overline{Sp}(E)$. Luego por def de clausura $\overline{Sp}(E)\supseteq \overline{Sp(E)}$

^f320eb

>[!Lemma] Riesz
>Sea $X$ normado, $Y$ subespacio cerrado  con $Y\neq X$. Sea $\alpha \in(0,1)$. Entonces $\exists x_{\alpha}\in X$ con $\lVert x_{\alpha} \rVert=1$ tal que $\lVert x_{\alpha}-y \rVert >\alpha \quad \forall y\in Y$ 
>>[!Proof]-
>>1. Tomamos $x\in X\setminus Y$ cualquiera. Luego  $d=\inf\{ \lVert x-z \rVert:z\in Y \}>0$
>>2. $0<\alpha<1  \Rightarrow d<d\alpha ^{-1}$
>>3. Entonces por definición de ínfimo $\exists z\in Y$ tal que $d<\lVert x-z \rVert<d\alpha ^{-1}$
>>4. $x_{\alpha}=\frac{x-z}{\lVert x-z \rVert}$ luego $\lVert x_{\alpha} \rVert=1$. Esto nos dice que $x_{\alpha }\not\in Y$ porque si no $x=x_{\alpha }\|x-z\|+z \in Y$ absurdo
>>5. $\lVert x_{\alpha}-y \rVert =\left\lVert  \frac{x-z}{\lVert x-z \rVert }-y  \right\rVert = \frac{1}{\lVert x-z \rVert }\lVert x-(z+\lVert x-z \rVert y) \rVert > \frac{d}{d\alpha ^{-1}}$

^ae7428

>[!Theorem] No compactos en dimension infinita
>Sea $X$ espacio vectorial dimension infinita 
>$$D=\{ x \in X:\lVert x \rVert_{} \leq 1 \}\quad K=\{ x \in X: \lVert x \rVert_{} =1 \}$$
>no son compactos
>>[!Proof]-
>>1. $x_{1}\in K$ como dim infinita $Sp(\{ x_{1} \})\neq X$ además $Sp$ es cerrado por ser de dim finita [[#^3196e0]]
>>2. Entonces vale [[#^ae7428]] $\exists x_{2}\in K$ tal que $\lVert x_{1}-x_{2} \rVert_{}\geq \frac{1}{2}$
>>3. Hacemos lo mismo con $Sp(\{ x_{1},x_{2} \})$ ósea encontramos $x_{3}$ tal que $|| x_{i} -x_{3}||> \frac{1}{2}\quad i=1,2$ 
>>4. Generalizando $\exists x_{n}\in K$ tal que $\lVert x_{n}-x_{m} \rVert_{}\geq \frac{1}{2}\quad\forall n\neq m$
>>5. Asi armamos una sucesion que no puede tener sub convergente porque si fuese convergente seria de cauchy (Notar que si asumimos choice todo ev es normado y todo normado es métrico entonces es secuencialmente compacto por eso se puede usar la contradicción)

^8db74f

>[!Remark] Si son compactos entonces es de dim finita
>$D$ y $K$ son compactos $\Rightarrow$ $X$ dim finita

^94f211

>[!Definition] Espacio de Banach
> Un espacio de Banach es un espacio normado que es completo con la metrica asociada a la norma

^1ccf36

>[!Theorem] Propiedades de espacios de Banach
>1. Todo normado de dim finita es Banach
>2. Si $X$ es metrico completo $C_{\mathbb{F}}$ es banach
>3. Si $(X,\sum,\mu)$ subespacio medible $\Rightarrow L^p(X) \ (1\leq p\leq \infty)$ son banach
>(En particular $\ell^p \ (1\leq p\leq \infty$ son banach)
>4. $X$ Banach, $Y$ subespacio entonces $Y$ Banach $\iff Y$ cerrado
>>[!Proof]-
>>1. Visto arriba [[#^26042d]]
>>2. Se asume visto en Reales 
>>3. Se asumen visto en Reales
>>4. [[#^83c633]]

^49a70f

>[!Theorem] Otra propiedad en Banach
>Sea $X$ de Banach $\{ x_{n} \} \subseteq X$. Si la serie $\sum\lVert x_{n} \rVert_{}$ converge entonces $\sum x_{k}$ converge
>>[!Proof]-
>>1. $\bigg\lvert  \sum^m \lVert x_{k} \rVert - \sum^n \lVert x_{k} \rVert \bigg\rvert =\sum^m_{k=n+1} \lVert x_{k} \rVert \leq\epsilon \quad\forall m\geq n\geq n_{0}$ (por ser convergente la serie, las sumas parciales son de cauchy)
>>2. Sea $S_{n}=\sum^n x_{k}$ entonces $\lVert S_{m}-S_{n} \rVert\leq \lVert  \sum^m_{k=n+1}x_{k}  \rVert\leq \sum^m_{k=n+1}\lVert x_{k} \rVert\leq\epsilon$
>>3. Entonces $S_{n}$ es una sucesión de Cauchy en $X$. Como $X$ completo $S_{n}$ converge

^1fb9a8
