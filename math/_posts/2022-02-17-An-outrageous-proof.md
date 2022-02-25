---
usemathjax: true
---
## An absurd proof that $\sqrt{2}$ is irrational

*Edit:* I was made aware that this proof appeared on [Stackexchange](https://math.stackexchange.com/a/1311239/510814) before and I don't want to claim authorship at all!

Sometimes a good tool to make people remember something is to do something utterly outrageous. I will hence give you the worst proof you have ever seen to show that $\sqrt{2}$ is irrational. It uses a bit of non-trivial number theory and a bit of model theory and also it uses a weak form of the axiom of choice.

###  Ultraproducts
Ultraproducts pose a fundamental tool in model theory and we will do some unholy work with them. First a quick reminder: We fix some language $\mathcal{L}$ and take any index set $I$ to index a bunch of $\mathcal{L}$-structures $(M_i)_{i \in I}$. We then take a non-trivial ultrafilter [^1] $\mathcal{U}$ of $I$ and define

$$ \prod_{\mathcal{U}} M_i = \prod_{i \in I} M_i / \sim_{\mathcal{U}}  $$  

where $$(x_i)_{i \in I} \sim (x'_i)_{i \in I}$$ if and only if the set
$$ \{i \in I \mid x_i=x'_i \}$$ is in $\mathcal{U}$.

One then also interprets $\prod_{\mathcal{U}} M_i$ as an $\mathcal{L}$-structure by checking that functions remain well-defined and by defining relations to hold iff they hold on filter sets. This leads to the following result:


[^1]: A non-trivial ultrafilter is a maximal filter that is not a principal ultrafilter (i.e. just all the sets that contain some fixed $x \in I$)

> #### Łoś's theorem 
> Let $\varphi$ be any $\mathcal{L}$-sentence - for instance if $$\mathcal{L}=\{0,1,+,-,\ast\}$$ is the language of rings $\varphi$ could be the sentence that says "$2$ is a square" - then
>$$\prod_{\mathcal{U}} M_i \vDash \varphi \Leftrightarrow \{i \in I \mid M_i \vDash \varphi \} \in \mathcal{U}.$$

So the ultraproduct believes a sentence to be true if and only if the set of models that believe the sentence is a filter set. 

### Squares in finite field
If $p=8n+3$ is prime for some $n \in \mathbb{Z}$, then we can use basic properties of the [Legendre Symbol](https://en.wikipedia.org/wiki/Legendre_symbol) to see, that

$$ \left(\frac{2}{p}\right)=-1 $$
which is equivalent to say that $2$ is not a square modulo $p$.

By a bit more heavy machinery, namely [Dirichlet's theorem on arithmetic progression](https://en.wikipedia.org/wiki/Dirichlet%27s_theorem_on_arithmetic_progressions) 
there are infinitely many primes of the form $p=8n+3$.
Let $P$ be the set of those primes.

### The ridiculous magic trick
We now envoke the axiom of choice[^2] to produce a non-principal ultrafilter on $P$ and build a new field:
$$ F:=\prod_{\mathcal{U}} \mathbb{F}_p. $$
By Łoś's theorem the following things are true:
 
- $F$ is  a field, cause all the $\mathbb{F}_p$ are fields and that is a first-order property.
- All the $\mathbb{F}_p$ believe that there is no square root of $2$, so $F$ also does not have a square root of $2$.
- There are arbitrarily large $p$'s in $P$, hence the  theorem $\underline{1+\ldots+1}_{p-\text{times}} \neq 0$ is true in $\mathbb{F}_p$ for cofinitely many $p$, hence $F$ necessarily has characteristic $0$.
- Because $F$ has characteristic $0$, there is a unique embedding $\mathbb{Q} \hookrightarrow F.$
- So $\mathbb{Q}$ can not have a square root of 2, because $F$ does not even have one!


I wonder if there is an easier proof for this...

[^2]: Indeed something a tiny bit weaker!
