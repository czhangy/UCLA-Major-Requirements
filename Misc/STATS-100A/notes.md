# STATS 100A - Spring '22 - Sanchez

[TOC]

## Lecture 1: Classical Probability and Partitions

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



## Lecture 2: Modern Probability, Bayes' Theorem, and Independence

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

  - The classical definition of probability satisfies the axioms

    - All other definitions of probability must satisfy them

  - For any given sample space `S`, many different probability functions can be defined that satisfy the axioms

  - Properties of a Probability Function that Follow from the Axioms

    - Theorem: let `P` be a probability function and let `A` be any event in a sample space `S`, then:

      - $$
        P(\emptyset)=0
        $$

    - Theorem: let `P` be a probability function and let `A` be any event in a sample space `S`, then:

      - $$
        P(A^C)=1-P(A)
        $$

      - Complement rule

    - Theorem: let `P` be a probability function and let `A` and `B`  be any events in a sample space `S`, then the probability that "only `A` happens is":

      - $$
        P(A\cap B^C)=P(A)-P(A\cap B)
        $$

    - Theorem:  let `P` be a probability function and let `A` and `B`  be any events in a sample space `S`, then:

      - $$
        P(A\cup B)=P(A)+P(B)-P(A\cap B)
        $$

      - Addition rule

    - Worth noting the different between probability of "only `A` or only `B`" and the probability of "`A` or `B`"

      - Probability of only `A` or only `B` is a union of mutually exclusive events and its solution follows from the third axiom

  - Summary:

    - We saw the Kolmogorov axioms of probability and learned some rules that follow from those axioms
    - We distinguished between the events "`A` or `B`" and "only `A` or only `B`"
    - In future lessons, we will see how repeated use of the rules allow us to calculate events of increasing complexity
      - No matter what the context is, if using probability, we must satisfy the axioms and theorems

- Conditional Probability, Total Probability, and Bayes' Theorem

  - Learning goal: distinguish between the probability of an event in the universal set, `S`, and the probability of the same event in a subset of `S`

    - Calculating the probability that two events happen to elements in the universal set
    - Calculate conditional probability and unconditional probability of an event
      - Given two events `A`, `B`, `P(A|B)` denotes probability of event `A` happening in the subset of `S` represented in `B`
        - That is a conditional probability
        - In contrast, `P(A)` denotes the probability of event `A` happening to elements in `S` (whether they are in `B` or not)
    - Calculate probability of `A` using information about joint probabilities and also definition of conditional probabilities
      - Law of total probability

  - Definition of Conditional Probability

    - Let `G` and `B` be two events, the conditional probability of event `G` given that `B` has occurred is denoted by `P(G|B)` and is defined as:

      - $$ {c}
        P(G|B)=\frac{P(G\cap B)}{P(B)}
        $$

      - The symbol `|` means "given that"

      - Similarly:

        - $$
          P(B|G)=\frac{P(B\cap G)}{P(G)}
          $$

    - 1st implication: product rule

      - We may calculate the probability of the intersection of two events if we know the conditional probability of one given the other and unconditional probabilities

      - $$
        P(G\cap B)=P(G|B)P(B)=P(B|G)P(G)
        $$

  - Bayes' Theorem

    - If you know the conditional probability `P(B|G)` you are able to calculate the inverse probability `P(G|B)`, if you also happen to know the total probabilities of the two events using Bayes' formula:

      - $$
        P(G|B)=\frac{P(B|G)P(G)}{P(B)}
        $$

  - Law of Total Probability of an Event

    - $$
      P(A)=P(A|B)P(B)+P(A|B^C)P(B^C)
      $$

    - More generally, if we have a partition of the sample space into `n` events `Gi`, then:

      - $$
        P(A)=\sum^n_{i=1}P(A|B_i)P(B_i)
        $$

  - Summary

    - Conditional probability, law of total probability, product rule, and Bayes' theorem broaden our ability to solve probability problems and make decisions under uncertainty when some extra information is known
      - They allow us to compute many more probabilities than we could compute with just the union rule, the complement rule, and other theorems derived from the axioms seen last time
      - They make decision making under uncertainty easier by giving us good decision rules
    - We can translate the information given regarding conditional events with a table, a tree, or just with the formulas, if we label what things represent what correctly
    - A student of probability must be able to indicate technically the probabilities of events, indicating which are the events , and also to represent that information verbally in everyday language

- Independence

  - Learning goals:

    - Appreciate the important role that independence plays in solving many problems and in finding the probabilities of outcomes in sample spaces resulting from repeated experiments
    - Understand what independence means
    - Definition of independence and apply the definition to prove independence
    - Product rule to calculate the joint probability of independent events
    - Show the implication of independence for conditional probability

  - Definition of Independence

    - Let `A` and `B` be two events defined on the same sample space

      - The events `A` and `B` are independent if:

        - $$
          P(A\cap B)=P(A)P(B)
          $$

      - A collection of events `A1`, `A2`, ..., `An` are independent if:

        - $$
          P(A_1\cap A_2\cap\ ...\ \cap A_n)=P(A_1)P(A_2)...P(A_n)
          $$

        - If `n` events are independent, any subsets of those events are also independent

    - We prove independence by applying the definition of independence

  - The Product Rule for Independence

    - Used to calculate joint probability of independent events

    - If two events `A`, `B` are independent, then we calculate their joint probability as follows:

      - $$
        P(A\cap B)=P(A)P(B)
        $$

  - Implication of Independence for Conditional Probability

    - $$
      P(G|B)=\frac{P(G\cap B)}{P(B)}=\frac{P(G)P(B)}{P(B)}=P(G)
      $$

    - The probability of event `G` happening in subgroup `B` is the same as the probability of `G` happening in the overall population

      - Group `B` is no different than the whole population

    - Seeing that event `B` has happened doesn't change our initial probability of event `G` happening

    - The prior probability of event `G` is the same as the posterior probability of `G`

  - Summary

    - Applied the definition to prove independence
    - Showed that independence implies that the conditional probability of an event `A` given `B` equals the unconditional probability of `A`
    - Applied independence and previously learned probability rules to different contextual problems

- Judgements Under Uncertainty

  - The Representativeness Heuristic
    - How likely is `X` to be a member of category `Y` vs. how much does `X` resemble the stereotype of `Y`
    - What's wrong with using representativeness?
      - The likelihood that `X` is a member of category `Y` depends on how many `Y`s there are
        - That is, depends on the prior probability of `Y`
  - What Can You Do About It?
    - Now that you know it exists, you are better able to recognize it in your own life and correct for it
      - Consider prior probabilities
      - Be wary of small samples



## Lecture 3:

- 

