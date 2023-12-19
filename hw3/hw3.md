## Duality
### 5.3
Lagrangian function:
$$L(x,\lambda)=c^Tx+\lambda f(x)$$

Dual function:
$$\begin{aligned}
g(\lambda)
&=\underset{x}\inf\left(L(x,\lambda)\right)\\
&=\underset{x}\inf\left(c^Tx+\lambda f(x)\right)\\
&=\begin{cases}-\lambda \underset{x}\sup (-\frac{c^T}{\lambda} x-f(x)),\lambda >0\\-\infin, \lambda =0\end{cases}\\
&=\begin{cases}-\lambda f^*(-\frac{c}{\lambda}),\lambda >0\\-\infin ,\lambda=0\end{cases}
\end{aligned}$$

Dual problem:
$$\begin{aligned}
&\underset{x}\max&-\lambda f^*(-\frac{c}{\lambda})\\
&\text{s.t. }&\lambda >0
\end{aligned}$$

Since $h(c,-\lambda)=-\lambda f^*(-\frac{c}{\lambda})$ is the perspective function of convex function $f^*(c)$, the dual problem is convex.

---
### 5.4
(a) Let $c^T=\lambda_1 w ^TA$, then:
$$\underset{x}\inf\left(c^Tx\right)=\begin{cases}\lambda_1 w ^Tb,\lambda_1\le 0\\-\infin,\text{otherwise}\end{cases}$$

(b) 
$$\begin{aligned}
&\underset{\lambda_1,w }\max&\lambda_1 w ^T b\\
&\text{s.t. }&w \succeq 0,\lambda_1 \le 0\\
& &c=\lambda_1 A^T w 
\end{aligned}$$

(c) Lagrangian function:
$$L(x,\lambda_2)=c^Tx+\lambda_2^T(Ax-b)$$

Dual function:
$$\begin{aligned}
g(\lambda)
&=\underset{x}\inf\left(c^Tx+\lambda_2^T(Ax-b)\right)\\
&=\underset{x}\inf\left((c^T1+\lambda_2^T A)x-\lambda_2^T b\right)\\
&=\begin{cases}-\lambda_2^T b,(c^T1+\lambda_2^T A)=0\\-\infin,\text{otherwise}\end{cases}
\end{aligned}$$

Dual problem:
$$\begin{aligned}
&\underset{\lambda_2}\max &-\lambda_2^T b\\
&\text{s.t. }&(c^T1+\lambda_2^T A)=0\\
& &\lambda_2 \succeq 0
\end{aligned}$$

Denote $\lambda^T=-\lambda_2^T=\lambda_1w ^T$, then the two problems above becomes the same:
$$\begin{aligned}
&\underset{\lambda}\max &\lambda^T b\\
&\text{s.t. }&c=A^T\lambda,\lambda \preceq 0
\end{aligned}$$

---
### 5.6
(a) Given the fact that $\lVert z\rVert _\infin\le \lVert z\rVert _2, \lVert z\rVert _2\le \sqrt{m}\lVert z\rVert _\infin$:
$$\lVert Ax_{ls}-b\rVert _\infin\le \lVert Ax_{ls}-b\rVert _2\le \lVert Ax_{ch}-b\rVert _2\le \sqrt{m}\lVert Ax_{ch}-b\rVert _\infin$$

(b) 
$$\begin{aligned}
&x_{ls}=(A^TA)^{-1}A^Tb\\
\Rightarrow &r_{ls}=b-A(A^TA)^{-1}A^Tb\\
\Rightarrow &A^Tr_{ls}=A^Tb-A^TA(A^TA)A^Tb=0\\
\Rightarrow &A^T\hat\nu=A^T\tilde\nu=0 
\end{aligned}$$

and $\lVert\hat\nu \rVert _1=\lVert\tilde\nu\rVert _1=1\le 1$, hence they're both feasible.

$$b^T\tilde\nu
=\frac{b^Tr_{ls}}{\lVert r_{ls}\rVert _1}
=\frac{b^Tr_{ls}-((A^Tr_{ls})^Tx_{ls})^T}{\lVert r_{ls}\rVert _1}
=\frac{(b-Ax_{ls})^Tr_{ls}}{\lVert r_{ls}\rVert _1}
=\frac{\lVert r_{ls}\rVert _2^2}{\lVert r_{ls}\rVert _1}$$
$$b^T\hat\nu=-b^T\tilde\nu
=-\frac{\lVert r_{ls}\rVert _2^2}{\lVert r_{ls}\rVert _1}<b^T\tilde\nu$$

$b^T\tilde\nu$ is the better bound.

The bound in part (a) is $\frac{\lVert Ax_{ls}-b\rVert _\infin}{\sqrt{m} }=\frac{\lVert r_{ls}\rVert _\infin}{\sqrt{m} }\le \frac{\lVert r_{ls}\rVert _2}{\sqrt{m} }\le\frac{\lVert r_{ls}\rVert _2^2}{\lVert r_{ls}\rVert _1}=b^T\tilde\nu$.

--- 
### 5.7
(a) Lagrangian function:
$$L(x,\lambda)=\underset{i}\max\left(y_i\right)+\sum_i\lambda_i(a_i^Tx+b_i-y_i)$$

Dual function:
$$\begin{aligned}
g(\lambda)
&=
\underset{x,y}\inf\left(\underset{i}\max\left(y_i\right)+\sum_i\lambda_i(a_i^Tx+b_i-y_i)\right)\\
&=
\begin{cases}
    \underset{y}\inf \left(\underset{i}\max\left(y_i\right)+\lambda^Tb-\lambda^Ty\right),\sum_i\lambda_ia_i=0\\
    -\infin ,\text{otherwise}
\end{cases}\\
&=
\begin{cases}
    \lambda^Tb,\sum_i\lambda_ia_i=0,\lambda\succeq 0,1^T\lambda=1\\
    -\infin ,\text{otherwise}
\end{cases}
\end{aligned}$$

Dual problem:
$$\begin{aligned}
&\underset{\lambda}\max &\lambda^T b\\
&\text{s.t. }&\sum_i\lambda_ia_i=0\\
& &\lambda\succeq 0,1^T\lambda=1
\end{aligned}$$

(b)
$$\begin{aligned}
&\underset{x,y}\max &y\\
&\text{s.t. }&a_i^Tx+b_i-y\le 0,i=1,...,m
\end{aligned}$$

Dual function:
$$g(\lambda)=\underset{x,y}\inf\left(y+\sum_i\lambda_i(a_i^Tx+b_i-y)\right)$$

Dual problem:
$$\begin{aligned}
&\underset{\lambda}\max &\lambda^T b\\
&\text{s.t. }&\sum_i\lambda_ia_i=0\\
& &\lambda\succeq 0,1^T\lambda=1
\end{aligned}$$

The LP dual is equal to the dual obtained in part (a).

(c) Let $b^T\nu^*-\sum_i \nu_i^*\log \nu_i^*$ be the optimal value of the dual GP, then
$$p_{gp}^*=b^T\nu^*-\sum_i \nu_i^*\log \nu_i^* \le p_{pwl}^*-\sum_i \nu_i^*\log \nu_i^*\\
\Rightarrow p_{gp}^*-p_{pwl}^*\le -\sum_i \nu_i^*\log \nu_i^*\le \log m$$

Therefore, $0\le p_{gp}^*-p_{pwl}^*\le \log m$.

(d) Lagrangian function:
$$L(x,y,z)=\frac{1}{\gamma}\log\sum_i \exp(\gamma y_i)+z^T(Ax+b-y)$$

Dual function:
$$g(z)=\begin{cases}\underset{y}\inf\text{ }\frac{1}{\gamma}\log\sum_i\exp(\gamma y_i)+z^T(b-y),A^Tz=0\\-\infin,\text{otherwise}\end{cases}$$

Let $\frac{d\frac{1}{\gamma}\log\sum_i\exp(\gamma y_i)+z^T(b-y)}{dy}=0$, then we get $\frac{e^{\gamma y_i}}{\sum_i e^{\gamma y_i}}=z_i$ for all $i$.

That is solvable only when $1^Tz=1,z\succeq 0$. 

At this moment, $y_i=\frac{\log (z_i\sum_j e^{\gamma y_j})}{\gamma}$.

$$\Rightarrow g(z)=\begin{cases}b^Tz-\frac{1}{\gamma}\sum_i z_i\log z_i,A^Tz=0,1^Tz=1,z\succeq 0\\-\infin,\text{otherwise}\end{cases}$$

Dual problem:
$$\begin{aligned}
&\underset{}\max & b^Tz-\frac{1}{\gamma}\sum_i z_i\log z_i\\
&\text{s.t. } & A^Tz=0,1^Tz=1\end{aligned}$$

Denote the optimal value of it as $p^*_{gp}(\gamma)$, then:
$$p_{gp}^*(\gamma)=b^Tz^*-\frac{1}{\gamma}\sum_i z_i^*\log z_i^*\le b^Tz^*+\frac{1}{\gamma}\log m=p^*_{pwl}+\frac{1}{\gamma}\log m$$

i.e. $p^*_{gp}(\gamma)-p^*_{pwl}\le \frac{1}{\gamma}\log m$

In conclusion, as we increase $\gamma$, $p^*_{gp}(\gamma)$ become closer to $p^*_{pwl}$.

--- 
### 5.9 
(a) 
$$\begin{bmatrix}\sum_k a_ka_k^T&a_i\\a_i^T&1\end{bmatrix}=\begin{bmatrix}\sum_{k\neq i}a_ka_k^T&0\\0&0\end{bmatrix}+\begin{bmatrix}a_i\\1\end{bmatrix}[a_i,1]\succeq 0$$

Then the Schur complements of the top left block $1-a_i^T(\sum_ka_ka_k^T)^{-1}a_i\ge 0$ i.e. $a_i^TX_{sim}a_i\le 1$.

In conclusion, $X_{sim}$ is feasible.

(b) Let $\lambda =t1$, then the problem becomes
$$\begin{aligned}
&\underset{t}\max\text{ }&\log\det\left(\sum_i a_ia_i^T\right)+n\log t-mt+n\\
&\text{s.t. }& t\ge 0
\end{aligned}$$

Denote $h(t)=\log\det\left(\sum_i a_ia_i^T\right)+n\log t-mt+n$. Let $h'(t)=0$, we get $t=\frac{n}{m}$, the optimal value of $t$.

The dual objective at this $\lambda$ is 
$$g(\lambda)=\log\det\left(\sum_i a_ia_i^T\right)+n\log \frac{n}{m}=\log\det\left(\sum_i a_ia_i^T\cdot\left(\frac{n}{m}\right)^n\right)$$

This is equal to the primal objective value for $X=\left(\frac{m}{n}\right)^n X_{sim}$ but no more then the optimal value.

The volume of ellipsoid is proportional to $e^{-\frac{F}{2}}$, where $F$ is the optimal value of the primal objective.

Therefore, the volume of the given ellipsoid is no more than $(\frac{m}{n})^{\frac{n}{2}}$ more than the volume of the minimum volume ellipsoid.

--- 
### 5.10 
(a) Let $X=\sum_i x_iv_iv_i^T$, then the problem becomes:
$$\begin{aligned}
&\underset{x}\max\text{ }&\log\det(X^{-1})\\
&\text{s.t. } &X=\sum_i x_iv_iv_i^T\\
& &x\succeq 0,1^Tx=1
\end{aligned}$$

Lagrangian function:
$$\begin{aligned}
L(x,U,u,w)
&=\log\det(X^{-1})+\textbf{tr}(UX)-\sum_ix_iv_i^TUv_i-u^Tx+w(1^Tx-1)\\
&=\log\det(X^{-1})+\textbf{tr}(UX)-\sum_i x_i(v_i^TUv_i+u_i-w)-w
\end{aligned}$$

Dual function:
$$
g(U,u,w)
=\begin{cases}\underset{X}\inf \left(\log\det(X^{-1})+\textbf{tr}(UX)-w\right),v_i^TUv_i+u_i-w=0\text{ for } i\in[1,p]\\-\infin,\text{otherwise}\end{cases}
$$

Denote $h(X)=\log\det(X^{-1})+\textbf{tr}(UX)-w$, then 
$$h'(X)=\frac{d\log\det(X^{-1})}{d\det(X^{-1})}\cdot\frac{d\det(X^{-1})}{dX^{-1} }\cdot\frac{dX^{-1} }{dX^T}+U\frac{d\textbf{ tr}X}{dX^T}=-X^{-1}+U$$

Let $h'(X)=0$, then we get $X=U^{-1}$.

$$
g(U,u,w)=\begin{cases}\log\det U+p-w,v_i^TUv_i+u_i-w=0\text{ for } i\in[1,p]\\-\infin,\text{otherwise}\end{cases}
$$

Dual problem:
$$\begin{aligned}
&\underset{U,w}\max &\log\det U+p-w\\
&\text{s.t. }& v_i^TUv_i\le w\text{ for } i\in[1,p]
\end{aligned}$$

Simplified dual problem:
$$\begin{aligned}
&\underset{U'}\max &\log\det U'+p\log p\\
&\text{s.t. }& v_i^TU'v_i\le 1\text{ for } i\in[1,p]
\end{aligned}$$

(b) Let $X=\sum_i x_iv_iv_i^T$, then the problem becomes:
$$\begin{aligned}
&\underset{x}\max\text{ }&\textbf{tr}(X^{-1})\\
&\text{s.t. } &X=\sum_i x_iv_iv_i^T\\
& &x\succeq 0,1^Tx=1
\end{aligned}$$

Lagrangian function:
$$\begin{aligned}
L(x,U,u,w)
&=\textbf{tr}(X^{-1})+\textbf{tr}(UX)-\sum_ix_iv_i^TUv_i-u^Tx+w(1^Tx-1)\\
&=\textbf{tr}(X^{-1})+\textbf{tr}(UX)-\sum_i x_i(v_i^TUv_i+u_i-w)-w
\end{aligned}$$

Dual function:
$$
g(U,u,w)
=\begin{cases}\underset{X}\inf \left(\textbf{tr}(X^{-1})+\textbf{tr}(UX)-w\right),v_i^TUv_i+u_i-w=0\text{ for } i\in[1,p]\\-\infin,\text{otherwise}\end{cases}
$$

Denote $h(X)=\textbf{tr}(X^{-1})+\textbf{tr}(UX)$, then $h'(X)=-X^{-2}+U$.

Let $h'(X)=0$, then we get $X=U^{-\frac{1}{2} },(U\in S^p_{++})$.

$$
g(U,u,w)
=\begin{cases}2\textbf{ tr}(U^{\frac{1}{2} })-w,v_i^TUv_i+u_i-w=0\text{ for } i\in[1,p],U\succ 0 \\-\infin,\text{otherwise}\end{cases}
$$

Dual problem:
$$\begin{aligned}
&\underset{U,w}\max &2\textbf{ tr}(U^{\frac{1}{2} })-w\\
&\text{s.t. }& v_i^TUv_i\le w\text{ for } i\in[1,p]\\
& &U\succ 0
\end{aligned}$$

Simplified dual problem:
$$\begin{aligned}
&\underset{U}\max &(\textbf{tr}(U'^{\frac{1}{2} }))^2\\
&\text{s.t. }& v_i^TU'v_i\le 1\text{ for } i\in[1,p]\\
& &U'\succ 0
\end{aligned}$$


--- 
### 5.11
Let $y_i=A_ix+b_i$, then the problem becomes
$$\begin{aligned}
&\underset{x,y}\min &\sum_i\lVert y_i\rVert _2+
\frac{\lVert x-x_0\rVert _2^2}{2}\\
&\text{s.t. }& y_i=A_ix+b_i,i=1,...,N\end{aligned}$$

Lagrangian function:
$$L(x,\lambda_1,\lambda_2,...,\lambda_N)=\sum_i\lVert y_i\rVert _2+\frac{\lVert x-x_0\rVert _2^2}{2}+\sum_i \lambda_i^T(y_i-A_ix-b_i)$$

Dual function:
$$\begin{aligned}
g(\lambda_1,\lambda_2,...,\lambda_N)
&=\underset{x,y}\inf \left(\sum_i\lVert y_i\rVert _2+\frac{\lVert x-x_0\rVert _2^2}{2}+\sum_i \lambda_i^T(y_i-A_ix-b_i)\right)\\
&=\underset{x,y}\inf \left(\sum_i(\lVert y_i\rVert _2+\lambda_i^Ty_i)+(\frac{\lVert x-x_0\rVert _2^2}{2}-\sum_i \lambda_i^TA_ix)-\sum_i\lambda_i^Tb_i\right)
\end{aligned}$$

$$\underset{y}\inf \left(\sum_i(\lVert y_i\rVert _2+\lambda_i^Ty_i)\right)
=\underset{y}\inf \left(\sum_i\lVert y_i\rVert _2(1+\frac{\lambda_i^Ty_i}{\lVert y_i\rVert _2})\right)
=\begin{cases}0,\lVert \lambda_i\rVert _2\le 1\text{ for }i\in[1,N]\\-\infin,\text{otherwise}\end{cases}$$

$$\underset{x}\inf \left(\frac{\lVert x-x_0\rVert _2^2}{2}-\sum_i \lambda_i^TA_ix\right)=\left(\frac{\lVert x-x_0\rVert _2^2}{2}-\sum_i \lambda_i^TA_ix\right)\Big|_{x=x_0+\sum_j A_j^T\lambda}=-\frac{\lVert\sum_iA_i^T\lambda_i\rVert _2^2}{2}-\sum_i A_ix_0^T\lambda_i$$

$$
\Rightarrow g(\lambda_1,\lambda_2,...,\lambda_N)
=\begin{cases}-\frac{\lVert\sum_iA_i^T\lambda_i\rVert _2^2}{2}-\sum_i(A_ix_0+b_i)^T\lambda_i,\lVert \lambda_i\rVert _2\le 1\text{ for }i\in[1,N]\\-\infin,\text{otherwise}\end{cases}
$$

Dual problem:
$$\begin{aligned}
&\underset{\lambda_1,\lambda_2,...,\lambda_N}\max &-\frac{\lVert\sum_iA_i^T\lambda_i\rVert _2^2}{2}-\sum_i(A_ix_0+b_i)^T\lambda_i\\
&\text{s.t. }& \lVert \lambda_i\rVert _2\le 1,i=1,...,N\end{aligned}$$

--- 
### 5.12 
Let $y_i=b_i-a^T_ix$, then the problem becomes
$$\begin{aligned}
&\underset{x,y}\min &-\sum_i\log(y_i)\\
&\text{s.t. }& y=b-Ax\end{aligned}$$

Lagrangian function:
$$L(x,y,\lambda)=-\sum_i\log(y_i)+\lambda^T(y-b+Ax)$$

Dual function:
$$\begin{aligned}
g(\lambda)
&=\underset{x,y}\inf \left(-\sum_i\log(y_i)+\lambda^T(y-b+Ax)\right)\\
&=\begin{cases}\sum_i\log \lambda_i+m-\lambda^Tb,A^T\lambda=0,\lambda\succ 0\\-\infin,\text{otherwise}\end{cases}
\end{aligned}$$

Dual problem:
$$\begin{aligned}
&\underset{\lambda}\max &\sum_i\log \lambda_i+m-\lambda^Tb\\
&\text{s.t. }& A^T\lambda=0,\lambda\succ 0\end{aligned}$$

--- 
### 5.13
(a) Dual function:
$$\begin{aligned}
g(\lambda,\nu)
&=\underset{x}\inf\left(c^Tx+\lambda^T(Ax-b)+\nu^Tx-x^T\mathbf{diag}(\nu)x\right)\\
&=\underset{x}\inf\left(-x^T\mathbf{diag}(\nu)x+(c^T+\lambda^TA+\nu^T)x-\lambda^Tb\right)\\
&=\begin{cases}\frac{1}{4}\sum_i\frac{(c_i+\lambda^Ta_i+\nu_i)^2}{\nu_i}-\lambda^Tb,\nu\preceq 0\\-\infin,\text{otherwise}\end{cases}
\end{aligned}$$

Dual problem:
$$\begin{aligned}
&\underset{\lambda,\nu}\max &\frac{1}{4}\sum_i\frac{(c_i+\lambda^Ta_i+\nu_i)^2}{\nu_i}-\lambda^Tb\\
&\text{s.t. }&\lambda\succeq 0,\nu\preceq 0
\end{aligned}$$

(b) Consider simplifying the dual problem in part (a):

Let $f(\nu_i)=\frac{(c_i+\lambda^Ta_i+\nu_i)^2}{\nu_i}$, then $f(\nu_i)=\begin{cases}4(c_i+\lambda^Ta_i),c_i+\lambda^Ta_i\le 0\\0,c_i+\lambda^Ta_i>0\end{cases}=\min\{0,4(c_i+\lambda^Ta_i)\}$.

Therefore, the dual problem can be simplified as:
$$\begin{aligned}
&\underset{\lambda}\max &\sum_i\min\{0,(c_i+\lambda^Ta_i)\}-\lambda^Tb\\
&\text{s.t. }&\lambda\succeq 0
\end{aligned}$$

For the LP relaxation:

- Lagrangian function:
$$\begin{aligned}L(x,u,v,w)&=c^Tx+u^T(Ax-b)-v^Tx+w^T(x-1)\\&=(c^T+u^TA-v^T+w^T)x-b^Tu-1^Tw\end{aligned}$$
- Dual function:
$$g(u,v,w)=\begin{cases}-b^Tu-1^Tw,c^T+u^TA-v^T+w^T=0\\-\infin,\text{otherwise}\end{cases}$$
- Dual problem:
$$\begin{aligned}&\underset{u,v,w}\max&-b^Tu-1^Tw\\&\text{s.t. }&u\succeq 0,v\succeq 0,w\succeq 0\\& &c^T+u^TA-v^T+w^T=0\end{aligned}$$
- Another form of dual problem:
$$\begin{aligned}&\underset{u,v,w}\max\text{ }&1^T(c+A^Tu-v)-b^Tu\\&\text{s.t. }&u\succeq 0,v\succeq 0\\& &(c+A^Tu-v)\preceq 0\end{aligned}$$

As we can see, the dual problem of Lagrangian relaxation and the dual problem of LP relaxation are the same. So the lower bounds obtained via them are the same.

--- 
### 5.21
(a) The constraint set is $\{(x,y)|x=0,y>0\}$, which is convex.

The objective function $f(x,y)$ is convex since $\nabla^2f=\begin{pmatrix}e^{-x}&0\\0&0\end{pmatrix}\succeq 0$.

Hence this is a convex optimization problem. The optimal value is obviously 1.

(b) Dual function:
$$g(\lambda)=\underset{x,y>0}\inf \left(e^{-x}+\lambda\frac{x^2}{y}\right)=\begin{cases}0,\lambda\ge0\\-\infin,\lambda<0\end{cases}$$

Dual problem:
$$\begin{aligned}
&\underset{\lambda}\max &0\\
&\text{s.t. }&\lambda\succeq 0
\end{aligned}$$

Obviously, $\lambda^*\in\mathbb{R},d^*=0$, and the optimal duality gap is $p^*-d^*=1$.

(c) Slater's condition does not hold for this problem.

(d) $p^*(u)=\begin{cases}1,u=0\\0,u>0\end{cases}$.

When $u>0$, the dual problem is:
$$\begin{aligned}
&\underset{\lambda}\max &-\lambda u\\
&\text{s.t. }&\lambda\succeq 0
\end{aligned}$$

Then $-\lambda^*u=0$. So the global sensitivity inequality does not hold.

--- 
### 5.27
Lagrangian function:
$$
\begin{aligned}
L(x,\nu)&=\lVert Ax-b\rVert _2^2+\nu^T(Gx-h)\\
&=x^TA^TAx+(G^T\nu-2A^Tb)^Tx-\nu^Th
\end{aligned}
$$

KKT conditions:
1. Primal constraints: $Gx^*-h=0$
2. Dual constraints: None
3. Complementary slackness: None
4. Gradient of Lagrangian with respect to $x$ vanishes: $2A^TAx^*+G^T\nu-2A^Tb=0$

According to the KKT conditions, we can solve the equations and get:
$$\nu^*=2(G(A^TA)^{-1}G^T)^{-1}(G(A^TA)^{-1}A^Tb-h)$$

$$x^*=(A^TA)^{-1}\left(G^T(G(A^TA)^{-1}G^T)^{-1}(h-G(A^TA)^{-1}A^Tb)+A^Tb\right)$$

---
### 5.30
Lagrangian function:
$$
L(X,\lambda)=\textbf{tr }X-\log\det X+\lambda^T(Xs-y)
$$

KKT conditions:
1. Primal constraints: $X^*s=y,X^*\succ 0$
2. Dual constraints: None
3. Complementary slackness: None
4. Gradient of Lagrangian with respect to $x$ vanishes: $I-(X^*)^{-1}+\frac{1}{2}(\lambda s^T+s\lambda^T)=0$

According to the KKT conditions:

$$\begin{aligned}
&(X^*)^{-1}=I+\frac{1}{2}(\lambda s^T+s\lambda^T)\\
\Rightarrow &s=(X^*)^{-1}y=y+\frac{1}{2}(\lambda+(\lambda^Ty)s)\\
\Rightarrow &\lambda^Ty+y^Ty=1\\
\Rightarrow &\lambda=(1+y^Ty)s-2y\\
\Rightarrow &X^{-1}=I+(1+y^Ty)ss^T-ys^T-sy^T\\
\Rightarrow &X^*=I+yy^T-\frac{1}{s^Ts}ss^T
\end{aligned}$$

---