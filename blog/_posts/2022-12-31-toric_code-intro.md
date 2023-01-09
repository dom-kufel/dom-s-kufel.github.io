---
layout: post
title: Toric code intro
description: >
  A page showing how regular markdown content is styled in Hydejack.
image: /assets/img/blog/example-content-ii.jpg
sitemap: false
---

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

There should be whitespace between paragraphs.

Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](another-page).

* toc
{:toc .large-only}


*[plaquettes]: Fancy term for each of the little squares in the lattice.
[^1]: Note that some people (see e.g., <a href="#wenchenbook">*[Zeng et al. (2015)]*</a> define $$A_v$$ operators as products of Pauli $$Z$$ operators; and $$B_p$$ operators as products of Pauli $$X$$ - this is just the matter of convention and does not change the physics in any essential way (since it corresponds to simply swapping $$X$$'s with $$Z$$'s i.e. a change of basis by conjugating all qubits with the Hadamard gate).
[^2]: Terminology comment: Hamiltonian containing of Pauli strings which are mutually commuting (as above) is often called stabilizer Hamiltonian - language coming from error correction - more on this later
[^3]: I.e. the eigenbasis of the Pauli $$Z$$ operator.
[^4]: Just to recap: ground state at this stage just being a generic linear combination of closed loop configurations as described before.

## Toric code basics

In the simplest realization, toric code is a model of qubits (two-level systems) placed on the links of the 2D square lattice with periodic boundary conditions (thus making a torus). We define the <a id="eq:H_TC">Hamiltonian</a> for the system to be
\begin{equation}
H = -\sum_v A_v - \sum_p B_p
\end{equation}
where $$B_p= \prod_j Z_j$$ acts on plaquettes and $$A_v = \prod_j X_j$$ acts on each of the vertices[^1]. For later we will also define a dual lattice as the one shifted by $$[1/2,1/2]$$ vector from the “primal” one - see Fig. !!!!b.  

Our goal for now is to **find ground state(s)** of the above model. I claim that each of the four ground states found consists of the **equal amplitude superposition of the closed loop configurations**, and that the ground states differ by which out of four topologically inequivalent loops on torus they contain. We will argue for this claim real quick. First, note that all the terms within the Hamiltonian mutually commute with one another i.e. $$[A_v, B_p]=0 \ \ \forall v,p$$ - you will prove it in the exercise below[^2]. This remarkably simplifies the problem by allowing to consider the two sums separately, and our strategy becomes: first (i) minimize the energy of one of the sums in <a href="#eq:H_TC">Eq. 1</a> and then (ii) impose the other sum as the constraint on the choice of the ground state.

**Exercise:** Show that for the operators defined above $$[A_v, B_p]=0 \ \ \forall v,p$$. <a href="#hint1">Hint</a>
{:.message}

To realize (i), for convenience, let’s work in the computational[^3] basis and pick the sum over $$B_p$$ operators.
Undoubtedly all $$| 0 >$$ is one of the states which will be both an eigenstate (we are in Pauli Z basis) and minimize the $$- \sum_p B_p$$ term. But by far it is not the unique state: any state where qubits in $$|1>$$ state make closed loops on a dual lattice (see Fig.!!!) would work equally well. Eigenstate minimizing the energy of the $$- \sum_p B_p$$ term is simply a linear combination (with arbitrary coefficients) of configurations where qubits in $$|1>$$ form closed loops on a dual lattice.

**Exercise:** Convince yourself (in drawing) that this is true.
{:.message}

But don’t forget: we still need to resolve (ii) i.e. impose the constraint of the $$-\sum_v A_v$$ term. Consider the action of $$A_v$$ operator on a vertex: it will simply flip the states of the qubits adjacent to that vertex. If we start from a particular closed loop configuration, the action of $A_v$ will change it to some other *topologically equivalent* closed loop configuration. We can thus think of the process of applying $A_v$’s as simply that of “reconnecting” the closed loops within the same topological equivalence class. Now we demand from a ground state[^4] $$ |\psi>$$ to fulfill $$A_s |\psi>  = +1 |\psi> \forall s$$ i.e. loosely speaking after any reconnection of the closed loop configurations, state should remain invariant. This is only possible if we restrict an arbitrary superposition state $$|\psi>$$ found before, to the one of the four ground states consisting of an equal amplitude superposition of all topologically equivalent closed loop configurations (See Fig. !!)

Nice! Summarizing the first key result:

**Fact 1: ** Ground states formed from the equal superpositions of topologically equivalent loops on torus.
{:.note}

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