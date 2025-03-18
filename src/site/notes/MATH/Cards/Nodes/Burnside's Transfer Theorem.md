---
{"dg-publish":true,"aliases":["Burnside's transfer theorem"],"permalink":"/MATH/Cards/Nodes/Burnside's Transfer Theorem/","dgPassFrontmatter":true}
---


> [!definition] transfer
> Let $H<G$ be a subgroup and $\Omega=[G:H]=\{Hx_1,\cdots,Hx_n\}$. Define $\hat g:Hx\mapsto Hxg$ and $\tau_g\in\mathrm{Sym}(n)$ be the permutation induced from $\hat g$. Since $Hx_ig=Hx_{i^{\tau(g)}}$, we have that $x_igx_{i^{\tau(g)}}^{-1}\in H$. 
> 
> Define $h_i(g)=x_igx_{i^{\tau(g)}}^{-1}$, and define
> 
> $$\begin{aligned}
> V_{G\to H}:G&\to H/H',\\
> g&\mapsto \big(\Pi_{i=1}^nh_i(g)\big)H'
> \end{aligned}$$
> 
> as a *transfer* from $G$ to $H/H'$.

**Observation.** 
- $V_{G \rightarrow H}$ is a homomorphism from $G$ to $H / H^{\prime}$;
- $V_{G \rightarrow H}$ does not depend on the choices of $x_1, \cdots, x_n$;
- Writing $\hat{g}$ in cycle form $\left(H x_1, H x_1 g, \cdots, H x_1 g^{l_1-1}\right)\left(H x_2, H x_2 g, \cdots, H x_2 g^{l_1-2}\right) \cdots\left(H x_t, \cdots, H x_t g^{l_t-1}\right)$, then there is $V_{G \rightarrow H}(g)=\Pi_{i=1}^n\left(x_i g^{l_i} x_i^{-1}\right) H$. 

> [!definition] p-nilpotent
> A group $G$ is called *$p$-nilpotent* if $G=NP$, where $N\lhd G$ and $P$ is a Sylow $p$-subgroup, and $N\cap P=1$.

> [!theorem] Burnside's transfer theorem
> Let $G$ be a finite group, and let $P$ be a Sylow $p$-subgroup. If $N_G(P)=C_G(P)$, then $G$ is $p$-nilpotent.

`\begin{proof}`
Since $N_G(P)=C_G(P)\geqslant P$, then $P$ is abelian and $P'=1$. 

Since $V_{G\to P}(g)=\Pi_{i=1}^tx_ig^{l_i}x_i^{-1}=\Pi_{i=1}^tg^{l_1+\cdots+l_t}=g^{|G/P|}$, $V_{G\to P}$ is surjective. So $V_{G\to P}:G\to P$ has kernel $K$ and $G/K\cong P$. So $K\lhd G$ such that $G=KP$ and so $G$ is $p$-nilpotent.
`\end{proof}`
# Applications

> [!theorem]
> Let $G$ be finite of which Sylow subgroups are all cyclic. Let $p$ be the smallest prime divisor of $G$ and let $P$ be a Sylow $p$-subgroup of $G$. Then:
> - $G$ is $p$-nilpotent.
> - $G$ is solvable.
{ #sezt3q}


`\begin{proof}`
Since $P$ is cyclic and $p$ is the smallest prime divisor, we have that $N_G(P)/C_G(P)\lesssim \mathrm{Aut}(P)$ and $N_G(P)/C_G(P)=1$. So $G$ has a normal subgroup $K$ with $|G/K|=|P|$. Then $K$ is $q$-nilpotent where $q>p$ is the smallest prime divisor of $K$. Repeat this procedure and we get $G\rhd K\rhd K_1\cdots\rhd K_m$. Note that $K_m$ is a Sylow subgroup and $K_i/K_{i+1}$ is solvable. So $G$ is solvable.
`\end{proof}`

> [!corollary]
> If a Sylow $2$-group of $G$ is cyclic, then $G$ is solvable.

`\begin{proof}`
By [[MATH/Cards/Nodes/Burnside's Transfer Theorem#^sezt3q\|#^sezt3q]], $G$ is $2$-nilpotent and so there exists $N\lhd G$ such that $G=NP$ and $|N|$ is odd. By [Feit–Thompson theorem](https://en.wikipedia.org/wiki/Feit–Thompson_theorem), $G$ is solvable.
`\end{proof}`

> [!proposition]
> Let $G$ be a finite nonabelian simple group, and let $p$ be the smallest prime divisor of $|G|$. Then $|G|$ is divisible by $p^3$ or $12$.

`\begin{proof}`
Suppose $|G|$ is not divisible by $p^3$, then $p^2||G|$. Otherwise, a Sylow $p$-subgroup $P=C_p$ and $G$ is $P$-nilpotent, contradiction by $G$ simple. Thus $P$ is cyclic or $P\cong C_p\times C_p$. The first case is impossible. Hence $P\cong C_p\times C_p$ and $N_G(P)\neq C_G(P)$. Further $N_G(P)/C_G(P)\lesssim\mathrm{Aut}(P)=\mathrm{GL}_2(p)$ and $|\mathrm{GL}_2(p)|=p(p-1)^2(p+1)$. Since $p$ is the smallest prime divisor and $G$ is nonsolvable, then $p=2$ and $p+1=3$. It yields that $12\big||G|$.  
`\end{proof}`
