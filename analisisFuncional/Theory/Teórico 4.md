---
dateCreated: 2024-09-23,17:12
tags:
  - Fourier
  - FunctionalAnalysis
---
>[!Theorem] Stone-Weierstrauss. Pols desnsos en reales
>Sea $M\subseteq \mathbb{R}$ entonces los polinomios con coeficientes reales son densos en $C_{\mathbb{R}}(M)$

^f39524

>[!Theorem] Continuas densas en $L^{p}$ con $p\neq\infty$  
>El conjunto $C[a,b]$ es denso en $L^{p}[a,b]$ con $1\leq p<\infty$
^ad83ce
## Series de Fourier

>[!Theorem] Base de $L^{2}[0,\pi]$
>$$C=\left\{  c_{0}(x)=\left( \frac{1}{\pi} \right),c_{n}(x)=\left( \frac{2}{\pi} \right)^{\frac{1}{2}}\cos nx : n\in\mathbb{N} \right\}$$
>es una base ortonormal de $L^{2}[0,\pi]$
>>[!Proof]
>>1. Ortonormal hacer
>>2. Basta ver que $\overline{Sp}C=L^{2}_{\mathbb{R}}[0,\pi]$. Por [[Teórico 3#^f63eb1]]
>>3. Sea $f\in L^{2}_{\mathbb{R}}[0,\pi]$. Por [[Teórico 4#^ad83ce]] existe $g_{1}\in C_{\mathbb{R}}[0,\pi]$ tal que $\lVert g_{1}-f \rVert_{2}\leq \frac{\epsilon}{2}$ 
>>4. Luego basta probar que $\forall g_{1}\in C_{\mathbb{R}}[0,\pi]$ existe $g_{2}\in Sp(C)$ tal que $\lVert g_{2}-g_{1} \rVert_{2}\leq \frac{\epsilon}{2}$ 
>>5. Sea ahora $g_{1}\in C_{\mathbb{R}}[0,\pi]$ arbitrario. Como $cos:[0,\pi]\rightarrow[-1,1]$ es biyectiva y continua podemos definir $h(s)=g_{1}(cos^{-1}(s))\quad\forall s\in [-1,1]$ y entonces $h\in C_{\mathbb{R}}[-1,1]$. 
>>6. Por [[Teórico 4#^f39524]] existe pol $p$ tsl que $|h(s)-p(s)|< \frac{\epsilon}{2\sqrt{ \pi }}\quad\forall s\in [-1,1]$
>>7. Sea $g_{2}(x)=p(cos(x))$ entonces $|g_{2}(x)-g_{1}(x)|=|g_{2}(cos^{-1}(s))-g_{1}(cos^{-1}(s))|=|p(s)-h(s)|\leq \frac{\epsilon}{2\sqrt{ \pi }}\quad\forall x\in [0,\pi]$
>>8. Entonces $$\lVert g_{2}-g_{1} \rVert_{2}=\left(\int_{0}^{\pi}\big(g_{2}(x)-g_{1}(x)\big)^{2}\right)^{1/2} \leq \frac{\epsilon}{2} $$ 
>>9. Finalmente notamos que $p(cos(x))$ se puede reescribir como $\sum^{m}_{n=1}\alpha_{n}cos(nx)\in Sp(C)$ Para ciertos $\alpha _{n},m$ (lo vemos abajo) 

^7dc16f

>[!Remark] Polinomios de Chevyshev
>Sean $T_{n}$ pols de Chevyshev. $$T_{0}(x)=1,T_{1}(x)=x,T_{n+1}(x)=2xT_{n}(x)-T_{n-1}(x)$$ 
>Entonces es fácil ver $cos(nx)=T_{n}(cos(x))$ usando ($cos^{2}(x)=\frac{1+cos(2x)}{2}$) 

>[!Corollary] $L^{2}$ es separable
>$L^{2}[0,\pi]$ es separable.
>>[!Proof]-
>>1. Tiene BON por [[Teórico 4#^7dc16f]]
>>2. [[Teórico 3#^a44e0c]]

^88c019

>[!Theorem] Base de $L^{2}[0,\pi]$ con $\sin$  
> $$S=\left\{  s_{n}(x)=\left( \frac{2}{\pi } \right)^{\frac{1}{2}} \sin nx:n\in \mathbb{N} \right\}$$
>is una base ortonormal en $L^{2}[0,\pi]$
>>[!Proof]
>>3. Lo primero es similar al anterior. 
>>4. Sea $f\in L_{\mathbb{R}}^{2}$ para $\delta>0$ sea $f_{\delta }(x)=\begin{cases} 0 & x \in [0,\delta ]\cup [\pi-\delta ,\pi]\\ f(x)& x \in [\delta ,\pi-\delta ]\end{cases}$ 
>>5. Entonces $\lVert f_{\delta }-f \rVert_{2}<\epsilon$ si $\delta \neq 0$ 
>>6. Y como $\frac{f_{\delta }(x)}{sen(x)}\in L_{\mathbb{R}}^{2}$ por el teorema anterior podemos aproximar $\frac{f_{\delta }(x)}{sen(x)}$ Por $\sum^{m}_{n=1}\alpha_{n}cos(nx)$ 
>>7. Luego podemos aproximar $f_{\delta }$ por $\sum^{m}_{n=1}\alpha_{n}cos(nx)sen(x)=\frac{1}{2}\sum^{m}_{n=1}\alpha _{n}(sen((n+1)x)-sen((n-1)x))\in Sp(S)$ 

^df1be3

>[!Theorem] Bases de Fourier
>$$E=\left\{  e_{n}(x)=(2\pi )^{-\frac{1}{2}} e^{inx}  :n\in \mathbb{N} \right\}$$
>$$F=\left\{  2^{-\frac{1}{2}}c_{0},2^{-\frac{1}{2}} c_{n},2^{-\frac{1}{2}} s_{n}:n\in \mathbb{N}    \right\}$$
>son bases ortonormales de $L^{2}_{\mathbb{C}}[-\pi,\pi]$. Ademas $F$ es base ortonormal de $L^{2}_{\mathbb{R}}[-\pi,\pi]$
>>[!Proof]
>>1. Es fácil ver que $F$ es ortonormal.
>>2. Supongamos que $F$ no es base en $L^{2}_{\mathbb{R}}[-\pi,\pi]$. Entonces existe una función no nula $f\in L^{2}_{\mathbb{R}}[-\pi,\pi]$ tal que
>>   $$(f,c_{0})=(f,c_{n})=(f,s_{n})=0\quad\forall n\in\mathbb{N}.$$ 
>>3. Escribiendo estas igualdades como integrales se tiene
>>   $$0=\int_{-\pi}^{\pi} f(x)\,dx = \int_{0}^{\pi} \big(f(x)+f(-x)\big)\,dx,$$
>>   $$0=\int_{-\pi}^{\pi} f(x)\cos nx\,dx = \int_{0}^{\pi} \big(f(x)+f(-x)\big)\cos nx\,dx,$$
>>   $$0=\int_{-\pi}^{\pi} f(x)\sin nx\,dx = \int_{0}^{\pi} \big(f(x)-f(-x)\big)\sin nx\,dx.$$ 
>>4. Por la parte (a) del Teorema 3.47 y los Teoremas 3.54 y 3.56 (o por unicidad de la expansión en cosenos y senos), de las dos primeras igualdades se obtiene que $f(x)+f(-x)=0$ para c.a.e. $x\in[0,\pi]$, y de la tercera que $f(x)-f(-x)=0$ para c.a.e. $x\in[0,\pi]$.
>>5. De ambas igualdades se concluye que $f(x)=0$ para c.a.e. $x\in[-\pi,\pi]$, lo cual contradice que $f$ no es la función nula. Por tanto $F$ debe ser una base ortonormal en $L^{2}_{\mathbb{R}}[-\pi,\pi]$.
>>6. Finalmente, en el Ejemplo 3.39 se muestra que $E$ es ortonormal en $L^{2}_{\mathbb{C}}[-\pi,\pi]$ y, usando la identidad $e^{inx}=\cos nx + i\sin nx$, se ve que $\mathrm{Sp}(E)=\mathrm{Sp}(F)$; por tanto $E$ también es una base ortonormal.


^230c12

## Operadores lineales continuos

>[!Definition] Operador Lineal
>Sea $X,Y$ normados (sobre el mismo $\mathbb{F}$). Decimos que $T:X\rightarrow Y$ es lineal si 
>$$T(\alpha x+\beta y)= \alpha Ty + \beta Ty\quad\forall {x,y}\in X\quad\alpha ,\beta \in \mathbb{F}$$

^ef2b84

>[!Remark] Continuidad de operador lineal
>Decimos que $T$ continua en $x_0\in X$ si $\forall \epsilon>0,\quad\exists\delta$ tal que $\lVert x-x_{0} \rVert\Rightarrow\lVert Tx-Tx_{0} \rVert<\epsilon$

^0e0e82

>[!Lemma] Equivalencia de continuidad para operadores lineales
>Sean $X$ e $Y$ ev normados y $T:X\rightarrow Y$ una transformacion lineal. Son equivalentes:
>1. $T$ es uniforme continua
>2. $T$ es continua
>3. $T$ es continua en 0
>4. Existe un numero real positivo $k$ tal que $\lVert Tx \rVert\leq k\quad\forall x\in X$ y $\lVert x \rVert\leq_{1}$
>5. Existe un numero real positivo $k$ tal que $\lVert Tx \rVert\leq k\lVert x \rVert\quad\forall x\in X$ 
>>[!Proof]
>>Hacer

^cae689

>[!example] Ejemplo de operador lineal continuo
>$T:C_{\mathbb{F}}[0,1]:\rightarrow \mathbb{F}$ definida por $$T(f)=f(0)$$ es continua
>>[!Proof]
>>1. Sea $f\in C_{\mathbb{F}}[0,1]$. Usando la norma supremo tenemos
>>   $$|T(f)|=|f(0)|\leq \sup\{ |f(x)|:x\in[0,1]\}=\|f\|_{\infty}.$$ 
>>2. Por la condición (e) del Lema 4.1 (equivalencia de continuidad) se sigue que $T$ es continua con constante $k=1$.


^9798e1

>[!Lemma] Multiplicar $\ell^{\infty}$ por algo $\ell^{p}$ esta en el $\ell^{p}$   
> Si $\{ c_{n} \}\in \ell^{\infty}$ y $\{ x_{n} \}\in \ell^{p}$ con $1\leq p<\infty$ entonces $\{ c_{n}x_{n} \}\in \ell^{p}$ y $$\sum^{\infty}_{n=1} \lvert c_{n}x_{n} \rvert ^{p} \leq\lVert \{ c_{n} \} \rVert_{\infty}^{p} \sum^{\infty}_{n=1} \lvert x_{n} \rvert ^{p} $$
>>[!Proof]
>>1. Sea $\lambda=\|\{c_n\}\|_{\infty}=\sup\{ |c_n|:n\in\mathbb{N}\}<\infty$. Entonces para todo $n$ se tiene $|c_n|\leq\lambda$, por lo que
>>   $$|c_n x_n|^p \leq \lambda^p |x_n|^p.$$ 
>>2. Sumando sobre $n$ y usando comparación obtenemos
>>   $$\sum_{n=1}^{\infty} |c_n x_n|^p \leq \lambda^p \sum_{n=1}^{\infty} |x_n|^p <\infty.$$ 
>>3. Por tanto $\{c_n x_n\}\in\ell^p$ y se cumple la desigualdad anunciada.



>[!example] Operador lineal continuo
>Si $\{ c_{n} \}\in \ell^{\infty}$ luego $T : \ell^{1}\rightarrow \mathbb{F}$ definida por $$T(\{ x_{n} \})=\sum^{\infty}_{n=1}  c_{n}x_{n}$$
>es continua

^a511bc

>[!example] Operador lineal no continuo
>Sea $C_{\mathbb{C}}[0,1]$ y $\mathcal{P}$ subespacio de polinomios. Definimos $T :\mathcal{P}\rightarrow \mathcal{P}$ dada por $Tp=p'$. Dicho $T$ no es continuo
>>[!Proof]-
>>1. Supongamos que es continua entonces por $(e)$ [[Teórico 4#^cae689]] $\exists k$ tal que $\lVert T(x) \rVert\leq k\lVert x \rVert\quad\forall x\in \mathcal{P}$ 
>>2. Sea $n\in \mathbb{N}$ tal que $k<n$. Miro $x^{n}\in P$  
>$$\lVert T(x^{n} ) \rVert =\lVert nx^{n-1}  \rVert =n\lVert x^{n-1}\rVert=n>k.1=k\lVert x^{n} \rVert$$
>que es absurdo (aca en los polinomios estamos tomando norma infinito que es la inducida por $C_{\mathbb{C}}[0,1]$ ) 
^63dcb1
