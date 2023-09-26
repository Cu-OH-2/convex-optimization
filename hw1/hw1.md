### Q1：$\inf\{sin(n):n\ge 1\}=?$ write down the answer and prove it

$\inf\{\sin(n):n\ge 1\}=-1$，证明：

首先，$sin(n)\ge-1$，因此 $-1<=sin(n), \forall n\ge 1$.\
假设存在 $u$ 满足 $u\le x, \forall x\in \{\sin(n):n\ge 1\}$ 且 $u>-1$\
由 $\sin(\frac{3\pi}{2})=-1\in \{\sin(n):n\ge 1\}$，得 $u\le-1$，这与 $u>-1$ 矛盾，假设不成立.\
所以 $\inf\{\sin(n):n\ge 1\}=-1$.

---

### Q2: Prove Cauchy-Schwartz inequality $\bold{x}^T\bold{y}\le \Vert \bold{x}\Vert_2 \Vert \bold{y}\Vert_2$ in two ways

方法1：\
$\bold{x}^T\bold{y}=\sum_i x_iy_i$, $\Vert \bold{x}\Vert_2 \Vert \bold{y}\Vert_2=\sqrt{\sum_i x_i^2}\sqrt{\sum_i y_i^2}$\
要证 $\bold{x}^T\bold{y}\le \Vert \bold{x}\Vert_2 \Vert \bold{y}\Vert_2$\
即证 $\sum_i x_iy_i\le \sqrt{\sum_i x_i^2}\sqrt{\sum_i y_i^2}$\
即证 $(\sum_i x_iy_i)^2\le \sum_i x_i^2{\sum_i y_i^2}$\
即证 $\sum_{i=1}^n x_i^2y_i^2+\sum_{i=1}^n\sum_{j=i+1}^n 2x_iy_ix_jy_j\le \sum_{i=1}^n x_i^2y_i^2+\sum_{i=1}^n\sum_{j=i+1}^n (x_i^2y_j^2+x_j^2y_i^2)$\
即证 $\sum_{i=1}^n\sum_{j=i+1}^n 2x_iy_ix_jy_j\le \sum_{i=1}^n\sum_{j=i+1}^n (x_i^2y_j^2+x_j^2y_i^2)$\
由于 $(x_iy_j-x_jy_i)^2=(x_i^2y_j^2+x_j^2y_i^2)-2x_iy_ix_jy_j \ge 0$，有 $2x_iy_ix_jy_j\le (x_i^2y_j^2+x_j^2y_i^2), \forall i,j\in[1,n]$\
因此 $\sum_{i=1}^n\sum_{j=i+1}^n 2x_iy_ix_jy_j\le \sum_{i=1}^n\sum_{j=i+1}^n (x_i^2y_j^2+x_j^2y_i^2)$，原命题得证.

方法2：\
若 $\bold{x}=0$ 或 $\bold{y}=0$，$\bold{x}^T\bold{y}=\Vert \bold{x}\Vert_2 \Vert \bold{y}\Vert_2=0$，不等式成立.\
否则 $\cos{\langle\bold{x},\bold{y}\rangle}=\frac{\bold{x}^T\cdot\bold{y}}{\Vert \bold{x}\Vert_2 \Vert \bold{y}\Vert_2}\le 1$，$\Vert \bold{x}\Vert_2 \Vert \bold{y}\Vert_2> 0$，得 $\bold{x}^T\bold{y}\le \Vert \bold{x}\Vert_2 \Vert \bold{y}\Vert_2$，不等式成立.\
综上，不等式成立.

---

### Q3: Let $\bold{A}$ be a matrix of size $m\times n$. Denote the range space of $\bold{A}$ as $R(\bold{A})$ and the null space of $\bold{A}$ as $N(\bold{A})$, respectively. Prove $R(\bold{A})=N^\perp(\bold{A}^T)$

$R(\bold{A})=\{\bold{Ax}|\bold{x}\in \mathbb{R}^n\}$\
$R^\perp(\bold{A})=\{\bold{y}|\bold{x}^T\bold{y}=0,\forall\bold{x}\in R(\bold{A})\}$\
$N(\bold{A}^T)=\{\bold{x}|\bold{A}^T\bold{x}=0\}$\
$N^\perp(\bold{A}^T)=\{\bold{y}|\bold{x}^T\bold{y}=0,\forall \bold{x}\in N(\bold{A}^T)\}$

先证 $\forall \bold{u}\in R(\bold{A}),\bold{u}\in N^\perp(\bold{A}^T)$：\
假设 $\bold{u}\in R(\bold{A})$，则 $\exist\bold{v}\in \mathbb{R}^n,\bold{Av}=\bold{u}$.\
任取 $\bold{x}\in N(\bold{A}^T)$，有 $\bold{A}^T\bold{x}=0$，$(\bold{A}^T\bold{x})^T=\bold{x}^T\bold{A}=0$，$\bold{x}^T\bold{Av}=\bold{x}^T\bold{u}=0$.\
所以 $\bold{u}\in N^\perp(\bold{A}^T)$，结论得证.

再证 $\forall \bold{u}\in N^\perp(\bold{A}^T),\bold{u}\in R(\bold{A})$：\
即证 $\forall \bold{u}\in R^\perp(\bold{A}),\bold{u}\in N(\bold{A}^T)$.\
假设 $\bold{u}\in R^\perp(\bold{A})$，则 $\forall \bold{x}\in \mathbb{R}^{n},(\bold{Ax})^T\bold{u}=0$，即 $\forall \bold{x}\in \mathbb{R}^{n},\bold{x}^T(\bold{A}^T\bold{u})=0$.\
因此 $\bold{A}^T\bold{u}=0$，即 $\bold{u}\in N(\bold{A}^T)$，结论得证.

综上，$R(\bold{A})=N^\perp(\bold{A}^T)$ 得证.

---

### Q4: For any two matrices, prove $trace(\bold{AB})=trace(\bold{BA})$

假设 $\bold{A}\in\mathbb{R}^{n\times m}$，$\bold{B}\in\mathbb{R}^{m\times n}$：\
$trace(\bold{AB})=\sum_{i=1}^n(\bold{AB})_{ii}=\sum_{i=1}^n\sum_{j=1}^m \bold{A}_{ij}\bold{B}_{ji}=\sum_{j=1}^m\sum_{i=1}^n \bold{B}_{ji}\bold{A}_{ij}=\sum_{j=1}^m(\bold{BA})_{jj}=trace(\bold{BA})$

---

### Q5: Prove a useful inequality: $\bold{A}\succeq 0\Leftrightarrow \langle\bold{A},\bold{B}\rangle\ge 0$ for all $\bold{B}\succeq 0$

假设 $A,B\in\mathbb{R}^{n\times n}$：

先证充分性 $\bold{A}\succeq 0\Rightarrow \langle\bold{A},\bold{B}\rangle\ge 0, \forall\bold{B}\succeq 0$：\
特征值分解 $\bold{A}=\bold{P}^T\bold{CP},\bold{B}^T=\bold{Q}^T\bold{D}\bold{Q}$，其中 $\bold{P},\bold{Q}$ 为单位正交阵\
$\langle\bold{A},\bold{B}\rangle=trace(\bold{AB}^T)=trace(\bold{\bold{P}^T\bold{CPQ}^T\bold{D}^T\bold{Q}})=trace(\bold{CDP}^T\bold{P}\bold{Q}^T\bold{Q})=trace(\bold{CD})\ge 0$

再证必要性 $\langle\bold{A},\bold{B}\rangle\ge 0,\forall\bold{B}\succeq 0 \Rightarrow \bold{A}\succeq 0$：\
假设 $\bold{A}\nsucceq0$，则 $\exist \bold{u}\neq 0,\bold{u}^T\bold{Au}<0$\
取 $\bold{B}=\bold{uu}^T$，则 $\langle\bold{A},\bold{B}\rangle=trace(\bold{AB}^T)=trace(\bold{Auu}^T)=\langle\bold{Au},\bold{u}\rangle=\bold{u}^T\bold{Au}<0$\
与条件矛盾，假设不成立.

原命题得证.

---

### Q6: Define $f(\bold{x})\triangleq \Vert\bold{Ax}-\bold{b}\Vert_2^2$. Compute $\nabla f(\bold{x})$ and $\nabla^2 f(\bold{x})$

$\nabla f(\bold{x})=$

$\nabla^2 f(\bold{x})=$

---

### Q7: Define $f(\bold{x})\triangleq \Vert\bold{Ax}-\bold{xx}^T\Vert_F^2$. Compute $\nabla f(\bold{x})$ and $\nabla^2 f(\bold{x})$



---

### Q8: For the logistic regression example in lecture notes, compute $\nabla^2 E(\bold{w})$



---

### Q9: Define $f(\bold{x})\triangleq \log{\sum_{k=1}^n (\exp(x_k))}$. Prove $\nabla^2 f(\bold{x})\succeq 0$

$\nabla^2 f(\bold{x})=\begin{pmatrix}
\frac{\exp(x_1)\left(\sum_{k=1}^{n}\exp(x_k)\right)-\exp(x_1)^2}{\left(\sum_{k=1}^{n}\exp(x_k)\right)^2} & \frac{-\exp(x_1)\exp(x_2)}{\left(\sum_{k=1}^{n}\exp(x_k)\right)^2} & \cdots & \frac{-\exp(x_1)\exp(x_n)}{\left(\sum_{k=1}^{n}\exp(x_k)\right)^2} \\
\frac{-\exp(x_2)\exp(x_1)}{\left(\sum_{k=1}^{n}\exp(x_k)\right)^2} & \frac{\exp(x_2)\left(\sum_{k=1}^{n}\exp(x_k)\right)-\exp(x_2)^2}{\left(\sum_{k=1}^{n}\exp(x_k)\right)^2} & \cdots & \frac{-\exp(x_2)\exp(x_n)}{\left(\sum_{k=1}^{n}\exp(x_k)\right)^2} \\
\vdots & \vdots & & \vdots \\
\frac{-\exp(x_n)\exp(x_1)}{\left(\sum_{k=1}^{n}\exp(x_k)\right)^2} & \frac{-\exp(x_n)\exp(x_2)}{\left(\sum_{k=1}^{n}\exp(x_k)\right)^2} & \cdots & \frac{\exp(x_n)\left(\sum_{k=1}^{n}\exp(x_k)\right)-\exp(x_n)^2}{\left(\sum_{k=1}^{n}\exp(x_k)\right)^2}
\end{pmatrix}$

---

### Q10: Find at least one example in either of the following two fields that can be formulated as an optimization problem and show how to formulate it: 1.EDA software 2.cluster scheduling for data centers

