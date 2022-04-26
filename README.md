# STfDS_Assignment3
### Ravida Saitova, BS18-DS01
#### April 2022

#### the colab original file with edit history could be found here: https://colab.research.google.com/drive/1gHOJGsIgJzvLDRNthJmg4X_f_kxeUPQt?usp=sharing

#  Application of Sampling

The goal for this homework is to implement an optimization algorithm called Simulated Annealing (SA). It is based on sampling and the optimization procedure is similar to the Metropolis-Hastings (MH) algorithm. Because the optimization is based on sampling, SA allows to optimize even non-differentiable functions, and thus it is applicable to optimizing combinatorial problems. 

## Motivation

A is a stochastic global optimization algorithm. As many other randomized algorithms, SA appears to be surprisingly simple, yet efficient at achieving its task (given conditions). The name and inspiration for the algorithm come from metallurgy, where controlled heating and cooling of the material allows it to form larger crystalline structure and improve properties. A popular description of the method can be found on Wikipedia page.

## Algorithm

Fuction of Simulated Annealing:
1. Sample initial $x_0$, set time step $t = 0$;
2. Set initial temperature T. To avoid problems with numerical overflow when calculating the exponent, set the temperature comparable with the initial value of the system’s energy;
3. Generate $x'$ from $g(x'|xt)$. For continuous problems, the common solution
is to use the normal distribution;
4. Calculate acceptance ratio $\alpha = \frac{p(x')}{ p(x_t)}$ ;
5. Generate $u ∼ U(0, 1)$. If $u \leq \alpha$, accept the new state $x_{t+1} = x'$ , otherwise propagate the old state. Pass $x_t+1$ to the output of the sampler;
6. Reduce temperature T. Temperature annealing does not have to take place on every iteration. The temperature can be decreased every N iteration as well. There is no strict rule about this;
7. Increment t;
8. Repeat 2-8 until cooled down. The solution can be sampled before the
system is cooled down, but we have no way of knowing whether this was
the optimal solution
