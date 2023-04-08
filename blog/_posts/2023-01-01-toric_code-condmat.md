---
layout: post
title: Long-range entanglement and correlations in the toric code.
description: >
  I discuss toric code and its connections to topological order, long-range entanglement and quantum spin liquids.
sitemap: false
hide_last_modified: true
---

[^1]: Be aware that in the past there were many definitions of long-range entanglement flying around (especially in the condensed matter community). For instance <a href="#references">[Zeng et al. (2015) Chp. 7]</a> makes the definition of long-range entanglement essentially equivalent to the one of the "intrinsic" topological order: such definition would e.g., exclude GHZ state from being long-range entangled.
[^2]: Acting with single $$Z$$ we swap the sign of the $$\vert 1 \dots 1 \rangle$$ term, creating state orthogonal to the original GHZ state. If we act with two $$Z$$ (location does not matter) we swap the sign twice thus reverting back to the GHZ state (resulting in a $$1$$ overlap).  

[**In construction...**]

<!-- Product states and entangled states are surely different.

Connection of **information** to physical notion of **matter** is puzzling me for a long time. Studying entropy given

I think it first struck me when I studied entropy in thermodynamics: this mysterious state function which was supposed to never decrease in an isolated system. -->

<!-- Connection of **information** to physical notion of **matter** is puzzling me for a long time. I think it first struck me when I studied entropy in thermodynamics: this mysterious state function which was supposed to never decrease in an isolated system. Later, I was amazed to learn that this entropy has yet another face: as a measure of the information uncertainty - which has been wonderfully demonstrated in e.g., Landauer's principle. I was futher curious: what are some other connections between information and matter, especially in the quantum realm? "It from qubit" - an on-going research effort trying to understand "highly" entangled **quantum matter** from the **quantum information** perspective - turned out to be an answer.  -->


<!-- I remember fondly how amazed I was when I have learnt about Aristotelian "essence" of objects: a set of properties without which the entity loses its identity. In the same spirit, afterwards, studying entropy taught me that the amount of this "essence" might be quantified by the **information** contained in it. "Information" though was a mysterious concept to me, difficult to be connected to any physical notion of **matter** I could envision. Ugh, at that stage things seemed too *nebulous* to me. But then I heard about the recent effort in quantum: deriving "it from qubit" became a *concrete* research direction through study of "highly" entangled quantum matter from the quantum information perspective. -->

In this blogpost I would like to follow the "it from qubit" spirit and discuss concrete aspects of a 2D toric code model displaying some striking connections between quantum matter *and* information. Specifically we will study (somewhat confusing) properties of the toric code such as presence of the long-range entanglement (yet $$0$$ correlation length!) and discuss how it links to a wider class of so-called quantum spin liquids - models which recently came within reach of the experiments. I assume basic familiarity with the 2D toric code model (see e.g., my other blogpost giving a very short intro to it). In section <a href="long-range-entanglement">1</a> we will discuss what we mean by saying that toric code ground state and GHZ state has "long-range entanglement" and provide a simple proof that this is indeed the case. Next, in section <a href="toric-code-vs-ghz">2</a> we will discuss finer differences between the entanglement structure of toric code and GHZ state. In section <a href="long-range-entanglement-and-anyons">3</a> we will discuss peculiar fact of excitations in toric code costing only constant energy (regardless of how far they are separated) and connect it to the long-range entanglement. In section <a href="long-range-entanglement-and-observables-correlations">4</a> how to reconcile long-range entangled property with the statement about its $$0$$ correlation length; in section <a href="quantum-spin-liquids">5</a> we will show how toric code fits within a wider class of models and how they might be experimentally realized. This blogpost assumes basic familiarity with the toric code physics: if you have not studied it in detail see my previous [blogpost](https://dom-kufel.github.io/blog/2023-01-19-toric_code-intro/) to get a concise introduction. Stay tuned: I promise there are few cute ideas along the way!

* Long-range Entanglement
* Long-range Entanglement and anyons
* Toric code vs GHZ
* Entanglement and correlations
* Quantum Spin Liquids
{:toc}

## Long-range entanglement
What do we mean by long-range entanglement[^1]? Define a quantum circuit consisting of 1 qubit and 2-qubit nearest neighbour unitaries. We say that state is **long-range entangled** if its preparation from a product state *necessarily* requires quantum circuit depth scaling with the system size. What are some familiar states which are long-range entangled? For instance, $$\vert \textrm{GHZ} \rangle$$ state on $$n$$ qubits and any of the toric code ground states $$\vert \textrm{TC}_j \rangle$$ ($$j=0,1,2,3$$) are long-range entangled. Let's think about why.

Perhaps the simplest example is preparation of the $$\vert \textrm{GHZ} \rangle = \frac{1}{\sqrt{2}} \left( \vert 00 \rangle + \vert 11 \rangle \right)$$ state from $$\vert 0 \rangle^{\otimes n}$$ is to apply a Hadamard gate on the first qubit and then a set of $$N-1$$ CNOT gate layers between the 0th and k-th qubit ($$k=1,\dots,N$$) - see quantum circuit for $$N=3$$ in Fig. 1. In this case depth of the required circuit clearly scales with the system size (depth goes like $$N$$). We will demonstrate similar non-constant depth circuit for the toric code in section  <a href="quantum-spin-liquids">4</a>.

<p style="text-align:center;"><img src="/assets/img/blog/GHZpreparation.png" width="500"/></p>

That example is all good, but what we intend to show is different: namely that there exists no way of preparing the $$\vert GHZ \rangle$$ other than the circuit depth scaling with the system size. One of the ways of proving this formally is to use the following lemma due to <a href="#references">[Piroli et al. (2021)]</a>

[Piroli et al. (2021) Prop. 1 (informal)]Let $$A,B$$ be regions (collection of points) on the regular lattice in $$D$$ dimensions, defined such that $$d(A,B)>2 l$$ (where $$d(A,B)$$ is the minimum graph distance between $$A$$ and $$B$$) and operators $$Q_A$$ and $$Q_B$$ to be supported on $$A$$ and $$B$$ respectively. If state $$\vert \phi \rangle$$ may be prepared by a quantum circuit of depth (at most) $$l$$ from a product state $$\vert 0 \rangle$$ then the following is true $$\forall \ Q_A, Q_B $$:
$$\langle \phi \vert Q_A Q_B \vert \phi \rangle = \langle \phi \vert Q_A \vert \phi \rangle \langle \phi \vert Q_B \vert \phi \rangle$$
{:.message}

In other words, if we can given an example of $$Q_A, Q_B$$ such that $$\langle \phi \vert Q_A Q_B \vert \phi \rangle \neq \langle \phi \vert Q_A \vert \phi \rangle \langle \phi \vert Q_B \vert \phi \rangle$$ then $$\phi$$ had to be prepared by a quantum circuit of depth greater than $$l$$.

What is the intuition behind this lemma? Well, roughly speaking if the state is *not* "long-range" entangled and we consider two operators lying on disjoint, far-separated regions then we imagine that joint measurment statistics of the observables will be the same as measuring them separately (i.e. they are independent).  

Okay, so equipped with this lemma let's formally show that $$\vert GHZ \rangle$$ cannot be prepared with a finite depth circuit. Pick $$Q_A=Z_1$$ and $$Q_B=Z_N$$ (Pauli operator $$Z$$ acting on the first and last qubit in the chain respectively). Then $$\langle GHZ \vert Q_A \vert GHZ \rangle = 0$$ and $$\langle GHZ \vert Q_B \vert GHZ \rangle = 0$$ yet[^2] $$\langle GHZ \vert Q_A Q_B \vert GHZ \rangle = 1$$. This result implies that the state $$ \vert GHZ \rangle $$ cannot be prepared with a circuit of depth $$(N-1)/2$$: and this depth already scales with the system size and is an untight lower bound for actual depth required. Thus GHZ is long-range entangled. You will similarly show that $$\vert TC_j \rangle$$ is long-range entangled in the exercise below.

**Exercise:** Show that given $$\vert \phi \rangle= \vert TC_j \rangle$$ $$\exists Q_A, Q_B$$ such that $$\langle \phi \vert Q_A Q_B \vert \phi \rangle \neq \langle \phi \vert Q_A \vert \phi \rangle \langle \phi \vert Q_B \vert \phi \rangle$$ and therefore $$ \vert TC_j \rangle$$ is long-range entangled. <a href="#hint1">Hint</a>
{:.message}

Wonderful! Let us summarize what we have learnt

**Fact 1:** State is long-range entangled if it cannot be prepared from a product state using circuit with depth not scaling with the system size. Toric code ground states and GHZ states might be shown to be long-range entangled.  
{:.note}

## Long-range entanglement and anyons

Okay, so what we have done so far is to elaborate on the definition of the long-range entanglement and shown that under this definition GHZ and toric code are long-range entangled. As hinted before this definition is supposed to convey that some states are "more distant" to product states than the others. What consequences might it have? It turns out that in the toric code it has profound consequences for the properties of the excitations ("anyons") in the many-body system <a href="#references">[Savary&Balents (2016)]</a>. From !!! recall a peculiar property of these anyons: after creating a pair of anyons, you pay no energy for moving them around! It turns out that this property directly stems out from the "loopy" form of the toric code ground states. 

<!-- Does the loopy structure neccesarily imply LRE?-->

To be more precise: 

Define the 2D toric code as a set of qubits placed on the links of the 2D square lattice with periodic boundary conditions with the following <a id="eq:H_TC">Hamiltonian</a>
\begin{equation}
H = -\sum_v A_v - \sum_p B_p
\end{equation}
where $$B_p= \prod_j Z_j$$ acts on plaquettes and $$A_v = \prod_j X_j$$ acts on each of the vertices.

Now imagine you apply $$X$$ operator to some edge of the lattice. This will frustrate two plaquette operators (of the form $$B_p=\prod_{j\in p} Z_j$$) touching this edge (i.e. create two "m" anyons) and cost 2 units of energy. Now imagine you apply few more $$X$$ operators to the nearby connected edges thus creating a Pauli $X$ "string". How much more of energy we had to pay to propagate m anyons? Zero. It is weird. For instance consider another familiar problem: say spin chain in a ground state of global z-oriented magnetic field. Imagine then similarily flipping spins with a string of $X$ operators: the energy cost you pay is proportional to the length of the string! 

So what is the underlying reason for such peculiar behaviour of the toric code excitations? The key is careful analysis of the meaning of the "loop-gas" structure of the toric code. Consider one of the toric code ground states and then create a pair of far-separated anyons by applying a string of Pauli operators (anyons are its endpoints). Focus on the regions of the toric code away from the endpoints of the string. If you zoom in such regions you will notice that despite of applying the error string the loop-gas structure of the toric code state is exactly preserved. This is because different loop configurations within the massive superposition will simply get mapped into one another under the application of the Pauli string (see Fig. !!!). Of course, at the precise endpoints of the string this will no longer be true and we will "disturb" the original ground state. But this is precisely why we only pay the energy cost for excitations only at the endpoints of the string! Since a string has always to endpoints we will pay only a constant (in system size) energy cost for propagating the anyons! And now we see that this is all due to the loopiness of the ground state!  

**Fact 2:** Zero energy cost for moving around the excitations in the toric code directly stems from the loop-gas form of its ground state.
{:.note}

## Toric code vs GHZ
<!-- Mention: GHZ long-range entangled and topo entangled are different. Proper study. -->


## Long-range entanglement and observables correlations

Alright, so we have seen how long-range entanglement in toric code is responsible for some of its other peculiar properties. But what is precisely "long-range" in a "long-range entanglement"?

 <!-- Roughly speaking it means that there exist some operators  -->

## Quantum Spin liquids

## References
<a id="pirolipaper">*[Piroli et al. (2021)]*</a> Piroli, L., Styliaris, G. and Cirac, J.I., 2021. Quantum circuits assisted by local operations and classical communication: Transformations and phases of matter. *Physical Review Letters, 127(22), p.220503.* [*arXiv version*](https://arxiv.org/abs/2103.13367).

<a id="wenchenbook">*[Zeng et al. (2015)]*</a> Zeng, B., Chen, X., Zhou, D.L. and Wen, X.G., 2015. Quantum Information Meets Quantum Matter--From Quantum Entanglement to Topological Phase in Many-Body Systems. [*arXiv version*](https://arxiv.org/abs/1508.02595).

<a id="savarybalents">*[Savary&Balents (2016)]*</a> Savary, L. and Balents, L., 2016. Quantum spin liquids: a review. Reports on Progress in Physics, 80(1), p.016502. [*arXiv version](https://arxiv.org/abs/1601.03742)

## Hints to exercises
<a id="hint1">**Hint:**</a> Think about (non-local) logical Pauli operators.
