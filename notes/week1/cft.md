

Some Notes on CFTs
==

*Jake Bian, May 2015. *

This is (yet another) pedagogical review of conformal field theories, with a slight emphasis on clarifying the geometric aspects.


[toc]

# The Big Picture

## Why CFTs

Aside from our immediate string theory applications, why do we care about CFTs?

The most attractive general aspect  of CFTs is perhaps that CFTs are Interacting, yet exactly solvable field theories.

There's a nice remark from Kaplan's AdS/CFT notes that I think is worth paraphrasing:



> UV complete theories are conformal
 $\implies$ "Well defined QFTs are either CFTs or RG flow between CFTs"
$\implies$  "Studying space of CFTs is like studying space of well-defined QFTs"




Some other well-known motivations

- AdS/CFT, obviously
- 2D critical phenomena

We will make a few remarks on the correspondence when appropriate in these notes. We will not discuss condensed matter. 

## The structure of these notes

We follow a now-typical sequence for introducing CFTs

1. **The "C" in CFT**: Introduce conformal group and its action on (pseudo-)  Riemannian manifolds in general. 
2. **The "FT" in CFT**:  Introduce conformally invariant field theories. 
3. **CFTs in real life**:  Go through canonical examples of CFTs

    Since these notes are a part of a course following Polchinski's book, in light of the fact that we don't exactly follow Polchinski's (rather confusing) CFT chapter, we will conclude these notes with:

**Appendix: CFTs according to a friend**: Summarize how Polchinski derives the same results that we derive here as well as picking out terminology mismatches that we may have introduced.


# The "C" in CFT


## Global definition 

### As a metric-preserving diff

> *Definition* : Let $(M, g)$ be a (pseudo-) Riemannian manifold, A **conformal transformation (CT)**  $f$ is a diffeomorphism $M \to M$ s. t.
> $$f^*g = e^{\sigma}g$$
> 
> where $\sigma$ is some smooth map $M \to \mathbb{R}$

As always, a definition should always be followed a few useful remarks:

- In some local chart $(U, x)$ of $M$, the components of $g$ transform like:

$$\frac{\partial f ^\mu}{\partial x^\alpha}\frac{\partial f ^\nu}{\partial x^\beta} g_{\mu\nu} (x) = g(f(x))$$


- When $M$ is flat and Euclidean, CT can be easily seen as a angle-preserving map (inner product / norm is preserved, in any $M$).
- A CT is a map from $M$ to itself, a Weyl transformation is a map from $(M, g) \to (M, e^\sigma g)$, a new manifold.
- A diffeomorphism is conformal $\iff$ it preserves lightcone structure (proving this is a quick exercise)

And a slightly harder to prove fact:

- every metric over a 2 dimensional manifold is conformally flat.

Equipped with this fact, we can explain the 'conformal gauge' which often appear in literature in an elegant manner, see appendix.

### Lie group structure

Let's denote The set of all conformal maps on $M$  by $CO_M$
> Remark 1: $CO_M$ forms a group

This is easy to show:

- $C_M$ is a subgroup of $Diff(M, M)$, the set of diffeomorphisms from $M$ to $M$
- $C_M$ is clearly closed under composition.


$CO_M$ then is a group which acts on $M$ in the obvious way. Furthurmore

> Remark 2:  $CO_M$ is a smooth manifold

Proof of this is beyond the scope of these notes, hence we take this remark for granted - not unlike how people often take for granted, say, the fact that the Lorentz group is a Lie group. 

As is often the case in physics when we give the Lie algebra of the Lie group the interpretation of a infinite small 'generator', the Lie group we end up with is only the component connected to unity. This is then how we shall define the conformal group;

> Definition:  The **conformal group** over $M$ is the component of $CO_M$ connected to the group identity. We denote it $C_M$.

## Roadmap: finding conformal reps on coordinates

We want to explicitly write down the representations of the conformal group and algebra in any local coordinates of $M$ - we do this as follows:

1. Since the conformal condition is defined at each point, we must start with finding killing vectors generating local transformations on each tangent space. These are local symmetries important in their own right.
2. From these, find globally defined conformal generators, these form the (global) conformal algebra, i.e. it's a algebra corresponding to a globally defined lie group.
3. Exponentiate conformal algebra to find the corresponding lie group. (In physics terms: Use infinitesmall transformations to construct finite transformations)

## Conformal killing vectors

### The Conformal Killing Vector Field

Recall that a killing vector field is a vector field along which the metric is preserved, that is, the Lie derivative of the metric vanishes along a killing vector field $X_K$

$$\mathcal{L}_{X_k}g = 0$$

Much like being conformal is weaker condition on a map than being an isometry, in the sense that the metric is allowed to gain a prefactor - a conformal killing vector is vector field where the metric is allowed to change by a multiple of itself:

$$\mathcal{L}_{X_k}g = \epsilon(p) g$$

Where $\tau$ is a smooth map $M  \to \mathbb{R}$. From here one can obtain the conformal killing equation by computing the Lie derivative and demanding the above. However, here we choose to instead follow a Lie-group theoretic approach to clarify the relationship between CKVs and the Conformal group (viewed as a Lie group) and its algebra.

Recall the Lie algebra of a Lie group $G$ is the set of all left-invariant vector fields over $G$, which is isomorphic to $T_eG$, the tangent space of $G$ at the group identity. This gives the rise to the physics view point that the Lie algebra is the 'infinitesmall generators' of the Lie group. Let's work this out.

### From Killing Vector to Lie Algebra

Very few QFT courses mention the relationship between Killing vectors and Lie algebras when deriving, say, the Poincare algbera & group (in fact very few of them mention Killing vectors at all), hence this might be something worth reminding ourselves of.

We can define a transitive Lie group action of $C_M$ on $M$ by letting a representation of $C_M$ act on components of a local chart. 
For any $\rho$, a $dim(M)$-dimensional rep of $C_M$ , we can define such an action: 

let $g \in C_M$, and $p \in M$ covered some chart $(U, \varphi)$, we define:

$$g(p) \equiv \varphi^{-1}(\rho(g)x^\mu(p))$$

where $x^\mu = \varphi^\mu(p)$. (*Excercise: show that this action is chart-independent when $p$ lies in an overlap of charts*)


Let $c$ be a smooth curve $[0, 1] \to C_M$ such that $c(0) = e$. For any fixed $t$ c(t) is a map:

$$c_t \equiv c(t): M \to M$$

Now we look at the special case that $t$ is small. Take $t = \varepsilon$, we can taylor expand $c$ as a curve to $C_M$ about \epsilon=0:

$$c(\varepsilon) = c(0) + \varepsilon\frac{dc(t)}{dt} \bigg|_{t=0} + O(\varepsilon^2)\\
= e + \varepsilon K + O(\varepsilon^2) $$

where $K \equiv \frac{dc(t)}{dt} \bigg|_{t=0} \in T_eC_M$ is the tangent to $c$ at unity, and therefore lives in the Lie Algebra. (Note: this expansion is schematic - we're not equipping the Lie group with an addition operation -  we're viewing $C_M$ as a manifold, going to some coordinates, and expanding these maps to $\mathbb{R}^n$) The action of $c_\varepsilon$ on $M$ is then:

$$c_\varepsilon(p) = [e + \varepsilon K](p) \\
= (1 + \varepsilon\rho(K))x^\mu
\\= x^\mu + \varepsilon \rho_K^\mu(x)$$

We can now give a common alternative definition of a conformal killing vector: a conformal killing vector is one whose components are $\rho_K^\mu$. This is the precise relationship between conformal killing vectors and Lie algebra elements. 

A few remarks before we move on:

- It is a useful exercise to show that this definition is equivalent to the one we gave in terms of the Lie derivative. 
-  This discussion naturally extends to killing vectors for isometries

### Deriving the Conformal Killing equation[^blumenhagen]
[^blumenhagen]: This and the few following sections largely follow Blumenhagen's book.

To solve for the Lie algebra, we simply demand $c_\varepsilon$ to be conformal. 

- take the $p \mapsto c_\varepsilon(p)$ map we defined -
-  demand the metric to transform by gaining a scale factor

We've so far insisted so far working with tensors in a coordinate-free form. But since these notes are prepared for a talk for physics students, and in order to make contact with the field theory material later on, we present do the following computations in some coordinates $x^\mu$ .

The action of the Lie algebra on a component $x^\mu$ of $x \in U$ is (again):

$$x^\mu \mapsto c(x) \equiv x^\mu +\varepsilon K(x)^\mu $$

Where we've abbreviated our notation to let $K(x)$ denote what we previously called $\rho_k[x]$, and $c$ what we used to call $c_\varepsilon$. We now demand this map takes our metric to a multiple of itself:

$$(c^*g)_{\mu\nu} \overset{!}{=} A g_{\mu\nu}$$

Where $A$ is a constant.  Evaluating the LHS:

 $$\frac{\partial c^a}{\partial x^\mu} \frac{\partial c^b}{\partial x^v} g_{ab} = (\delta^a_\mu + \varepsilon \partial_\mu K^a) (\delta^b_\nu + \varepsilon \partial_\nu K^b)g_{ab}
$$

Keeping terms up to 1st order in $\varepsilon$ and equating with RHS yields:

$$g_{\mu a}\partial_\nu K^a + g_{\nu a}\partial_\mu K^a = Bg_{\mu\nu}$$

where $B$ is another constant. Now act on both sides with g:

$$2\partial_\mu K^\mu = B d$$

where d is the dimension. Putting this together we eliminate $B$ and obtain 


>**Conformal Killing Equation (CKE)**:
>$$\partial_\nu K_u + \partial_\mu K_v - \frac{2}{d}\partial_\mu K^\mu g_{\mu\nu} = 0$$

Where as usual, the $K$s with lower indices are the 1-form duals of the vectors using the diffeomorphism given by the metric.

There is another useful form of this. We do this through a sequence of tricks:

1. apply $\partial^\nu \equiv g^{a\nu}\partial_a$ 
2. take a derivative $\partial_\nu$ to the result
3. add the resulting equation to itself, but with $\mu$ and $\nu$ switched
4. use the killing equation to rewrite the term that the laplacian acts on. 

The result is

> **Alternative form for the CKE**.
> $$(d - 1) \partial^2(\partial^a K_a) = 0$$

### CKV solutions

We now proceed find a basis for the killing vectors and talk briefly about their geometric interpretations.

The alternative form above tells us that $K_a$ is at most a order 2 function of the coordinates. Hence a basis for solution to the $K$s are the polynomials:

$$\{1, x^\mu, x^\mu x^\nu\}$$


## Explicit CKV for d != 2


Observe that for $d=1$, the CKE is automatically satisfied - that is, all diffeomorphisms on the line are conformal. We now look at the $d>2$ case briefly.

- Mention: Conformal group = AdS diffeomorphism group


## Explicit CKV for d = 2

### The setting:  coordinates, maps, Riemann sphere

Why is 2D special?

In $d = 2$, a map is conformal $\iff$ its coordinate representation is holomorphic (where of course we're implicitly viewing $\mathbb{R}^2$ as the complex plane). We can view all special properties of 2D Conformal groups as corollaries of this fact:

1. Holomorphic functions (or more generally a quotient of holomorphic functions - meromorphic ones)  naturally act on the Riemann sphere - not the plane. We work on the Riemann sphere
2. Holomorphic maps have Laurent Expansions.


- isothermal coordinates
- in 2D conformal $\iff$ holomorphic => Use Riemann sphere
- Holomorphic & anti-holomorphic
- Mobius transforms

### The Witt Algebra
- As Laurent Expansion.

**Witt algebra is the Lie algebra of $Diff(S^1)$**

This is a very well-known and geometrical remark but I am not aware of any particularly geometrical way to show it. The simplest way is perhaps the following [^lubos-credit]: 

- Consider all smooth functions over the circle. AKA periodic functions
- These have Fourier expansions. Write down the Fourier nodes. These look exactly like the Witt algebra. 


  [^lubos-credit]:  I stumbled upon this particular way of identifying witt algebra with circle Diff generators in something written by [Lubos Motl](http://physics.stackexchange.com/questions/12022/geometric-visual-interpretation-of-virasoro-algebra)


### Global Conformal Group & algebra in d=2 (its finite!)
- poles of laurent modes


## Virasoro Algebra

### Central extensions in general
- Group extensions in general: what does it mean to extend a group. 
- What is a central extension in terms of adding a term to the commutator.
- quantization => central extend operator algebra. e.g. QM

### Virasoro is Central extension of Witt
- using Jacobi identities that the Witt algebra satisfies, we see that the Virasoro algbera is completely fixed up to a central charge, to be fixed by your specific theory.

## The "FT" in CFT

### What is a CFT
#### Defining  a field theory
#### Defining a CFT

### The setting of CFT: Radial quantization
- mention: it's technically an annulus, not a disk!
#### The coordinate map
#### From cylinder operators to disk operators

### The CFT Hilbert Space
#### Virasoro Reps
#### Hilbert Space
#### Quantizing Laurent Modes
#### Asymptotic states

### The CFT Path Integral
#### The path integral
#### EM tensor

### More on CFT Operators
#### Radial ordering
#### Normal ordering

### Primary fields & Conformal Dimension

### OPEs
#### OPE Existence
#### Momentum Tensor
#### 2 & 3 point functions
#### Ward Identities
#### "CFT Data"

### CFT Interactions
#### Vertex Operator
#### c-theorem

### Operator-state correspondance
#### Operator-state correspondance in general
#### Operator-state correspondance in CFTs
#### AdS/CFT as a operator to operator map
- Aside: AdS interactions & Witten diagrams
#### OPE Associativity/ Conformal Bootstrap

## CFTs in Real Life

### The Free scalar boson
In this section we apply what we learned to the free CFT scalar boson.
#### The theory
#### Momentum Tensor
#### Correlators
#### Central Charge
#### Fock space

### Other examples

We describe these other examples, and leave the details of the conformal theories as excercises/reading assignments.

#### bc CFT
#### Linear Dilaton
#### Free 

## Appendix: CFTs according to a friend

### Rephrasing results from Chapter 1

Remember for the Polyakov action (or string sigma model), we introduced an auxilary metric $h_{ab}$ and argued by counting degrees of freedom that you can 'fix a gauge' in which $h_{ab} = \eta_{ab} $, then later had to deal with different consequences of this gauge fixing. There's an alternative, simpler way to state this.

- $h$ is a metric over a 2 dimensional manifold $M$
$\implies$ $h$ is conformally flat, that is $h = e^\sigma \eta$
- $h$ is Weyl invariant
$\implies$ $\sigma$ is constant

Hence $h = \eta$ up to some constant multiple - the *conformal gauge*  really just choosing some coordinates in which $h$ is diagonal. 

How is this is a gauge fixing in the usual sense? One way to answer this is to consider the tangent bundle $TM$, then indeed choosing a coordinate map is the same things as choosing a local trivialization - a gauge fixing.

### Terminology/notation differences

- Polchinski calls the Witt Algebra "Virasoro generators"
- Polchinski calls primary fields 'tensor fields'