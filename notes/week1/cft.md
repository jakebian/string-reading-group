

Some Notes on CFTs
==

*Jake Bian, May 2015. *

This is (yet another) pedagogical review of conformal field theories, with a slight emphasis on clarifying the geometric aspects.


[toc]

# The Big Picture

## Why CFTs

Aside from our immediate string theory applications, why do we care about CFTs?

The most attractive general aspect  of CFTs is perhaps that CFTs give us examples of interacting, yet exactly solvable field theories.

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

### As a diffeomorphism

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

Rather confusingly, being conformally flat means being related to a flat space through a Weyl transformation, not a conformal map.

Equipped with this fact, we can explain the 'conformal gauge' which often appear in literature in an elegant manner, see appendix.

### As a Lie group

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

Also observe that clearly the group of isometries of $M$ is a subgroup of $CO_M$ - we will see this fact manifest again shortly when we classify the generators of the Lie algebra.

### Roadmap: finding conformal action on coordinates

We want to explicitly write down the actions of the conformal group and algebra in any local coordinates of $M$ - we do this as follows:

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


### Conformal Killing Vector from Conformal Algebra

TODO: add more physics words to this section. Write down infinitesmall, coordinate, form.

We will talk about both the conformal killing vectors and the conformal algebra extensively in the following sections. It is therefore worthwhile to recall a few things from differential geometry in order to clarify the relationship between the Lie Algebra and vector fields over $M$.

Recall the Lie algebra $\mathcal{A}_G$ of a Lie group $G$ is the set of all left-invariant vector fields over $G$, which is isomorphic to $T_eG$, the tangent space of $G$ at the group identity. 

Any vector field $V$ over $G$ generates an integral curve starting at the identity (or 1-parameter group acting on the identity), i.e. a curve $C_{V} : \mathbb{R} \to G$ such that

$$\frac{d}{dt} C_V(t) = V(p)\\ C_V(0) = e$$

Specializing to Lie Algebra vector fields - these are right invariant, hence a vector field $A \in \mathcal{A}_G$ is uniquely determined by its value on $T_eG$, which we will denote by $A_0$. 

We can now define the *exponential map*:

$$exp:  T_eG \to G \\ A_0 \mapsto C_A(1)$$

By the chain rule we can then show the identity:

$$\exp(tA_0) = C_A(t)$$


 One can show that any connected component of a Lie group is covered by the 1-parameter groups generated by its Lie algebra.  That is, every element $g \in G$ connected to the identity can be written as:

$$g = \exp(tA)$$

for some $t \in [0, 1]$, $A \in \mathcal{A}_G$.

Now we move to the manifold $M$ that $G$ acts on. We assume that  $G$ acts on $M$ from the left with some well-defined action $p \mapsto gp$.

The fundamental vector field $A^\#$ over $M$ generated by lie algebra element $A$ is defined as:

$$ A^\#(p) \equiv \frac{d}{dt} (\exp(tA_0) p) |_{t =0}$$

In the case of the conformal algebra, we say $A^\#$ is the Killing vector field associated with the conformal algebra element $A$. This is the precise relationship between the conformal algebra and conformal killing vector fields. 

The punchline of all this can be stated as follows:

> The **killing vector field $A^\#$ associated with Lie algebra element $A$** at $p \in M$ is the tangent to the curve generated by acting on the point $p$ with the 1-parameter group generated by $A$

It can be shown that these vector fields generated by the Lie algebra have exactly the form of conformal Killing vector fields. 

However, **not every conformal killing vector field is generated by a Lie algebra element**. That is, given a vector which generates infinitesmall conformal transformations locally, it does not necessarily have a representation as a tangent of a curve from acting on a point by a one-parameter group. This means there may be more conformal Killing vectors than there are Lie algebra elements. For example, in 2 dimensions, there is a infinite number of conformal Killing vectors, however only a finite number of elements in the conformal algebra (more on this later). 

In the language of physicists, we say the conformal Killing vectors are generators of *local* conformal transformations, whereas the Lie algebra generates *global* conformal transformations.

This correspondence between the Lie algebra and the vector fields also answers a question that surely would have crossed the mind of the more mathematically minded physicist - when we define the action of a killing vector in the coordinate form - why are we allowed to add the components of a vector to the components of a coordinate for a point? At least for Lie algebra-generated killing vectors, the answer is this is approximately the coordinate representation of the infinitesmall action of the 1-parameter group generated by an Lie algebra element.


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

There are two more useful form of this. We discover them through a sequence of contrived tricks:

1. apply $\partial^\nu \equiv g^{a\nu}\partial_a$ 
2. take a derivative $\partial_\nu$ to the result
3. add the resulting equation to itself, but with $\mu$ and $\nu$ switched
4. use the killing equation to rewrite the term that the laplacian acts on. 

We obtain:

>Alternative forms of the CKE:
> 1. $$(\eta_{\mu\nu}\partial^2 + (d-2)\partial_\mu\partial_\nu)(\partial^a K_a) = 0$$
Contracting with $\eta ^{\mu\nu}$ gives:
2.
> $$(d - 1) \partial^2(\partial^a K_a) = 0$$


### Dimensions matter!

Observe that for $d=1$, the CKE in alternative form 2 is automatically satisfied - that is, all diffeomorphisms on the line are conformal. We now look at the $d>2$ case briefly.

Now for $d=2$, the CKE in alternative form 1 reads:

$$\partial^2 ( \partial^a K_a) = 0$$

This says $ \partial^a K_a$ is a harmonic function. We know a way to study harmonic functions is to view them as real and imaginary components of a holomorphic functions on the Riemann sphere. This is exactly the approach we will take.


For $d > 2$, we observe that alternative form (1) no longer has that simple form as in $d=2$. Furthermore the alternative form (2) then tells us that  $K_a$ is at most a order 2 polynomial of the coordinates.

Hence, in the next section, we study the $d>2$ case and $d = 2$ case separately.


## Conformal group in d> 2
### Directions of symmetry: classifying the 1-parameter groups

The last form of the CKV above tells us that the components of $K$ are at most a order 2 polynomial of the coordinates. Hence a basis for solution these components viewed as functions of some coordinates in $M$ are the polynomials in $x$ coordinates. That is, the most general form for the components of $K$ at any $x \in M$ in these coordinates:

$$K = [a^\mu + b^\mu_\nu x^\nu + c^\mu_{\nu\sigma}x^\nu x^\sigma] \partial_\mu$$

We can consider this expression order by order. For now we redirect the reader to Blumenhagen's book for classifying these.


- SCT: invert -> translate -> invert


#### Compactifying our spaces
The special conformal transformations take the form [^joshphysics]:

[^joshphysics]:  Solving for the integral curve of the infinitesmall conformal generator looks like a rather ugly task, however it can be done with a smart change of variables, see [this physics SE answer](http://physics.stackexchange.com/questions/121920/integrating-the-generator-of-the-infinitesimal-special-conformal-transformation/122283?noredirect=1#comment249123_122283)

$$x^\mu \mapsto \frac{x^\mu - (x \dot{} x) b^\mu}{1 - 2(b \dot{} x) + (b \dot{} b)(x\dot{} x)}$$

In order for this equation to make sense everywhere, in particular when the denominator is $0$, we must change our definition of "everywhere" to include the point at infinity - this should look familiar - we do an analogous thing in complex analysis. 

To justify this mathematically, one simply has to note that the map from $\mathbb{R}^n$ to its conformal compactification $\mathbb{R}^n \cup \{ \infty \}$ is a diffeomorphism.

#### Conformal group for general signatures
We quote the following result:

>  For $\mathbb{R}^{(p, q)}$, the conformal group is  $$SO(p + 1, q +
> 1)$$

In particular for $p= 1, q = d - 1$, the conformal group is

$$SO(2, d)$$

Recall $AdS^{d+1}$ can be defined as the '$(2,d)$ hypersphere: a $ SO(2, d)$ symmetric surface embedded in $\mathbb{R}^{(2,d)}$. That is:

> $$Diff(AdS^{d+1}) \simeq C({\mathbb{R}^{(1, d-1)}})$$

Notice we have not discussed any field theory at all up to this point, the moral here is there's magic at a purely geometrical level that allows the gauge/gravity duality to work.


## Conformal group in d = 2

### Maps on the Riemann Sphere

We already saw that the conformal Killing equation in 2 dimensions looks different than the $d>2$ case. Another reason for liking $d=2$ is that complex analysis gives us tools to compute things. The first step to thinking about conformal transforms as complex analysis is the following observation: in d = 2, the CKV reduces to the Cauchy Riemann equations. Therefore:

> In $d = 2$, a map $M \to M$ is conformal $\iff$ its coordinate
> representation is holomorphic


Where of course we're implicitly viewing $\mathbb{R}^2$ as the complex plane. We can view all the nice properties of 2D Conformal transformations as springing from our ability to leverage the rich collection of theorems about holomorphic functions, aka. the theory of complex analysis.

#### Complex Coordinates

We make the following diffeomorphism from the $\mathbb{R}^2 \cup \{ \infty \}$ to $\mathbb{C}^2 \cup \{ \infty \}$. The two spaces are clearly diffeomorphic - so we can and should think about this as a coordinate change.

$$ z \equiv x^0 + i x^1 ~~ \bar{z}\equiv x^0 - i x^1$$

Some people would call this going to the lightcone gauge and performing a Wick rotation. Some people enjoy using big words, good for them. 

In these coordinates, we know that a conformal (holomorphic) map only depend on $z$, that is

$$ K(z, \bar z) = K(z)$$

Now a function $f$ in $\mathbb{R}^2$ has the decomposition:

$$f(a, b) = (f_x(a), f_y(b))$$

We want to find such a decomposition for $K$ as well in terms of the complex coordinates $(z, \bar z)$. Let $C_K$ denote the $M \to M$ map given by  $K$:

$$C_K: (z, \bar z) \mapsto (K(z), \overline{K(z)})$$
 
$K$ has a Laurent expansion about the origin:

$$K(z) = \sum_{n \in \mathbb{Z}} k_n z^n$$

We define:

$$\overline{K}(z) \equiv \overline{K(\bar z)} = \sum_{n \in \mathbb{Z}} \overline{k_n} {z}^n$$

Observe:
$$\overline{K}(\overline z) =\sum_{n \in \mathbb{Z}} \overline{k_n} \bar{z}^n = \overline{K(z)} $$

Hence we have:
$$C_K(z, \bar z) = (K(z), \overline K(\bar z))$$

Observe the $\overline K$ is also holomorphic - this is the decomposition we sought for. It is also illuminating to introduce the operator

$$\overline K_
-(z) \equiv  \overline K(\bar z))$$

Observe that $\overline K_-$ is anti-holomorphic. We can then write
$$C_K: z \mapsto (K(z), \overline K_
-( z))$$


Hence we see that when we let a conformal map acting on a point $z$ the Riemann sphere, and try to see what's the corresponding effect in its components, we find that

- the $z$ component transforms by a holomorphic function of $z$
-  the $\bar z$ comonent  transforms by an antiholomorphic function of $z$.

### The Witt Algebra

Each conformal (holomorphic) map has a Laurent expansion, the modes in the Laurent expansion therefore form a infinite basis for all holomorphic functions. This is called the *Witt Algebra* - the set of conformal Killing vectors that *locally* generate conformal transformations in $d=2$. We will later see that only a subset of the Witt algebra should be identified as the algebra of the global conformal group, because all but a few of the Witt algebra elements are defined on a  open strict subset of the Riemann sphere.


#### Laurent Modes & A convenience redefinition
A conformal map $K(z)$ is holomorphic, hence has an expansion

$$K(z) = \sum_{n \in \mathbb{Z}} k_n z^n$$

As a vector, as we saw earlier, it has components

$$ K(z) = \sum_{n \in \mathbb{Z}} \overline k_n \overline z^n \partial_{\bar z} +  k_n z^n\partial_z$$


In this talk we will work out the algebra first with $z^n$ as a basis for the conformal killing vectors. Then we see that the commutation relations will look much nicer once we shift the indices and flip a sign, and use $-z^{n+1}$.



#### Witt algebra is the Lie algebra of $Diff(S^1)$

This is a very well-known result for the group $Diff(S^1)$ is very well-studied by mathematicians. The simplest way to see this fact perhaps the following [^lubos-credit]: 

- Consider all smooth functions over the circle. AKA periodic functions
- These have Fourier expansions. Write down the Fourier nodes. Rewriting $z$ as the exponential mod the integer exponent, this now looks exactly like the Witt algebra. 


  [^lubos-credit]:  I stumbled upon this particular way of identifying witt algebra with circle Diff generators in something written by [Lubos Motl](http://physics.stackexchange.com/questions/12022/geometric-visual-interpretation-of-virasoro-algebra)


### Global Conformal Group & algebra in d=2 (its finite!)

Observe

$l_n$ is non-singular at $0$ only for $n \ge -1$
$l_n$ is non-singular at $\inf$ only for $n \le 1$

Hence the globally we have three generators $\{l_{-1}, l_0, l_1\}$. Observe this looks a lot like the case we had for $d>2$.

First observe, clearly $l_{-1}$ generates translations

Now choose $z = e^{i \phi}$, we see combinations of $l_0$ with its anti-holomorphic dual generates rotations and dilations.

 - The remaining one is the special conformal transformation

Observe combinations these are exactly the mobius trnasformations.


## Quantizing the 2D algebra: Virasoro Algebra

### Central extensions in general

There's a very general story relating central extension of groups to quantization of symmetry. We will not discuss that here, but we still would like to provide an minimal amount of motivation for central extension beyond simply writing down an extra term in the right of the commutators.

Quantizing infinitesmall, locally conformal maps on the mobius sphere has a nice analogy that we're already familiar with - quantizing generators of translations in phase space, $(x, p)$. We will briefly  demonstrate here that quantization in that case is simply using the centrally extended algebra.  Equivalently, we are moving to the projective representation from the full representation, which is equivalent to adding a central charge to the full representation.


### Virasoro is Central extension of Witt
- using Jacobi identities that the Witt algebra satisfies, we see that the Virasoro algbera is completely fixed up to a central charge, to be fixed by your specific theory.

# The "FT" in CFT

## Classical conformal field theory

While defining a quantum field theory is in general not easy, Wightman axioms and what not. Defining a classical field theory is rather easy, so let's first take a look at the classical aspects of CFTs.

### Primary Conformal Fields

In CFTs we start by employing what may seem like a rather unconventional definition of a classical field. Here the definition we need to employ is:

> A primary conformal field *behaves* like the $(z, z, ... , \bar z, \bar z, ...)$ component of a $(h, \bar h)$ tensor over $M$ under a conformal transformation


Then under a conformal transformation (holomorphic map) $f$, we obtain the transformation law:

$$\Phi(z, \bar z) \mapsto \left( \frac{\partial f}{\partial z} \right) ^ h \left( \frac{\partial f}{\partial \bar z} \right) ^ \bar h \Phi(z, \bar z) $$

If this only holds for global conformal maps, the field is said to be quasi-primary. 


### Momentum Tensor

Here we show that Conformal invariance implies a traceless momentum tensor. The only facts we need to recall about the momentm tensor is that it's traceless, and that  Noether's theorem says $$j_\mu = T_{\mu\nu} K^\nu$$ is preserved. Tracelessness of momentum tensor comes from $\partial^\mu partial_\mu = 0$

- In particular, for the case that $K$ is a translation (a constant), we find
$$\partial^\mu T_{\mu\nu} = 0$$

- Using the above we can eliminate a term from the Leibneiz rule.
- Sneakily using the fact the $T$ is symmetric, write the remaning term in the form of the conformal killing equation. The result is:
$$T^\mu_\mu = 0$$
 

## What is a CFT

### As a path integral
For mathematical concreteness, it is beneficial to define a field theory as a path integral with all of its n-point correlators. For CFTs, we may define it as all correlators between primary fields.

### As a Hilbert Space

- There exists a vacuum $| 0 \rangle$ invariant under some representation of the conformal group.

Following traditional Peskin-Schroeder-esque sloppiness one of the ways to obtain a Hilbert space for the field theory is to obtain a Hamiltonian. So let's talk about radial quantization.




## The setting of CFT: Radial quantization
- mention: it's technically an annulus, not a disk!
### The coordinate map
### From cylinder operators to disk operators

### The CFT Hilbert Space
#### Virasoro Reps
### Hilbert Space
### Quantizing Laurent Modes
### Asymptotic states

## The CFT Path Integral
### The path integral
### EM tensor

## More on CFT Operators
### Radial ordering
### Normal ordering

## Primary fields & Conformal Dimension

## OPEs
### OPE Existence
### Momentum Tensor
### 2 & 3 point functions
### Ward Identities
### "CFT Data"

## CFT Interactions
### Vertex Operator
### c-theorem

## Operator-state correspondance
### Operator-state correspondance in general
### Operator-state correspondance in CFTs
### AdS/CFT as a operator to operator map
- Aside: AdS interactions & Witten diagrams
### OPE Associativity/ Conformal Bootstrap

# CFTs in Real Life

## The Free scalar boson
In this section we apply what we learned to the free CFT scalar boson.
### The theory
### Momentum Tensor
### Correlators
### Central Charge
### Fock space

## Other examples

We describe these other examples, and leave the details of the conformal theories as excercises/reading assignments.

### bc CFT
### Linear Dilaton
### Free 

# Appendix: CFTs according to a friend

## Chapter 1 results in CFT language

### The Conformal Gauge
Remember for the Polyakov action (or string sigma model), we introduced an auxilary metric $h_{ab}$ and argued by counting degrees of freedom that you can 'fix a gauge' in which $h_{ab} = \eta_{ab} $, then later had to deal with different consequences of this gauge fixing. There's an alternative, simpler way to state this.

- $h$ is a metric over a 2 dimensional manifold $M$
$\implies$ $h$ is conformally flat, that is $h = e^\sigma \eta$
- $h$ is Weyl invariant
$\implies$ $\sigma$ is constant

Hence $h = \eta$ up to some constant multiple - the *conformal gauge*  really just choosing some coordinates in which $h$ is diagonal. 

How is this is a gauge fixing in the usual sense? One way to answer this is to consider the tangent bundle $TM$, then indeed choosing a coordinate map is the same things as choosing a local trivialization - a gauge fixing.

## Terminology/notation differences

- Polchinski calls the Witt Algebra "Virasoro generators"
- Polchinski calls primary fields 'tensor fields'