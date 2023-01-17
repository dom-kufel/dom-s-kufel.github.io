---
layout: post
title: Quick intro to the 2D toric code
description: >
  A real quick introduction to the 2D toric code.
sitemap: false
---

<!-- image: /assets/img/blog/example-content-ii.jpg -->

*
{:toc .large-only}


*[plaquettes]: Fancy term for each of the little squares in the lattice.
*[braiding]: Loosely speaking "moving particles around each other"
[^1]: If it does not immediately become clear why see [this](https://commons.wikimedia.org/wiki/File:Torus_from_rectangle.gif) animation.
[^2]: Note that some people (see e.g., <a href="#references">*[Zeng et al. (2015)]*</a> define $$A_v$$ operators as products of Pauli $$Z$$ operators; and $$B_p$$ operators as products of Pauli $$X$$ - this is just the matter of convention and does not change the physics in any essential way (since it corresponds to simply swapping $$X$$'s with $$Z$$'s i.e. a change of basis by conjugating all qubits with the Hadamard gate).
[^3]: Terminology comment: Hamiltonian containing of Pauli strings which are mutually commuting (as above) is often called stabilizer Hamiltonian - language coming from error correction - more on this later
[^4]: I.e. the eigenbasis of the Pauli $$Z$$ operator.
[^5]: One way of showing this is to show that the "twist factor" in a topological quantum theory <a href="#references">[Simon (2020) Chp. 26.2]</a> is +1 (moving $$e$$ (or $$m$$) particle involves only applying $$X$$ (or $$Z$$) operators which all commute with each other).
[^6]: Or in our case more of a 1D spatial projection of the 2D trajectory of the particle defined on a 2D toric code!
[^7]: In case this explanation was unclear or too quick: see e.g., <a href="#references">[Simon (2020) Chp. 2 and Chp. 26.2]</a>.
[^8]: Just to recap: ground state at this stage just being a generic linear combination of closed loop configurations as described before.
[^9]: If this is not surprising I would encourage you to study symmetry-breaking paradigm due to Landau. The point of the topological order is precisely to 'disavow Landau' as [John Preskill would say](http://theory.caltech.edu/~preskill/colloquium/Balents.htm).
[^10]: If it is not immediately clear think about associating to each point in the primal and dual lattice the eigenvalue of the corresponding vertex/plaquette operator. The ground state would simply correspond to all $$+1$$ eigenvalues. Consequently regardless where we create excitations to it - they will correspond to $$-1$$ eigenvalue particle-like "peaks" in otherwise uniform energy density background.    
[^11]: We will discuss what happens if we consider topologically inequivalent loops in the next <a href="#long-range-entanglement">section</a>.  
[^12]: There is a quite deep reason behind this, which we will explore more in the other blogpost. !!!
[^13]: This observation allows us to prove the 4-fold ground state degeneracy in an alternative way to the one described in the <a href="#hamiltonian-and-ground-states">first section</a>. The main idea is as follows: eigenvalues of each of the vertex/plaquette operators can be $+1$ or $-1$ (they are formed of Pauli operators which are both unitary and Hermitian); this means that there are $$2^N$$ possible states. The conditions $$\prod_{\textrm{all} \ \ v} A_v = \mathbb{1} \ \ \ \prod_{\textrm{all} \ \ p} B_p = \mathbb{1}$$ however imply that two of these operators will not be independent: effectively we have $$2^{N-2}$$ independent quantum numbers. This means that the ground state degeneracy will be $$2^N/2^{N-2}=4$$.  
[^14]: Main idea is as follows: loosely speaking, for quantum error correction, the longer the error string the larger chance that it corresponds to uncorrectable error. As described <a href="#quasiparticle-excitations">before</a>, energy cost paid for the pair of excitations of any length is the same; for self-correcting memory (for storing quantum information) we want to retain non-locality of information encoding but yet penalize for longer excitation strings. It turns out that due to their dimensionality, 3D and 4D toric code energetically penalize long excitations one and two types of Pauli errors respectively.

## Hamiltonian and Ground States

In the simplest realization, toric code is a model of qubits (two-level systems) placed on the links of the 2D square lattice with periodic boundary conditions (thus making a torus[^1]). We define the <a id="eq:H_TC">Hamiltonian</a> for the system to be
\begin{equation}
H = -\sum_v A_v - \sum_p B_p
\end{equation}
where $$B_p= \prod_j Z_j$$ acts on plaquettes and $$A_v = \prod_j X_j$$ acts on each of the vertices[^1]. For later we will also define a dual lattice as the one shifted by $$[1/2,1/2]$$ vector from the “primal” one - see Fig. 1.  

![Full-width image](/assets/img/blog/toric_code_primal_dual.png){:.lead width="600" height="100"}
Fig. 1: "Primal" and dual lattices of the toric code.
{:.figure}

Our goal for now is to **find ground state(s)** of the above model. I claim that each of the four ground states found consists of the **equal amplitude superposition of the closed loop configurations**, and that the ground states differ by which out of four topologically inequivalent loops on torus they contain. We will argue for this claim real quick. First, note that all the terms within the Hamiltonian mutually commute with one another i.e. $$[A_v, B_p]=0 \ \ \forall v,p$$ - you will prove it in the exercise below[^2]. This remarkably simplifies the problem by allowing to consider the two sums separately, and our strategy becomes: first (i) minimize the energy of one of the sums in <a href="#eq:H_TC">Eq. 1</a> and then (ii) impose the other sum as the constraint on the choice of the ground state.

**Exercise:** Show that for the operators defined above $$[A_v, B_p]=0 \ \ \forall v,p$$. <a href="#hint1">Hint</a>
{:.message}

To realize (i), for convenience, let’s work in the computational[^3] basis and pick the sum over $$B_p$$ operators.
Undoubtedly all $$ \vert 0 \rangle$$ is one of the states which will be both an eigenstate (we are in Pauli Z basis) and minimize the $$- \sum_p B_p$$ term. But by far it is not the unique state: any state where qubits in $$\vert 1 \rangle$$ state make closed loops on a dual lattice (see Fig. 2) would work equally well. Eigenstate minimizing the energy of the $$- \sum_p B_p$$ term is simply a linear combination (with arbitrary coefficients) of configurations where qubits in $$\vert 1 \rangle$$ form closed loops on a dual lattice.

**Exercise:** Convince yourself (in drawing) that this is true.
{:.message}

But don’t forget: we still need to resolve (ii) i.e. impose the constraint of the $$-\sum_v A_v$$ term. Consider the action of $$A_v$$ operator on a vertex: it will simply flip the states of the qubits adjacent to that vertex. If we start from a particular closed loop configuration, the action of $$A_v$$ will change it to some other *topologically equivalent* closed loop configuration. We can thus think of the process of applying $$A_v$$’s as simply that of “reconnecting” the closed loops within the same topological equivalence class. Now we demand from a ground state[^4] $$ \vert \psi \rangle$$ to fulfill $$A_s \vert \psi \rangle  = +1 \vert \psi \rangle \forall s$$ i.e. loosely speaking after any reconnection of the closed loop configurations, state should remain invariant. This is only possible if we restrict an arbitrary superposition state $$ \vert \psi \rangle$$ found before, to the one of the four ground states consisting of an equal amplitude superposition of all topologically equivalent closed loop configurations (See Fig. 3)

Nice! Summarizing the first key result:

**Fact 1:** Ground states formed from the equal superpositions of topologically equivalent loops on torus.
{:.note}

<!-- {:.lead width="100" height="100"} -->
{:style="text-align:center";}
![placeholder](/assets/img/blog/torus.png){: width="300"; height="650"}
![placeholder](/assets/img/blog/torus.png){: width="300"; height="650"}

<!-- Fig. 2: Four topologically inequivalent loops on torus. Lorem Ipsum dolert adshashdashhdas hdashdash hdaskj a adskhbdas $$C_4$$ corresponds to the trivial loop.
{:.figcaption} -->

<!-- Fig. 2: Four topologically inequivalent loops on torus. Lorem Ipsum dolert adshashdashhdas hdashdash hdaskj a adskhbdas $$C_4$$ corresponds to the trivial loop.
{:.figure} -->

![placeholder](/assets/img/blog/toric_code_loop_example.png){style="display:block; margin-left:auto; margin-right:auto"; width="400"; height="350"}
Fig. 3: Example lnaskjdbksa adskbkdasjb kjadsbkdasb kjbadskbsad kjbdaskjbasd ljnasdkjbads kjbakjbsadkjm
{:.figure}

![Full-width image](/assets/img/blog/toric_code_loopy_gs.png){:.centered}
Fig. 4:
{:.figure}


## Excitations

Having found the ground state, natural question is the following: what are the excited states of the model? A brief look at <a href="#eq:H_TC">Eq. 1</a> suggests that the excitations should simply correspond to $$-1$$ eigenvalues of $$A_v$$ or $$B_p$$ operators which might be thought to live on the vertices of the primal or dual lattice (see Fig !!!). These excitations (often called **anyons**) are "particle-like" (thus often called quasiparticles) i.e. they correspond to the localized energy excitation on a toric code ground state with a uniform energy density profile[^6] <a href="#references">[Zeng et al. (2015) p. 180]</a>.

![Full-width image](/assets/img/blog/excitations.png){:.centered}
Fig. 4:
{:.figure}

We can create a *pair* of quasiparticles excitations by applying string operators. String operators consist of product of Pauli $$X$$ or $$Z$$ Pauli Z operators applied to the qubits (see Fig. !!!). A curious fact[^8] is that the total energy cost for the excitations created is dependent only on the number of excitations and not on a particular type of a string operator used e.g., both applying a single Pauli $$X$$ operator costs the same amount of energy as applying a *topologically trivial*[^7] string of Pauli $$X$$ operators.  

**Fact 2:** Excitations in the toric code (anyons) might be created in pairs by applying Pauli strings.
{:.note}

### Single excitations

So far we have discussed how to create a pair of excitations. Is it possible to create a single, isolated, excitation by applying Pauli strings? Short answer: no. To see this, we first make the following <a id="eq:observation">observation</a>
\begin{equation}
\prod_{\textrm{all} \ \ v} A_v = \mathbb{1} \ \ \ \prod_{\textrm{all} \ \ p} B_p = \mathbb{1}
\end{equation}
for the toric code defined on periodic boundary conditions (on torus) - as described in the previous sections[^9].

**Exercise:** Convince yourself (in drawing) that this observation is true.
{:.message}

Equipped with the observation above it is easy to show why creation of single (or more generally any odd number of) excitations is impossible: this would violate the condition in the above <a href="eq:observation">equation</a> which holds throughout.

### Loop excitations and error correction

Okay, so summarizing what we have arrived at so far: we cannot create single excitations by applying Pauli strings but we can easily create pairs of excitations. Given the "loopy" nature of the ground state we discovered in the <a href="#hamiltonian-and-ground-states">first section</a> we naturally ask: does anything interesting happen if the excitations form closed loops? Absolutely: it turns out that creating a *topologically trivial* closed loop of excitations is equivalent to creating no excitations at all. This is a really curious fact, so let me state it again in a different way: starting from a ground state we can create a set of excitations, pair them up (thus creating closed excitations loops) and get the ground state again! The physical intuition behind it is simple: since the ground states correspond to equal amplitude sum of closed loop configurations, the action of the closed loop string simply reorders the terms within the sum without changing the overall result! This "completing the loop" trick is one of the reasons why toric code is useful for the [quantum error correction](https://www.arthurpesah.me): if we say that the excitations were created by some unwanted "errors" in the form of Pauli strings then these errors might be annihilated by applying more Pauli strings and completing the loops.

**Fact 3:** Applying Pauli strings forming closed loops is equivalent to applying no string operators at all.
{:.note}

### Anyons and their statistics

If excitations are indeed "particle-like" and they are indistinguishable, can we classify them in a similar fashion to elementary particles (being either bosons or fermions)? Yes, we say that there are three types of anyons in the toric code: $$e$$ anyon (single vertex excitation), $$m$$ anyon (single plaquette excitation) and $$\epsilon$$ anyon (or a dyon) consisting of vertex and plaquette excitations bound together. $$e$$ and $$m$$ anyons in the toric code have abelian bosonic statistics i.e. the many-body state is invariant under exchanging two identical $$e$$ and $$m$$ anyons[^5].

It turns out that $$\epsilon$$ anyons are fermions. To see this we need to first show that braiding the $$e$$ particle around $$m$$ particle (and vice-versa) accumulates $$-1$$ phase. This is clear from the following

![Full-width image](/assets/img/blog/statistics.png){:.centered}
Fig. 4:
{:.figure}

Now I claim that the proof of fermionic statistics of $$\epsilon$$ particle follows from the figure below <a href="#references">[Kitaev&Laumann (2010) p. 15]</a>:

![Full-width image](/assets/img/blog/braiding.png){:.centered}
Fig. 4:
{:.figure}

{:.text-align-center}
![placeholder](https://via.placeholder.com/100x150)
![placeholder](https://via.placeholder.com/100x150)

{:style="text-align:center;"}
![placeholder](https://via.placeholder.com/100x150)
![placeholder](https://via.placeholder.com/100x150)


WoW, initially it might seem that there is a lot to unpack here, but in fact everything is plain and simple. Lines in Fig. !!! correspond to the $$(2+1)-D$$ worldlines of the anyons. Wordlines are nothing else than space-time graph[^6] of the particle motion with time going up on the image and particles moving around each other in space (horizontal direction). We utilize identities found before (bottom row) to simplify each of the crossings in the top row: picking up a $$-1$$ factor for braiding $$e$$ around $$m$$ translates into the fermionic statistics of $$\epsilon$$ particle![^7]  

**Fact 4:** Three types of (anyonic) excitations correspond to vertex, plaquette and "dyonic" violations and these have bosonic, bosonic and fermionic exchange statistics respectively.  
{:.note}


<!-- What changes if we introduce open boundary conditions? -->

## Local indistinguishability

In the previous section I stressed few times that the excitation loops considered are the ones which are *topologically trivial*. What if we considered e.g., Pauli $$X$$ strings which were making topologically *non-trivial* loops (e.g., ones corresponding to $$C_1, C_2 \textrm{or} C_3$$ in Fig. !!!)? Note that such *non-trivial* loops are automatically *non-local* since they need to transverse through the whole system.

Let us take a ground state of the toric code, say the one consisting of topologically trivial loops. What happens if we now apply to it a topologically non-trivial Pauli string loop, say $$C_2$$? Linearity allows us to apply the topologically non-trivial string to each of the components in the closed-loop superposition: therefore now all of the terms within the superposition belong to the $$C_2$$ equivalence class and the resulting state is thus another ground state $\vert \psi_2 \rangle (as shown in Fig. !!!). Applying the same argument to the other ground states we immediately notice the following

**Fact 5:** Ground states are **locally indistinguishable** i.e. may be mapped onto each other only by using non-local operators.
{:.note}

We might restate the above result in the following way: if operator $$M$$ is local (i.e. does not involve operators going through the whole system) then we have $$\langle \psi_i \vert M \vert \psi_j \rangle = C_M \delta_{ij}$$ where $$C_M$$ is a constant only dependent on $$M$$.

Interestingly, local indistinguishability is one of the key components for system to possess **topological order** i.e. loosely speaking to exhibit topology-dependent ground state degeneracy without breaking any underlying symmetry[^5] which cannot be removed by any local, sufficiently weak perturbation of the Hamiltonian <a href="#references">[Zeng et al. (2015) p. 166]</a>. In the case of the toric code we indeed see the 4-fold ground state degeneracy which purely depends on the topology of the space and using local indistinguishability it might be shown that its ground state degeneracy cannot be lifted by any local, sufficiently weak perturbations <a href="#references">[Bravyi et al. (2010)]</a>.

## Conclusions

I hope I convinced you that the toric code is a fascinating model.

<!-- Typically discussed in the thermodynamic limit? -->

<!-- Where to discuss anyons? -->

## FAQ
1. Can toric code be defined only on a square lattice? No, in principle we can define toric code on any lattice. See e.g., <a href="#references">[Simon (2020) Chp. 25.5]</a>.
2. Can toric code be defined in the systems beyond 2D? Yes, in particular a 4D toric code is model particularly interesting from the perspective of error correction since it might act as a self-correcting quantum memory[^10].
3. Can toric code be defined for system other than qubits? Yes, for $N$ level system we have $$Z_N$$ toric code generalization; which we can further extend to more general groups in so-called a Kitaev double model (possibly possessing non-Abelian anyons)!

<!--
### Header 3


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
``` -->
## References
<a id="wenchenbook">*[Zeng et al. (2015)]*</a> Zeng, B., Chen, X., Zhou, D.L. and Wen, X.G., 2015. Quantum Information Meets Quantum Matter--From Quantum Entanglement to Topological Phase in Many-Body Systems. [*arXiv preprint arXiv:1508.02595*](https://arxiv.org/abs/1508.02595).

<a id="simonbook">*[Simon (2020)]*</a> Simon, S.H., 2020. Topological Quantum: Lecture Notes and Proto-Book. Unpublished prototype. [*Online*](http://www-thphys.physics.ox.ac.uk/people/SteveSimon).

<a id="leshouchestopo">*[Kitaev&Laumann (2010)]*</a> Kitaev, A. and Laumann, C., 2010. Topological phases and quantum computation. Exact methods in low-dimensional statistical physics and quantum computing, Lecture Notes of the Les Houches Summer School, (89), pp.101-125. [*arXiv preprint arXiv:0904.2771*](https://arxiv.org/abs/0904.2771).

<a id="stabilitytopo">*[Bravyi et al. (2010)]*</a>  Bravyi, S., Hastings, M.B. and Michalakis, S., 2010. Topological quantum order: stability under local perturbations. *Journal of mathematical physics, 51(9), p.093512* [*arXiv preprint version*](https://arxiv.org/abs/1001.0344).

## Hints to exercises
<a id="hint1">**Hint:**</a> Whenever Pauli X and Z meet on the same site they anti-commute, otherwise (e.g., $$[X \otimes \mathbb{1},\mathbb{1} \otimes Z]$$ they commute.
