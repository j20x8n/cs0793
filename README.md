java c
Financial computing 
Final exam 
Fall 2024 
Question 1: The trinomial model for pricing options
In class, we discussed the binomial model for pricing European options. Here, we extend this to the so-called trinomial model, where we assume that an asset can increase in price (“up-tick”), decrease in price (“down-tick”), or stay the same in two subsequent time steps.
Specifically, we have the following cases:

Additionally, we may derive that the probabilities of an “up-tick” (pu), a “down-tick” (pd), or staying the same (pm) as:

(a) Show that if λ = 1, then the trinomial lattice and the binomial lattice models are identical.
(b) Assume λ =√2. Implement in C++ the trinomial lattice. Assume that we divide our expiry time T into nsteps discrete time units (i.e., ∆t = nsteps/T). Use your code to calculate the call and put prices for a European style. option. You may use the code that we wrote in class and adapt it as needed.
(c) Expectedly, your code will be very slow. Implement the memoized version of your trinomial lattice. Your answers in part (b) and (c) should be identical, but the memoized version should be able to run faster.
NOTE: If you successfully code part (c), then you can omit part (b). That is, part (c) supersedes part (b). If you are unsure about your memoized version, then code both to secure partial credit.
Good luck!
Question 2: Pricing a barrier option using simulation in C++ 
In class, we talked a lot about the distribution of the price for a single asset/instrument, and agreed that it follows a log-normal distribution. We also discussed about continuous barrier options: specifically we want you to focus on “up-and-out” and “up-and-in” barriers here.
(a) Assume that we know the starting price S0, the expected return r, the volatility σ, and the expiry time T of a single asset. We also have the option barrier B and the exercise (strike) price E. Create the necessary C++ code that simulates the path of that asset when the time T is discretized into nsteps time-steps (that is, the time steps are equal to ∆t = nsteps/T). To test your code, feel free to use nsteps = 30.
(b) Use your code from part (a) to simulate more paths; specifically, create Nsims paths for the asset. Then, estimate the probability of hitting the barrier from below. Estimate this probability for changing values of the barrier from 1.5 · S0 to 6 · S0.
(c) Finally, using simulation, price the continuous barrier call option (for the “up-and-out” and “up-and-in” cases). Plot the change in the price as the number of simulations changes from Nsims = 10 to Nsims = 1000 in increments of 10. Your code should produce two text files as an output that has the “up-and-out” call option price for each number of simulations in each line of the first file and the “up-and-in” call option for each number of simulations in each line of the second file.
NOTE: As an example, feel free to use S0 = $1, and T = 5 years, with r = 0.08 and σ = 30%. However, please define these variables in the beginning of your code so that I can edit and change them at will! Thanks in advance.
Question 3: Network optimization in pricing 
We have discussed the binomial mode代 写Financial computing Final exam Fall 2024C/C++
代做程序编程语言l in class for pricing options. In this question, we will generalize this to more than two possible outcomes (“up-tick” and “down-tick”). We will also try to use a metric to quantify how prominent a specific price at a time is at predicting the final stock price.
Specifically, assume that we have an asset with expiration date T that is decomposed into dis-crete time steps (like in the binomial model we saw in class) such as ∆t = nsteps/T. Assume that nsteps = 30 for the duration of the exercise. Now, for a starting asset price of S0, the next asset price at time ∆t will be S1, followed by S2, and so on.
This is where it gets interesting: assume that the asset price is random with a probability dis-tribution written as vector π(t). That is, at each time step t, the probability that the asset price moves by current price St = s to another price St+1 = s0 is equal to p(s,st)0. Moreover, assume that the possible prices that an asset can take are already known and are equal to s1, s2, . . . , sm. Hence, an asset can move from S0 = s to some price sk at time t = 1, followed by price s` at time t = 2 with probability p(0)s,skand then p(1)sk,s` . For simplicity, we assume that each move-ment is independent, and hence the probability of path S0 = s → sk → s` is equal to p(0)s,sk·p(1)sk,s` .
For example, if you have 6 time steps and m = 6 possible stock prices, then you should have the network of Figure 1.
(a) Formulate a linear program (a mathematical formulation with only linear constraints) that identifies the most probable path from the start (the node at time t = 0 that has price S0) to a terminal node (any of the nodes in the last time step). Note that, by construction, every such path will have exactly nsteps − 1 arcs.
(b) Based on your linear program in part (a), write a new linear program that identifies nscenarios most probable disjoint paths (as a whole). For the purposes of this exercise, as-sume that two paths are disjoint if they are not using any of the same edges. See Figure 2 for an example of three disjoint paths.
NOTE 1: Your formulation (linear program) in part (b) should return a set of paths that cumulatively have the maximum probability. For example, assume that we have 5 paths with probabilities equal to 40%, 25%, 25%, 5%, 5%. Furthermore, assume that the first (most probable) path uses at least one edge that is also present in the second path; as well as another edge that is in the third path. Then, your linear formulation should return paths 2 and 3 as the top 2 most probable paths (with a cumulative probability of 50%), rather than path 1 and either of paths 4 or 5. Please let me know if you need more clarification on this point.
NOTE 2: You do not need to write any code for this exercise.

Figure 1: An example of the network of prices for 6 time steps. Notice that it is a complete m-partite graph, where every node in a previous time step can eventually lead to any node in the subsequent time step.

Figure 2: An example of three disjoint paths. Note that we are allowed to visit the same node! However, we are not allowed to use the same arc for two paths or more.







         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
