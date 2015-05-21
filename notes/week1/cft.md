
# Notes on CFTs

[toc]

## The Big Picture

### Why CFTs

#### Role of CFTs in string theory 
For a not-very-straightfoward answer, see [this mathoverflow question](http://mathoverflow.net/questions/77635/what-exactly-is-the-relation-between-string-theory-and-conformal-field-theory)


#### Why we like CFTs, aside from string theory 

The most attractive general aspect  of CFTs is perhaps:

- CFTs are Interacting, yet exactly solvable field theories

There's a nice remark from Kaplan's AdS/CFT notes that I think is worth quoting:

- UV complete theories are conformal
 $\implies$ "Well defined QFTs are either CFTs or RG flow between CFTs"
$\implies$  "Studying space of CFTs is like studying space of well-defined QFTs"

Some other well-known motivations

- AdS/CFT, obviously
- 2D critical phenomena

We will make a few remarks on the correspondence when appropriate in these notes. We will not discuss condensed matter. 

### The structure of these notes

We follow a now-typical sequence for introducing CFTs

1. **The "C" in CFT**: Introduce conformal group and its action on (pseudo-)  Riemannian manifolds in general. 
2. **The "FT" in CFT**:  Introduce conformally invariant field theories. 
3. **CFTs in real life**:  Go through canonical examples of CFTs

    Since these notes are a part of a course following Polchinski's book, in light of the fact that we don't exactly follow Polchinski's (rather confusing) CFT chapter, we will conclude these notes with:

4. **CFTs according to a friend**: Summarize how Polchinski derives the same results that we derive here as well as picking out terminology mismatches that we may have introduced.


## The "C" in CFT

### Roadmap

We will first define the conformal group. Then We want to write down the conformal group and algebra explicitly - we do this as follows:

- Since conformal condition is defined at each point, we must start with finding killing vectors generating local transformations on each tangent space. These are local symmetries important in their own right.
- From these, find globally defined conformal generators, these form the (global) conformal algebra, i.e. it's a algebra corresponding to a globally defined lie group.
- Exponentiate conformal algebra to find the corresponding lie group. (In physics terms: Use infinitesmall transformations to construct finite transformations)

### Global definition 

#### As a diff preserving metric everywhere.

#### Lie group structure
- Mention this: in 2D, every metric is conformally flat. This chart is called "conformal gauge"


### Conformal killing vectors

#### Recall what is a killing vector field

#### Conformal Killing equation

#### Classifying CKVs
- Classify generators: translation, rotation + dilation, special
- Draw pictures


### Explicit CKV for d != 2

#### d = 1

#### d > 2
- Mention: Conformal group = AdS diffeomorphism group


### Explicit CKV for d = 2

#### The setting:  coordinates, maps, Riemann sphere
- isothermal coordinates
- in 2D conformal $\iff$ holomorphic => Use Riemann sphere
- Holomorphic & anti-holomorphic
- Mobius transforms

#### The Witt Algebra
- As Laurent Expansion.
- Visualization as reparametrization on a cricle, [ see lubos](http://physics.stackexchange.com/questions/12022/geometric-visual-interpretation-of-virasoro-algebra)

#### Global Conformal Group & algebra in d=2 (its finite!)
- poles of laurent modes


### Virasoro Algebra

#### Central extensions in general
- Group extensions in general: what does it mean to extend a group. 
- What is a central extension in terms of adding a term to the commutator.
- quantization => central extend operator algebra. e.g. QM

#### Virasoro is Central extension of Witt
- using Jacobi identities that the Witt algebra satisfies, we see that the Virasoro algbera is completely fixed up to a central charge, to be fixed by your specific theory.

## The "FT" in CFT

### Roadmap

### What is a CFT

#### Defining  a field theory
#### Defining a CFT
#### CFT Data
