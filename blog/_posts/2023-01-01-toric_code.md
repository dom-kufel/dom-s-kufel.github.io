---
layout: post
title: Toric code from condensed matter perspective.
description: >
  With a brief intro to toric code, I discuss its connections to topological order, long-range entanglement and quantum spin liquids.
sitemap: false
hide_last_modified: true
---

Working in the field of quantum technologies I often chat to people from a variety of quantum-focused fields.  A weird thing happens if people from traditionally different communities talk about the same stuff. This is how I have first heard about the toric code: both condensed matter and quantum error correction people spoke about it a lot. After I started reading about the toric code, I soon discovered why people talk about it so much: toric code is a paradigmatic example for both topological quantum error correction and topological order in condensed matter. More broadly, toric code, nicely links topology to many-body quantum systems and displays some striking connections between quantum matter and information. Curious!

In this blogpost I would like to approach toric code from a condensed matter angle and discuss its (somewhat confusing) properties such as long-range entanglement (yet $$0$$ correlation length!) and connections to a wider class of so-called quantum spin liquids - models which recently came within reach of the experiments. Stay tuned: I promise there are few cute ideas along the way.

- Table of Contents
{:toc .large-only}

*[weird]: Read: interesting
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

To realize (i), for convenience, let’s work in the computational[^3] basis and pick the sum over B_p operators. Undoubtedly all $$|0 \right>$$ is one of the states which will be both an eigenstate (we are in Pauli Z basis) and minimize the $$- \sum_p B_p$$ term. But by far it is not the unique state: any state where qubits in $$|1 \rangle$$ state make closed loops on a dual lattice (see Fig.!!!) would work equally well. Eigenstate minimizing the energy of the $$- \sum_p B_p$$ term is simply a linear combination (with arbitrary coefficients) of configurations where qubits in $$|1\rangle$$ form closed loops on a dual lattice.

**Exercise:** Convince yourself (in drawing) that this is true.
{:.message}

But don’t forget: we still need to resolve (ii) i.e. impose the constraint of the $$-\sum_v A_v$$ term. Consider the action of $$A_v$$ operator on a vertex: it will simply flip the states of the qubits adjacent to that vertex. If we start from a particular closed loop configuration, the action of $A_v$ will change it to some other closed loop configuration. We can thus think of the process of applying $A_v$’s as simply that of “reconnecting” the closed loops. Now we demand from a ground state[^4] $$|\psi \rangle$$ to fulfill $$A_s |\psi \rangle  = +1 | \psi \rangle \forall s$$: loosely speaking that after any reconnection of the closed loop configurations, state should remain invariant. This is only possible if we restrict an arbitrary superposition found before to ground state $$|\psi\rangle$$ being an equal amplitude superposition of *all* closed loop configurations.

## Inline HTML elements

HTML defines a long list of available inline tags, a complete list of which can be found on the [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/HTML/Element).

- **To bold text**, use `**To bold text**`.
- *To italicize text*, use `*To italicize text*`.
- Abbreviations, like HTML should be defined like this `*[HTML]: HyperText Markup Language`.
- Citations, like <cite>&mdash; Mark otto</cite>, should use `<cite>`.
- ~~Deleted~~ text should use `~~deleted~~` and <ins>inserted</ins> text should use `<ins>`.
- Superscript <sup>text</sup> uses `<sup>` and subscript <sub>text</sub> uses `<sub>`.

Most of these elements are styled by browsers with few modifications on our part.

## Heading 2
Vivamus sagittis lacus vel augue rutrum faucibus dolor auctor. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit. Morbi leo risus, porta ac consectetur ac, vestibulum at eros.

### Heading 3
Vivamus sagittis lacus vel augue rutrum faucibus dolor auctor.

#### Heading 4
Vivamus sagittis lacus vel augue rutrum faucibus dolor auctor.

##### Heading 5
Vivamus sagittis lacus vel augue rutrum faucibus dolor auctor.

###### Heading 6
Vivamus sagittis lacus vel augue rutrum faucibus dolor auctor.

## Code

Cum sociis natoque penatibus et magnis dis `code element` montes, nascetur ridiculus mus.

~~~js
// Example can be run directly in your JavaScript console

// Create a function that takes two arguments and returns the sum of those
// arguments
var adder = new Function("a", "b", "return a + b");

// Call the function
adder(2, 6);
// > 8
~~~

## Lists

Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Aenean lacinia bibendum nulla sed consectetur. Etiam porta sem malesuada magna mollis euismod. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.

* Praesent commodo cursus magna, vel scelerisque nisl consectetur et.
* Donec id elit non mi porta gravida at eget metus.
* Nulla vitae elit libero, a pharetra augue.

Donec ullamcorper nulla non metus auctor fringilla. Nulla vitae elit libero, a pharetra augue.

1. Vestibulum id ligula porta felis euismod semper.
2. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.
3. Maecenas sed diam eget risus varius blandit sit amet non magna.

Cras mattis consectetur purus sit amet fermentum. Sed posuere consectetur est at lobortis.

HyperText Markup Language (HTML)
: The language used to describe and define the content of a Web page

Cascading Style Sheets (CSS)
: Used to describe the appearance of Web content

JavaScript (JS)
: The programming language used to build advanced Web sites and applications

Integer posuere erat a ante venenatis dapibus posuere velit aliquet. Morbi leo risus, porta ac consectetur ac, vestibulum at eros. Nullam quis risus eget urna mollis ornare vel eu leo.

## Images

Quisque consequat sapien eget quam rhoncus, sit amet laoreet diam tempus. Aliquam aliquam metus erat, a pulvinar turpis suscipit at.

![800x400](https://via.placeholder.com/800x400 "Large example image")

![400x200](https://via.placeholder.com/400x200 "Medium example image")

![200x200](https://via.placeholder.com/200x200 "Small example image")

## Tables

Aenean lacinia bibendum nulla sed consectetur. Lorem ipsum dolor sit amet, consectetur adipiscing elit.

| Name     | Upvotes   | Downvotes |
|:---------|:----------|:----------|
| Alice    |        10 |        11 |
| Bob      |         4 |         3 |
| Charlie  |         7 |         9 |
|==========|===========|===========|
|Totals    |        21 |        23 |

Nullam id dolor id nibh ultricies vehicula ut id elit. Sed posuere consectetur est at lobortis. Nullam quis risus eget urna mollis ornare vel eu leo.

*[HTML]: HyperText Markup Language
*[CSS]: Cascading Style Sheets
*[JS]: JavaScript

## References
<a id="wenchenbook">*[Zeng et al. (2015)]*</a> Zeng, B., Chen, X., Zhou, D.L. and Wen, X.G., 2015. Quantum Information Meets Quantum Matter--From Quantum Entanglement to Topological Phase in Many-Body Systems. [*arXiv preprint arXiv:1508.02595*](https://arxiv.org/abs/1508.02595).

## Hints to exercises
<a id="hint1">**Hint:**</a> Whenever Pauli X and Z meet on the same site they anti-commute, otherwise (e.g., $$[X \otimes \mathbb{1},\mathbb{1} \otimes Z]$$ they commute.
