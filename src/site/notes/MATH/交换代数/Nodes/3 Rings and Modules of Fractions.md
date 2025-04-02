---
{"dg-publish":true,"permalink":"/MATH/交换代数/Nodes/3 Rings and Modules of Fractions/","dgPassFrontmatter":true}
---


> [!definition]
> Let $A$ be a ring. We say a subset $S\subseteq A$ is multiplicatively closed if $1\in S$ and $S$ is closed under multiplication. 

> [!definition]
> For multiplication closed $S\subseteq A$, define a relation $\equiv$ on $A\times S$, where $(a,s)\equiv (b,t)$ iff $(at-bs)u=0$ for some $u\in S$. 

We claim that $\equiv$ is an equivalent relation. It suffices to check transitivity. Suppose $(a,s)\equiv (b,t)$ and $(b,t)\equiv (c,u)$, then $(at-bs)v=(bu-ct)w=0$ for some $v,w\in S$. Notice that $(au-cs)tvw=atvuw-ctwsv=bsvuw-buwsv=0$ and we have done. 

> [!definition]
> Let $a/s$ be the equivalent class of $(a,s)$. Let $S^{-1}A$ be the set of equivalent classes, that is, $S^{-1}A:=A\times S/\sim$. One can define a ring structure by $a/s+b/t=(at+bs)/st$ and $a/s\cdot b/t=ab/st$. We call $S^{-1}A$ *the ring of fractions* of $A$ w.r.t. $S$.  

**Remark.** We need to check the computation is well-defined. See [[Pasted image 20250331195545.png|here]]. 

**Fact.** We have a map $A\to S^{-1}A:a\mapsto a/1$. It is NOT necessarily injective. For example, if $0\in S$, then $S^{-1}A=0$. e.g. $A=\mathbb{Z}$ and $S=\{0,1\}$. 

> [!example] important
> Let $I\subseteq A$ be an ideal. Easy fact: $I$ is prime iff $A-I$ is multiplication closed. (if $a,b\notin I$, then $ab\notin I$)
> 
> In this case for $S=A-p$, denote $S^{-1}A$ be $A_p$, and call it the *localization* of $A$ at $p$. 
> 
> Fact: $A_p$ is a local ring. Indeed, consider $m=\{a/s:a\in p\}\subseteq A_p$, it is an ideal. For any $b/t\notin m$, $b\in A-p$ and $t/b\in A_p$ and so $b/t\in (A_p)^\times$. By [[MATH/交换代数/Nodes/1 Rings and Ideals#^ysw57c\|1 Rings and Ideals#^ysw57c]], $m$ is the unique maximal ideal. 
> 
> Fact: $A_p/m\simeq \mathrm{Frac}(A/p)$. Prove later. 

> [!example] also important
> Let $f\in A$. Let $S=\{1,f,\cdots,f^n,\cdots\}$. Then denote $S^{-1}A$ by $A_f$. Note that if $0\in S$, $S^{-1}A=0$. 
> 
> - $A=\mathbb{Z}$, $f=p$, $S=\{p^n\}_{n\geqslant 0}$. $S^{-1}A=\{a/p^n\}_{n\geqslant 0,a\in \mathbb{Z}}$. Here we do not use $\mathbb{Z}_p$ here. 
> - $A=\mathbb{Z}$, $S=\mathbb{Z}-(p)$, then get $\mathbb{Z}_{(p)}=\{a/b:(b,p)=1\}$. 

> [!proposition]
> Let $S$ be a multiplicative closed set, and let $g:A\to B$ be a ring homomorphism such that $g(s)\in B^\times$ for all $s\in S$. Then there exists unique $h$ such that 
> 
> ![Pasted image 20250331202034.png|180](/img/user/%E9%99%84%E4%BB%B6/Pasted%20image%2020250331202034.png)
> 
> is commute.

`\begin{proof}`
Define $h(a/s)=g(a)/g(s)\in B$. We only check it is well-defined. If $a/s=a'/s'$, we aim to show $g(a)/g(s)=g(a')/g(s')$. Since $(as'-a's)t=0$ for some $t\in S$, one have $(g(as')-g(a's))g(t)=0$. Thus $g(as')=g(a's)$ by $g(t)\in B^\times$. 
`\end{proof}`


> [!definition]
> Let $M$ be an $A$-module. For a multiplicative closed set $S$, define relation on $M\times S$, 
> 
> $$(m,s)=(m',s') \iff \exists t\in S, t(sm'-s'm)=0$$
> 
> which is an equivalent relation. Define $S^{-1}M=\{m/s:m\in M,s\in M\}$ as the set of equivalent classes. 

**Fact.** $S^{-1}M$ is an $S^{-1}A$-module via $a/s\cdot m/t=am/st$. Also there is a $A$-module homomorphism $M\to S^{-1}M,m\mapsto m/1$. 

**Notation.** If $S=A-p$, denote $M_p$; if $S=\{f^n:n\geqslant 0\}$, denote $M_f$. 

**Easy Fact.** $u:M\to N$ is an $A$-module homomorphism induces an $S^{-1}A$-module homomorphism. $S^{-1}u:S^{-1}M\to S^{-1}N,m/s\to u(m)/s$. 

> [!proposition]
> The operation $S^{-1}$ is exact on $A$-modules. That is, if $M'\stackrel{f}{\to} M\stackrel{g}{\to}M''$ is a exact sequence of $A$-module, then $S^{-1}M'\stackrel{S^{-1}f}{\to} S^{-1}M\stackrel{S^{-1}g}{\to}S^{-1}M''$ is also exact.
{ #092787}


`\begin{proof}`
We aim to show $\mathrm{im}(S^{-1}f)=\ker (S^{-1}g)$. Since $(S^{-1}g)\circ(S^{-1}f)=S^{-1}(g\circ f)=0$, one have $\mathrm{im}(S^{-1}f)\subseteq\ker(S^{-1}g)$. 

On the other hand, suppose $m/s\in\ker (S^{-1}g)$, then $g(m)/s=0/1$ in $S^{-1}M''$. It deduces that $g(m)t=0$ for some $t\in S$ and so $g(tm)=0$, $tm\in \ker g=\mathrm{im} f$. Assume that $tm=f(m')$ for some $m'\in M'$. So $m/s=tm/ts=f(m')/ts\in\mathrm{im}(S^{-1}f)$. 
`\end{proof}`


> [!proposition]
> There exists unique $S^{-1}A$-module isomorphism 
> 
> $$f:S^{-1}A\otimes_A M\simeq S^{-1}M,a/s\otimes m\mapsto am/s.$$
> 
>
{ #d61f0b}


`\begin{proof}`
Consider $S^{-1}A\times M\to S^{-1}M$ by $(a/s,m)\mapsto am/s$. It is clearly $A$-bilinear, so there exists a unique map $f:S^{-1}A\otimes _A M\to S^{-1}M$. It is easy to check $f$ is $S^{-1}A$-linear and is surjective. 

To show $f$ injective, let $f(x)=0$. Note that $x=\sum_{i=1}^n a_i/s_i\otimes m_i=1/(s_1\cdots s_n)\otimes m$ for some $m$. It deduces that $f(x)=f((1/s)\otimes m)=m/s=0$. Then there exists $t\in S$ such that $tm=0$ and so $x=(1/s)\otimes m=(1/st)\otimes (tm)=0$. 
`\end{proof}`


> [!corollary]
> $S^{-1}A$ is a flat $A$-module.
{ #8p663h}


`\begin{proof}`
By [[MATH/交换代数/Nodes/3 Rings and Modules of Fractions#^092787\|#^092787]] and [[MATH/交换代数/Nodes/3 Rings and Modules of Fractions#^d61f0b\|#^d61f0b]].
`\end{proof}`


> [!proposition]
> Let $M,N$ be $A$-modules. Then $S^{-1}M\otimes_{S^{-1}A}S^{-1}N\simeq S^{-1}(M\otimes_A N)$. 

`\begin{proof}`
By [[MATH/交换代数/Nodes/3 Rings and Modules of Fractions#^d61f0b\|#^d61f0b]], we have 

$$\begin{aligned}
S^{-1}M\otimes_{S^{-1}A} S^{-1}N&\simeq (M\otimes_A S^{-1}A)\otimes_{S^{-1}A}(N\otimes_A S^{-1}A)\\&=M\otimes _A N\otimes _AS^{-1}A\\
&=(M\otimes _AN)\otimes_A S^{-1}A\\&=S^{-1}(M\otimes _A N)
\end{aligned}$$

and we finish the proof.
`\end{proof}`


**Example.** $M_p\otimes_{A_p}N_p=(M\otimes_A N)_p$. 

# Local Properties

> [!definition]
> A property $P$ of a ring $A$ (or of an $A$-module $M$) is said to be a "local property", if $A$ (or $M$) has $P$ iff $A_p$ (or $M_p$) has $P$ for any $p\in \mathrm{Spec} A$.

> [!proposition]
> Let $M$ be a $A$-module. TFAE:
> - $M=0$;
> - $M_p=0$ for all prime ideal $p$;
> - $M_m=0$ for all maximal ideal $m$.
{ #663ccb}


`\begin{proof}`
i)->ii)->iii) is trivial. 

iii)->i) If $M\neq 0$, take nonzero $x\in M$ and then $\mathrm{Ann}(x)\subseteq A$ is a proper ideal and $\mathrm{Ann}(x)\subseteq m$ for some maximal ideal $m$. 

Consider $M\to M_m=M\otimes_A (A-m)^{-1}A,x\mapsto x\otimes 1$. Since $M_m=0$, $x/1=0$. Then there exists $t\in A-m$ such that $tx=0$ and so $t\in \mathrm{Ann}(x)\subseteq m$, contradicting with $t\notin m$. 
`\end{proof}`


> [!proposition]
> Let $\phi:M\to N$ be a homomorphism between $A$-modules. TFAE:
> - $\phi$ is injective;
> - $\phi_p:M_p\to N_p$ is injective for all prime ideal $p$;
> - $\phi_m:M_m\to M_m$ is injective for all maximal ideal $m$.
> 
> Similar statements hold after replacing "injective" by "surjective" or "bijective". 

`\begin{proof}`
i)->ii) Recall $M_0\simeq M\otimes_A A_p$ and by [[MATH/交换代数/Nodes/3 Rings and Modules of Fractions#^8p663h\|#^8p663h]].

ii)->iii) Trivial. 

iii)->i) Let $P=\ker \phi$. Then $0\to P\to M\to N$ is left exact. For any maximal ideal $m$, $A_m$ is flat $A$-module yields that $0\to P_m\to M_n\to N_n$ is left exact. It deduces that $P_m=0$ and so $P=0$ by [[MATH/交换代数/Nodes/3 Rings and Modules of Fractions#^663ccb\|#^663ccb]]. 
`\end{proof}`


> [!proposition]
> Let $M$ be an $A$-module. TFAE:
> - $M$ is a flat $A$-module;
> - $M_p$ is a flat $A_p$-module for all prime ideal $p$;
> - $M_m$ is a flat $A_m$-module for all maximal ideal $m$. 

`\begin{proof}`





