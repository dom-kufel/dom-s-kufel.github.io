---
layout: post
title: Quick intro to the 2D toric code
description: >
  A simple, quick introduction to the 2D toric code.
sitemap: false
---

<!-- image: /assets/img/blog/example-content-ii.jpg -->

*
{:toc .large-only}


*[plaquettes]: Fancy term for each of the little squares in the lattice.
[^1]: Note that some people (see e.g., <a href="#references">*[Zeng et al. (2015)]*</a> define $$A_v$$ operators as products of Pauli $$Z$$ operators; and $$B_p$$ operators as products of Pauli $$X$$ - this is just the matter of convention and does not change the physics in any essential way (since it corresponds to simply swapping $$X$$'s with $$Z$$'s i.e. a change of basis by conjugating all qubits with the Hadamard gate).
[^2]: Terminology comment: Hamiltonian containing of Pauli strings which are mutually commuting (as above) is often called stabilizer Hamiltonian - language coming from error correction - more on this later
[^3]: I.e. the eigenbasis of the Pauli $$Z$$ operator.
[^4]: Just to recap: ground state at this stage just being a generic linear combination of closed loop configurations as described before.
[^5]: If this is not surprising I would encourage you to study symmetry-breaking paradigm due to Landau. Topological order allows us to 'disavow Landau' as [John Preskill says](http://theory.caltech.edu/~preskill/colloquium/Balents.htm).
[^6]: If it is not immediately clear think about associating to each point in the primal and dual lattice the eigenvalue of the corresponding vertex/plaquette operator. The ground state would simply correspond to all $$+1$$ eigenvalues. Consequently regardless where we create excitations to it - they will correspond to $$-1$$ eigenvalue particle-like "peaks" in otherwise uniform energy density background.    

## Hamiltonian and ground states

In the simplest realization, toric code is a model of qubits (two-level systems) placed on the links of the 2D square lattice with periodic boundary conditions (thus making a torus). We define the <a id="eq:H_TC">Hamiltonian</a> for the system to be
\begin{equation}
H = -\sum_v A_v - \sum_p B_p
\end{equation}
where $$B_p= \prod_j Z_j$$ acts on plaquettes and $$A_v = \prod_j X_j$$ acts on each of the vertices[^1]. For later we will also define a dual lattice as the one shifted by $$[1/2,1/2]$$ vector from the “primal” one - see Fig. !!!!b.  

Our goal for now is to **find ground state(s)** of the above model. I claim that each of the four ground states found consists of the **equal amplitude superposition of the closed loop configurations**, and that the ground states differ by which out of four topologically inequivalent loops on torus they contain. We will argue for this claim real quick. First, note that all the terms within the Hamiltonian mutually commute with one another i.e. $$[A_v, B_p]=0 \ \ \forall v,p$$ - you will prove it in the exercise below[^2]. This remarkably simplifies the problem by allowing to consider the two sums separately, and our strategy becomes: first (i) minimize the energy of one of the sums in <a href="#eq:H_TC">Eq. 1</a> and then (ii) impose the other sum as the constraint on the choice of the ground state.

**Exercise:** Show that for the operators defined above $$[A_v, B_p]=0 \ \ \forall v,p$$. <a href="#hint1">Hint</a>
{:.message}

To realize (i), for convenience, let’s work in the computational[^3] basis and pick the sum over $$B_p$$ operators.
Undoubtedly all $$ \vert 0 \rangle$$ is one of the states which will be both an eigenstate (we are in Pauli Z basis) and minimize the $$- \sum_p B_p$$ term. But by far it is not the unique state: any state where qubits in $$\vert 1 \rangle$$ state make closed loops on a dual lattice (see Fig.!!!) would work equally well. Eigenstate minimizing the energy of the $$- \sum_p B_p$$ term is simply a linear combination (with arbitrary coefficients) of configurations where qubits in $$\vert 1 \rangle$$ form closed loops on a dual lattice.

**Exercise:** Convince yourself (in drawing) that this is true.
{:.message}

But don’t forget: we still need to resolve (ii) i.e. impose the constraint of the $$-\sum_v A_v$$ term. Consider the action of $$A_v$$ operator on a vertex: it will simply flip the states of the qubits adjacent to that vertex. If we start from a particular closed loop configuration, the action of $$A_v$$ will change it to some other *topologically equivalent* closed loop configuration. We can thus think of the process of applying $$A_v$$’s as simply that of “reconnecting” the closed loops within the same topological equivalence class. Now we demand from a ground state[^4] $$ \vert \psi \rangle$$ to fulfill $$A_s \vert \psi \rangle  = +1 \vert \psi \rangle \forall s$$ i.e. loosely speaking after any reconnection of the closed loop configurations, state should remain invariant. This is only possible if we restrict an arbitrary superposition state $$ \vert \psi \rangle$$ found before, to the one of the four ground states consisting of an equal amplitude superposition of all topologically equivalent closed loop configurations (See Fig. !!)

Nice! Summarizing the first key result:

**Fact 1:** Ground states formed from the equal superpositions of topologically equivalent loops on torus.
{:.note}

## Quasiparticle Excitations

Having found the ground state, natural question is the following: what are the excited states of the model? A brief look at <a href="#eq:H_TC">Eq. 1</a> suggests that the excitations should simply correspond to $$-1$$ eigenvalues of $$A_v$$ or $$B_p$$ operators which might be thought to live on the vertices of the primal or dual lattice (see Fig !!!). These excitations are "particle-like" (thus often called quasiparticles) i.e. they correspond to the localized energy excitation on a toric code ground state with a uniform energy density profile[^6] <a href="#references">[Zeng et al. (2015) p. 180]</a>.

We can create a *pair* of quasiparticles excitations by applying string operators. String operators consist of product of Pauli $$X$$ or $$Z$$ Pauli Z operators applied to the qubits (see Fig. !!!). A curious fact is that the total energy cost for the excitations created is dependent only on the number of excitations and not on a particular type of a string operator used e.g., both applying a single Pauli $$X$$ operator costs the same amount of energy as applying a (sufficiently short) string of few Pauli $$X$$.  

Is it possible to create a single excitation by applying Pauli strings? To answer this question we first make the following observation: $$\prod_{\textrm{all} v} A_v = \mathbb{1}$$ and $$\prod_{\textrm{all} p} B_p = \mathbb{1}$$ where we imply.  

**Exercise:** Convince yourself (in drawing) that this is true.
{:.message}

What if the excitations form closed loops?


## Local indistinguishability

So far we have focused on topologically trivial excitation strings.

The main idea behind topological order is the existence of a ground state degeneracy without breaking any underlying symmetry[^5]. More formally <a href="#references">[Zeng et al. (2015) p. 166]</a>

System exhibits *topological order* if (a) ground state degeneracy only dependent on the topology of space e.g., $$2^{2g}$$ on a genus $$g$$ Riemann surface (b) ground state degeneracy cannot be removed by any local, sufficiently weak perturbations of the Hamiltonian.
{:.note}

Does the toric code exhibit topological order? First, Hamiltonian has no underlying symmetries and yet ground state has a 4-fold degeneracy which purely depends on the topology of the space (we will discuss why geometry does not matter in the next section). Second, it might be shown that ground state degeneracy is stable to local, sufficiently weak perturbations of the Hamiltonian. TPQO...

## Generalizations of the toric code
*any lattice
*higher dimensional toric cdoe
*Z_N toric
*Kitaev double

### Header 3

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![](https://assets-cdn.github.com/images/icons/emoji/octocat.png)

### Large image

![](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists

Name
: Godzilla

Born
: 1952

Birthplace
: Japan

Color
: Green

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this. Or is it?
```

```
The final element.
```
## References
<a id="wenchenbook">*[Zeng et al. (2015)]*</a> Zeng, B., Chen, X., Zhou, D.L. and Wen, X.G., 2015. Quantum Information Meets Quantum Matter--From Quantum Entanglement to Topological Phase in Many-Body Systems. [*arXiv preprint arXiv:1508.02595*](https://arxiv.org/abs/1508.02595).

## Hints to exercises
<a id="hint1">**Hint:**</a> Whenever Pauli X and Z meet on the same site they anti-commute, otherwise (e.g., $$[X \otimes \mathbb{1},\mathbb{1} \otimes Z]$$ they commute.
