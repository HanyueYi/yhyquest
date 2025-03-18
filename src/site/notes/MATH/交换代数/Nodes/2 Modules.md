---
{"dg-publish":true,"permalink":"/MATH/交换代数/Nodes/2 Modules/","dgPassFrontmatter":true}
---


> Highlights: Nakayama lemma, snake lemma, tensor product, flatness

Define $\mathrm{Hom}_A(M,N)=\{A\mbox{-module homomorphisms }f:M\to N\}$. It has an $A$-module structure. The construction is "functorial", namely. If $u:M'\to M$ is a homomorphism, then it deduces a homomorphism 

$$\mathrm{Hom}(M,N)\to\mathrm{Hom}(M',N),f\mapsto f\circ u.$$

Similarly, given $v:N\to N'$, it induces a homomorphism $\mathrm{Hom}(M,N)\to \mathrm{Hom}(M,N')$.

**Example.** Compute $\mathrm{Hom}_\mathbb{Z}(\mathbb{Z}/4\mathbb{Z},\mathbb{Z}/6\mathbb{Z})$. Since $f(\overline1)$ is divisible by $3$, there is $f(\overline 1)\in\{\overline 0,\overline 3\}$. It deduces that $\mathrm{Hom}_\mathbb{Z}(\mathbb{Z}/4\mathbb{Z},\mathbb{Z}/6\mathbb{Z})\simeq \mathbb{Z}/2\mathbb{Z}$. 

**Easy Facts.**
- $\mathrm{Hom}_A(A,M)\simeq M,f\mapsto f(1)$
- For ideal $\alpha\subseteq A$, define $\alpha M=\{\sum_{i=1}^n \alpha_i x_i:\alpha_i\in \alpha,x_i\in M\}\subseteq M$ is a submodule. When $\alpha=(a)$, write $aM=(a)M$. 

> [!definition]
> For submodules $N,P\subseteq M$, define $(N:P)=\{a\in A:aP\subseteq N\}\subseteq A$ an ideal. Denote annihilator of $M$ as $\mathrm{Ann}(M):=(0:M)$. Note $M$ as an $A$-module can also be regarded as an $A/\mathrm{Ann}(M)$-module. Say $M$ is a faithful $A$-module if $\mathrm{Ann}(M)=0$. 

> [!proposition]
> $M$ is a finitely generated $A$-module iff there exists an surjective $A^n\twoheadrightarrow M$ iff $M$ is a quotient module of $A^n$.

> [!proposition]
> Suppose $M$ is a finitely generated $A$-module, and $\alpha\subseteq A$ is an ideal. Let $\phi:M\to M$ be an endomorphism such that $\phi(M)\subseteq\alpha M$. Then $\phi$ satisfies an equation of form 
> 
> $$\phi^n+a_1\phi^{n-1}+\cdots+a_{n-1}\phi+a_n=0$$
> 
> on $M$ for some $a_i\in \alpha$, namely, $\sum_{i=0}^n a_i\phi^{n-i}(m)=0$ for all $m\in M$.
{ #41223f}


**Example.** Let $M=\mathbb{Z}e_1\oplus \mathbb{Z} e_2$ and $\alpha=(2)$. Define $\phi$ by $\phi\begin{pmatrix} e_1\\ e_2\end{pmatrix}=\begin{pmatrix} 2 & 0\\ 4 & 8\end{pmatrix}\begin{pmatrix} e_1\\ e_2\end{pmatrix}$. Then by Cayley-Hamilton, $(\phi-2)(\phi-8)=0$.

`\begin{proof}`
Choose a set of generators $\{e_1,\cdots,e_n\}$ of $M$. Then $\phi\begin{pmatrix}e_1\\\vdots \\e_n\end{pmatrix}=T\begin{pmatrix}e_1\\\vdots \\e_n\end{pmatrix}$ for some $T\in\mathrm{Mat}_{n\times n}(\alpha)$. Let $P(x)$ be the characteristic polynomial of $T$, then $P(\phi)=0$ by Cayley-Hamilton.
`\end{proof}`


> [!corollary]
> Let $M$ be a finitely generated $A$-module, and let $\alpha$ be an ideal of $A$ with $\alpha M=M$. Then there exists $x\equiv 1\pmod{ \alpha}$ such that $xM=0$.
{ #d05ae0}


`\begin{proof}`
Let $\phi=\mathrm{id}_M:M\to \alpha M=M$. By [[MATH/交换代数/Nodes/2 Modules#^41223f\|#^41223f]], $\phi$ satisfies 

$$\phi^n+\sum_{i=1}^n a_i \phi^{n-i}=0$$

on $M$ with $a_i\in \alpha$. Let $x=1+a_1+\cdots+a_n$, then $xM=0$.
`\end{proof}`


> [!proposition] Nakeyame lemma
> Let $M$ be a finitely generated $A$-module, and let $\alpha\subseteq A$ be an ideal with $\alpha\subseteq\mathrm{Jac}(A)$. If $\alpha M=M$, then $M=0$.
{ #c2a5d0}


`\begin{proof}`
By [[MATH/交换代数/Nodes/2 Modules#^d05ae0\|#^d05ae0]] there exists $x=1+a$ with $a\in\mathrm{Jac}(A)$ such that $xM=0$. By [[MATH/交换代数/Nodes/1 Rings and Ideals#^h2e8bp\|1 Rings and Ideals#^h2e8bp]], $1+a\in A^\times$ and so $M=0$.
`\end{proof}`

**Remark.** The most useful situation is when $A$ is a local ring with $\alpha=m_A=\mathrm{Jac}(A)$. [[MATH/交换代数/Nodes/2 Modules#^c2a5d0\|#^c2a5d0]] tells if $M$ is finitely generated and $m_AM=M$, then $M=0$. 


> [!corollary]
> Let $M$ be a finitely generated $A$-module with submodule $N\subseteq M$. Let $\alpha\subseteq\mathrm{Jac}(A)$ be an ideal. Then $M=\alpha M+N$ yields that $M=N$.
{ #ffbd3c}


`\begin{proof}`
Apply [[MATH/交换代数/Nodes/2 Modules#^c2a5d0\|#^c2a5d0]] to $M/N$. Since $M=\alpha M+N$, there is $M/N=\alpha(M/N)$ and then $M/N=0$. Therefore, $M=N$.
`\end{proof}`


> [!proposition]
> Let $(A,m_A)$ be a local ring. Let $k=A/m_A$. Let $M$ be a finitely generated $A$-module, then $M/m_AM$ is a vector space over $k$. Let $x_1,\cdots,x_n\in M$. Suppose $\overline{x_1},\cdots,\overline{x_n}$ is a basis of $M/m_AM$, then $x_1,\cdots,x_n$ generate $M$. 

`\begin{proof}`
Let $N=\left\langle x_1,\cdots,x_n\right\rangle_A\subseteq M$. Then the composite $N\hookrightarrow M\twoheadrightarrow M/m_AM$ is surjective. It deduces that $M=N+m_AM$. By [[MATH/交换代数/Nodes/2 Modules#^ffbd3c\|#^ffbd3c]], $M=N$ and so $x_1,\cdots,x_n$ generate $M$.
`\end{proof}`


# Exact Sequence


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/math/ii/nodes/2-2-modules/#4kfb14" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



> [!definition]
> - Let $A \stackrel{f}{\to} B\stackrel{g}{\to} C$ be a chain and homomorphism of $R$-modules. We say it is *exact* at $B$ if $\mathrm{Im} f=\ker g$.
> - A finite sequence $A_0\stackrel{f_1}{\to} A_1\stackrel{f_2}{\to}\cdots\stackrel{f_n}{\to}A_n$ is exact, if it is exact at each $A_i(1\leqslant i\leqslant n-1)$, that is, $\mathrm{Im} f_i=\ker f_{i+1}$ for any $i$.
> - If $0\stackrel{ 0}{\to}X\stackrel{f}{\to}Y\stackrel{g}{\to}Z\stackrel{0}{\to}0$ is exact, then we say it is *short exact*. 

</div></div>


**Remark.** Any exact sequence can be split into short exact sequences. Namely, given 

$$\cdots\to M_{i-2}\stackrel{f_{i-1}}{\to} M_{i-1}\stackrel{f_i}{\to} M_i\stackrel{f_{i+1}}{\to} M_{i+1}\stackrel{f_{i+2}}{\to}M_{i+2}\to \cdots,$$

then we get $0\to \mathrm{im} f_i\to M_i\to M_i/\mathrm{im} f_i\to 0$ and $0\to \mathrm{im} f_{i+1}\to M_{i+1}\to M_{i+1}/\mathrm{im} f_{i+1}\to 0$, where $M_i/\mathrm{im} f_i=M_i/\ker f_{i+1}\simeq\mathrm{im} f_{i+1}$.

> [!proposition]
> - Let $M'\stackrel{u}{\to}M\stackrel{ v}{\to}M''\to 0$ $(*)$ be a sequence of $A$-module homomorphism. Then it is exact iff for any $A$-module $N$, the induced sequence
>   
>   $$0\to \mathrm{Hom}(M'',N)\stackrel{\overline{v}}{\to}\mathrm{Hom}(M,N)\stackrel{\overline{u}}{\to}\mathrm{Hom}(M',N)\tag{**}$$
>   
>   is exact, where $\overline v:f\mapsto f\circ v$ and $\overline u:g\mapsto g\circ u$. 
> - (dual statement) Let $0\to N'\stackrel{u}{\to} N\stackrel{v}{\to} N''(☺️)$ be a sequence. It is exact iff for any $A$-module $M$, the induced sequence 
>   
>   $$0\to \mathrm{Hom}(M,N')\stackrel{\overline u}{\to} \mathrm{Hom}(M,N)\stackrel{\overline v}{\to} \mathrm{Hom}(M,N'')\tag{☺️☺️}$$
>   
>   is exact.
{ #jj28ws}


`\begin{proof}`
i) "->" Assume $(*)$ is exact. It is enough to show $\overline v$ is injective and $\mathrm{im}\overline v=\ker\overline u$. If $\overline v (f)=0$, then $M\stackrel{v}{\to} M''\stackrel{f}{\to}N$ is zero. But $v$ is surjective, then $f=0$. Note that $\overline u\circ\overline v=0$ as $v\circ u=0$, and it deduces that $\mathrm{im}\overline v\subseteq \ker\overline u$. Conversely, for any $g\in\ker\overline u$, we aim to find $f$ such that $g=f\circ v$. For $x\in M''$, let $\hat x\in v^{-1}(x)$ and set $f(x)=g(\hat x)$. We can verify that $f$ is well-defined and is a homomorphism of $A$-modules. Hence $\mathrm{im}\overline v=\ker\overline u$. 

"<-" It suffices to show $v$ is surjective and $\mathrm{im} u=\ker v$. If $v$ is not surjective, then let $N=M''/\mathrm{im} v\neq 0$ and apply to $(**)$, that is, 

$$0\to\mathrm{Hom}(M'',M''/\mathrm{im} v)\stackrel{\overline v}{\to}\mathrm{Hom}(M,M''/\mathrm{im} v)\stackrel{\overline u}{\to}\mathrm{Hom}(M',M''/\mathrm{im} v)$$

is exact. The surjective map $\pi:M''\to M''/\mathrm{im} v$ is a non-zero map, but $\overline v(\pi)$ is a zero map, which is a contradiction. Hence $v$ is surjective. 

Take $N=M''$ and $\mathrm{id}\in \mathrm{Hom}(M'',M'')$. Then $(**)$ is exact yields that $\mathrm{id}\circ v\circ u=0$ and so $\mathrm{im} u\subseteq\ker v$. Finally, we check $\mathrm{im} u\supseteq \ker v$. Now we take $N=M/\mathrm{im} u$ and 

$$0\to\mathrm{Hom}(M'',M/\mathrm{im} u)\stackrel{\overline v}{\to}\mathrm{Hom}(M,M/\mathrm{im} u)\stackrel{\overline u}{\to}\mathrm{Hom}(M',M/\mathrm{im} u)$$

is exact. Define canonical map $\pi:M\to M/\mathrm{im} u$. Notice that $\pi\circ u=0$, then $\pi\in\ker \overline u=\mathrm{im}\overline v$. Then there exists $\phi\in \mathrm{Hom}(M'',M/\mathrm{im} u)$ such that $\phi\circ v=\pi$. It deduces that $\phi(v(x))=\pi(x)=0$ and $x\in \mathrm{im} u$. Now we finish the proof.

ii) "->" Assume that $(☺️)$ is exact. It is enough to show $\overline u$ is injective and $\ker \overline v=\mathrm{im} \overline u$. If $\overline u(f)=0$, then $u\circ f=0$. Since $u$ is injective, we have $f=0$ and so $\overline u$ is injective. Note that $\overline v\circ\overline u=0$ as $v\circ u=0$, so $\mathrm{im}\overline u\subseteq\mathrm{ker} \overline v$. For any $g\in\ker \overline v$, we aim to find $f$ such that $g=f\circ u$. For any $m\in M$, define $f(m)= u^{-1}(g(m))$. Since $g(m)\in\ker v=\mathrm{im} u$ and $u$ is injective, $f$ is well-defined and $g=f\circ u$. Hence $\mathrm{im}\overline u=\mathrm{ker}\overline v$. 

"<-" Assume that $(☺️☺️)$ is exact. It suffices to show $u$ is injective and $\ker v=\mathrm{im} u$. If $u$ is not injective, then $\ker u\neq 0$. Let $M=\ker u$ and apply it to $(☺️☺️)$. The inclusion map $\iota:\ker u\hookrightarrow N'$ is included in $\mathrm{Hom}(M,N')$ and $\overline u(\iota)=0$, which contradicts with $\overline u$ injective. Take $M=N'$ and $\mathrm{id}_{N'}\in\mathrm{Hom}(N',N')$ satisfies $\overline v\circ\overline u\circ f=v\circ u=0$, that is, $\mathrm{im} u\subseteq\ker v$. Conversely, take $M=\ker v$ and 

$$0\to \mathrm{Hom}(\ker v,N')\stackrel{\overline u}{\to} \mathrm{Hom}(\ker v,N)\stackrel{\overline v}{\to} \mathrm{Hom}(\ker v,N'')$$

is exact. Since $\iota':\ker v\to N$ is an element of $\mathrm{Hom}(\ker v,N)$ and $\overline v(\iota')=0$, there is $\iota'\in \ker\overline v=\mathrm{im}\overline u$ and so there exists $\phi$ such that $u\circ\phi=\iota'$. Then for any $m\in\ker v$, we have $m=\iota'(m)=u(\phi(m))$ and $m\in\mathrm{im} u$. Now we finish the proof.  
`\end{proof}`


**Remark.** 
- "$\to 0$" in $(*)$ is necessary. For example, consider $\mathbb{Z}\stackrel{\times 0}{\to}\mathbb{Z}\stackrel{\times 2}{\to}\mathbb{Z}$ is exact but right exact. Then $\mathrm{Hom}(\mathbb{Z},\mathbb{Z})\stackrel{\times 2}{\to} \mathrm{Hom}(\mathbb{Z},\mathbb{Z})\stackrel{\times 0}{\to}\mathrm{Hom}(\mathbb{Z},\mathbb{Z})$. 
- "$0\to$" on LHS of $(*)$ is useless, as it cannot add "$\to 0$" to $(**)$. Consider $0\to \mathbb{Z}\stackrel{\times 2}{\to}\mathbb{Z}\to \mathbb{Z}/2\mathbb{Z}\to 0$. Apply $\mathrm{Hom}(*,\mathbb{Z})$, then $0\to 0\to\mathbb{Z}\stackrel{\times 2}{\to}\mathbb{Z}\to 0$ is only left exact. 

# Snake Lemma

> [!proposition] snake lemma
> Consider a commutative diagram where both rows are short exact.
> 
> $$\begin{CD}0 @>>> M' @> G>> M @> H>> M'' @>>> 0 \\@. @V f' VV @V f VV @V f''VV @. \\0 @>>> N' @>g  >> N @> h>> N'' @>>> 0 \\\end{CD}$$
> 
> Then we have an exact sequence 
> 
> $$0\to\ker f'\to \ker f\to \ker f''\to \mathrm{coker}f'\to\mathrm{coker}f\to\mathrm{coker}f''\to 0.$$
> 
>
{ #jgbcg4}


`\begin{proof}`
Notice that $\ker f'\to\ker f\to \ker f''$ are restriction of $M'\to M\to M''$. We can check that $g$ and $h$ induce maps $\mathrm{coker} f'\to\mathrm{coker} f$ and $\mathrm{coker} f\to\mathrm{coker} f''$. So it suffices to construct $d:\ker f''\to \mathrm{coker} f'$. For any $x\in M''$, take $\hat x\in M$ and so $f(\hat x)\in \ker h$. Then define $\check x\in N'$ such that $g(\check x)=\hat x$ and $\overline {\check x}\in\mathrm{coker} f'$ is what we desire. It is easy to check this map is well-defined. 

It remains to check the sequence is exact. For convenience, define 

$$0\to\ker f'\stackrel{G'}{\to} \ker f\stackrel{H'}{\to} \ker f''\stackrel{d}{\to} \mathrm{coker}f'\stackrel{g'}{\to}\mathrm{coker}f\stackrel{h'}{\to}\mathrm{coker}f''\to 0.$$

For any $x\in\ker d\leqslant M''$, there exists $y\in M$ such that $H(y)=x$. By the definition of $d$, we know $f(y)=g(d(x))=0$ and so $y\in \ker f$. It deduces that $x\in\mathrm{im}(H')$. Conversely, for any $x\in\mathrm{im}(H')$, there exists $y\in\ker f$ such that $x=H'(y)$. By the definition of $d$, there is $g(d(x))=f(y)=0$ and $d(x)=0$. Thus $x\in \ker d$. Now we have proved $\ker d=\mathrm{im} H'$. 

For any $x\in\ker g'$, there is $g'(x)=0$ and so $g(\hat x)\in \mathrm{im} f$ for any given preimage $\hat x\in N'$. Then there is $y\in M$ such that $f(y)=g(\hat x)$. By the definition of $d$, we know $d(H(y))=x$. In addition, since $f''(H(y))=h(f(y))=h(g(\hat x))=0$, $H(y)\in \ker f''$. It yields that $x\in\mathrm{im} d$. Conversely, for any $x\in \mathrm{im} d$, there exists $y$ such that $d(y)=x$ and $z\in M$ such that $H(z)=y$ and $f(z)=g(\hat x)$ for any given $x\in N'$. By the definition of $d$, there is $g'(x)=\overline {f(z)}\in \mathrm{coker} f$ and so $g'(x)=0$, $x\in \ker g'$. Now we have proved $\mathrm{im} d=\ker g'$.
`\end{proof}`


**Remark.** It is a general case of [[MATH/抽象代数II/Nodes/2.2 Modules#^b0hne4\|short five lemma]].

# Tensor Product

**Motivations.**
- linear algebra: bilinear map
- algebraic geometry: fibre product of geometry spaces
- flatness: useful for localization

**Linear algebra.** Let $k$ be a field. Notice that bilinear map and linear map are different.
- Consider bilinear map $f:k^m\times k^n\to k^s$. It is different from $k$-linear map $k^{m+n}\stackrel{f'}{\to} k^s$, because $f(ax,ay)=a^2f(x,y)$ and $f'(ax,ay)=af(x,y)$. 
- Define $g:k\times k\to k,(a,b)\to a$, which is linear but not bilinear.
- A $k$-linear map $g:k\times k\to k^s$ is determined by $f(1,0)$ and $f(0,1)$; a $k$-bilinear map $g':k\times k\to k^s$ is determined by $f(1,1)$. 
- A $k$-bilinear map $h:k^m\times k^n\to k^s$ looks like a $k$-linear map $h:k^{mn}\to k^s$, as we will see $k^m\otimes k^n\simeq k^{mn}$. 

**Algebraic geometry.** Note a fact that $\mathrm{Spec}(A\times B)=\{p\times B,A\times q:p\in\mathrm{Spec}(A),q\in\mathrm{Spec}(B)\}$. Hence, $\mathrm{Spec}(\mathbb{C}[x]\times \mathbb{C}[y])=\mathrm{Spec} (\mathbb{C}[x])\sqcup\mathrm{Spec}(\mathbb{C}[y])$. By [[MATH/代数几何/Nodes/1.1 Some Algebra#^6rh0cw\|1.1 Some Algebra#^6rh0cw]], the set of maximal ideal of $\mathbb{C}[x,y]$ is $\mathrm{Spm}(\mathbb{C}[x,y])=\{(x-a,y-b):a,b\in \mathbb{C}\}$. In fact, $\mathbb{C}[x]\otimes \mathbb{C}[y]\simeq \mathbb{C}[x,y]$. 

Consider $\mathbb{Z}$-bilinear map $f:\mathbb{Z}\times \mathbb{Z}/2\mathbb{Z}\to P$, which is determined by $f(1,\overline 1)$. Note that $f(1,\overline 1)+f(1,\overline 1)=f(1,\overline 0)=0$, then $f(1,\overline 1)\in P[2]$. In summary, the above bilinear map is same as a $\mathbb{Z}$-linear map $\widetilde f:\mathbb{Z}/2\mathbb{Z}\to P$. Later we will see $\mathbb{Z}\otimes _\mathbb{Z} \mathbb{Z}/2\mathbb{Z}\simeq \mathbb{Z}/2\mathbb{Z}$. 

> [!definition]
> Let $A$ be a ring, and let $M,N,P$ be $A$-modules. A map $f:M\times N\to P$ is $A$-bilinear if $f(ax+by,cz+dw)=acf(x,z)+adf(x,w)+bc f(y,z)+bdf(y,w)$. 

> [!proposition]
> Let $M$ and $N$ be $A$-modules. Then there exists a pair $(T,g)$ where $T$ is an $A$-module and $g:M\times N\to T$ is an $A$-bilinear map, with the universal property: Given any $A$-module $P$, and any $A$-bilinear map $f:M\times N\to P$, there exists unique $A$-linear map $f':T\to P$ such that $f=f'\circ g$, that is, $f$ factors through $g$. 
> 
> ![Pasted image 20250305212919.png|200](/img/user/%E9%99%84%E4%BB%B6/Pasted%20image%2020250305212919.png)
> 
> Moreover if $(T,g)$ and $(T',g')$ are two such pairs with above property, then there exists unique isomorphism $j:T\to T'$ such that $j\circ g=g'$.
{ #aa5afc}


`\begin{proof}`
**Uniqueness.** Suppose $(T,g)$ and $(T',g')$ are two distinct pairs with the property above. Apply $T$ with $P=T'$ and $T'$ with $P=T$, then there exist $j:T\to T'$ and $j':T'\to T$ such that $j'\circ j=j\circ j'=\mathrm{id}$. 

![Pasted image 20250305213258.png|180](/img/user/%E9%99%84%E4%BB%B6/Pasted%20image%2020250305213258.png)

**Existence.** Let $C$ be the free $A$-module $A^{M\times N}$, namely, a free $A$-module with basis $\{(x,y):x\in M,y\in Y\}$. So an element in $C$ has unique expression $\sum_{i=1}^n a_{i}(x_i,y_i)$. Let $D$ be the submodule of $C$ generated by the following elements:
- $(x+x',y)-(x,y)-(x',y)$,
- $(x,y+y')-(x,y)-(x,y')$,
- $(ax,y)-a(x,y)$,
- $(x,ay)-a(x,y)$.

Let $T=C/D$. For $(x,y)\in C$, denote $x\otimes y$ as image in $T=C/D$. Thus, $T$ is generated by $\{x\otimes y:x\in M,y\in N\}$. Now define 

$$g:M\times N\to T,(m,n)\mapsto m\otimes n,$$

which is a $A$-bilinear map. We now verify the universal property. Let $f:M\times N\to P$ be a bilinear map. It suffices to construct $f':T\to P$ such that $f=f'\circ g$. We define $\overline f:C=A^{M\times N}\to P,(m,n)\mapsto f(m,n)$, and we can easily see $D\subseteq \ker \overline f$. So $\overline f$ induces a map $f':C/D=T\to P$. Remark that 

$$f'\circ g(m,n)=f'(m\otimes n)=f(m,n)$$

and so $f'\circ g=f$. Hence, for each bilinear map $f:M\times N\to P$, we can find $f'$ such that $f'\circ g=f$ and so $(T,g)$ is what we desire. 
`\end{proof}`


> [!definition]
> Call the module $T$ above as the *tensor product* of $M$ and $N$, also denote as $T=M\otimes_AN$. Sometimes, just $M\otimes N$ if the context is clear. Also the map $g:M\times N\to M\otimes N$ is simply $g((m,n))=m\otimes n$. In particular, the $A$-module $M\otimes_AN$ is generated by $\{m\otimes n:m\in M,n\in N\}$. Indeed, if $\{m_i:i\in I\}$ generates $M$ and $\{n_i\}$ generates $N$, then $\{m_i\otimes n_j:i\in I,j\in J\}$ generates $M\otimes_AN$. 

**Remark.** Not all elements of $M\otimes_AN$ is of the form $x\otimes y$. In other word, $g:M\times N\to M\otimes N$ is in general not surjective. For example, let $M=\mathbb{Z}e\oplus \mathbb{Z} f$ and $N=\mathbb{Z}g\oplus \mathbb{Z}h$, then $e\otimes g+f\otimes h\in M\otimes_\mathbb{Z}N$ cannot equal to some $x\otimes y$ with $x\in M$ and $y\in Y$. 

> [!proposition]
> Let $M,N,P$ be $A$-modules. Then there exists unique isomorphisms:
> - $M\otimes N\to N\otimes M$ such that $x\otimes y\mapsto y\otimes x$;
> - $(M\otimes N)\otimes P\to M\otimes(N\otimes P)\to M\otimes N\otimes P$;
> - $(M\oplus N)\otimes P\to (M\otimes P)\oplus (N\otimes P)$;
> - $A\otimes M\to M$ such that $a\otimes x\mapsto ax$. 
{ #9968ad}


`\begin{proof}`
i) Consider $f:M\times N\to N\otimes M,(x,y)\mapsto y\otimes x$ and $g:M\times N\to M\otimes N,(x,y)\mapsto x\otimes y$. By [[MATH/交换代数/Nodes/2 Modules#^aa5afc\|#^aa5afc]], there exists unique $f':M\otimes N\to N\otimes M$ such that the diagram commutes. 

![Pasted image 20250317192406.png|250](/img/user/%E9%99%84%E4%BB%B6/Pasted%20image%2020250317192406.png)

Now, in a parallel way, use the universal property of $N\otimes M$, then we get $\widetilde{f'}(n\otimes m)=m\otimes n$ such that the diagram commutes.

![Pasted image 20250317192848.png|250](/img/user/%E9%99%84%E4%BB%B6/Pasted%20image%2020250317192848.png)

It is easy to check $f'$ and $\widetilde{ f'}$ are inverse to each other. 

iv) Consider

![Pasted image 20250317193646.png|220](/img/user/%E9%99%84%E4%BB%B6/Pasted%20image%2020250317193646.png)

where $f:A\times M\to M,(a,m)\mapsto am$, then there exists unique $f':A\otimes M\to M$ such that the diagram commutes. Now define $h:M\to A\otimes M,m\mapsto 1\otimes m$. To check $f'$ and $h$ are inverse to each other, it suffices to check $a\otimes m=1\otimes am$. 

Recall the proof of [[MATH/交换代数/Nodes/2 Modules#^aa5afc\|#^aa5afc]], let $C$ be the free $A$-module $A^{M\times N}$ and $D$ be the $A$-submodule generated by $(x+x',y)-(x,y)-(x',y)$, $(x,y+y')-(x,y)-(x,y')$, $(ax,y)-a(x,y)$ and  $(x,ay)-a(x,y)$. Let $T=C/D$, and let $g:M\times N\to T,(m,n)\mapsto m\otimes n$. So we must have 

$$(a,m)-(1,am)=(a,m)-a(1,m)+a(1,m)-(1,am)\in D$$

which yields $g((a,m))=g((1,am))$ and so $a\otimes m=1\otimes am$. 
`\end{proof}`



> [!proposition]
> Let $M_1,\cdots,M_r$ be $A$-module. Then there exists $(T,g)$ where $g:M_1\times \cdots\times M_r\to T$ is a multilinear map such that for any $A$-module $P$ and multilinear map $f:M_1\times \cdots\times M_r\to P$, there exists unique $f$ such that the diagram commutes. 
> 
> ![Pasted image 20250317200619.png|250](/img/user/%E9%99%84%E4%BB%B6/Pasted%20image%2020250317200619.png)

`\begin{proof}`
Similar to [[MATH/交换代数/Nodes/2 Modules#^aa5afc\|#^aa5afc]]. 
`\end{proof}`

## Strange Things about Tensor Product

Consider $M'\subseteq M$ and $N'\subseteq N$, then $M'\times N'\hookrightarrow M\times N$ is submodule. However, it could happen $M'\otimes N'\to M\otimes N$ is not injective. Use the following diagram to define the map.

![Pasted image 20250317201420.png|250](/img/user/%E9%99%84%E4%BB%B6/Pasted%20image%2020250317201420.png)

**Example.** Let $A=\mathbb{Z}$, $M=\mathbb{Z}\cdot e\supseteq M'=\mathbb{Z}\cdot(2e)$, and let $N=\mathbb{Z}/2\mathbb{Z}\cdot f =N'$. So we have 

$$\mathbb{Z}\cdot(2e)\otimes _{\mathbb{Z}}(\mathbb{Z}/2\mathbb{Z})\cdot f\to \mathbb{Z}\cdot e\otimes_\mathbb{Z} (\mathbb{Z}/2\mathbb{Z})\cdot f,2e\otimes f\mapsto 2e\otimes f=e\otimes 2f=0.$$

Claim that $2e\otimes f\neq 0$ in LHS. In fact, we have the following commutative diagram. 

![Pasted image 20250317203330.png|400](/img/user/%E9%99%84%E4%BB%B6/Pasted%20image%2020250317203330.png)

Here we use the isomorphism $(\mathbb{Z}\cdot 2e)\otimes_\mathbb{Z}(\mathbb{Z}/2\mathbb{Z})\cdot f\stackrel{\sim}{\to}\mathbb{Z}\cdot e\otimes (\mathbb{Z}/2\mathbb{Z}\cdot f), 2e\otimes f\mapsto e\otimes f$. Recall that $(\mathbb{Z}\cdot e)\otimes_\mathbb{Z}(\mathbb{Z}/2\mathbb{Z}\cdot f)\simeq (\mathbb{Z}/2\mathbb{Z})\cdot f$ by [[MATH/交换代数/Nodes/2 Modules#^9968ad\|#^9968ad]]. So the bottom row being zero map implies the top row is zero map. 

