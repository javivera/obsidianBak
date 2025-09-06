---
dateCreated: 2024-09-22,22:22
---
>[!Definition] Convexo
> $A \subset X$ espacio vectorial es convexo si $\forall x,y \in A$ $$tx+(1-t)y \in A \quad \forall t \in (0,1)$$

^cffc55

> [!Remark] Todo e.v es convexo
>  Todo espacio vectorial es convexo

^688643

>[!Proposition] Proy sobre un convexo (VER) 
> $A$ convexo y cerrado y $p\in\mathcal{H}$ Hilbert entonces $$\exists !q\in A \ / \ \lVert p-q \rVert=\inf\{ \lVert p-a \rVert\ :\ a\in A \}$$ 
> (Notar que como $A$ es cerrado $q$ es un mínimo) 
>>[!Proof]-
>>- Existencia
>>	1. $\gamma = \inf\{ \lVert p-c \rVert:c\in A \}$ usar def de infimo $\gamma^2\leq\lVert p-q_{n} \rVert \leq \gamma^2 + \frac{1}{n}$
>>	2. Ver $f_{n}=p-q_{n}$ es cauchy
>>	3.    $\lVert 2p-(q_{n}-q_{m})\rVert^2+\lVert q_{n}-q_{m} \rVert = \lVert (p-q_{n}) + (p-q_{m})\rVert^2 + \lVert (p-q_{n})-(p-q_{m}) \rVert^2$ 
>> 	  (R.Paralelogramo) $= 2\lVert p-q_{n} \rVert^2+2\lVert p-q_{m} \rVert^2 \leq 4\gamma^2+2\left( \frac{1}{n}+\frac{1}{m} \right)$
>>	4. Como $A$ conexo $\frac{1}{2}(q_{n}+q_{m})\in A$
>>	5. $4\gamma^2 \leq 4\left\lVert  p-\frac{1}{2}(q_{n}+q_{m})  \right\rVert^2 = \lVert 2p-(q_{n}+q_{m}) \rVert^2$ (Por 1.)
>>	6. $\lVert f_{n}-f_{m} \rVert^{2}=\lVert q_{n}-q_{m} \rVert^{2} < 2\left( \frac{1}{n} +\frac{1}{m}\right)$
>>	7. Converge por que $H$ Hilbert
>>	8. $A$ cerrado entonces $q\in A$
>>	9. $\gamma^2 \leq \lVert p-q \rVert^2=\lim_{ n \to \infty }\lVert p-q_{n} \rVert^2\leq\lim_{ n \to \infty }\gamma^2 + \frac{1}{n}=\gamma^2$ (Norma es continua entonces limite entra)
>>
>>- Unicidad
>>	1. Supongo $w\in A$ tal que $\lVert p-w \rVert=\gamma$
>>	2. Entonces $\frac{1}{2}(q+w)\in A$ digamos $\left\lVert  p- \frac{1}{2}(q+w)  \right\rVert\geq\gamma$
>>	3. (Regla Paralelo) $\lVert (p-w) + (p-q) \rVert^2 + \lVert (p-w)-(p-q) \rVert^2 =2\lVert p-w \rVert^{2}+2\lVert p-q \rVert^{2}=4\gamma^2$
>>	4. $4 \lVert q-w \rVert^2=4\gamma^2-4\left\lVert  p- \frac{1}{2}(q+w)  \right\rVert\leq 0$

^de887b

>[!Remark]
>Sea $p \in \mathcal{H}$ y $q \in A$ que satisface [[#^de887b]] convexo y $\mathbb{F}=\mathbb{R}$ entonces $$\|p-q\| = \min_{a \in A} \|p-a\| \iff \langle p-q, a-q \rangle \le 0\quad\forall a\in A$$
>>[!Proof]-
>>- (Ida) 
>>	1. Sea $a \in A$ y $v\in A$ definido como $v = (1-t)q+ta \quad t \in [0,1]$
>>	2. $$\|p-q\|^{2} \le \|p-v\|^{2} = \|(p-q)-t(a-q)\|^{2}$$(la desigualdad vale por hipotesis y por que $v\in A$)
>>	3. Recordemos por definición (considerando que $\mathbb{F}=\mathbb{R}$ ) :
>>	$$\|u-v\|^2 = \langle u-v, u-v \rangle = \langle u, u \rangle - 2\langle u, v \rangle + \langle v, v \rangle$$
>>	En este caso, $u = p-q$ y $v = t(a-q)$, así que:
>>	$$\|(p-q) - t(a-q)\|^2 = \|p-q\|^2 - 2t\langle p-q, a-q \rangle + t^2\|a-q\|^2$$
>>	4. Por lo tanto $$0 \le t\|a-q\|^2 - 2\langle p-q, a-q \rangle$$
>>	5. Usando $t\rightarrow 0$ concluimos $0 \geq \langle p-q, a-q \rangle$
>>
>>- (Vuelta) 
>>	1. Devuelta usando $\mathbb{F}=\mathbb{R}$ $$\begin{align}\|p-a\|^2 & = \|(p-q)-(a-q)\|^2\\&= \|p-q\|^2 + \|a-q\|^2 - 2\langle p-q, a-q \rangle\\&\ge \|p-q\|^2 \quad \forall a \in A\end{align}$$
>>	(La desigualdad vale por hipótesis) 

^1741ed

>[!Remark] En dim finita no hace falta convexo para realizar distancia
>En dim finita la existencia de $q$ es cierta inclusive sin que $A$ sea convexo pues $\{ q_{n} \}$ es acotada entonces tiene un sub convergente. 
>Pero si $A$ no es convexo la unicidad en general no es cierta ej. $A$ circunferencia y $p$ el centro

^1f282b

>[!Theorem] Descomposicion ortogonal de vector
>Sea $Y$ subespacio cerrado en $\mathcal{H}$ Hilbert entonces $\forall x \in H\quad\exists \ (y\in Y,z\in Y^{\perp})$ tal que $x=y+z$. Ademas $\lVert x \rVert^2=\lVert y \rVert^2+\lVert z \rVert^2$ (Generalizacion de Pitagoras)
>>[!Proof]-
>>Existencia
>>1. $x \in \mathcal{H}\quad Y\neq \emptyset$ convexo ([[Teórico 3#^688643]])  y cerrado entonces por [[Teórico 3#^1741ed]]
>>
>>2. $\exists y\in Y$ tal que $\lVert x-y \rVert\leq \lVert x-u \rVert\quad \forall u\in Y$
>>3. $z=x-y$
>>4. $\forall u\in Y\quad\lVert z-u \rVert=\lVert x-(y+u) \rVert\geq \lVert x-y \rVert=\lVert z \rVert$ ($y+u\in Y$ por ser subespacio)
>>5. Por [[Teórico 2#^ad0aac]] $z\in Y^{\perp}$
>>
>>Unicidad
>>6. Suponemos $x=y_{1}+z_{1}=y_{2}+z_{2}$ entonces $y_{1}-y_{2}=z_{2}-z_{1}$ entonces $y_{1}-y_{2}\in Y$ y también $y_{1}-y_{2}\in Y^{\perp}$ entonces $y_{1}-y_{2}=0$ entonces $y_{1}=y_{2}$ entonces $x_{1}=x_{2}$ 

^3686bc

>[!Corollary] Doble ortogonal de cerrado
>Si $Y$ subespacio cerrado en $\mathcal{H}$ hilbert entonces $Y=Y^{\perp\perp}$ 
>>[!Proof]-
>>1. $Y\subset Y^{\perp\perp}$. $x \in Y^{\perp\perp}$ entonces $x=y+z$ [[Teórico 3#^3686bc]]
>

^31d10a

>[!Remark]
>Si $Y$ no es cerrado $Y\neq Y^{\perp\perp}$ por que $Y^{\perp\perp}$ es cerrado por [[Teórico 2#^7a502c]] inciso f

>[!Corollary] Doble ortogonal de no cerrado
>Si $Y$ subespacio Hilbert entonces $Y^{\perp\perp}=\overline{Y}$
>>[!Proof]-
>>1. $Y\subseteq \overline{Y}$ y $\overline{Y}^{\perp}\subseteq Y^{\perp}$ 
>>2. Entonces $Y^{\perp\perp}\subseteq \overline{Y}^{\perp\perp}=\overline{Y}$ por [[Teórico 3#^31d10a]] tenemos $Y^{\perp\perp}=\overline{Y}$ 
>>3. Por otro lado $Y\subseteq Y^{\perp\perp}$  entonces $\overline{Y}=\overline{Y^{\perp\perp}}=Y^{\perp\perp}$ (la u.tima igualdad porque $Y^{\perp\perp}$ es cerrado) 

^3660c8
## Base ortogonal de dimension infinita

>[!Definition] Sucesion Ortonormal
> Sea $X$ e.v.pi. Una sucesion $\{ e_{n} \}\subseteq X$ se dice ortonormal si $\lVert e_{n} \rVert=1\quad\forall {n}\in\mathbb{N}$ y $(e_{n},e_{m})=0\quad\forall n\neq m$

^3b183b
>[!Example]
>- En $\ell^{2}$ tenemos $\{ e_{n} \}$ que es ortonormal
>- En $L^{2}_{\mathbb{C}}[-\pi,\pi]$ tenemos $e_{n}(x)=\frac{1}{\sqrt{2\pi}}e^{inx}$ con $n\in\mathbb{Z}$. Entonces
>$$\begin{align}(e_{n},e_{m})=\frac{1}{2\pi}\int_{-\pi}^{\pi} e^{inx}\overline{e^{imx}}\,dx&=\frac{1}{2\pi}\int_{-\pi}^{\pi} e^{i(n-m)x}\,dx\\&=\frac{1}{2\pi}\left[\frac{e^{i(n-m)x}}{i(n-m)}\right]_{-\pi}^{\pi}\\&=\frac{1}{2\pi}\cdot\frac{e^{i(n-m)\pi}-e^{-i(n-m)\pi}}{i(n-m)}\\&=\frac{1}{2\pi}\cdot\frac{2i\sin((n-m)\pi)}{i(n-m)}=0\quad (n\neq m)\end{align}$$
>y $(e_n,e_n)=1$. Entonces es sucesión ortonormal

>[!Theorem] Dim infinita tiene sucesion ortonormal
>Todo $X$ e.v.pi de dimension infinita contiene una sucesion ortonormal 
>>[!Proof]-
>> Usando algo similar [[Teórico 1#^8db74f]] tenemos una sucesion de $\{ x_{n} \}\subset X$ de vectores unitarios que son linealmente independientes por construccion. Aplicamos Grahm-Schmidt y obtenemos sucesion ortonormal

^252a33

>[!Remark]
>Si $X$ es e.v.pi dimension k y $\{ e_{1},\ldots,e_{k} \}$ es base de $X$ entonces $$x=\sum^{k}_{n=1}(x,e_{n})e_{n}$$Queremos ver si esto se puede generalizar en dimension infinita a $$x=\sum^{\infty}_{n=1}(x,e_{n})e_{n}$$

>[!Theorem] Desigualdad de Bessel
>$X$ e.v.pi $\{ e_{n} \}\subset X$ sucesion ortonormal entonces $\forall x \in X$ la serie $\sum^{\infty}_{n=1} \lvert (x,en) \rvert^{2}$ converge y $$\sum^{\infty}_{n=1}\lvert (x,e_{n}) \rvert^{2}\leq\lVert x \rVert^{2}$$
>>[!Proof]-
>>1. Sea $y_{k} = \sum^{k}_{n=1}(x,e_{n})e_{n}$
>>2. Calculo de $\|x-y_k\|^2$ usando ortonormalidad. Entonces
>>$$\|x-y_k\|^2 = \langle x-y_k, x-y_k \rangle = \langle x,x\rangle - \langle x, y_k\rangle - \langle y_k, x\rangle + \langle y_k, y_k\rangle$$
>>3. Ademas $\langle x, y_k\rangle = \sum_{n=1}^k (x,e_n)\overline{(x,e_n)} = \sum_{n=1}^k |(x,e_n)|^2$ por lo tanto $\langle y_k, x\rangle = \overline{\langle x, y_k\rangle} = \sum_{n=1}^k |(x,e_n)|^2$
>>4. Y por otro lado $\|y_k\|^2 =\left\lVert  \sum^{k}_{n=1}\alpha_{n}e_{n}  \right\rVert^{2} =\sum^{k}_{n=1}|\alpha_{n}|^{2}= \sum_{n=1}^k |(x,e_n)|^2$
>>5. Reemplazando en 2. $$\|x - y_k\|^2 = \|x\|^2 - \sum_{n=1}^k |(x,e_n)|^2 - \sum_{n=1}^k |(x,e_n)|^2 + \sum_{n=1}^k |(x,e_n)|^2 = \|x\|^2 - \sum_{n=1}^k |(x,e_n)|^2$$ 
>>6. Por lo tanto $$\sum^{k}_{n=1}\lvert (x,e_{n}) \rvert^{2} = \lVert x \rVert^{2} - \lVert x-y_{k} \rVert^{2}\leq\lVert x \rVert^{2}$$
>>7. Entonces las sumas parciales son crecientes y acotadas por lo tanto el limite de la series existe. Entonces usando limite se termina.

^1a2dbf

>[!Theorem]
>Sea $\mathcal{H}$ un Hilbert y $\{ e_{n} \}\subseteq\mathcal{H}$ una sucesion ortonormal y $\{ \alpha_{n} \}\subseteq\mathbb{F}$ entonces
>$$\sum^{\infty}_{n=1} \alpha_{n}e_{n} \text{ converge } \iff \sum^{\infty}_{n=1} \lvert \alpha_{n} \rvert ^{2} \text{ converge }\bigg(\iff \{ \alpha_{n} \}\in\ell^{2} \bigg) $$
>Si esto ocurre $$\left\lVert  \sum^{\infty}_{n=1} \alpha_{n}e_{n}   \right\rVert ^{2} =\sum^{\infty}_{n=1} \lvert \alpha_{n} \rvert ^{2} $$
>>[!Proof]-
>>1. $(\Rightarrow)$ Sea $x=\sum^{\infty}\alpha_{n}e_{n}\leq\infty$ 
>>2. $(x,e_{m})=\lim_{ k \to \infty }\left( <\sum^{k}_{n=1}\alpha_{n}e_{n},e_{m} >\right)=\alpha_{m}$ ($k\geq m$ cuando a partir de algun momento)
>>3. $\sum^{\infty}_{n=1}\lvert \alpha_{n} \rvert^{2}=\sum^{\infty}_{n=1}\lvert (x,e_{n}) \rvert^{2}\leq\lVert x \rVert^{2} = \left\lVert  \sum^{\infty}_{n=1}\alpha_{n}e_{n}  \right\rVert\leq\infty$ 
>> (Por [[Teórico 3#^1a2dbf]])
>>4. $(\Leftarrow)$ Sea $x_{k}=\sum^{k}_{n=1}\alpha_{n}e_{n}$
>>5. $\lVert x_{k}-x_{j} \rVert_{2}=\left\lVert  \sum^{k}_{n=1}\alpha_{n}e_{n}  \right\rVert^{2}=\sum^{k}_{n=j+1}\lvert \alpha_{n} \rvert^{2} \xrightarrow[j,k \to \infty]{} 0$ (Por que la serie converge)
>>6. Como $\{ x_{k} \}$ es de cauchy en un Hilbert converge
>>
>>Por ultimo como las series converge y como en finito ya tenemos la igualdad. 
>>$$\left\lVert  \sum^{\infty}_{n=1} \alpha_{n}e_{n}   \right\rVert ^{2} =\lim_{ k \to \infty }\left\lVert  \sum^{k}_{n=1}\alpha_{n}e_{n}  \right\rVert^{2}=  \lim_{ k \to \infty }\sum^{k}_{n=1}\lvert \alpha_{n} \rvert^{2}=\sum^{\infty}_{n=1} \lvert \alpha_{n} \rvert ^{2}$$
> Detalle de esta ultima parte 
> $$\begin{align}\left\lVert  \sum^{k}_{n=1} \alpha_{n}e_{n}  \right\rVert ^{2} & =\left( \sum^{k}_{n=1} \alpha_{n}e_{n},\sum^{k}_{n=1} \alpha_{n}e_{n} \right)\\ &=\sum^{k}_{n=1} (\alpha_{n}e_{n},\alpha_{n}e_{n})\\& =\sum^{k}_{n=1} \alpha_{n}\overline{\alpha_{n}}(e_{n},e_{n})\\&=\sum^{k}_{n=1} \lvert \alpha_{n} \rvert ^{2} \end{align}$$

^4e7cf9

>[!Corollary] Convergencia de series en un Hilbert
>Sea $\{ e_{n} \}\subseteq \mathcal{H}$ Hilbert una sucesion ortonormal entonces $\forall {x}\in{\mathcal{H}}$ sucede que $$\sum^{\infty}_{n=1}(x,e_{n})e_{n}$$ converge en $\mathcal{H}$
>>[!Proof]-
>> 1. Por [[Teórico 3#^1a2dbf]] $\sum^{\infty}_{n=1}\lvert (x,e_{n}) \rvert^{2}$ converge
>> 2. Por [[Teórico 3#^4e7cf9]] (Vuelta) esto implica $\sum^{\infty}_{n=1}(x,e_{n})e_{n}$ converge
>> 3. En particular converge en $\mathcal{H}$ por qué es cerrado y subespacio
>> (Notar que en la vuelta usamos fuertemente Hilbert) 

^f3d5ec

>[!Remark]
>Surge ahora la pregunta cuando sucede que $$\sum^{\infty}_{n=1}(x,e_{n})e_{n}$$ converge en particular a $x$
>

>[!example] $x$ no se puede escribir como suma en base ortonormal 
>Sea $\{ e_{n} \}\subseteq\mathcal{H}$ ortonormal y $\{ e_{2n} \}$ subsucesion (osea otra sucesion ortonormal). 
>Se puede ver que $e_{1}\neq\sum^{\infty}_{n=1}\alpha_{2n}e_{2n}$. Por ende encontramos un $x\in\mathcal{H}$ que no se puede escribir como dicha suma

^9558c7

>[!Theorem] 3.47 Bon de Hilbert
>Sea $\{ e_{n} \}\subseteq\mathcal{H}$ Hilbert sucesions ortonormal son equivalentes
>1. $\{ e_{n}:n\in\mathbb{N} \}^{\perp}$ = $\{ 0 \}$
>2. $\overline{Sp}(\{ e_{n}:n\in\mathbb{N} \})=\mathcal{H}$
>3. $\lVert x \rVert^{2}=\sum^{\infty}_{n=1}\lvert (x,e_{n}) \rvert^{2}$ (Teorema de Parseval)
>4. $x=\sum^{\infty}_{n=1}(x,e_{n})e_{n}$
>
>Decimos que $\{ e_{n} \}$ es base ortonormal de $\mathcal{H}$ si cumple alguna de las condiciones anteriores. Notar que para una base ortonormal entonces se cumple la igualdad en la desigualdad de Bessel [[Teórico 3#^1a2dbf]]
>>[!Proof]-
>>$(1.\Rightarrow 4.)$ $x \in\mathcal{H}$, $y=x-\sum^{\infty}_{n=1}(x,e_{n})e_{n}$ entonces $\forall {m}\in\mathbb{N}$ vale $$(y,e_{m})=(x,e_{m})-\lim_{ N \to \infty } \left( \sum^{N}_{n=1} (x,e_{n})e_{n},e_{m} \right) = 0$$
>>Entonces $y \in\{ e_{n}:n\in\mathbb{N} \}^{\perp} = \{ 0 \}$  
>>($4.\Rightarrow 2.$ ) $x=\lim\limits_{ k\to \infty }\sum^{k}_{n=1}(x,e_{n})e_{n}$. Además $\sum^{k}_{n=1}(x,e_{n})e_{n}\in Sp(\{ e_{n} \})$ por lo tanto $x\in \overline{Sp}(\{ e_{n} \})$ y esto vale para todo $x$ 
>>$(4.\Rightarrow 3.)$ Por hipotesis $$x=\sum^{\infty}_{n=1}(x,e_{n})e_{n}$$
>>Entonces por [[Teórico 3#^4e7cf9]] $$\lVert x \rVert^{2}= \lVert \sum^{\infty}_{n=1}(x,e_{n})e_{n}\rVert^{2}=\sum^{\infty}_{n=1}\lvert (x,e_{n}) \rvert^{2}$$
>>$(3\Rightarrow 1)$ Sea $x\in \{ e_{n} \}^{\perp}$ entonces $\lVert x \rVert=\sum^{\infty}_{n=1}|(x_{n},e_{n}|^{2})=0$ mostrando que $x=0$ 
>>$(2\Rightarrow 1)$ Sea $y\in\{ e_{n} \}^{\perp}$ entonces $(y,e_{n})=0\quad\forall {n}\in\mathbb{N}$ por lo tanto $e_{n}\in\{ y \}^{\perp}$
>>$Sp\{ e_{n} \}\subseteq\{ y \}^{\perp} \text{ (Por 2) }\Rightarrow\mathcal{H}=\overline{Sp}\{ e_{n} \}\subseteq\overline{\{ y \}^{\perp}}=\{ y \}^{\perp}$
>>Entonces $y=0$

^f63eb1

>[!Remark] Diferencia entre span y span cerrado en dimension infinita
>$Sp(\{ e_{n} \})$ tiene todas las combinaciones lineales **finitas** de vectores en $\{ e_{n} \}$ (Que es numerable infinito) pero para que valga [[Teórico 3#^f63eb1]] necesito considerar las sumas infinitas. Esto corresponde a considerar $\overline{Sp}\{ e_{n} \}$. En dimension finita el span es cerrado (por que todo ev lo es)  y por lo tanto igual a su clausura asi que no hace falta diferenciar entre estos conceptos pero en dimension infinia si es importante diferenciar 

^b3a19f

>[!Remark]
>El $\ell^{2}$ tiene BON porque podemos tomar $\{ e_{n} \}\subseteq \ell^{2}$ (con $e_{i}=(0,\ldots,1,\ldots,0,\ldots)$  el $1$ en la posicion $i$)  y dado $x\in \ell^{2}$ podemos escribir $x=\sum^{\infty}_{n=1}(x,e_{n})e_{n}$ 

^51eebf

>[!Theorem] 3.52 Hilbert dim infinita separable sii BON de Hilbert
>1. Espacios normados de dim finita son separables
>2. Un Hilbert de dim infinita es separable $\iff$ tiene una BON de Hilbert
>>[!Proof]-
>>1. $X$ finito $\{ e_{1},\ldots,e_{k} \}$ base. El conjunto de los vectores $\sum^{k}_{n=1}\alpha_{n}e_{n}$ donde $\alpha_{n}\in\mathbb{Q}$ (o $\alpha_{n}\in \mathbb{Q}+i\mathbb{Q}$ ) es denso y numerable (lo vemos en parte 2) 
>>2. 
>>- $(\Rightarrow)$ Tenemos $\{ x_{n} \}$ denso y numerable a partir de el armamos $\{ x_{n_{j}} \}$ dejando de lado los $x_{j}$ que son combinacion lineal de algun elemento anterior. 
>>- Por lo tanto $\{ x_{n_{j}} \}$ sera linealmente idependiente. 
>>- Aplicamos Grahm-Schmidt y obtenemos una sucesión ortonormal $\{ e_{n} \}$  $$Sp\{ e_{n} \}=Sp\{ x_{n_{j}} \}=Sp\{ x_{n} \}$$ 
>>- Como $\{ x_{n} \}$ era denso en $\mathcal{H}$ entonces $\overline{Sp}\{ e_{n} \}=\overline{Sp\{ e_{n} \}}=\overline{Sp\{ x_{n} \}}=\mathcal{H}$ base ortonormal 
>>([[Teórico 3#^f63eb1]])
>>- $(\Leftarrow)$ Ahora tenemos BON $\{ e_{n} \}$. Afirmamos que el conjunto $A$ de los $x\in\mathcal{H}$ que son expresables como sumas finitas $\sum^{k}_{n=1}\alpha_{n}e_{n}$ con $\alpha_{n}\in\mathbb{Q}$ (o $\mathbb{Q}+i\mathbb{Q})$ es denso y numerable.
>>- $A$ numerable es trivial.
>>- Sea $y\in\mathcal{H}$ entonces $y=\sum^{\infty}_{n=1}\beta_{n}e_{n}$ y sabemos que vale $\sum^{\infty}_{n=1}\lvert \beta_{n} \rvert^{2}\leq\infty$ ([[Teórico 3#^4e7cf9]]) entonces $\sum^{\infty}_{n=N+1}\lvert \beta_{n} \rvert^{2}< \frac{\epsilon^{2}}{2}$
>>- Para $n=1,\ldots,N$ elegimos $\alpha_{n}$ tales que $\lvert \beta_{n}-\alpha_{n} \rvert^{2}\leq \frac{\epsilon^{2}}{2N}\quad n=1,\ldots,N$ (Densidad en $\mathbb{Q}$)
>>- $\lVert y-x \rVert^{2}=\sum^{N}_{n=1}\lvert \beta_{n}-\alpha_{n} \rvert^{2}+\sum^{\infty}_{n=N+1}\lvert \beta_{n} \rvert^{2}\leq\epsilon^{2}$
>>- Entonces $A$ es denso en $\mathcal{H}$

^a44e0c

>[!Corollary]
>$\ell^{2}$ es separable. $L^{2}[a,b]$ es separable. Veremos mas adelante que tienen BON de Hilber
>>[!Proof]-
>>1. Sale de [[Teórico 3#^51eebf]] y [[Teórico 3#^a44e0c]]
^f743a7
 
>[!example] Hilbert no separable
>Hilbert que no es separable. $$\tilde{L}^{2}(\mathbb{R})=\{ f:\mathbb{R}\rightarrow\mathbb{R} \ / \ f(x)\neq 0\text{ a lo sumo para numerables }x \ \text{ y } \ \sum^{}_{x\in\mathbb{R}}f(x)^{2}<\infty\}$$ 
>>[!Proof]-
>>2. Es facil ver que es Hilbert con $(f,g)=\sum^{}_{x\in\mathbb{R}}f(x)g(x)$ (Suma finita sale por Holder) 
>>3. Sea 
>>$$f_{y}(x) = \begin{cases} 1 & x=y \\ 0 & cc \end{cases}$$
>>Estan en el $\tilde{L}^{2}$. Y además hay no numerables de estas $f_{y}$ 
>>Ademas $\lVert f_{y}-f_{z} \rVert=2$. Si tuviese un denso numerable del $\tilde{L^{2}}$ para cada $f_{y}$ me armo una bola de radio mas chico que 2 cada una de estas bolas tiene algun elemento de dicho denso numerable, pero no se intersecan entre si. Absurdo porque tengo no numerables bolas.

^2e31bc

