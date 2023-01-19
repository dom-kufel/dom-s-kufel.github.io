---
layout: post
title: Toric code from condensed matter perspective.
description: >
  I discuss toric code and its connections to topological order, long-range entanglement and quantum spin liquids.
sitemap: false
hide_last_modified: true
---

!!! More broadly, toric code, nicely links topology to many-body quantum systems and displays some striking connections between quantum matter *and* information.

In this blogpost I would like to further highlight these matter-information connections by discuss (somewhat confusing) properties of the toric code such as presence of the long-range entanglement (yet $$0$$ correlation length!), how it links to a wider class of so-called quantum spin liquids - models which recently came within reach of the experiments. I assume basic familiarity with the 2D toric code model (see e.g., my other blogpost giving a very short intro to it). In section <a href="long-range-entanglement">2</a> we will discuss what we mean by saying that toric code has "long-range entanglement" and provide a simple proof that this is indeed the case. In section <a href="long-range-entanglement-and-observables-correlations">3</a> how to reconcile long-range entangled property with the statement about its $$0$$ correlation length; in section <a href="quantum-spin-liquids">4</a> we will show how toric code fits within a wider class of models and how they might be experimentally realized. Stay tuned: I promise there are few cute ideas along the way!

<!-- * Long-range Entanglement
* Entanglement and correlations
* Quantum Spin Liquids -->

- Table of Contents
{:toc .large-only}

*[weird]: Read: interesting

## Long-range entanglement
What do we mean by long-range entanglement? We say that state is long-range entangled if it cannot be prepared by a quantum circuit with constant-depth i.e. depth required does not scale with the system size. What are some familiar states which are long-range entangled?


Define the 2D toric code as a set of qubits placed on the links of the 2D square lattice with periodic boundary conditions with the <a id="eq:H_TC">Hamiltonian</a>
\begin{equation}
H = -\sum_v A_v - \sum_p B_p
\end{equation}
where $$B_p= \prod_j Z_j$$ acts on plaquettes and $$A_v = \prod_j X_j$$ acts on each of the vertices.


## Long-range entanglement and observables correlations

## Quantum Spin liquids

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
