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



## Lecture 3: Random Variables and Cumulative Distributions

- Discrete Variables

  - Introduction

    - In the study of probability we start with sample spaces and probability measures, but modeling real problems leads very quickly to the need to use function as a way of describing experiments
    - Generally these functions are real-valued and they measure some relevant information about an experiment or a process having probabilities associated with the different outcomes or states of the process
    - This is simply saying that the object we are usually interested in is a function defined on some sample space where there is a probability measure

  - Goal:

    - Appreciate the convenience of summarizing the outcomes of the experiments that interest us with a function call random variables and its probability mass function
    - We will learn to create tables (or a mathematical formula) for discrete random variables associated with sample spaces to which we have assigned a probability measure
      - We will call the most important table or formula PMF
    - We will use the PMF as a model for real problems
    - We will learn to calculate the expectation, variance, and standard deviation of a random variable using the PMF

  - Definition of Discrete Random Variable

    - A function whose domain are events in a discrete sample space and whose range is the set of real numbers is called a random variable
      - If the random variable is denoted by `X` and has as  a domain the sample space `S = {o1, o2, ..., on}`, then we write `X({ok, ..., ok})`, for the value of `X` that is shared by each of the elements in the event `{ok, ..., oj}`

  - Definition of Probability Mass Function of a Discrete Random Variable

    - A PMF of a finite random variable summarizes the unique values of the random variables and the probability of seeing those unique values
      - To find that probability we find out the probabilities of the outcomes in `S` that have that value of the random variable and add those probabilities
    - Alternative representations of PMFs:
      - Table (if the random variable doesn't have too many values)
      - Graph
      - Formula (in some well known PMFs)

  - Expectation, Variance, and Standard Deviation of a Discrete Random Variable

    - Expected value of a discrete random variable `X`:

      - Center of gravity of the PMF

      - $$
        \mu_X=E(X)=\sum_xxP(X=x)
        $$

    - Variance of a discrete random variable `X`:

      - Average of the square distance of values of `X` from the expected value

      - $$
        \sigma^2_X=Var(X)=E[(X-\mu_X)^2]=\sum_x(x-\mu_X)^2P(x)
        $$

    - Solving the units problem of variance:

      - The standard deviation of a discrete random variable `X`

      - $$
        \sigma=SD(X)=\sqrt{Var(X)}
        $$

  - Summary

    - Put in more compact form, from scratch, the outcome of an experiment and their probabilities
    - Create tables (or a mathematical formula) that helped us find answers without having to do the longer calculations we had done so far
      - We need everything from lectures 1-2 also
    - Calculate the expectation, variance, and standard deviation of a random variable

-  Continuous Variables

  - Goals

    - Appreciate the generality of the concepts already learned and the power of mathematics to allow us to generalize them
    - Continuous sample spaces need calculus for us to be able to answer the usual probability, expectations, and other probability questions we have about experiments
    - Families of continuous random variable are conspicuous in many domains of nature and human endeavors
      - It is important that we can apply what we learned to them

  - Introduction

    - If a measurement can take any value in an interval in a real line, then it is not possible to assign a probability to every point, becuase there are infinite points
      - The `P(S)` would be greater than `1` and the axioms would not be satisfied
    - Assigning probability of `0` to each point would not make sense either, the axioms must be satisfied
    - A convention to avoid the problem is the concept of probability density function

  - Density Function of a Continuous Random Variable

    - Suppose the simple events of a sample space can be indexed by the real number `x`

      - Let `a` be the smallest possible simple event (which could be `-INF`) and `b` the largest (which could be `+INF`)
      - Any other real number in between is allowed

    - If a function `f(x)` exists such that:

      - $$
        f(x)\ge0,a\le x\le b\\
        \int^a_bf(x)dx=1\\
        \text{For event }B=\{k<x<m\},P(B)=\int^m_kf(x)dx
        $$

      - The function `f` is called the probability density function (PDF) of the random variable `X`, `a <= X <= b` and we say that `X` is a continuous random variable

        - We could write the range of random variable as `a < X <= b` or `a <= X < b` or `a < X < b` and it would all be the same range

    - We can make a nonnegative function a density function by finding the constant of proportionality that makes it so

    - The exponential family

      - Suppose an event happens at a constant rate `λ`

      - The random variable `X` measuring the time until the first event and the time between events is a random variable with range `[0, INF)` and has density function:

        - $$
          f(x)=\lambda e^{\lambda x},x\ge0
          $$

  -  Expectation, Variance, and Standard Deviation of a Discrete Random Variable

    - For the continuous random variable `X` with domain in the real line equal to `[a, b]`:

      - $$
        \mu_X=E(X)=\int^b_axf(x)dx\\
        E(X^k)=\int^b_ax^kf(x)dx\\
        E(g(X))=\int^b_ag(x)f(x)dx\\
        \sigma^2=E[(X-\mu_X)^2]=\int^b_a(X-\mu_X)^2f(x)dx=E(X^2)-[E(X)]^2
        $$

  - The Uniform Family

    - A uniform random variable `X` on an interval `(a, b)` is a uniform random variable if its density function `f(x)` is constant on `(a, b)` and `0` elsewhere

    - $$
      f(x)=\frac{1}{b-a},a<x<b
      $$

  - Summary

    - Continuous sample spaces need calculus for us to be able to answer the usual probability, expectations and other probability questions we have about experiments
    - Review of expectation and variance, for continuous random variables
      - Seeing the common threads between the discrete and the continuous
      - We defined them in general, and illustrated the definitions with several examples

- Cumulative Distributions

  - Goals

    - To be flexible: we use what we can , depending on what we know, always
    - Define and calculate the cumulative distribution function given a density function
    - Calculate probabilities using the CDF when it's known
    - Define and calculate percentiles using the CDF
    - Using the CDF as a method to find the distribution of a function of a random variable

  - CDF of a Continuous Random Variable

    - If `X` is a continuous random variable with density `f(x)`, then the cumulative distribution function is a function `F` from `R -> R` such that:

      - $$
        F(X)=Prob(X\le x)
        $$

    - The limit of `F(X)` as `X` goes to infinity is `1`, and as `X` goes to negative infinity is `0`

    - Example:

      - $$
        f(x)=\lambda e^{-\lambda t}\\
        F(x)=1-e^{\lambda x},x\ge0\\
        P(a\le X\le b)=F(b)-F(a)
        $$

  - Property of the CMF of a Continuous Random Variable `x`

    - The density is the derivative of the CDF with respect to `x`

    - $$
      f(x)=\frac{dF(x)}{dx}=\lambda e^{-\lambda t},x\ge 0
      $$

  - Percentiles

    - We define the 100th percentile of a continuous variable `X` with domain `[a, b]` as the value `c` of the random variable such that:

      - $$
        F(c)=P(X\le c)=\int^c_af(x)dx=q
        $$

  - Density of Functions of a Continuous Random Variable

    - Let `X` be a random variable with density `f(x)`
    - Finding the expected value or variance of a linear function of a continuous random variable `g(x)` doesn't require knowing the probability distribution of `g(x)`; only the equation of `g(x)` is required and `f(x)`
    - If we wanted to compute probabilities for the function fo the random variable, we will need the density of that function
      - A more complicated topic is to find the actual density of that function of the random variable
    - If `X` has a density function `f(X)`, and if `U` is some function of `X`, then we find `F(u) = P(U <= u)` directly by integrating `f(X)` over the region for which `U <= u`
      - We can find the probability density function for `U` by differentiating `F(u)`

  - Summary

    - Defined and calculated the cumulative distribution function given a density function
    - Calculated probabilities using the CDF when it's known
    - Defined and calculated percentiles using the CDF
    - Used the CDF as a method to find the distribution of a function of a random variable



## Lecture 4: Sampling, Poisson Model, and LOTUS

- Random Sampling

  - Besides avoiding bias, why is random sampling desirable
    - Random sampling has properties that are well understood thanks to probability theory, whereas the properties of other methods are unknown

  - Goal: to comprehend that we can be transparent only when we do random sampling because:
    - We can use mathematical urn models to see the different in number of samples obtained with or without replacement
    - We can calculate probability of an event when sampling with or without replacement
    - We can calculate probability of obtaining a number of success when sampling with or without replacement
  
  - Goal: to realize that a simple probability density function model can help us answer important questions, when we translate from everyday language to the more technical language of probability
  
    - We will go through the type of activity that a data scientist would do to use probability to answer a research question
  
  - Lognormal Probability Model for a Continuous Nonnegative Random Variable
  
    - $$
      f(y)=\frac{1}{y\sqrt{2\pi\sigma^2}}e^{-\frac{(\log y-\mu)^2}{2\sigma^2}},0<y\le\infty,\sigma>0\\
      E(y)=e^{\mu+\frac{\sigma^2}{2}}\\
      Var(y)=(e^{\sigma^2}-1)e^{2\mu+\sigma^2}
      $$
  
    - If the random variable `Y` is lognormally distributed with that expected value and that variance, then:
  
      - $$
        \log(y)\sim N(\mu,\sigma^2)
        $$

  - Process:

      - Data
        - Probability modeling of the whole population guided by the distribution of data
        - Estimation of the population model and more probability models for property of the estimated model

- The Poisson Model

  - Goal: increase awareness of how the same probability models that tell us probabilities of events under usual random conditions can help us detect anomalies and appreciate the combination of models to solve more complex problems

    - Learn how to identify a Poisson experiment
    - Learn the formula for the Poisson probability model, its expectation, variance, moment generating function, expectations of functions of a Poisson random variable
      - Combining the Poisson with other models

    - Learn to determine when we are talking about a Poisson extended period

  - Poisson random variables are present in uniform distributions

  - When a count per unit of time or space is not a Poisson random variable

    - Epidemics, contagion: the occurrence of one case of mumps increases the probability of seeing another case nearby
      - Event occurrences clustered together

    - Overdispersion: event occurrences more dispersed than expected
      - e.g., seeing a territorial animal decreases the probability of seeing another animal nearby

  - The Poisson Random Variable

    - Probability Mass Function:

      - $$
        P(Y=y)=\frac{\lambda^ye^{-\lambda}}{y!},y=0,1,2,...,\lambda>0\\
        E(Y)=\lambda,Var(Y)=\lambda
        $$

      - `λ` is the parameter of the Poisson model

        - Affects the location of the distribution and its shape

  - The grid for which we know the rate could be time, space, volume, distance, etc.

    - Examples:
      - The number of calls to an office telephone per business hour
      - The number of atoms decaying per sample of some radioactive substance
      - The number of mutations carried per individual in a population
      - The number of seeds successfully germinated per mother plant
      - The number of failures per power plant pump

  - Poisson Extended Period

    - Example:
      - Suppose they tell us that the `X`, number of people entering a hospital per hour, is expected to be 2
        - `λ = 2` for the Poisson model

      - But they ask us for the probability that a total of 3 people enter in 2 hours
        - In this case, the model to use is the model for `Y` = number of people entering per 2 hours
          - `λ = 4` for this model

    - In a Poisson extended period, the new `λ` is proportional to the old `λ`

  - Summary

    - Distinguished between when a Poisson model makes sense to use as a model and when it does not make sense to use it
    - Learned the formula of the Poisson PMF, its expectation, variance, and used it to solve simple and complex problems
    - Learned what Poisson extended period is and applied the concept

- LOTUS

  - $$
    E(g(x))=\sum_xg(x)P(x)\\
    E(g(x))=\int_xg(x)f(x)dx
    $$

  - Allows for the discovery of:

    - The linearity of the expected operator
    - A particular property of variance

  - Linearity of Expected Operator

    - Discrete Case:

      - $$
        g(x) = a + bx\\
        E(g(x))=\sum_x(a+bx)P(x)\\
        E(g(x))=\sum_xaP(x)+\sum_xbxP(x)\\
        E(g(x))=a\sum_xP(x)+b\sum_xxP(x)\\
        E(g(x))=a+bE(x)
        $$

    - Continuous Case:

      - $$
        g(x)=a+bx
        E(g(x))=\int_x(a+bx)f(x)fx\\
        E(g(x))=\int_xaf(x)dx+\int_xbxf(x)dx\\
        E(g(x))=a\int_xf(x)dx+b\int_xxf(x)dx\\
        E(g(x))=a+bE(x)
        $$

  - Variance Shortcut

    - $$
      Var(x)=E(x^2)-\mu_x^2
      $$

      - $$
        \sigma_x^2=E[(x-\mu_x)^2]=E[(x^2+\mu_x^2-2\mu_xx)]\\
        \sigma_x^2=\sum_x(x^2+\mu_x^2-2\mu_xx)P(x)\\
        \sigma_x^2=\sum_xx^2P(x)+\sum_x\mu_x^2P(x)-\sum_x2\mu_xxP(x)\\
        \sigma_x^2=E(x^2)+\mu_x^2\sum_xP(x)-2\mu_x\sum_xxP(x)\\
        \sigma_x^2=E(x^2)+\mu_x^2-2\mu_x(\mu_x)=E(x^2)-\mu_x^2
        $$

    - $$
      Var(a+bx)
      $$

      - $$
        Var(a+bx)=\sum_x(a+bx-E(a+bx))^2P(x)\\
        Var(a+bx)=\sum_x(a+bx-(a+\mu_x))^2P(x)\\
        Var(a+bx)=\sum_x(b(x-\mu_x))^2P(x)\\
        Var(a+bx)=\sum_xb^2(x-\mu_x)^2P(x)=b^2\sum_x(x-\mu_x)^2P(x)\\
        Var(a+bx)=b^2Var(x)
        $$





## Lecture 5:

- 

