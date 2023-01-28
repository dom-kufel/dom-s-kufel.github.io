---
layout: post
title: Knotty subject
description: This is a brief, rough, sketch of the workshops I conducted for the high-school students in Lublin, Poland, Dec 2022.
---

[In construction...]

We all know what a knot is. Even more we all had to untie some annoyingly tangled knot at some point. Is there any way to rigorously tell if one knot is more difficult to be untangled than the other? Or even if two knots are different? 

You might initially think that these problems are simple to figure out on a case-by-case basis. 

<p style="text-align:center;"><img src="/assets/img/outreach/haken.png" width="250"/></p>
<p style="text-align:center;"><img src="/assets/img/outreach/thistlethwaite.png" width="250"/></p>
Fig. 1: Haken and Thistlethwaite unknots. Yes, if you spent long enough untangling them, you would be able to make a simple loop!
{:.figure}


## Reidemeister moves

We define the <a id="eq:H_TC">Hamiltonian</a> for the system to be
\begin{equation}
H = -\sum_v A_v - \sum_p B_p
\end{equation}   

## Further reading


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

<div class="gumroad-product-embed" data-gumroad-product-id="nuOluY"><a href="https://gumroad.com/l/nuOluY">Loading…</a></div>

## Large Tables

| Default aligned |Left aligned| Center aligned  | Right aligned  | Default aligned |Left aligned| Center aligned  | Right aligned  | Default aligned |Left aligned| Center aligned  | Right aligned  | Default aligned |Left aligned| Center aligned  | Right aligned  |
|-----------------|:-----------|:---------------:|---------------:|-----------------|:-----------|:---------------:|---------------:|-----------------|:-----------|:---------------:|---------------:|-----------------|:-----------|:---------------:|---------------:|
| First body part |Second cell | Third cell      | fourth cell    | First body part |Second cell | Third cell      | fourth cell    | First body part |Second cell | Third cell      | fourth cell    | First body part |Second cell | Third cell      | fourth cell    |
| Second line     |foo         | **strong**      | baz            | Second line     |foo         | **strong**      | baz            | Second line     |foo         | **strong**      | baz            | Second line     |foo         | **strong**      | baz            |
| Third line      |quux        | baz             | bar            | Third line      |quux        | baz             | bar            | Third line      |quux        | baz             | bar            | Third line      |quux        | baz             | bar            |
| Second body     |            |                 |                | Second body     |            |                 |                | Second body     |            |                 |                | Second body     |            |                 |                |
| 2 line          |            |                 |                | 2 line          |            |                 |                | 2 line          |            |                 |                | 2 line          |            |                 |                |
| Footer row      |            |                 |                | Footer row      |            |                 |                | Footer row      |            |                 |                | Footer row      |            |                 |                |
{:.scroll-table}


## Code blocks

~~~js
// Example can be run directly in your JavaScript console

// Create a function that takes two arguments and returns the sum of those
// arguments
var adder = new Function("a", "b", "return a + b");

// Call the function
adder(2, 6);
// > 8
~~~

 -->
## References
<a id="wenchenbook">*[Zeng et al. (2015)]*</a> Zeng, B., Chen, X., Zhou, D.L. and Wen, X.G., 2015. Quantum Information Meets Quantum Matter--From Quantum Entanglement to Topological Phase in Many-Body Systems. [*arXiv version*](https://arxiv.org/abs/1508.02595).

<a id="simonbook">*[Simon (2020)]*</a> Simon, S.H., 2020. Topological Quantum: Lecture Notes and Proto-Book. Unpublished prototype. [*Online*](http://www-thphys.physics.ox.ac.uk/people/SteveSimon).

<a id="leshouchestopo">*[Kitaev&Laumann (2010)]*</a> Kitaev, A. and Laumann, C., 2010. Topological phases and quantum computation. Exact methods in low-dimensional statistical physics and quantum computing, Lecture Notes of the Les Houches Summer School, (89), pp.101-125. [*arXiv version*](https://arxiv.org/abs/0904.2771).

<a id="stabilitytopo">*[Bravyi et al. (2010)]*</a>  Bravyi, S., Hastings, M.B. and Michalakis, S., 2010. Topological quantum order: stability under local perturbations. *Journal of mathematical physics, 51(9), p.093512* [*arXiv version*](https://arxiv.org/abs/1001.0344).

<a id="kitaevmasterpiece">*[Kitaev (2006)]*</a>  Kitaev, A., 2006. Anyons in an exactly solved model and beyond. *Annals of Physics, 321(1), pp.2-111.* [*arXiv version*](https://arxiv.org/abs/cond-mat/0506438)

<a id="spinliquids">*[Savary&Balents (2016)]*</a> Savary, L. and Balents, L., 2016. Quantum spin liquids: a review. *Reports on Progress in Physics, 80(1), p.016502*. [*arXiv version*](https://arxiv.org/abs/1601.03742)

## Hints to exercises
<a id="hint1">**Hint:**</a> Whenever Pauli X and Z meet on the same site they anti-commute, otherwise (e.g., $$[X \otimes \mathbb{1},\mathbb{1} \otimes Z]$$ they commute.

<a id="hint2">**Hint:**</a> Think about the discrete version of Stokes' theorem. Why should it apply here?