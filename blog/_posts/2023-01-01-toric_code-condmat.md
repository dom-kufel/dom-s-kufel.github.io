---
layout: post
title: It from Qubit - long-range entanglement and correlations in the toric code.
description: >
  I discuss toric code and its connections to topological order, long-range entanglement and quantum spin liquids.
sitemap: false
hide_last_modified: true
---

I remember fondly how amazed I was when I have learnt about Aristotelian "essence" of entities: a set of properties without which the entity loses its identity. Afterwards, studying entropy taught me, in the same spirit, that the amount of this "essence" might be quantified by the **information** contained in it. "Information" though was a mysterious concept to me, difficult to be connected to any physical notion of **matter** I could envision. Ugh, at that stage things seemed too *nebulous* to me. But then I have heard about the recent effort in quantum: deriving "it from qubit" became a *concrete* research direction through study of "highly" entangled quantum matter from the quantum information perspective.

In this blogpost I would like to follow the "it from qubit" spirit and discuss concrete aspects of a 2D toric code model displaying some striking connections between quantum matter *and* information. Specifically we will study (somewhat confusing) properties of the toric code such as presence of the long-range entanglement (yet $$0$$ correlation length!) and discuss how it links to a wider class of so-called quantum spin liquids - models which recently came within reach of the experiments. I assume basic familiarity with the 2D toric code model (see e.g., my other blogpost giving a very short intro to it). In section <a href="long-range-entanglement">2</a> we will discuss what we mean by saying that toric code has "long-range entanglement" and provide a simple proof that this is indeed the case. In section <a href="long-range-entanglement-and-observables-correlations">3</a> how to reconcile long-range entangled property with the statement about its $$0$$ correlation length; in section <a href="quantum-spin-liquids">4</a> we will show how toric code fits within a wider class of models and how they might be experimentally realized. Stay tuned: I promise there are few cute ideas along the way!

* Long-range Entanglement
* Entanglement and correlations
* Quantum Spin Liquids
{:toc}

## Long-range entanglement
What do we mean by long-range entanglement? We say that state is **long-range entangled** if it cannot be prepared (from a product state) by a quantum circuit with a "constant-depth" i.e. depth required does not scale with the system size. What are some familiar states which are long-range entangled? For instance, $$\vert \textrm{GHZ} \rangle$$ state on $$n$$ qubits and any of the toric code ground states $$\vert \textrm{TC}_j \rangle$$ ($$j=0,1,2,3$$) are long-range entangled. Let's think about why.

Perhaps the simplest example is preparation of the $$\vert \textrm{GHZ} \rangle = \frac{1}{\sqrt{2}} \left( \vert 00 \rangle + \vert 11 \rangle \right)$$ state from $$\vert 0 \rangle^{\otimes n}$$ is to apply a Hadamard gate on the first qubit and then a set of $$N-1$$ CNOT gate layers between the 0th and k-th qubit ($$k=1,\dots,N$$) - see quantum circuit for $$N=3$$ in Fig. 1. In this case depth of the required circuit clearly scales with the system size (depth goes like $$N$$). We will demonstrate similar non-constant depth circuit for the toric code in section  <a href="quantum-spin-liquids">4</a>.

<p style="text-align:center;"><img src="/assets/img/blog/GHZpreparation.png" width="500"/></p>

That example is all good, but what we intend to show is different: namely that there exists no way of preparing the $$\vert GHZ \rangle$$ other than the circuit depth scaling with the system size. Perhaps the simplest way of showing this formally is to use the following (informal version of the) lemma due to <a href="#references">[Piroli et al. (2021) Prop. 1]</a>

Let $$A,B$$ be regions (collection of points) on the regular lattice in $$D$$ dimensions, defined such that $$d(A,B)>2 l$$ (where $$d(A,B)$$ is the minimum graph distance between $$A$$ and $$B$$) and operators $$Q_A$$ and $$Q_B$$ to be supported on $$A$$ and $$B$$ respectively. If state $$\vert \phi \rangle$$ may be prepared by a quantum circuit of depth (at most) $$l$$ from a product state $$\vert 0 \rangle$$ then the following is true $$\forall \ Q_A, Q_B $$:
$$\langle \phi \vert Q_A Q_B \vert \phi \rangle = \langle \phi \vert Q_A \vert \phi \rangle \langle \phi \vert Q_B \vert \phi \rangle$$
{:.message}

In other words, if we can given an example of $$Q_A, Q_B$$ such that $$\langle \phi \vert Q_A Q_B \vert \phi \rangle \neq \langle \phi \vert Q_A \vert \phi \rangle \langle \phi \vert Q_B \vert \phi \rangle$$ then $$\phi$$ had to be prepared by a quantum circuit of depth greater than $$l$$.

Equipped with this lemma let's formally show that $$\vert GHZ \rangle$$ cannot be prepared with a finite depth circuit. Pick $$Q_A=$$ and $$Q_B=$$. Then
You will similarly show that $$\vert TC_j \rangle$$ is long-range entangled in the exercise below.

**Exercise:** Show that given $$\vert \phi \rangle= \vert TC_j \rangle$$ $$\exists Q_A, Q_B$$ such that $$\langle \phi \vert Q_A Q_B \vert \phi \rangle \neq \langle \phi \vert Q_A \vert \phi \rangle \langle \phi \vert Q_B \vert \phi \rangle$$ and therefore $$ \vert TC_j \rangle$$ is long-range entangled. <a href="#hint1">Hint</a>
{:.message}

<!-- Is any state reachable by an arbitrarily deep circuit? -->

We define the 2D toric code as a set of qubits placed on the links of the 2D square lattice with periodic boundary conditions with the following <a id="eq:H_TC">Hamiltonian</a>
\begin{equation}
H = -\sum_v A_v - \sum_p B_p
\end{equation}
where $$B_p= \prod_j Z_j$$ acts on plaquettes and $$A_v = \prod_j X_j$$ acts on each of the vertices.


## Long-range entanglement and observables correlations

## Quantum Spin liquids

## References
<a id="pirolipaper">*[Piroli et al. (2021)]*</a> Piroli, L., Styliaris, G. and Cirac, J.I., 2021. Quantum circuits assisted by local operations and classical communication: Transformations and phases of matter. *Physical Review Letters, 127(22), p.220503.* [*arXiv version*](https://arxiv.org/abs/2103.13367).

## Hints to exercises
<a id="hint1">**Hint:**</a> Think about (non-local) logical Pauli operators.
