# STATS 100A - Spring '22 - Sanchez

[TOC]

## Lecture 1: Modern Probability and Partitions

- Classical definition:

  - $$
    P(\text{event})=\frac{\text{number of ways the event can happen}}{\text{number of ways event can happen + number of ways it cannot happen}}
    $$

  - Assumptions that must hold in order to use classical probability:

    - The outcomes of the experiment must be equally likely

- Building Blocks for Modern Probability

  - Goal: realize that the algebra of sets helps us be precise in defining the universal set for any experiment and subsets of it, thus helping us define the domain of the function that we will call probability
    - In particular, we will name the universal set the **Sample Space**
      - Subsets of it will be called **events**
      - They will be constructed for several experiments
    - The algebra of sets will be used to create events that have special meaning in the context of each experiment
  - To make decisions properly, it helps to have clear what are acceptable values
    - That requires knowing the domain experiment
    - Without knowing the values that make sense for an experiment (and that depends on the kind of experiment), it is impossible to assign probabilities to them and to be precise
  - A random experiment is a very broad concept
    - It is any action for which the outcome is not pre-determined
  - The sample space, `S`
    - The answer to the question: what could potentially be the outcome of the random experiment
    - The sample space is the biggest set (the universal set) containing all the reasonable outcomes of a random experiment
    - When an experiment is performed, it results in one and only one element of the sample space
    - A sample space can be:
      - Finite
      - Countably infinite
      - Uncountably infinite
    - Learning to put together the elements of a sample space is the first skill needed to succeed in the use of probability
      - The domain of a probability measure is the sample space
    - Explicitly defined notation
    - Experiments with different structure may have similar sample spaces and vice versa
  - Events
    - An event (always denoted by a capital letter) is a subset of the sample space, and therefore a set
  - Summary
    - Random experiments are experiments whose outcome is uncertain, but if we make an effort and know our domain, we can define all outcomes
    - A sample space `S` is a set containing all logically reasonable outcomes of the sample experiment
      - Any outcome of a random experiment must be in `S`
      - Events are subsets of the sample space
        - An event occurs if an outcome in the event occurs
    - Event operations and algebra of events are, mathematically speaking, the set operations and algebra of sets

- Partitions

  - A partition of `A` is a collection of subsets of `A`, `R1`, `R2`, ... , `Rn` such that:

    - $$
      R_i\ne\emptyset\text{ for all }i
      $$

    - $$
      R_i\cap R_j=\emptyset
      $$

    - $$
      \bigcup_{i=1}R_i=A
      $$



## Lecture 2: Probability Measure

- In this lecture:

  - Probability is not an intrinsic property of physical objects, but rather a mathematical function on sets in a sample space
  - This generality, and the results that follow from it makes probability very useful for decision-making and many of its other uses
  - We will describe the Kolmogorov axioms of probability which characterize the measure called probability
  - We will state (without proof) some theorems which follow from the axioms
    - Union rule, complement rule, probability of only one event, etc.
    - To get probabilities right, you must know these rules
    - Probability calculations are based on these rules
  - We will apply the theorems in different contexts
    - The same rules but a large variety of different contexts is what makes probability so useful for many things

- Notation:

  - `S` denotes the sample space
  - `P` denotes the probability of an event
  - Any other capital letter represents an event

- Kolmogorov's Probability Axioms:

  - Probability is a function `P` defined on sets of the larger set `S` such that this function satisfies Kolmogorov's axioms

  - If `A` is an event in the sample space `S`:

    - $$
      P(A)\ge0\text{ for all events }A 
      $$

    - $$
      P(S)=1
      $$

      - `S` always happens, any outcome of the experiment is in `S`

    - Axiom of countable additivity: if `A1`, `A2`, ... is a collection of pairwise disjoint or mutually exclusive events, all defined on a sample space `S`, then:

      - $$
        P(\bigcup^{\infty}_{i=1}A_i)=\sum^\infty_{i=1}P(A_i)
        $$

      - The probability of the union of mutually exclusive events is the sum of their probabilities

- 

