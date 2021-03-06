

Some Notes on CFTs
==

*Jake Bian, May 2015. *

This is (yet another) pedagogical review of conformal field theories, with a slight emphasis on clarifying the geometric aspects. This is a work in progress.


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

These are followed by three appendices

**Appendix A: Hilbert space foliations, lattices & local operators** This appendix outlines how (I think) field theory Hilbert space should be understood in general.

**Appendix B: Ads/CFT as an Operator-to-operator map** This appendix attempts to explain some results from the correspondence using only the tools introduced in these notes.

**Appendix C: CFTs according to a friend**:   Since these notes are a part of a course following Polchinski's book, in light of the fact that we don't exactly follow Polchinski's (rather confusing) CFT chapter, this appendix tries to reconcile our notation with Joe's. 

These notes were covered in two talks, which is very a very likely cause for the excess amount of content in the appendices.


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
$l_n$ is non-singular at $\infty$ only for $n \le 1$

Hence the globally we have three generators $\{l_{-1}, l_0, l_1\}$.  Hence just like in $d>2$, the algebra of globally defined conformal transformations is finite. Let's consider these one by one:

$$P_z \equiv  l_{-1} = - \partial_z, \\
P_\bar z \equiv  \bar l_{-1} = - \partial_\bar z $$

This clearly generates translations so let's give it another name.

Writing $z = re^{i \phi}$, we find:

$$l_{0} = -  \frac12 \partial_r + \frac i2 \partial_\phi \\ 
    \bar l_{0} = -  \frac12 \partial_r - \frac i2 \partial_\phi
$$


We can define linear combinations:

$$ D \equiv l_0 + \bar l_0 = -r \partial_r \\
L \equiv i(l_0 - \bar l_0) = -\partial_\phi$$

The remaining one is the special conformal transformations

$$ K_z \equiv l_1 = - z^2 \partial_z \\
 K_\bar z \equiv  \bar  l_1 = - \bar z^2 \partial_ \bar z$$

In summary, we have labeled our (global) conformal algebra by the symmetry transformation they generate, and obtained the set

$$\{ P, D, L, K \}$$ 

Where $P$ and $K$ are vectors, $D$ and $L$ each have a single component. 
This is in fact the general picture in higher dimensions as well. In $d>2$,  $L$ becomes an anti=symmetric tensor, $D$ remains a scalar, $P$ and $K$ remain vectors.


## Quantizing the 2D algebra: Virasoro Algebra

### Central extensions in general

There's a very general story relating central extension of groups to quantization of symmetry. We will not discuss that here, but we still would like to provide an minimal amount of motivation for central extension beyond simply writing down an extra term in the right of the commutators.

Quantizing infinitesmall, locally conformal maps on the mobius sphere has a nice analogy that we're already familiar with - quantizing generators of translations in phase space, $(x, p)$. We will briefly  demonstrate here that quantization in that case is simply using the centrally extended algebra.  Equivalently, we are moving to the projective representation from the full representation, which is equivalent to adding a central charge to the full representation.

TODO: finish writing this up.

### Virasoro is Central extension of Witt
- using Jacobi identities that the Witt algebra satisfies, we see that the Virasoro algbera is completely fixed up to a central charge, to be fixed by your specific theory.

# The "FT" in CFT

## Classical conformal field theory



### Primary Conformal Fields

Turns out the central objects in field theory can be defined as things in a classical field theory

> A primary conformal field *behaves* like the $(z, z, ... , \bar z, \bar z, ...)$ component of a $(h, \bar h)$ tensor over $M$ under a conformal transformation


Then under a conformal transformation (holomorphic map) $f$, we obtain the transformation law:

$$\Phi(z, \bar z) \mapsto \left( \frac{\partial f}{\partial z} \right) ^ h \left( \frac{\partial f}{\partial \bar z} \right) ^ \bar h \Phi(z, \bar z) $$

If this only holds for global conformal maps, the field is said to be quasi-primary. 

Infinitesmally, one can show:

$$\delta_{\varepsilon K, \varepsilon \bar K} \phi(z, \bar z)= \varepsilon (h \partial_z K + K \partial_z) \phi(z, \bar z) + \text{anti-holomorphic} $$

This can be taken as an alternative definition of a primary field, we will encounter two more definitions of a primary field. To learn CFTs (roughly) is to learn to appreciate the various equivalent definitions of a primary field.

### Momentum Tensor

#### Conformal implies traceless
Here we show that Conformal invariance implies a traceless momentum tensor. The only facts we need to recall about the momentm tensor is that it's traceless, and that  Noether's theorem says

$$j_\mu = T_{\mu\nu} K^\nu$$ 

is preserved. Tracelessness of momentum tensor comes from $\partial^\mu j_\mu = 0$

- In particular, for the case that $K$ is a translation (a constant), we find
$$\partial^\mu T_{\mu\nu} = 0$$

- Using the above we can eliminate a term from the Leibneiz rule.
- Sneakily using the fact the $T$ is symmetric, write the remaining term in the form of the conformal killing equation. The result is:
$$T^\mu_\mu = 0$$
 
 
#### $d = 2$ case: holomorphic momentum tensor

In complex coordinates in 2 dimensions, the result is the following:

- $T_{z \bar z} = T_{\bar z z} = 0$
- $T_{zz}$ is holomorphic
- $T_{\bar z \bar z}$ is anti-holomorphic

Motivated by this, we define $T(z) \equiv T_{zz}$, $T(\bar z) \equiv T_{\bar z \bar z}$. These completely specify the momentum tensor in 2 dimensions.

## The CFT Hilbert Space

I recommend glancing over **appendix A** at this point.

### Conformal theory on $S^1 \times \mathbb{R}$

So far we have been considering conformal transformations and field theories over a general Riemannian (Euclidean) manifold $M$ [^euclidean-comment]. For concreteness, we now restrict ourselves to the case that $M \sim S^1 \times \mathbb{R}$, most directly visualized as the cylinder. One should note that many aspects of the discussion below can be generalized straightforwardly to the field theory on $S^n \times \mathbb{R}$.[^slavanotes]

[^euclidean-comment]:  One would of course obtain the Minkovskian version through a Wick rotation, given that the topology of $M$ allows this to be done without severe consequences. In the case that $M$ is not nice enough to behave well under a wick rotation, there will likely be other more serious problems plaguing any QFT defined on $M$

[^slavanotes]: https://sites.google.com/site/slavarychkov/

#### The radial map

$S^1 \times \mathbb{R}$ of course has a global cover - for the purposes of defining a field theory over $M$ there's no reason to use any other cover than the global cover. The most direct/natural coordinates are probably:

$$(t, x) \in  \mathbb R \times [0, 2\pi)$$

An alternative cover can be defined in terms of this one:

$$(z, \bar z) \equiv (e^{t + ix}, e^{ t - ix})$$

This map is clearly a diffeomorphism:

$$\mathbb R \times [0, 2\pi) \to \mathbb C - \{0\}$$

Hence both these are global covers of $M$. The former is easier pictured as a cylinder whereas the latter is easier pictured as a punctured disc (or an annulus) with infinite (outer) radius.

It can be easily seen that for transformations in $M$, we have the following dual interpretations in these two coordinate systems:

Cylinder                     | Annulus
---------------------------- | -------
Translation in $t$ direction | Dilation
Translation in $x$ direction | Rotation

Consider some classical field theory defined over $M$ with local coordinate $t$ being interpreted as the time direction.  Then, very concretely, when one writes our field theory Hamiltonian (time evolution operator) in the annulus coordinates, it would becomes the dilation generator. Similarly a translation in the $x$ direction would look like a rotation operator in the annulus coordinates.



#### Labeling of conformal killing vectors is coordinate dependent

A clarification is in order - recall we defined a conformal transformation as a coordinate-independent map $M \to M$. However, we now we have a situation where a dilation in one coordinate for $M$ is not a dilation on another coordinate system.

The takeaway from this is that although conformal transformation is defined globally and coordinate-independently, the classification of conformal algebra elements (into dilations, translations, special conformal transformations, etc.) is coordinate dependent. That is, although we have a single set of Killing vectors, and a single conformal group and algebra, we don't know how to label these vector fields over $M$ until we go to some coordinates. The algebra of the Poincare generators on the cylinder is interpreted as the algebra of dilations and rotations on the annulus.

One can perhaps summarize and generalize this in the phrase "physical interpretation is coordinate-dependent, mathematics is not". This distinction between coordinate-independent mathematical objects and coordinate-dependent physical interpretations carries over to the quantum theory. See **Appendix A**. 



### States & operators in CFT

Our approach is to learn as much as possible about states and operators in $d=2$ CFTs by only studying elements of the Virasoro algebra.

#### Verma Modules

Denotes our Virasoro algebra by $\{ L _n \}_{n \in \mathbb Z}$, recall the commutation relation is:

$$
[L_m, L_n]= (m-n)L_{m + n} + c \delta_{-m, n}
$$

Along with another algebra withe same commutation relations which commutes with this, denoted by $\{ \bar L _n \}_{n \in \mathbb Z}$.

Recall our dilation operator is given by

$$D = L_0 + \bar L_0$$

A few lines of computation shows:

$$[D, L_n] = - n L_n$$

This tells us that in some representation of the Virasoro algebra on a Hilbert space,  with respect to eigenstates of the operator representation of $D$:

- $L_n$ for $n < 0$ are creation operators
- $L_n$ for $n > 0$ are annihilation operators

Given a highest weight state $|h\rangle$, that is, a state $h$ that is anihilated by all $L_n$ for $n > 0$. Any such state $h$ defines a *Verma Module* $V_h$ given by the set of states:

$\{ |h \rangle, \\  L_{-1}|h \rangle,  \\ L_{-1}L_{-1}|h \rangle, L_{-2}|h\rangle,\\ ... \}$

These highest weight states $h$ are called primary states, and the rest of the states are known as descendents of $h$.  

#### Primaries & Descendants

> **Defintion**: A **primary state** is a state $|\phi \rangle$ such that $L_n | \phi \rangle = 0$ for all $n > 0$.

By the above discussion, each primary state defines a set of descendent states to form the Verma module $V_\phi$. For completeness let's state

> **Defintion**: A **descendent state** is any state obtained by acting on a primary state $|\phi \rangle$ with a composition of any sequence of
> operators $L_n$ with $n < 0$.

Now consider a primary state which can be written as

$$ |\phi \rangle = \phi |0 \rangle$$

where of course $|0 \rangle$ is the field theory vacuum. (For now we can think of the states that can be written in the above form as a special class of states. It will turn out all states we care about in a CFT have this property, more on this later.) This motivates the definition of a primary operator:

> **Definition**: A **primary operator** is a linear operator $\phi$ on CFT Hilbert space such that $$[L_n , \phi] = 0$$

And similarly

> **Defintion**: A **descendent operator** is any operating obtained by appending (by composition) to a primary operator $\phi$ a composition
> of any sequence of operators $L_n$ with $n < 0$.

To make contact with our definition of a primary operator in terms of transformation properties, it is necessary to work out some OPEs.

#### Momentum tensor and Virasoro Algebra

The holomorphic part of the momentum tensor has a Laurent expansion:

$$T(z) = \sum_{n \in Z} z^{-n - 2}L_n$$

with:

$$L_n = \frac 1 {2 \pi i} \oint dz [z^{n+1}T(z)]$$

(You can see there's again some contrived index shifting here, since we thoroughly motivated the index shifting in the Witt algebra we leave it as an exercise to figure out why the shifting here is convenient.)

It is easy to show that $L_n$ form Noether charges associated with the $n$-th generator of the Witt algebra. It can be verified by computing the OPE that $L_n$ satisfies the Virasoro algebra. 



## CFT Correlators

### Quantities of interest

#### Correlators
In a quantum field theory, we're interested in correlators like:

$$\langle O_1(x_1) _2(x_2) ... \rangle$$

Where the $O$s are operators on field theory Hilbert space. In the path integral formalism the above reads

$$\int [\mathcal DO_1O_2... ] e^{iS[O_1, O_2, ...]}  O_1(x_1)O_2(x_2)...$$

with a normalization factor that we left out. In the canonical picture this reads:

$$\langle 0 | T [O_1(x_1) O_2(x_2) ...] | 0 \rangle$$

In the following we adopt the perhaps confusing, but standard notation

$$ O_1(x_1) O_2(x_2) ...\equiv \langle O_1(x_1) O_2(x_2) ... \rangle$$


#### Radial ordering

Recall in our CFT on a cylinder, time direction in the cylinder coordinates is interpreted as time. Switching to the annulus coordinates, clearly time ordering in the cylinder gets translated to ordering based on distance from origin, also known as the usual norm in $\mathbb C$. Hence radial ordering looks like:

$$R[A(z) B(w)] \equiv A(z)B(w) \theta(|z| - |w|) + B(w)A(z) \theta(|w| - |z|)$$

where $\theta$ is the heaviside step function in $\mathbb R$.

As an integrand, we show that the above has a neat interpretation in 2D CFT.

We first note the general identity:

$$ \oint_{|z| > |w|}dz - \oint_{|z| < |w|}dz  = \oint_{C(w)}dz$$

where $C(w)$ is a loop around $w$, $|z| > |w|$ is any curve for which $|z| > |w|$, etc.

Applying this to our radial ordering expression:

$$\oint_{C(w)}dz~ R[A(z) B(w)] \\
= \left(\oint_{|z| > |w|}dz - \oint_{|z| < |w|}dz \right)R[A(z) B(w)]\\
= \oint_{|z| > |w|}dz A(z)B(w) - \oint_{|z| < |w|}dzB(w)A(z) \\
= \oint dz R(A(z)B(w)) - \oint R(B(w)A(z)) \\
= \oint R([A(z), B(w)]) \\
= \oint [A(z), B(w)]  $$

where in the last three lines, the integration is around any curve which encloses an analytic neightborhood of $w$. In the last line we dropped the $R$ to embrace our sloppy but standard notation.


#### Normal ordering

In quantum field theory, *normal ordering* is defined as moving all 'creation' modes of an operator to the right. It is related to time ordering by Wick's theorem:

$$T\{\phi_1\phi_2...\} = N \{ \phi_1\phi_2... +\text{ all Wick contractions} \}$$

In a CFT, we will discover another useful expression for the normal ordered product, but that requires some knowledge of OPEs, to which we now turn.

### A first OPE: momentum tensor
Following Blumenhagen's book, working out the OPE for the product 
$T \phi$ for some primary field $\phi$ is an exercise that is useful for both pedagogical and conceptual reasons. Pedagogically, this serves as a good first exposure to OPEs and radial ordering. Conceptually, the resulting OPE allows us to connect the tensorial definition of primary fields to the representation theoretic definition given in the previous section.

Once again, we remind the reader that all operator expressions below are to be seen as VEVs of time ordered products.

Let's fix a time $x^0$. Recall Noether's theorem tells us that the charge associated with a symmetry of the field theory (CTs in our case) is the integral of 0-th component of current over space, in 2 dimensions this reads:

$$Q = \int j^0 dx^1 $$

In a quantum theory, the charge is promoted to an operator, and we have the property under conformal transformation, any (bounded) Hilbert space operator $O$ transforms as:

$$ \delta O = [ Q, O]$$ 

Recalling
$$j_\mu = T_{\mu\nu} K^\nu$$ 

TODO: finish writing this

The result is:

$$T(z) \phi(w, \bar w) = \frac h {(z - w)^2}\phi(\omega, \bar \omega) + \frac 1 {(z - w)} \partial_\omega \phi(\omega, \bar \omega) + \text{non-singular terms}$$

Similarly for anti-holomorphic component of $T$. 

This is called an operator-product expansion. Aside from the self-explanatory name, we note the singular terms on the RHS are multiplied by the operators $\phi$ and its derivatives. This is always the case for OPEs.

This OPE can be taken as yet another alternative definition of a primary field. 


### State-operator Isomorphism

Going back to identifying the Virasoro algebra generators with Laurent modes of momentum tensor, for $n = 0$, we have: 

$$L_0 = \frac 1 {2 \pi i} \oint dz [zT(z)]$$

We can now use the OPE we just obtained to compute the quantity
$ [L_0, \phi(w, \bar w)]$. We $ [L_0, \phi(w, \bar w)]$.

We find that taking the following limit yields a rather nice result:

$$[L_0, \phi(0)] = h \phi(0)$$

where $$ \phi(0)\equiv\lim_{w, \bar w \mapsto 0} \phi( w, \bar w)$$

Similarly:
$$[\bar L_0, \phi(0)] = \bar h \phi(0)$$

Combined together this yields:

$$[D, \phi(0)] = (h + \bar h) \phi(0)$$

Acting on the vacuum state, this reads

$$D| \phi\rangle = (h + \bar h) | \phi \rangle$$

where $| \phi\rangle\equiv \phi(0) |0 \rangle$. For this reason, $\triangle \equiv h + \bar h$ is called the **conformal weight** of $\phi$. 

Replacing $D$ with $L \sim L_0 - \bar L_0$ in the above analysis, we find that $ h - \bar h$ are the angular momentum eigenvalues of $|\phi\rangle$, for this reason $l \equiv h - \bar h$ is called the **conformal spin** of $\phi$. 

To summarize, we just showed:

- A primary field of conformal dimensions $(h , \bar h)$ evaluated at the origin acting on the vacuum generates an eigenstate of $D$ with weight $\triangle$ and spin $l$.
- Conversely every eigenstate of $D$,  $|\triangle, s\rangle$, can be generated by some by a primary operator with weight $(\triangle + l, \triangle - l)$

This is called the **operator-state-correspondence**. One can say that it's an isomorphism if we identify all primary fields with the same conformal dimensions - which is. To obtain the rest of the states in the field theory, one would act on these primary states with the virasoro 'creation operators' to obtain descendent states, i.e. $L_n$ for $n < 0$.

Because this is important let's state it again: 

> **Operator-state correspondence**: Every state in a CFT can be obtained by a linear combination of primary and descendent operators  acting on an arbitrarily small neighborhood of the origin.

We state that this holds for higher dimensions as well.

### The general OPE

An immediate consequence of the State-Operator correspondence is the existence of the general OPE. Consider a product of any 2 operators:

$$A(x)B(y) = A(x-y)B(0) \equiv A(q) B(0)$$

where in 2D we would have something like $x = (z, \bar z)$, and where we've used translation invariance. The state-operator correspondence tells us that we can write:

$$A(q)B(0) = \sum_{O \in \text{primaries}} C_O(q, \partial) O(0)$$

this equation is to be read as: LHS acting on the vacuum would create some field theory state, which by the correspondance can be written as a linear combination of primaries and their descendents, i.e. the RHS.

This is what some would call a 'proof' of the existence of a general OPE between any two operators in the field theory. 

### Primary operators: a summary

Throughout these notes we defined primary operators by the following ways

- As an object whose pullback looks like that of a component of a $(h, \bar h)$ tensor
- As an object which transforms in a particular way under conformal transformations
- As a field which has a particular OPE with the momentum tensor
- As an operator which creates a highest-weight state with regards to the Virasoro algebra.

We already showed that the first three are equivalent. To see that the last definition is also equivalent,  by a similar computation as how we obtained the state-operator correspondance, one can show

$$L_n | \phi \rangle = 0 ~~\forall n > 0$$

### Two & three point functions, general correlators

In 2D, by conformal invariance, one can map any function of 2 or 3 variables to anywhere on the Riemann sphere. 2 & 3 point functions are in fact completely fixed up to scaling factors. These are found in literature.[^Klaput] 

[^Klaput]: for example see Theorem 3.25 in this nice [thesis](http://einrichtungen.ph.tum.de/T30e/research/theses/KlaputDiplomarbeit.pdf) by Klaput, which also happen to be a very well-done review for everything in this note. 

What about 4 and 5 point functions? One can simply decompose these into pairs, with a possible triplet, then evaluate the pairs using the operator product expansion. This leads to what's called the conformal partial wave expansion. It should be clear that any way of dividing these into pairs leads to the same result, this is called OPE associativity, crossing symmetry, bootstrap equation.

The coefficients in the 2 & 3 point functions (or equivalently the combination of them that appear in the partial wave expansion) are known as CFT data. A field theory is completely specified when all the correlators are fixed, in a CFT all correlators are fixed by these coefficients.  



# Appendix A: Hilbert space foliations, lattices & local operators

To clearly understand the notions of local operators, vertex operators,  foliation of Hilbert space & radial quantization, it is beneficial to think of spacetime as a union of spatial lattices.

## The "canonical" picture

Consider the statement:

$$O_x \text{ is a local operator acting at } x$$

In the "canonical" (e.g. Peskin & Schroeder) picture of QFT Hilbert space, this means $O$ is an operator-valued distribution over our spacetime $M$, that is sharply peaked at $x \in M$. 

If one were to write the product of two such local operators $O_xO_y$, one would picture a composition of these sharp operator-valued distributions. We suggest that the lattice interpretation of this, as described below, is much cleaner.



## Hilbert space foliation from spacetime foliation

In the lattice decomposition of Hilbert space, one associates a Hilbert space to each point in space:

$$x \mapsto H_x$$


Let $B \times \mathbb{R} \equiv \{B_t | t \in \mathbb{R}\}$ be a foliation of $M$. For each leaf $B_t$ in the foliation, we can define a subspace of $H$ associated with $B_t$:

$$\tilde H_{t} \equiv \otimes^{x \in B_t} H_x$$

Our full Hilbert space is given by:

$$ H = \cup^{t \in R} \tilde H_t \sim \mathbb{R} \times \tilde H_0 $$

where we've assumed the Hilbert space leaves are isomorphic (given that we started with a foliation of $M$ where all leaves are isomorphic, this assumption is mild). We demand there exists unitary operators which map between these leaves in Hilbert space:
$$U(s) : \tilde H_t \to \tilde H_{t + s}$$

One then has the picture where computing a correlator is the same thing taking a ground state at the $t = -\infty$ leaf, map it to the $t = \infty$ leaf by $U$, then take a inner product with the ground state there.

## Hilbert space is foliation independent
It makes an interesting and non-trivial exercise to show that this Hilbert space is in fact independent of your choice of foliation. Here we provide a hint.

One might observe that two points $x$ and $y$ on the same leaf in one foliation may lie in different leaves given a different foliation. One can then consider an entangled state between the Hilbert spaces at each of these points, which naively would live on  $H_x \otimes H_y$, and observe that this space is only a subspace of our total Hilbert space if the foliation is chosen such that $x$ and $y$ lie on the same leaf. The trick out of this dilemma is to realize that such a state can be represented in a foliation where $x$ and $y$ lie on different leaves by mapping the degrees of freedom onto the same leaf through the unitary map. These are the kind of tricks needed to show that total Hilbert spaces constructed from different foliations are in fact isomorphic.

## Local operators in the lattice decomposition

In this picture, the statement:

$$O_x \text{ is a local operator acting at } x$$

can be simply stated as

$$O_x \text{ is a linear operator on the subspace } H_x$$

And the product of two such operators

$$O_xO_y$$

is to be seen as the operator:

$$(O_x \otimes I ) \dot{}(I \otimes O_y) $$

acting on the subspace $H_x \otimes H_y$. At least to the me this formalism is much cleaner and more visual.


The vacuum state of the QFT Hilbert space, on each time slice, is given in the lattice picture by:

$$|0\rangle \equiv \otimes^{x \in B_t}|0\rangle_x$$

where $|0\rangle_x$ is the state annihilated by the annihilation  operator $a(x)$, an operator on $H_x$.

## Foliation of CFT Hilbert space

Somewhere in these notes we presented the cylinder and annulus coordinates for the manifold $M = S^1 \times \mathbb{R}$. There we mentioned that our physical theory, as a collection of mathematical objects, should be viewed as a field theory defined over $M$, in a coordinate-independent manner. We are free to switch between different physical interpretations by switching coordinates.

Let's consider structure of our QFT Hilbert space following our the discussion on foliation above.  In the cylinder coordinates, one would construct a sequence of hilbert spaces using with time slices and unitary evolution generated by the Hamiltonian. But after we've constructed this Hilbert space using restrictions from our physical interpretation, we are free to look at the field theory we defined in a coordinate-independent way. Switching to radial coordinates, we see that we have foliated our Hilbert space into radial slices related by transformations generated by (representations of) integral curves of the dilation operator. Although we mentioned that Hilbert space should be foliation independent (up to an isomorphism), in practice field theorists tend to pick a foliation and stick with it. This is the one we pick.



# Appendix B: AdS/CFT as an operator-to-operator map
## The operator statement of the duality 

The conjecture reads, in global coordinates in AdS, at some fixed time slice, $(r, x)$, let $\Phi(r, x)$ be some field in some field theory in the bulk, one can take the limit:

$$O(x) \equiv \lim_{r \mapsto \infty }r^\triangle\phi(r, x)$$

The conjecture is that this defines an operator on the CFT. 

## Bulk interactions & Witten diagrams

One can then compute correlators like:

$$\langle O_1(x_1) O_2(x_2) ...\rangle$$

On the bulk side, this is a usual correlator that can be perturbatively computed with Feynman diagrams and taking the limit where the inserted fields go to the boundary (in practice one would derive bulk-to-boundary propagators and bulk-to-bulk propagators, then use them to write the correct contributions from Feynman graphs). Feynman diagrams with incoming and outgoing fields living on the boundary of AdS are known as Witten diagrams.

On the CFT side, we know these correlator have a conformal partial wave expansion. In particular, the 2 and 3 point functions are completely fixed up to overall coefficients. Different types of interactions in the bulk would therefore manifest as shifts in the values of these coefficients. 

# Appendix C: CFTs according to a friend

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