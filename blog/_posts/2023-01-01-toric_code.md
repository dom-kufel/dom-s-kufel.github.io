---
layout: post
title: Toric code from condensed matter perspective.
description: >
  With a brief intro to toric code, I discuss its connections to topological order, long-range entanglement and quantum spin liquids.
sitemap: false
hide_last_modified: true
---

Working in the field of quantum technologies I often chat to people from a variety of quantum-focused fields.  A weird thing happens if people from traditionally different communities talk about the same stuff. This is how I have first heard about the toric code: both condensed matter and quantum error correction people spoke about it a lot. At that stage I decided to get a better idea of this mysterious “toric code thing”. I soon discovered why people talk about it so much: toric code is a paradigmatic example for both topological quantum error correction and topological order in condensed matter. More broadly, toric code, nicely links topology to many-body quantum systems and displays some striking connections between quantum matter and information. Exciting! In this blogpost I would like to discuss few basic properties of a toric code model, viewing it from condensed matter perspective (since quantum error correction view of it is somewhat more well-known). Stay tuned: I promise there are few cute ideas along the way.

<!-- [^1]: Read: interesting -->
*[weird]: Read: interesting

## Toric code basics

In the simplest realization, toric code is a model of qubits (e.g., spins-1/2) placed on the links of the 2D square lattice with periodic boundary conditions (thus making a torus). We define the Hamiltonian for the system to be
\begin{equation}
H = -\sum_v A_v - \sum_p B_p
\label{eq:H_TC}
\end{equation}
where $$A_v = \prod_j X_j$$ acts on each of the vertices and $$B_p= \prod_j Z_j$$ acts on “plaquettes” (fancy term for each of the little squares in the lattice) [Footnote: Note that some people (see e.g., <d-cite key="wenchenbook"></d-cite> define A_v operators as products of Pauli Z operators; and B_p operators as products of Pauli X - this is just the matter of convention and does not change the physics in any essential way]. For later we will also define a dual lattice as the one shifted by $$[1/2,1/2]$$ vector from the “primal” one - see Fig. !!!!b.  

Our goal for now is to find the ground state of the above model. First, note that all the terms within the Hamiltonian mutually commute with one another i.e. $$[A_v, B_p]=0 \ \ \forall v,p$$ - you will prove it in the exercise below. (Terminology comment: Hamiltonian containing of Pauli strings which are mutually commuting (as above) is often called stabilizer Hamiltonian - language coming from error correction - more on this later). This remarkably simplifies the problem: we (i) minimize the energy of one of the sums in Eq. \ref{eq:H_TC} and then (ii) impose the other sum as the constraint on the choice of the ground state.


**Exercise:** Show that for the operators defined above $$[A_v, B_p]=0 \ \ \forall v,p.$$ <br> ( Hint: Whenever Pauli X and Z meet on the same site they anti-commute, otherwise (e.g., $$[X \otimes \mathbb{1},\mathbb{1} \otimes Z]$$ they commute.)
{:.message}

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
