---
{"dg-publish":true,"permalink":"/MATH/交换代数/Nodes/7 Noetherian Rings/","dgPassFrontmatter":true}
---


> Highlight: Hilbert basis theorem, Hilbert Nullstellensatz

> [!proposition]
> If $A$ is Noetherian, then $A/\alpha$ is also Noetherian.

`\begin{proof}`
By [[MATH/交换代数/Nodes/6 Chain Condition#^7j4294\|6 Chain Condition#^7j4294]].
`\end{proof}`


> [!proposition]
> Let $A\subseteq B$ be a subring, where $A$ is Noetherian and $B$ is a finitely generated $A$-module. Then $B$ is a Noetherian ring. 

`\begin{proof}`
By [[MATH/交换代数/Nodes/6 Chain Condition#^8ezl57\|6 Chain Condition#^8ezl57]], $B$ is a Noetherian $A$-module. For any $B$-submodule $N$ of $B$, it is also a $A$-submodule and so is finitely generated over $A$. Then $N$ is finitely generated over $B$. Thus $B$ is a Noetherian $B$-module.
`\end{proof}`


> [!theorem] Hilbert basis theorem
> Let $A$ be a Noetherian ring. Then $A[x]$ is also a Noetherian ring. 
> 
{ #b4d5c1}


`\begin{proof}`
Let $\alpha\subseteq A[x]$ be an ideal. Let $I=\{\text{leading coefficients of }f(x)\in \alpha\}$. Note that $I$ is an ideal of $A$, and then $I$ is finitely generated, that is, $I=(a_1,\cdots,a_n)A$. For each $i$, let $f_i=a_ix^{r_i}+\text{lower terms}\in \alpha$. Let $r=\max\{r_i\}_{i=1}^n$. Then we get a sub-ideal $\alpha'=(f_1,\cdots,f_n)A[x]\subseteq \alpha$. 

Let $f\in \alpha$ with $f=ax^m+\text{lower terms}$ and $a\in I$. If $m\geqslant r$, then one can do division using $f_1,\cdots,f_n$, namely, if $a=\sum_{i=1}^n u_ia_i$ with $u_i\in A$, then one can construct 

$$f-\sum_{i=1}^n u_i f_ix^{m-r_i}\in \alpha$$

and its degree $<\deg f$. Repeat this procedure, and we get $f=g+h$ where $g\in \alpha'$ and $\deg h<r$. 

Let $M=\oplus_{i=1}^{r-1}Ax^i\subseteq A[x]$ be a $A$-submodule. By the decomposition $f=g+h$, we have $\alpha=\alpha'+\alpha\cap M$ as $A$-modules. 

But now, $M$ is a Noetherian $A$-module and $\alpha \cap M$ is also Noetherian $A$-module. So $\alpha\cap M=(g_1,\cdots,g_m)_A$. It is easy to see $\alpha=(f_1,\cdots,f_n,g_1,\cdots,g_m)_{A[x]}$ and so $\alpha$ is finitely generated. 
`\end{proof}`

**Remark.** We have proved it [[MATH/抽象代数II/Nodes/2.3 Noetherian Rings and Modules#^75xtmd\|here]]. Similarly, we can prove that if $A$ is Noetherian, then $A[\![x]\!]$ is also Noetherian. The proof is similar, using "lowest term coefficient". See [[MATH/交换代数/Nodes/HW6#^elab7i\|here]]. 


> [!corollary]
> If $A$ is Noetherian, then $A[x_1,\cdots,x_n]$ is also Noetherian. 

> [!corollary]
> Let $B$ be a finitely generated $A$-algebra. If $A$ is Noetherian, then so is $B$. In particular, every finitely generated ring, and every finitely generated algebra over a field, is Noetherian.

`\begin{proof}`
There exists surjective map $A[x_1,\cdots,x_n]\twoheadrightarrow B$. 

Or see [[MATH/抽象代数II/Nodes/2.3 Noetherian Rings and Modules#^gmjk45\|2.3 Noetherian Rings and Modules#^gmjk45]]. 
`\end{proof}`


> [!proposition]
> Let $A \subseteq B \subseteq C$ be rings. Suppose that $A$ is Noetherian, that $C$ is finitely generated as an A-algebra and that $C$ is finitely generated as a B-module. Then $B$ is finitely generated as an A-algebra.
{ #983c2e}


**Counterexample.**
$k\subseteq k[x^n]\subseteq k[x]$, $B=k[x^2+x^3,x^4+x^6,\cdots]$

`\begin{proof}`
Write $C=A[x_1,\cdots,x_m]$ with $x_i\in C$, and write $C=\left\langle y_1,\cdots,y_n\right\rangle_B$ as $B$-module with $y_i\in C$. Then 

$$\begin{aligned}
&x_i=\sum_{j=1}^n b_{ij}y_j,\; b_{ij}\in B\;\;\;(1)\\
&y_iy_j=\sum_{k=1}^n b_{ijk}y_k, \; b_{ijk}\in B\;\;\;(2)
\end{aligned}$$

Let $B_0=A[b_{ij},b_{ijk}]\subseteq B$ be a subring, which is a finitely generated $A$-algebra. So now, it suffices to show $B$ is a finitely generated $B_0$-algebra. But in fact, one can show that $B$ is a finitely generated $B_0$-module. 

Indeed, for any $b\in B\subseteq C=A[x_1,\cdots,x_m]$, $B$ is a polynomial in $x_1,\cdots,x_m$ over $A$ and so $b$ is a polynomial in $y_1,\cdots,y_n$ over $B$ by (1). Furthermore, $b$ is a linear combination of $y_1,\cdots,y_n$ over $B_0$ by (2). Remark that $y_j\in C$ NOT in $B$, so they are not a set of generator of $B$ over $B_0$. But the above argument shows $B\subseteq \left\langle y_1,\cdots,y_n\right\rangle_{B_0}\subseteq C$. 

Since $A$ is a Noetherian ring, by [[MATH/交换代数/Nodes/7 Noetherian Rings#^b4d5c1\|#^b4d5c1]], $B_0=A[b_{ij},b_{ijk}]$ is also Noetherian ring. Then it yields that $\left\langle y_1,\cdots,y_n\right\rangle_{B_0}\supseteq B$ is a Noetherian $B_0$-module. So $B$ is a Noetherian $B_0$-module, proving the claim. 
`\end{proof}`


> [!proposition]
> Let $k$ be a field, and let $E$ be a finitely generated $k$-algebra. If $E$ is also a field, then $E/k$ is a finite extension.
{ #f58c35}


`\begin{proof}`
Write $E=k[x_1,\cdots,x_n]$ where $x_i\in E$. Since $E$ is also a field, $E=k(x_1,\cdots,x_n)$. If $E/k$ is not a finite extension, then not all $x_i$ are algebraic over $k$. We can reorder $x_i$ such that $x_1,\cdots,x_r$ are algebraic independent over $k$, and $x_{r+1},\cdots,x_n$ are algebraic over $k(x_1,\cdots,x_r):=F$. So we get $k\subseteq F\subseteq E$ where $E$ is a finitely generated $k$-algebra and $E$ is finitely generated $F$-module. By [[MATH/交换代数/Nodes/7 Noetherian Rings#^983c2e\|#^983c2e]], $F$ is a finitely generated $k$-algebra.

We claim that it is impossible. That is, it is impossible to write $k(x_1,\cdots,x_r)=k[y_1,\cdots,y_m]$. Indeed, write $y_j=f_j(x_1,\cdots,x_r)/g_j(x_1,\cdots,x_r)$ where $f_j,g_j\in k[x_1,\cdots,x_r]$, then $1/(g_1\cdots g_m+1)\notin\text{RHS}$. 
`\end{proof}`


> [!corollary]
> Let $k$ be a field, and let $A$ be a finitely generated $k$-algebra. If $m\subseteq A$ is a maximal ideal, then $A/m$ is a finitely extension of $k$.
{ #0346fb}


`\begin{proof}`
Let $E=A/m$ in [[MATH/交换代数/Nodes/7 Noetherian Rings#^f58c35\|#^f58c35]]. 
`\end{proof}`


> [!corollary] Hilbert Nullstellensatz, weak form
> Let $k$ be a algebraic closed field. If $m\subseteq k[x_1,\cdots,x_n]$ is a maximal ideal, then $m=(x_1-a_1,\cdots,x_n-a_n)$ with $a_i\in k$.
{ #8sohrm}


**Remark.** "null"=zero, "stellen"=point, "satz"=theorem

`\begin{proof}`
It has been proved in [[MATH/代数几何/Nodes/1.1 Some Algebra#^6rh0cw\|1.1 Some Algebra#^6rh0cw]]. 

By [[MATH/交换代数/Nodes/7 Noetherian Rings#^0346fb\|#^0346fb]], $k[x_1,\cdots,x_n]/m$ is a finite extension over $k$. Since $\overline k=k$, one have $k[x_1,\cdots,x_n]/m\stackrel{\theta}{\simeq} k$. Write $\theta(x_i)=a_i\in k$. Then $(x_1-a_1,\cdots,x_n-a_n)\subseteq m$. But LHS is maximal, which yields that $(x_1-a_1,\cdots,x_n-a_n)=m$.
`\end{proof}`


> [!corollary] Equivalent form of [[MATH/交换代数/Nodes/7 Noetherian Rings#^8sohrm\|#^8sohrm]]
> Let $k$ be a algebraic closed field. Let $I=(f_1,\cdots,f_m)\subsetneq k[x_1,\cdots,x_n]$ be a proper ideal. Then these $f_i$ have a common solution in $k^n$. 

`\begin{proof}`
Since $I$ is proper, $I\subseteq m$ for some maximal ideal $m$. By [[MATH/交换代数/Nodes/7 Noetherian Rings#^8sohrm\|#^8sohrm]], $I\subseteq (x_1-a_1,\cdots,x_n-a_n)$ and so $(a_1,\cdots,a_n)$ is a common solution for any $f\in I$. 
`\end{proof}`


**Remark.** For an ideal $I\subseteq k[x_1,\cdots,x_n]$, solution of $I$ is empty iff $I=k[x_1,\cdots,x_n]$. 


> [!theorem] Text-Ex. 7.14.
> It is a strong form of Hilbert Nullstellensatz. 
> 
> Let $\alpha\subsetneq k[x_1,\cdots,x_n]$ be an ideal. Define $V=\{(a_1,\cdots,a_n)\in k^n:f(a_1,\cdots,a_n)=0,\forall f\in \alpha\}$ as the solution set of $\alpha$. Define $I(V)=\{g\in k[x_1,\cdots,x_n]:g(a_1,\cdots,a_n)=0,\forall (a_1,\cdots,a_n)\in \alpha\}$. Then $I(V)=r(\alpha)$. 

`\begin{proof}`
See [[MATH/交换代数/Nodes/HW6#^oex7wh\|here]]. 
`\end{proof}`



