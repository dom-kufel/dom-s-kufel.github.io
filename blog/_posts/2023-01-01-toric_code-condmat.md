---
layout: post
title: "It from Qubit" - long-range entanglement and correlations in the toric code.
description: >
  I discuss toric code and its connections to topological order, long-range entanglement and quantum spin liquids.
sitemap: false
hide_last_modified: true
---

I remember fondly the moment when as a kid I have learnt about Aristotelian "essence" of entities, as a set of properties without which the entity loses its identity. Later studying entropy taught me that often we can remove some things from the object without sacrificing its "essence" or **information** contained in it. "Information" though was a mysterious concept to me, difficult to be connected to physical **matter**. Ugh, that's nebulous and seems hopeless. But then there was quantum. Deriving "it from qubit" became a concrete research effort through study of "highly" entangled quantum many-body systems.

In this blogpost I would like to follow the "it from qubit" spirit and discuss aspects of a 2D toric code model displaying some striking connections between quantum matter *and* information. Specifically we will study (somewhat confusing) properties of the toric code such as presence of the long-range entanglement (yet $$0$$ correlation length!) and discuss how it links to a wider class of so-called quantum spin liquids - models which recently came within reach of the experiments. I assume basic familiarity with the 2D toric code model (see e.g., my other blogpost giving a very short intro to it). In section <a href="long-range-entanglement">2</a> we will discuss what we mean by saying that toric code has "long-range entanglement" and provide a simple proof that this is indeed the case. In section <a href="long-range-entanglement-and-observables-correlations">3</a> how to reconcile long-range entangled property with the statement about its $$0$$ correlation length; in section <a href="quantum-spin-liquids">4</a> we will show how toric code fits within a wider class of models and how they might be experimentally realized. Stay tuned: I promise there are few cute ideas along the way!

* Long-range Entanglement
* Entanglement and correlations
* Quantum Spin Liquids
{:toc}

## Long-range entanglement
What do we mean by long-range entanglement? We say that state is **long-range entangled** if it cannot be prepared by a quantum circuit with a "constant-depth" i.e. depth required does not scale with the system size. What are some familiar states which are long-range entangled? For instance, $$\vert \textrm{GHZ} \rangle$$ state on $$n$$ qubits and any of the toric code ground states $$\vert \textrm{TC}_j \rangle$$ ($$j=0,1,2,3$$) are long-range entangled. Let's think about why.   

  <!-- = \frac{1}{\sqrt{2}} \left( \vert 00 \rangle + \vert 11 \rangle \right)$$  -->


We define the 2D toric code as a set of qubits placed on the links of the 2D square lattice with periodic boundary conditions with the following <a id="eq:H_TC">Hamiltonian</a>
\begin{equation}
H = -\sum_v A_v - \sum_p B_p
\end{equation}
where $$B_p= \prod_j Z_j$$ acts on plaquettes and $$A_v = \prod_j X_j$$ acts on each of the vertices.


## Long-range entanglement and observables correlations

## Quantum Spin liquids

## References
