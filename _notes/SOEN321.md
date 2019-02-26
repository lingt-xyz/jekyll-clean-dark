---
layout: post
title: SOEN 321
comments: false
---
<!--more-->

2019 Winter

## Outline

### Instructor
* Instructor: Hovhannes Harutyunyan
* Office: EV 003.155
* Email: haruty@cs.concordia.ca
* Office hours: Thursday 11:40 - 12:40 or by appointment

### Textbook
Discrete and Combinatorial Mathematics: An Applied Introduction (fifth edition) by Ralph P. Grimaldi, Addison-Wesley, 2003, ISBN 0-201-72634-3.

### Grading
* 15% Assignments 
* 25% Midterm Exam - in class (week 7 or 8)
* 60% Final Exam

### Assignments
* Assignment 1. (due on September 22 , 2018, 11:59pm)
* Assignment 2. (due on October 10, 2018, 11:59pm)
* Assignment 3. (due on November 11, 2018, 11:59pm)
* Assignment 4. (due on November 28, 2018, 11:59pm) 

---

## 1 Fundamental Principles of Counting

### 1.1 The Rules of Sum and Product

* The Rule of Sum: If a first task can be performed in {% raw %}$$m$${% endraw %} ways, while a second task can be performed in {% raw %}$$ n$${% endraw %} ways, and the two tasks cannot be performed simultaneously, then performing either task can be accomplished in any one of {% raw %}$$ m + n$${% endraw %} ways.
* The Rule of Product: If a procedure can be broken down into first and second stages, and if there are {% raw %}$$ m$${% endraw %} possible outcomes for the first stage and if, for each of these outcomes, there are {% raw %}$$ n$${% endraw %} possible outcomes for the second stage, then the total procedure can be carried out, in the designated order, in {% raw %}$$ mn$${% endraw %} ways.

### 1.2 Permutations

* Definition 1.1 For an integer {% raw %}$$n\geqslant0$${% endraw %}, {% raw %}$$n factorial$${% endraw %} (denoted {% raw %}$$n!$${% endraw %}) is defined by
{% raw %}
$$
n! =
\begin{cases}
1,  & \text{if $n=0$} \\
(n)(n-1)(n-2)\dots(3)(2)(1), & \text{if $n\geqslant1$}
\end{cases}
$$
{% endraw %}
* Definition 1.2 Given a collection of {% raw %}$$n$${% endraw %} distinct objects, any (linear) arrangement of these objects is called a {% raw %}$$permutation$${% endraw %} of the collection. The number of permutations of size {% raw %}$$r$${% endraw %}, where {% raw %}$$0\leqslant r\leqslant n$${% endraw %}, from a collection of {% raw %}$$n$${% endraw %} objects, is 
{% raw %}
$$
P(n,r)={(n)(n-1)(n-2)\dots(n-r+1)(n-r)(n-r-1)\dots(3)(2)(1)\over(n-r)(n-r-1)\dots(3)(2)(1)}={n!\over(n-r)!}
$$
{% endraw %}

> Anagram: a word formed by rearranging the letters of another word. Anagram is also called permutations.

e.g.: 

* ART: {% raw %}$$3\times2\times1=6$${% endraw %}
* MATH: {% raw %}$$4\times3\times2\times1=24$${% endraw %}
* CHAPTER: four letters word is {% raw %}$$7\times6\times5\times4$${% endraw %}
* Put *A*, *B*, *C* into 10 numbered boxes
    1. At most one per box: {% raw %}$$10\times9\times8=P(10,3)$${% endraw %}
    2. If boxes can get more than one: {% raw %}$$10\times10\times10$${% endraw %}
* *3* Objects into *10* numbered boxes, at most one per box:
    1. If objects are identical (they are the same): {% raw %}$${P(10, 3)\over3!}$${% endraw %}
    2. Otherwise: {% raw %}$$C(10, 3)={10!\over7!\times3!}=\binom{10}{3}$${% endraw %}
* How many 4 digital decimal numbers:
    1. If allow *0*: {% raw %}$$10\times10\times10\times10$${% endraw %}
    2. If allow *0* but no repeated digits: {% raw %}$$10\times9\times8\times7$${% endraw %}
    3. If no leading *0* and no repeated digits: {% raw %}$$9\times9\times8\times7$${% endraw %}
* How many 5 digital numbers:
    1. Must contain *0*: 

        {% raw %}$$
        \left.
        \begin{array}{l}
        0\quad \_\quad \_\quad \_\quad \_:&10^4\\
        \_\quad 0\quad \_\quad \_\quad \_:&10^4\\
        \_\quad \_\quad 0\quad \_\quad \_:&10^4\\
        \_\quad \_\quad \_\quad 0\quad \_:&10^4\\
        \_\quad \_\quad \_\quad \_\quad 0:&10^4
        \end{array}
        \right\}
        =5\times10^4
        $${% endraw %}

        * How about {% raw %}$$\color{red}{00012}$${% endraw %}, it was counted three times.
        * {% raw %}$$10^5 - 9^5$${% endraw %}: {% raw %}$$9^5$${% endraw %} is who does not contain {% raw %}$$0$${% endraw %}.
    2. Must contain *0* and *1*: {% raw %}$$10^5-9^5-9^5\color{red}{+8^5}$${% endraw %}
* Choose a committe of *3* from *80* students:
    1. (It's a committe, so order does not matter): {% raw %}$$\binom{80}{3}=C(80, 3)={80!\over77!\times3!}$${% endraw %}
    2. If choose *77*, should be the same: {% raw %}$$\binom{80}{77}=C(80, 77)={80!\over3!\times77!}$${% endraw %}
* Choose a committe of *6*; *3* of them are from *60* cs students and *3* of them are from *20* math students:
     {% raw %}$$\binom{60}{3}\times\binom{20}{3}$${% endraw %}
* *6* TAs, assign each TA to one time slot (A: 1-2pm; B: 2-3pm; C: 3-4pm), and every time slot should have *2* TAs:
    1. M1: {% raw %}$$\binom{6}{2}\times\binom{4}{2}\times\binom{2}{2}$${% endraw %}
    2. M2: think it differently. Because every TA should be assigned to one time slot, so the first time slot has *6* choices, and the second time slot has *5* choices, and so on. It becomes to an anagram problem.

        {% raw %}$$
        \_\quad \_\quad \_\quad \_\quad \_\quad \_\quad 
        $${% endraw %}

        But in each time slot, the TAs' order does not matter:

        {% raw %}$$
        {6!\over2!\times2!\times2!}
        $${% endraw %}
* BANANAS
    1. {% raw %}$${7!\over3!\times2!} $${% endraw %}
    2. What if no adjacent *A*s:

        {% raw %}$$
        \_B\_N\_N\_S\_
        \begin{cases}
        \text{BNNS}:  & 4!/2! \\
        A \text{ can be put to 5 positions:} & \binom{5}{3}
        \end{cases}
        \\
        \text{In total: }{4!\over2!}\times\binom{5}{3}
        $${% endraw %}
* Example 1.16 If six people, designated as A,B,...,F, are seated about a round table, how many different circular arrangements are possible, if arrangements are considered the same when one can be obtained from the other by rotation?
    6!/6=5!=120
* Example 1.17
    3X2X2X2X1X1=12
* Put 15 different books into two shelves so that there is at least one book on each shelf? (Consider the books in each arrangement to be stacked one next to each other, with the first book on each shelf at the left of the shelf.)
    * Separate them (1,2,3,...,15) into two parts, so a bar can be put at 14 positions: 15!*14
    * Three shelves: 15!*C(14,2)
    * For two shelves: why 15!*(2^15-2) is not right?

### 1.3 Combinations: The Binomial Theorem

* Theorem 1.1 {% raw %}$$The Binomial Theorem$${% endraw %}. If {% raw %}$$x$${% endraw %} and {% raw %}$$y$${% endraw %} are variables and {% raw %}$$n$${% endraw %} is a positive integer, then
    {% raw %}
    $$
    (x+y)^n=\binom{n}{0}x^0y^n+\binom{n}{1}x^1y^{n-1}+\binom{n}{2}x^2y^{n-2}+\dots+\binom{n}{n-1}x^{n-1}y^1+\binom{n}{n}x^{n}y^0=\sum_{k=0}^n\binom{n}{k}x^ky^{n-k}
    $$
    {% endraw %}

    Proof: Take {% raw %}$$n=4$${% endraw %} for example. The coefficient of {% raw %}$$x^2y^2$${% endraw %} in the expansion of the product

    {% raw %}
    $$
    (x+y)(x+y)(x+y)(x+y)
    $$
    {% endraw %}
    is the number of ways in which we can select two *x*'s from four *x*'s, one of which is available in each factor.
    
    That is, the coefficient of {% raw %}$$x^2y^2$${% endraw %} in the expansion of {% raw %}$$(x+y)^4 \text{ is } \binom{4}{2}=6$${% endraw %}, the number of ways to select two distinct objects from a collection of four distinct objects.
        
    

* Corollary 1.1 For each integer {% raw %}$$n\gt0$${% endraw %}.

    {% raw %}
    $$ 
    \binom{n}{0}+\binom{n}{1}+\binom{n}{2}+\dots+\binom{n}{n}=2^n\\
    \binom{n}{0}-\binom{n}{1}+\binom{n}{2}-\dots+(-1)^n\binom{n}{n}=0
    $$
    {% endraw %}


* Theorem 1.2 For positive integers

### 1.4 Combinations with Repetition


### 1.5 The Catalan Numbers

---

## 4 Properties of the Integers: Mathematical Induction

### 4.1 The Well-Ordering Principle: Mathematical Induction

* The Well-Ordering Principle: Every *nonempty* subset of {% raw %}$${\Bbb Z}^+$${% endraw %} contains a smallest element. (We often express this by saying that {% raw %}$${\Bbb Z}^+$${% endraw %} is *well ordered*.)

* Theorem 4.1 *The Principle of Mathematical Induction*. Let {% raw %}$$S(n)$${% endraw %} denote an open mathematical statement ( or set of such open statements) that involves one or more occurrences of the variable {% raw %}$$n$${% endraw %}, which represents a positive integer.
    1. If {% raw %}$$S(1)$${% endraw %} is true; and
    2. If whenever {% raw %}$$S(k)$${% endraw %} is true (for some particular, but arbitrarily chosen, {% raw %}$$k\in {\Bbb Z}^+$${% endraw %}), then {% raw %}$$S(k+1)$${% endraw %} is true;
    3. Then {% raw %}$$S(n)$${% endraw %} is true for all {% raw %}$${n\in \Bbb Z}^+$${% endraw %}.

### 4.2 Recursive Definitions


* e.g. {% raw %}$$\sum_{i=0}^k F_i^2=F_k\times F_{k+1}\text{, for all }k\geq1$${% endraw %} by Induction

    1. Base: 
        * {% raw %}$$k=1$${% endraw %}: {% raw %}$$\sum_{i=0}^1 F_i^2=F_0+F_1=1=F_1\times F_2$${% endraw %}
        * {% raw %}$$k=2$${% endraw %}: {% raw %}$$\sum_{i=0}^2 F_i^2=F_0+F_1+F_2=2=F_2\times F_3$${% endraw %} (why need k=2?)
    2. Inductive Hypothesis:

        Assume {% raw %}$$\sum_{i=0}^k F_i^2=F_k\times F_{k+1}\text{, for all }k=1,2,\dots,n\text{; that is, }k\leq n$${% endraw %}
    3. Inductive Step:

        Must prove {% raw %}$$\sum_{i=0}^{n+1} F_i^2=F_{n+1}\times F_{(n+1)+1}$${% endraw %}

    4. Proof:

        {% raw %}$$
        \begin{align*}
        \sum_{i=0}^{n+1} F_i^2 & = \sum_{i=0}^{n} F_i^2 + F_{n+1}^2 \\
        & = F_n\times F_{n+1} + F_{n+1}^2 \\ 
        & = F_{n+1}\times (F_n+F_{n+1}) \\ 
        & = F_{n+1}\times F_{n+2} \\ 
        & = F_{n+1}\times F_{(n+1)+1}
        \end{align*}

        $${% endraw %}

---

## 8 The Principle of Inclusion and Exclusion

### 8.1 The Priciple of Inclusion and Exclusion

* <green>Theorem 8.1</green> The Principle of Inclusion and Exclusion. Consider a set {% raw %}$$S\text{, with }\mathbf{card}(S)=N$${%endraw%}, and conditions {%raw%}$$c_i, 1\leqslant i\leqslant t$${%endraw%}, each of which may be satisfied by some of the elements of {% raw %}$$S$${%endraw%}. The number of elements of {% raw %}$$S$${%endraw%} that satisfy *none* of the conditions {%raw%}$$c_i, 1\leqslant i\leqslant t$${%endraw%}, is denoted by {%raw%}$$\overline {N}=N(\bar { c_1} \bar { c_2} \bar { c_3} \dots \bar { c_t})$${%endraw%} where

{% raw %}$$

\begin{align}
\overline { N} = & N\\
& -[N(c_1)+N(c_2)+N(c_3)+\dots + N(c_t)] \\
& +  [N(c_1 c_2)+N(c_1 c_3)+\dots+N(c_1 c_t)+N(c_2 c_3+\dots+N(c_{t-1} c_t))]\\ 
& -  [N(c_1 c_2 c_3)+N(c_1 c_2 c_4)+\dots+N(c_1 c_2 c_t)+N(c_1 c_3 c_4)+\dots+N(c_1 c_3 c_t)+\dots +N(c_{t-2} c_{t-1} c_t)]\\ 
& + \\
& \dots \\
& + (-1)^t N(c_1 c_2 c_3 \dots c_t)
\end{align}

$${% endraw %}

or 

{% raw %}$$

\begin{align}
\overline {N} = N - \sum_{1\leqslant i \leqslant t} N(c_i) + \sum_{1\leqslant i \lt j \leqslant t} N(c_i c_j) - \sum_{1\leqslant i \lt j \lt k \leqslant t} N(c_i c_j c_k) +  \dots + (-1)^t N(c_1 c_2 c_3 \dots c_t)
\end{align}

$${% endraw %}

* e.g.:
    A set of *S* contains 68 students in COMP 339. 

    Condition 1: Students from Computer Science; 

    Condition 2: Students from Math.

    {% raw %}$$

    N(\bar{c_1})

$${% endraw %}



* <green>Corollary 8.1</green> Under the hypotheses of Theorem 8.1, the number of elements in {% raw %}$$S$${%endraw%} that satisfy at least one of the condition {% raw %}$$c_i\text{, where }1\leqslant i\leqslant t$${%endraw%}, is given by {% raw %}$$N(c_1\text{ or }c_2\text{ or }\dots\text{ or } c_t)=N-\overline{N}$${%endraw%}

### 8.2 Generalization of the Principle

* Theorem 8.2 Under the hypotheses of Theorem 8.1, for each {% raw %}$$1\leqslant m\leqslant t$${% endraw %}, the number of elements in {% raw %}$$S$${% endraw %} that satisfy *exactly* {% raw %}$$m$${% endraw %} of the conditions {% raw %}$$c_1, c_2, \dots, c_t$${% endraw %} is given by

    {% raw %}$$
    E_m=S_m-\binom{m+1}{1}S_{m+1}+\binom{m+2}{2}S_{m+2}-\dots +(-1)^{t-m}\binom{t}{t-m}S_t
    $${% endraw %}

    If {% raw %}$$m=0$${% endraw %}, we obtain Theorem 8.1

* Corollary 8.2 {% raw %}$$L_m=S_m-\binom{m}{m-1}S_{m+1}+\binom{m+1}{m-1}S_{m+2}-\dots +(-1)^{t-m}\binom{t-1}{m-1}S_t$${% endraw %}

---

## 9 Generating Functions

### 9.1 Introductory Examples

### 9.2 Definition and Examples: Calculational Techniques

* Definition 9.1


### 9.3 Partitions of Integers

### 9.4 The Exponential Generating Function

* Definition 9.2

---

## 10 Recurrence Relations

### 10.4 The Method of Generating Functions

---

## 11 An Introduction to Graph Theory

### 11.1 Definitions and Examples

* Definition 11.1

* Definition 11.2

* Definition 11.3

* Theorem 11.1

* Definition 11.4

* Definition 11.5

* Definition 11.6

### 11.2 Subgraphs, Complements, and Graph Isomorphism

* Definition 11.7

* Definition 11.8

* Definition 11.9

* Definition 11.10

* Definition 11.11

* Definition 11.12

* Definition 11.13

### 11.3 Vertex Degree: Euler Trails and Circuits

* Definition 11.14

* Theorem 11.1

* Corollary 11.1

* Definition 11.15

* Theorem 11.3

* Corollary 11.2

* Definition 11.16

* Theorem 11.4

### 11.4 Planar Graphs

* Definition 11.17

* Definition 11.18

* Definition 11.19

* Theorem 11.5

* Theorem 11.6

* Corollary 11.3

* Definition 11.20

### 11.5 Hamilton Paths and Cycles

* Definition 11.21

* Theorem 11.7

* Theorem 11.8

* Theorem 11.9

* Corollary 11.5

* Corollary 11.6

### 11.6 Graph Coloring and Chromatic Polynomials

* Definition 11.22

* Theorem 11.10

* Theorem 11.11

* Theorem 11.12

* Theorem 11.13

* Theorem 11.14

### 11.7 Summary and Historical Review

---

## 12 Trees

### 12.1 Definitions, Properties, and Exmaples

* Definition 12.1

* Theorem 12.1

* Theorem 12.2

* Theorem 12.3

* Theorem 12.4

* Theorem 12.5

---

## 13 Optimization and Matching

### 13.4 Matching Theory

* Definition 13.9

* Theorem 13.7

* Corollary 13.6

* Definition 13.10

* Definition 13.11

* Theorem 13.8
