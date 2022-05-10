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




## Lecture 5: Discrete Models

- The Binomial Model

  - Goal: to understand how useful probability models are to guide us in the modeling of random variables found in research

    - Define a Bernoulli random variable and its expected value and variance
    - Define the Binomial random variable and its expected value and variance
    - Use the Binomial model when the parameter is known to answer questions
    - Have a framework for conducting empirical analysis of a random variable that can be modeled with the Binomial model

  - Bernoulli Random Variables

    - Have a value of either 0 or 1 (is binary)

      - $$
        P(X=x)=\begin{cases}1-p,&x=0\\p,&x=1\end{cases}
        $$

    - If the variable has a probability `p` to have a value of 1:

      - $$
        \mu_x=E(X)=\sum_xxP(X=x)=0(1-p)+1(p)=p\\
        \sigma_x^2=Var(X)=E[(X-\mu_x)^2]=\sum_x(x-\mu_x)^2P(x)=(0-p)^2(1-p)+(1-p)^2(p)\\
        =p(1-p)
        $$

    - We say that `X ~ Ber(p)`

  - Binomial Model

    - $$
      P(X=x)={n\choose x}p^xq^{n-x},x=0,1,2,...,n
      $$

      - `n` is the length of the sequence (the sample size)
      - `p` is the probability of success in each trial of the sequence

    - Assume:

      - All sequences in the sample space `S` have the same number of trials
      - `p` is the same in each of the `n` trials in the sequence
      - Independent Bernoulli trials (binary outcome in each independent trial)

    - $$
      E(X)=\sum_xxP(X=x)=\sum_xx{n\choose x}p^xq^{n-x}=np\\
      Var(X)=\sum_x(x-\mu_x)^2{n\choose x}p^xq^{n-x}=nqp
      $$

      - `q = 1 - p`

    - Be aware that with a large enough sample, you could approximate the Binomial model with a Gaussian distribution

  - Summary

    - We defined a Bernoulli random variable and its expected value and variance because a Binomial is a sequence of Bernoullis
    - We defined the Binomial random variable and its expectation and variance
      - The proof of the latter will be done separately

    - We were able to use the Bernoulli and Binomial when their parameters are known to answer questions
    - We acknowledged that the estimates of the parameters of the binomial obtained with data sampling are not the true parameters

- The Hypergeometric Model

  - Combinations Formula:

    - $$
      {n\choose x}=\frac{n!}{x!(n-x)!}
      $$

  - Relevant when the trials are not independent => probability of success changes from trial to trial

    - Ex) picking without replacement

  - Suppose:

    - We are randomly sampling `n` objects without replacement from a source that contains `a` successes and `N - a` failures
    - `X` represents the number of successes in the sample

  - $$
    P(X=x)=\frac{{a\choose x}{N-a\choose n-x}}{N\choose n}\\
    \text{for }x=\text{Max}(0,n+a-N),...,\text{Min}(a,n)
    $$

  - $$
    E(X)=n\times\frac{a}{N}\\
    Var(X)=\frac{na}{N}\times(1-\frac{a}{N})\times\frac{N-n}{N-1}
    $$

  - The binomial distribution can sometimes provide a reasonable approximation to the hypergeometric

    - Rough guideline: if we are not sampling more than 5% of the population, the binomial provides a reasonable approximation

- The Geometric Model

  - Goals:

    - Define a geometric random variable and know its expected value and variance
    - Use the geometric PMF when the parameter is known to predict events
    - Have a framework for conducting empirical analysis of a random variable that can be modeled with the geometric probability model

  - Model the random variable with a geometric PMF

    - Let `Y` be the number of Bernoulli trials it takes to find the first success
    - Note that the sequences of Bernoulli trials all have different length

  - $$
    P(Y=k)=(1-p)^{k-1}p,y=1,2,...
    $$

    - `p` is the same in each of the trials in the sequence
    - Independent Bernoulli trials (binary outcome in each independent trial)

  - $$
    E(Y)=\frac{1}{p}\\
    Var(Y)=\frac{1-p}{p^2}
    $$

  - Summary

    - Defined a geometric random variable and will know its expected value and variance
    - Used the geometric PMF when the parameter is known to predict events
    - Got a framework for conducting empirical analysis of a random variable that can be modeled with the geometric probability model

- The Negative Binomial Model

  - Goals

    - Define a negative binomial random variable and will know its expected value and variance
    - Use the distribution when the parameter is known to predict events
    - Have a framework for conducting empirical analysis of a random variable that can be modeled with the negative binomial probability model

  - Model the random variable with a negative binomial PMF

    - Let `Y` be the number of Bernoulli trials it takes to find the first `r` successes

  - $$
    P(Y=y)={y-1\choose r-1}p^r(1-p)^{y-r},y=r,r+1,...
    $$

    - `p` is the same in each of the trials in the sequence
    - Independent Bernoulli trials (binary outcome in each independent trial)

  - $$
    E(Y)=\frac{r}{p}\\
    Var(Y)=\frac{r(1-p)}{p^2}
    $$

  - Summary

    - Able to define a negative binomial random variable and know its expected value and variance
    - Able to use the distribution when the parameter is known to predict probabilities of events
    - Have a framework for conducting empirical analysis of a random variable that can be modeled with the negative binomial probability model

- The Gaussian Model

  - Goal: become aware of the important role the Gaussian model plays in measuring uncertainty when many factors are determining the value of a random variable and as an approximation to the binomial model

    - Indicate when the Gaussian density function is an appropriate model to measure uncertainty
    - State, without proof, the expected value and variance of a Gaussian random variable
    - Learn to calculate probabilities and percentiles for the Gaussian model using the Rossman/Chance app
    - Learn to convert any normal to a standard normal density and to express the value of a normal random variable in standard deviation units
    - Learn to apply the theoretical things learned to different contexts where the Gaussian density model is appropriate to measure our uncertainty

  - The Normal Random Variable

    - A random value is normal or Gaussian with parameters `μ` and `σ^2` if its probability density function is given by:

      - $$
        f(x)=\frac{1}{\sqrt{2\pi\sigma^2}}e^{\frac{(x-\mu)^2}{2\sigma^2}},-\infty<x<\infty,-\infty<\mu<\infty,\sigma>0
        $$

    - Features:

      - Bell-shaped and symmetrical
      - Mean, median, and mode are equal
      - Location is determined by the mean, `μ`
      - Spread is determined by the standard deviation, `σ`
      - The random variable has an infinite theoretical range: `-INF` to `INF`

  - The Empirical Rule

    - 68% of the distribution lies within one standard deviation of the mean
    - 95% of the distribution lies within two standard deviations of the mean
    - 99.7% of the distribution lies within three standard deviations of the mean

  - Recall that for any random variable with nonzero density in the domain `[a, b]`:

    - $$
      \mu_x=E(X)=\int^b_axf(x)dx\\
      E(X^k)=\int^b_ax^kf(x)dx\\
      E(g(X))=\int^b_ag(x)f(x)dx\\
      \sigma^2=E[(X-\mu_X)^2]=\int^b_a(X-\mu)^2f(x)dx=E(X^2)-\mu^2
      $$

    - Since the domain of a Gaussian is `[-INF, INF]`, we integrate from `-INF` to `INF`

  - Finding probabilities of normal random variables

    - Not easy mathematically, must be estimated

  - The Standard Normal Density

    - A normal distribution with mean 0 and variance 1

    - If we standardize a normal random variable `X` with parameters `μ` and `σ` in the following way:

      - $$
        Z=\frac{X-\mu}{\sigma}
        $$

    - The new standardizes normal random variable `Z` follows a standard normal distribution with `μ = 0` and standard deviation `σ = 1`

    - The advantages of presenting the information in `Z` version is that the measurement is then in standard deviations from the mean

  - Normal Approximation to the Binomial

    - If the sample size `n` is large and value of `p` is such that:

      - $$
        np>10\quad n(1-p)>10
        $$



## Lecture 6: Vector Random Variables

- Vector Random Variables: Introduction

  - Goal: to realize that more useful knowledge and predictive power is gained when we acknowledge the vector (multivariate) nature of information and use it according to the laws of probability

    - Construct joint bivariate discrete probability mass functions directly from a sample space
    - Calculate the total probability mass functions from a table of a joint PMF
    - Calculate total expectations, variance, and standard deviation
    - Define and determine independence of two discrete random variables in a table
    - Doing all of the above with both tables and formulas

  - Review: Total and Joint Probabilities

    - Ex) the factory with defective parts
    - We will do the same for other contexts, but the events will be values of random variables, numerical values that will allow us to put together different PMFs

  - Joint Probability Mass Function for a Vector Random Variable

    - Definition: let `X` and `Y` be discrete random variables, then the probability mass function of `X` and `Y` is given by:

      - $$
        P(x,y)=P(X=x,Y=y)\begin{cases}P(x,y)\ge0\\\sum\sum P(x,y)=1\end{cases}
        $$

      - Defined for all real numbers `x` and `y`

    - Can be given as a formula as well

      - Example:

        - $$
          P(X=x,Y=y)=\frac{1}{32}(x^2+y^2)
          $$
    
    - You may construct a table from a formula, but you would not do that if `X` or `Y` can take 1000 values
        - The formula would be much easier to work with
        - Abstraction with mathematics is there just to help us when things get too big to handle them as we would with a few numbers

- Building a Joint PMF to answer a research question

    - Ex) on randomly chosen Mondays, observe independent work-study students that may show up or not show up to work their shift

    - Methodology:

      - First think of what we might observe doing the random experiment

        - The sample space
        - Define your notation

      - Define the random variables of interest in our research question

      - Calculate the probability of each outcome

      - Summarize in one single joint PMF for `X` and `Y`

        - $$
          P(x,y)=P(X=x,Y=y)=\sum P(\{o_i\}\in S|X(o_i)=x\text{ and }Y(o_i)=y)
          $$

    - Extract as Much Information as We Can from the Joint PMF

      - Add across each row to obtain total probability of `X`
      - Add down each column to obtain total probability of `Y`
      - Use what we learned about univariate discrete PMFs to calculate expected value, variance, and standard deviation
    - Independence of 2 Discrete Random Variables

      - Definition: two discrete random variables `X` and `Y` are independent if the events `(X = x)` and `(Y = y)` are independent, i.e., if:

        - $$
          P(X=x,Y=y)=P(X=x)P(Y=y)\text{ for all }x\text{ and }y
          $$

      - If the condition doesn't hold for one pair, then we can conclude that they're not independent

        - If the condition holds for the first pair we try, then we must continue checking more pairs

    - If the Joint PMF is Given by a Formula, then Less Work Needs to be Done

      - We just need definitions of total probability mass function and review of the summation operator

      - Example:

        - $$
          P(X=x,Y=y)=\frac{1}{32}(x^2+y^2)\\
          P(X)=\sum_yP(X,y)=\sum_y[\frac{1}{32}(x^2)]+\sum_y[\frac{1}{32}(y^2)]=\frac{2}{32}(x^2)+\frac{1}{32}\\
          P(Y)=\sum_xP(x,Y)=\sum_x[\frac{1}{32}(x^2)]+\sum_x[\frac{1}{32}(y^2)]=\frac{14}{32}+\frac{4}{32}(y^2)
          $$

        - Using the definitions of expectation and variance, and properties of the summation operator, we can find:

          - $$
            \mu_x=E(X)=\sum_xxP(X=x)=\sum_x(\frac{2}{32}(x^3)+\frac{1}{32}x)=\frac{86}{32}=2.6875\\
            \sigma_x^2=Var(X)=\sum_x(x-2.6875)^2P(X=x)=\sum_x(x-2.6875)^2(\frac{2}{32}(x^2)+\frac{1}{32})\\
            =0.6836\\
            \sigma_x=\sqrt{0.6836}=0.8268
            $$

- Vector Random Variables: Conditional Probabilities

  - Goal: to realize that a conditional probability mass function is more accurate than an unconditional one when independence doesn't hold

    - How to use the joint bivariate discrete probability mass function table of two non-independent random variables, and the total probability mass function, to calculate the conditional probability mass functions for relevant subgroups
    - To calculate conditional expectations, variance, and standard deviation
    - To do all of the above but instead of using tables, using formulas
    - To construct joint PMFs given the unconditional PMFs of two independent random variables

  - Start with the Joint and Total PMFs

    - The total probability mass function is also called marginal probability, or prior probability, or unconditional probability mass function
      - Plainly speaking, it is called "the probability mass function when we have no additional information that allows us to be more specific"

    - If `X` and `Y` are not independent, then we need to be more precise in stating our probabilities of events corresponding to `X` and `Y`
      - Ex) "what is the probability of event `{ Y = 2 }` when `{ X  = 0 }` is true?"

  - Since `X` and `Y` are Not Independent, Calculate the Conditional PMF of `Y`

    - $$
      P(Y|X=x)=\frac{P(X=x\text{ and }Y)}{P(X=x)}
      $$

    - Notice that the conditional probabilities of `Y | X = 0` are not the same as the total probabilities

      - This happens when `X` and `Y` are not independent

  - Conditional Expectation, Conditional Variance, and Conditional Standard Deviation

    - $$
      E(Y|X=x)=\sum_yyP(Y|X=x)\\
      Var(Y|X=x)=\sum_y(y-E(Y))^2P(Y|X=x)
      $$

  - We Can Calculate Many More Conditional PMFs

  - If the Joint PMF is Given as a Formula, Less Work Needs to be Done

    - First find the general function
    - Then specialize it to the desired value

  - What Would the Conditional Probability Mass Function be if Two Discrete Random Variables `X` and `Y` are Independent?

    - First find the joint PMF
      - Since `X` and `Y` are independent, we can calculate the joint PMF by multiplying the probabilities found in the unconditional PMF

- Joint Behavior of Two Continuous Random Variables

  - Goal: to realize that by adding calculus to our bag of tools, we can generalize the concepts learned for discrete vector random variables to continuous vector random variables

    - Be able to calculate the joint probability of an event involving values of two continuous random variables using the joint probability density function
    - Be able to extract from the joint PDF the unconditional univariate PDFs
    - Be able to calculate unconditional expectations and variance
    - Be able to determine whether two continuous random variables are independent

  - Joint Probability of Two Continuous Random Variables

    - If `X` and `Y` are two continuous random variables, then the joint probability that values of `X` and `Y` lie in an interval `B` of the plane is calculated by the volume under the joint density function in that region

      - If region `B` is defined by intervals `a1, a2` for `X` and interval `b1, b2` for `Y`, then

        - $$
          P(a_1\le X\le a_2,b_1\le Y\le b_2)=\int^{a_2}_{a_1}\int^{b_2}_{b_1}f(x,y)dxdy
          $$

        - Where `f(x, y)` is the joint density function of `X` and `Y`, a nonnegative joint density function with volume under it throughout equal to `1`

  - Unconditional PDF of `X` and `Y`, `f(X)` and `f(Y)`

    - $$
      f(x)=\int^{\infty}_{-\infty}f(x,y)dy\\
      f(y)=\int^{\infty}_{-\infty}f(x,y)dx
      $$

    - The integration will be done over the domain of the corresponding variable, not necessarily infinity

      - We must watch out for the domain to find the densities correctly

  - Unconditional Expectations and Variance

    - $$
      \mu_x=E(X)=\int^{\infty}_{-\infty}xf(x)dx\\
      \sigma_x^2=\int^{\infty}_{-\infty}(x-\mu_x)^2f(x)dx=E(x^2)=[E(x)]^2\\
      \mu_y=E(Y)=\int^{\infty}_{-\infty}yf(y)dy\\
      \sigma_y^2=\int^{\infty}_{-\infty}(y-\mu_y)^2f(y)dy=E(y^2)=[E(y)]^2\\
      $$

    - The integration will be done over the domain of the corresponding variable, not necessarily infinity

      - We must watch out for the domain to find the densities correctly

  - Independence of Two Continuous Random Variables

    - Two continuous random variables `X` and `Y` are independent if:

      - $$
        f(x,y)=f(x)f(y)
        $$

  - Example: predicting the proportion of samples with certain amounts of total and type I impurities

    - Problem:

      - A certain process for production of an industrial chemical yields a product that contains two main types of impurities

      - For a certain volume of sample from this process, let `X` denote the proportion of total impurities in the sample, and let `Y` denote the proportion of type I impurities among all impurities found

      - Suppose that under investigation of many such samples, the joint distribution of `X` and `Y` can be adequately modeled by the following joint density function:

        - $$
          f(x,y)=\begin{cases}2(1-x),&0\le x\le1,0\le y\le1\\0&\text{elsewhere}\end{cases}
          $$

      - Find the proportion of samples having less than 50% impurities and proportion of type I impurities between 40% and 70%

        - $$
          P(x\le0.5,0.4\le y\le0.7)
          $$

    - Process:

      - $$
        P(x\le0.5,0.4\le y\le0.7)\\
        =\int^{0.7}_{0.4}\int^{0.5}_02(1-x)dxdy\\
        =\int^{0.7}_{0.4}[2x-x^2]^{0.5}_0dy\\
        =\int^{0.7}_{0.4}0.75dy\\
        =0.75y|^{0.7}_{0.4}=0.75(0.3)=0.225
        $$

    - Unconditional Probability Density Functions:

      - $$
        f(x)=\int^{\infty}_{-\infty}f(x,y)dy\\
        =\int^1_02(1-x)dy\\
        =2(1-x),0\le x\le1\\
        f(y)=\int^{\infty}_{-\infty}f(x,y)dx\\
        =\int^1_02(1-x)dx\\
        =(2x-x^2)^1_0\\
        =1,0\le y\le1\\
        $$


- Joint Behavior of Many Continuous Random Variables

  - If `xi` is continuous and independent:

    - $$
      f(x_1,x_2,...,x_n)=f(x_1)f(x_2)...f(x_n)
      $$

  - If `xi` is discrete and independent:

    - $$
      P(x_1, x_2,...,x_n)=P(x_1)P(x_2)...P(x_n)
      $$

  - If `x1, x2, ..., xn` are independent continuous and `f(x1) = f(x2) = ... = f(xn)`, then we say that they are independent, identically distributed (IID)

  - Examples:

    - Number of people per square meter in a mall
    - Time it takes a plane to reach flying altitude after take off




## Lecture 7: Correlation

- Bivariate Discrete Random Variables: Correlation

  - If two random variables are not independent, how related are they?

    - The answer to this question, if the two variables are linearly related, is given by the correlation coefficient

      - $$
        \rho_{X,Y}=\frac{Cov(X,Y)}{\sqrt{Var(X)}\sqrt{Var(Y)}}
        $$

      - $$
        Cov(X,Y)=E[(X-\mu_x)(Y-\mu_y)]=\sum_x\sum_y[(x-\mu_x)(y-\mu_y)]P(X=x,Y=y)
        $$

  - Goal: calculate the correlation between two discrete random variables that have a linear relation

    - Be able to calculate the covariance between two random variables directly from a joint PMF table, using as an example, the restaurant menu and the couple
    - Be able to calculate the correlation coefficient directly from the joint PMF table
    - Calculate covariance and correlation when the joint PMF is a function

  - If `X` and `Y` are not independent, then it makes sense to study the correlation

    - We start by calculating the covariance

      - We need the expected values of `X` and `Y` for covariance, so we must start by calculating those

      - We also need the variances of `X` and `Y` for correlation, so we calculate those next

      - Next, we must calculate the following for each cell of the joint probability table and then sum up the results:

        - $$
          [(x-\mu_x)(y-\mu_y)]P(x,y)
          $$

      - Finally, we plug in the covariance and solve

      - Note that correlation and covariance can both be negative values

  - Interpretation of the correlation coefficient

    - Closer to `+1`: stronger positive relation
    - Closer to `0`: very little linear relation
    - Closer to `-1`: stronger negative relation

  - If the joint PMF is given by a formula, we use the formula instead of a table

    - Example: the joint PMF of `X` and `Y` is given by:

      - $$
        P(X=x,Y=y)=\frac{1}{32}(x^2+y^2),x=0,1,2,3\text{ and }y=0,1
        $$

      - $$
        \mu_x=2.6875\\
        \mu_y=0.5625\\
        \sigma_x^2=0.6836\\
        \sigma_y^2=0.2461
        $$

      - $$
        Cov(X,Y)=\sum_x\sum_y[(x-2.6875)(y-0.5625)]\frac{1}{32}(x^2+y^2)=-0.0586
        $$

        - Plug in values from the function's discrete domain

      - $$
        \rho_{X,Y}=\frac{-0.0586}{\sqrt{0.6836}\sqrt{0.2461}}=-0.1428
        $$

  - If two discrete random values are not independent, how strong is the relation?

    - Depends on the joint PMF

- Bivariate Continuous Random Variables: Conditional Densities and Correlation

  - Calculate expectations and variances as before

  - Calculate covariance as follows:

    - $$
      E(xy)=\int_{x_1}^{x_2}\int_{y_1}^{y_2}(xy)f(x,y)dydx
      $$

    - $$
      Cov(x,y)=E(xy)-E(x)E(y)
      $$

  - Calculate correlation as before

- The Bivariate Gaussian Distribution

  - Goal: introduction to the world of regression analysis by figuring out where the regression line comes from

    - Joint bivariate normal and its multivariate matrix notation
    - Marginal distributions derived from a joint bivariate normal, which are univariate normal
    - Conditional distributions derived from a joint bivariate normal, which are univariate normal; finding probabilities; the regression line
    - The multinomial probability mass function

  - The Joint Bivariate Normal Density Function

    - $$
      f(x,y)=\frac{1}{2\pi\sigma_x\sigma_y\sqrt{1-\rho^2}}\text{exp}\{{-\frac{1}{2(1-\rho^2)}[(\frac{x-\mu_x}{\sigma_x})^2+(\frac{y-\mu_y}{\sigma_y})^2-2\rho(\frac{x-\mu_x}{\sigma_x})(\frac{y-\mu_y}{\sigma_y})]}\}
      $$

  - An Exception to `Cov(X, Y)`: The Independence Rule

    - If 2 random vairbales are independent, the covariance is `0` and so is the correlation
      - In general, covariance `0` doesn't imply independence

    - If `X` and `Y` follow a bivariate normal density, `Cov(X, Y) = 0` implies independence

  - Generalization: Multivariate Normal

    - In general, we say a `p`-dimensional vector random variable `Y` has a multivariate normal distribution if its density is given by:

      - $$
        f(y|\mu,\Sigma)=(2\pi)^{-\frac{p}{2}}|\Sigma|^{-\frac{1}{2}}\text{exp}\{-(y=\mu)^T\Sigma^{-1}(y-\mu)/2\}\\
        y=\begin{pmatrix}y_1\\y_2\\.\\.\\y_p\end{pmatrix},\quad\mu_y=\begin{pmatrix}\mu_1\\\mu_2\\.\\.\\\mu_p\end{pmatrix},\quad\Sigma=\begin{pmatrix}\sigma^2_1&\sigma_{1,2}&...&\sigma_{1,p}\\\sigma_{2,1}&\sigma_2^2&...&\sigma_2^p\\.&.&&.\\.&.&&.\\\sigma_{p,1}&...&...&\sigma_p^2\end{pmatrix}
        $$

  - Marginal Densities

    - $$
      f(x)\sim N(\mu_x,\sigma_x)\quad f(y)\sim N(\mu_y,\sigma_y)
      $$

    - $$
      f(x)=\int_{-\infty}^{\infty}f(x,y)dy=\frac{1}{\sqrt{2\pi\sigma_x^2}}\text{exp}\{-\frac{1}{2\sigma_x^2}(x-\mu_x)^2\},\quad-\infty<x<\infty\\
      f(y)=\int_{-\infty}^{\infty}f(x,y)dx=\frac{1}{\sqrt{2\pi\sigma_y^2}}\text{exp}\{-\frac{1}{2\sigma_y^2}(y-\mu_y)^2\},\quad-\infty<y<\infty\\
      $$

  - Conditional Densities

    - As in the general case:

      - $$
        f(X|Y)=\frac{f(x,y)}{f(y)}\quad f(Y|X)=\frac{f(x,y)}{f(x)}
        $$

    - Doing this in the bivariate normal case, we can obtain the conditional distributions:

      - $$
        f(Y|X=x)\sim N(\mu_{Y|X}=\mu_Y+\rho\frac{\sigma_Y}{\sigma_X}(x-\mu_X),\sigma_{Y|X}^2=(1-\rho^2)\sigma_Y^2)\\
        f(X|Y=y)\sim N(\mu_{X|Y}=\mu_X+\rho\frac{\sigma_X}{\sigma_Y}(y-\mu_Y),\sigma_{X|Y}^2=(1-\rho^2)\sigma_X^2)
        $$

      - Regression line

  - The Regression Line

    - The conditional mean of `Y` given `X` is called the regression line and is given by:

      - $$
        \mu_{Y|X}=\mu_Y+\rho\frac{\sigma_Y}{\sigma_X}(x-\mu_X)
        $$

    - The line represents the relation between `X` and `Y` as a linear regression

    - The intercept is:

      - $$
        \mu_Y
        $$

    - The slope is:

      - $$
        \rho\frac{\sigma_Y}{\sigma_X}
        $$

    - When we want to study the relation between two variables, it is assumed that we want to estimate that conditional expectation

      - So we fit the best possible line to the data (the regression line) and use that estimated line as an estimate of that conditional probability




## Lecture 8:

- 

