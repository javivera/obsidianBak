---
dateCreated: 2024-09-23,08:32
---
>[!Definition] Producto interno
> Un ev sobre $\mathbb{R}$ ($\mathbb{C}$). Un p.i. en X es una funcion $X \times X \to \mathbb{R} (\mathbb{C})$ tq $\forall x,y,z \in X, \quad \forall \alpha, \beta \in \mathbb{R} (\mathbb{C})$
> - a) $\langle x,x \rangle \ge 0 \quad$ (y $\langle x,x \rangle \in \mathbb{R}$)
> - b) $\langle x,x \rangle = 0 \iff x=0$
> - c) $\langle \alpha x + \beta y, z \rangle = \alpha \langle x,z \rangle + \beta \langle y,z \rangle$
> - d) $\langle x,y \rangle = \langle y,x \rangle\quad\big(\langle x,y \rangle = \overline{\langle y,x \rangle}\big)$

^033112

>[!Example]- Algunos productos internos
>- $(\cdot, \cdot): \mathbb{C}^n \times \mathbb{C}^n \to \mathbb{C}$ dado por $\langle x,y \rangle \mapsto \sum x_k \bar{y_k}$
>- $\langle \cdot, \cdot \rangle: \mathbb{R}^n \times \mathbb{R}^n \to \mathbb{R}$ dado por $\langle x,y \rangle \mapsto \sum_{k=1}^n x_k y_k$
>- Si X es un ev con base {$e_1, \dots, e_k$} y $x,y \in X$ con $x=\sum \lambda_k e_k$ e $y=\sum \beta_k e_k$ entonces $$\langle \cdot, \cdot \rangle: X \times X \to \mathbb{C}\quad\text{dada por}\quad\langle x,y \rangle \mapsto \sum \lambda_k \bar{\beta_k}$$ es producto interno
>- Sea $(X, \Sigma, \mu)$ un medible entonces  $$\langle\cdot,\cdot\rangle:L^{2}\times L^{2}\rightarrow \mathbb{C} \quad\text{ dada por}\quad\langle f,g \rangle = \int f \overline{g}$$ es prod interno en $L^2(X)$ (notar $\int|fg|<\infty$ por Hölder con p=q=2)
>Caso particular $a=\{ a_{n} \}\in \ell^{2}$, $b=\{ b_{n} \}\in \ell^2$ entonces la sucesión $\{ a_n b_n\}\in \ell^2$ luego la funcion $$\langle \cdot, \cdot \rangle: \ell^2 \times \ell^2 \to \mathbb{C} \ \ \text{ dada por }\ \ \langle a,b \rangle \mapsto \sum a_n \overline{b_n}$$es producto interno
>- Si $X$ ev con $\langle \cdot, \cdot \rangle$ y $S$ sub esp entonces la restricción de $\langle \cdot, \cdot \rangle$ es p.i. en $S$
>- Si $X,Y$ son ev con p.i $\langle \cdot, \cdot \rangle_1$ y $\langle \cdot, \cdot \rangle_2$ respectivamente. Y $Z=X \times Y$ entonces
> $$(X \times Y) \times (X \times Y) \to \mathbb{C}\quad\text{ con }\quad\langle (u,v),(x,y) \rangle_z = \langle u,x \rangle_1 + \langle v,y \rangle_2$$
> es p.i

>[!Lemma] Resultados evpi
> X evpi $x,y,z \in X \quad \alpha, \beta \in \mathbb{F}$ ent
> - a) $\langle 0,y \rangle = \langle x,0 \rangle = 0$
> - b) $\langle x, \alpha y + \beta z \rangle = \bar{\alpha}\langle x,y \rangle + \bar{\beta}\langle x,z \rangle$
> - c) $\langle \alpha x + \beta y, \alpha x + \beta y \rangle = |\alpha|^2 \langle x,x \rangle + |\beta|^2 \langle y,y \rangle + \alpha \bar{\beta} \langle x,y \rangle + \beta \bar{\alpha} \langle y,x \rangle$
>>[!Proof]
>> ej

^7316d2

>[!Proposition] Desigualdad Cauchy Schwartz
> $X$ evpi $x,y \in X$ entonces
> - (a) $|\langle x,y \rangle|^2 \le \langle x,x \rangle \langle y,y \rangle$
> - (b) La funcion $\|\cdot\|: X \to \mathbb{R}$ dada por $\|x\| = \langle x,x \rangle^{1/2}$ es norma en $X$
>>[!Proof]-
>>(a) $x,y \ne 0$ ent. usando c) del lema anterior con $\alpha = - \frac{\overline{\langle x,y \rangle}}{\langle x,x \rangle}$ y $\beta=1$ tenemos 
>> $$\begin{align}0 \le \langle \alpha x + \beta y, \alpha x + \beta y \rangle & = \left| \frac{\langle x,y \rangle}{\langle x,x \rangle} \right|^2 \langle x,x \rangle + \langle y,y \rangle - \frac{\overline{\langle x,y \rangle}}{\langle x,x \rangle} \langle x,y \rangle - \frac{\langle x,y \rangle \langle y,x \rangle}{\overline{\langle x,x \rangle}} \\& = \frac{|\langle x,y \rangle|^2}{\langle x,x \rangle} - \frac{|\langle x,y \rangle|^2}{\langle x,x \rangle} - \frac{\langle x,y\rangle\overline{\langle x,y \rangle}}{\langle x,x \rangle} + \langle y,y \rangle\\&=-\frac{|\langle x,y\rangle|^{2}}{\langle x,x\rangle}+\langle y,y\rangle\\&= -|\langle x,y\rangle|^{2}+\langle x,x\rangle \langle y,y\rangle\\& \leq \langle x,x\rangle \langle y,y\rangle\end{align}$$
>> Notar que usamos $|\langle x,y\rangle|^{2} = \overline{\langle x,y \rangle}\langle x,y\rangle$ (propiedad complejos $z\overline{z}=|z|^{2}$) y $\langle x,x\rangle=\overline{\langle x,x\rangle}$  
>> (b) Trivial, sale usando definicion de p.i basicamente. La desigualdad veamosla
>> 1. $$\begin{align}\|x+y\|^{2}&=\langle x+y, x+y \rangle\\&=\langle x, x\rangle+ \langle x, y \rangle+\langle y, x \rangle+\langle y, y \rangle\\& = \|x\|^{2}+\langle x, y \rangle+\overline{\langle x, y \rangle}+\|y\| \\ & =\|x\|^{2}+2Re(\langle x, y \rangle)+\|y\|\\ & \leq \|x\|^{2}+2|\langle x, y \rangle | + \|y\|\\&\leq \|x\|^{2}+2\|x\|\|y\|+\|y\|^{2}\\&=(\|x\|+\|y\|)^{2}\end{align}$$   

^28aa9a

>[!Remark] Norma Inducida
>La norma $$\|\cdot\| = \langle \cdot, \cdot \rangle^{1/2}$$ se dice que es inducida por el p.i. Cuando tengamos un evpi lo pensaremos como ev normado con p.i. 
>Es facil ver que $\mathbb{F}^k, \ell^2, L^2(X)$ (por los pi de todos los ej antes) con los p.i dados arriba inducen las normas definidas anteriormente. Entonces notar que [[#^28aa9a]] se puede escribir como
> $$|\langle x,y \rangle| \le \|x\|\|y\| $$

^692a1b

>[!Lemma] Igualdades producto interno
> Sea $X$ evpi $\langle, \rangle$ ent $\forall u,v,x,y \in X$. Se tiene
> - a) $\langle u+v, x+y \rangle - \langle u-v, x-y \rangle = 2\langle u,y \rangle + 2\langle v,x \rangle$
> - b) $4\langle u,y \rangle = \langle u+v,x+y \rangle - \langle u-v,x-y \rangle + i\langle u+iv,x+iy \rangle - i\langle u-ix,x-iy \rangle$ si $\mathbb{F}=\mathbb{C}$
>>[!Proof]
>> ej

^fd88a0

>[!Theorem] Regla Paralelogramo e Id Polarizacion
> Sea X evpi con norm inducida $\| \cdot \|$ ent $\forall x,y \in X$
> - (a) Regla del Paralelogramo $$\|x+y\|^2 + \|x-y\|^2 = 2(\|x\|^2 + \|y\|^2)$$
> (Si $\langle x,y\rangle=0$ entonces esta igualdad se transforma en Pitagoras ) 
> - (b) Si $\mathbb{F}=\mathbb{R}$  $$\text{ Si }\  4\langle x,y \rangle = \|x+y\|^2 - \|x-y\|^2$$
> - (c) Si $\mathbb{F}=\mathbb{C}$  $$ 4\langle x,y \rangle = \|x+y\|^2 - \|x-y\|^2 + i\|x+iy\|^2 - i\|x-iy\|^2$$
> (Esta ultima es llamada identidad de polarización)

^604f51

>[!Remark] Contraejemplo a regla del paralelogramo
>La norma en $C[0,1]$ no proviene de un p.i $(\|f\|_{C} = \max_{x \in[0,1]} |f(x)|)$ entonces no vale (a) facil
>>[!Proof]
>>HACER
> $\|x\| = \langle x,x \rangle^{1/2}$
> $\|x-y\| = \langle x-y,x-y \rangle^{1/2}$

^6139d8

 

>[!Proposition] Continuidad de producto interno
> Sea $X$ evpi y $\{x_n\},\{ y_{n} \}\in X$ tales que $x_n \to x, y_n \to y$ con $x,y\in X$ entonces
> $$\langle x_n, y_n \rangle \to \langle x,y \rangle$$
>>[!Proof]-
>>1. Usando C-S $|\langle x_n, y_n \rangle - \langle x,y \rangle| \le |\langle x_n, y_n \rangle - \langle x_n, y \rangle| + |\langle x_n, y \rangle - \langle x,y \rangle|\le \|x_n\|\|y_n-y\| + \|x_n-x\|\|y\|\to 0$

^d0aa26

## Ortogonalidad

>[!Definition] Ortogonalidad
> Sea $X$ evpi decimos que $x,y\in X$ son ortogonales si $\langle x,y \rangle = 0$. Decimos ademas $\{e_{1}, \dots, e_{n}\}\subset X$ es ortonormal si $\|e_k\|=1 \quad \forall k$ y $\langle e_{j}, e_{k} \rangle = 0\quad \forall j \neq k$

^fbf000

>[!Lemma] Base Ortonormal
> Sea $X$ evpi entonces un conjunto ortonormal $\{ e_1, \dots, e_k \}$ es l.i. en particular si $dim (X)=k$ entonces $\{ e_1, \dots, e_k \}$ es base de $X$ y $\forall x \in X$ $$x = \sum_{n=1}^k \langle x,e_n \rangle e_n$$
> En este caso decimos que $\{ e_1, \dots, e_k \}$ es base ortornomal y $\langle x, e_n \rangle$ son las coordenadas en esa base.

^90d991

>[!Theorem] Grahm-Schmidt
>Sea $X$ evpi y $\{ v_1, \dots, v_k \}$ l.i. en $X$ entonces existe base ortonormal $\{ e_1, \dots, e_k\}$ de $S=Sp\{v_1, \dots, v_k\}$
>>[!Proof]
>>ej

^c3046c

>[!Definition] Espacio Hilbert
>Un esp con p.i completo con respecto a la métrica asociada a la norma inducida por el evpi se dice esp Hilbert.

^78371d

>[!Example] Ejemplo de espacios Hilbert
>- (1) Todo ev de $dim<\infty$ con $(\cdot, \cdot)$ (todo lo de la clase pasada)
>- (2) $L^2(X)$, $l^2$ con los p.i estándar (ya asumimos que $L^p(X)$ es completo)

>[!Remark] Esp c/p.i que no son Hilbert.
>Sea $l^2_c = \big\{ \{{x_n}\}_{n \in \mathbb{N}}/ x_n \ne 0 \text{ solo en finitos n}\big\}$ es facil ver que $\langle \{x_n\}, \{y_n\} \rangle = \sum x_n \overline{y_n}$ es p.i con norma asociada $\|{x_n}\| = (\sum |x_n|^2)^{1/2}$. Pero no es completo
>>[!Proof]-
>> 1. Sea $x^{n}=\left( 1, \frac{1}{2},\ldots, \frac{1}{n},0,\ldots \right)$ claramente pertence a $l^{2}_{c}$ y sea $x=\left( 1, \frac{1}{2}, \ldots \frac{1}{n} , \frac{1}{n+1}, \ldots \right)$ 
>> 2. Entonces $\lVert x^{n}-x \rVert^{2}=\sum^{\infty}_{i=n+1} \frac{1}{i^{2}}\rightarrow 0$ converge a $0$ por ser cola de serie convergente
>> 3. Pero $x\not\in l_{c}^{2}$ con lo cual $l_{c}^{2}$ no es cerrado y sabemos que completo implica cerrado [[Teórico 1#^83c633]]. Con lo cual $l_{c}^{2}$ no puede ser completo por que seria cerrado

^13356c

>[!Proposition] Hilbert $\iff$ cerrado
>Sea $\mathcal{H}$ Hilbert (completo), $Y \subset \mathcal{H}$ sub esp entonces 
> $$Y \text{ es Hilbert}\iff Y \text{es cerrado en }\mathcal{H}$$
>>[!Proof]-
>>1. $Y$ Hilbert $\iff$ $Y$ completo. 
>>2. Pero sub esp de un metrico completo es completo $\iff$ es cerrado (clase pasada)

^5c7207

## Complemento ortogonal

>[!Definition] Complemento ortogonal
> $X$ ev con $(\cdot, \cdot)$. Dado $A \subset X$ definimos el complemento ortogonal de $A$ como $$A^\perp = \{ x \in X : (x,a)=0 \quad \forall a \in A\}$$
>(si $A=\emptyset$ ponemos $A^\perp=X$)

^833729

>[!Example] Ejemplo complementos ortogonales
>- (1)$X=\mathbb{R}^3 \quad A=\{(a_1, a_2, a_3) : a_3=0\}\implies A^\perp = \{(x_1, x_2, x_3) \in \mathbb{R}^3 : x_1=x_2=0\}$
>- (2) Sup que $\{ e_1, \dots, e_k \}$ base de $X$. $A=sp\{e_1, \dots, e_p\} \quad 1 \le p \le k$. Entonces $A^\perp=sp\{e_{p+1}, \dots, e_k\}$

>[!Lemma] Resultados de ortogonalidad
> X evpi, A $\subset$ X subconjunto ent
> - (a) $0 \in A^\perp$
> - (b) si $0 \in A \implies A \cap A^\perp = \{0\}$ (si no $A \cap A^\perp = \phi$)
> - (c) $\{0\}^\perp = X, X^\perp=\{0\}$
> - (d) Si $A$ contiene una bola $B_a(r)$ p/alg $r>0$ y $a \in A$ entonces $A^\perp=\{0\}$ 
>(En particular si $A$ es abierto no vacío entonces $A^\perp = \{0\}$)
> - (e) $B \subset A \implies A^\perp \subset B^\perp$
> - (f) $A^\perp$ es sub cerrado de $X$ 
> - (g) $A \subset (A^\perp)^\perp = A^{\perp\perp}$
>>[!Proof]-
>> - (a) ej
>> - (b) Sea $x_0 \in A \cap A^\perp \implies \langle x_0, x_0 \rangle = 0 \implies x_0=0$
>> Notar $\langle 0,a\rangle = 0 \quad \forall a \in A \implies 0 \in A^\perp$
>> - (c) Sea $y \in X^\perp \implies \langle y,x \rangle=0 \quad \forall x_0 \in X$ en particular $y\in X$ entonces $\langle y,y \rangle=0 \implies y=0 \implies X^\perp=\{0\}$. 
>> Por otro lado $x\in X$ entonces $\langle x,0\rangle=0$ entonces $x\in \{ 0 \}^{\perp}$   
>> - (d) Sup $\exists 0 \ne x_0 \in A^\perp$. Sea $y=\frac{x_0}{\|x_0\|}$ como $y \in A^\perp \implies \langle y,a \rangle = 0 \quad \forall a \in A$
>> Luego notar $a+\frac{r}{2}y \in B_{a}(r)\subseteq A$ por que $\|a - \left( a+ \frac{r}{2}y \right)\|=\frac{r}{2}\|y\|=\frac{r}{2}$ 
>> Entonces $0 \leq \frac{r}{2}\langle y,y \rangle=\langle y, a+\frac{r}{2}y \rangle = 0 \implies \|y\|^{2}=\langle y,y \rangle=0 \implies y=0 \implies x_{0}=0$
>> - (f) Sea $y,v \in A^\perp$ entonces $\langle\alpha y+\beta v,a\rangle=0$ entonces $\alpha y+\beta v \in A^{\perp}$. Por otro lado sea $\{ x_{n} \}$ con $x_{n}\rightarrow x$ entonces $0=\lim\limits_{ n \to \infty }(x_{n}-x,a)=(x,a)+\lim\limits_{ n \to \infty }(x_{n},a)=(x,a)\quad\forall a\in A$  

^7a502c

>[!Proposition]
>Sea $Y$ subesp de $X$ evpi entonces $x \in Y^\perp \iff \|x-y\| \ge \|x\| \quad \forall y \in Y$
>>[!Proof]-
>>Por [[#^7316d2]] $$\|x-\alpha y\|^2 = \|x\|^2 - \bar{\alpha }\langle x,y \rangle - \alpha \langle y,x \rangle + |\alpha |^2\|y\|^2 \quad \forall x \in X \quad \forall y \in Y \quad \forall \alpha  \in \mathbb{F}$$
>>(Ida) 
>> 1. Sea $x \in Y^\perp, y \in Y$ entonces $\langle x,y \rangle = \langle y,x \rangle = 0$ 
>> 2. Usando $\alpha=1$ arriba tenemos $$\|x-y\|^2 = \|x\|^2 + \|y\|^2 \ge \|x\|^2$$
>>
>>(Vuelta) 
>>1. $\|x-y\|^2 \ge \|x\|^2 \quad \forall y \in Y$ como $Y$ subesp entonces esto vale con $\alpha y$ en lugar de $y$.
>>2. Luego $$0 \le \|x-\alpha y\|^2 - \|x\|^2 = -\bar{\alpha}\langle x,y \rangle - \alpha\langle y,x \rangle + |\alpha|^2\|y\|^2$$
>>3. Sea $$\beta = \begin{cases} \frac{|\langle x,y \rangle|}{\langle y,x \rangle} & \text{si } \langle x,y \rangle \ne 0 \\ 1 & \text{si } \langle x,y \rangle = 0 \end{cases}$$
>>Notar $\beta\langle y,x \rangle = |\langle x,y \rangle|$, $\overline{\beta}=\frac{|\langle x,y\rangle|}{\langle x,y\rangle}$ y $|\beta|^{2}=1$ 
>> 4. Sea $\alpha = t\beta \quad t>0$ entonces $$0 \le -t\bar{\beta}\langle x,y \rangle - t\beta\langle y,x \rangle + t^2|\beta|^2\|y\|^2= -2t|\langle x,y \rangle| + t^2\|y\|^2$$
>>Entonces $|\langle x,y \rangle| \leq \frac{t}{2}\|y\|^2$
>>5. Si $y=0$ entonces $|\langle x,y \rangle|=0$ si no $0\leq |\langle x,y\rangle|\leq \lim\limits_{ t \to 0^{+} } \frac{t}{2}\|y\|^{2}=0$. Mostrando que $\langle x,y\rangle=0\quad\forall y\in Y$ osea $x\in Y^{\perp}$  
>>6. 

^ad0aac





