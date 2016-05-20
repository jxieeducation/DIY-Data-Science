##The DIY Guide to PyEvolve

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/pyevolve?pixel)](https://github.com/igrigorik/ga-beacon)

_Please make [Pull Requests](https://github.com/jxieeducation/DIY-Data-Science/pulls) for good resources, or create [Issues](https://github.com/jxieeducation/DIY-Data-Science/issues) for any feedback! Thanks!_

----------
###Table Of Contents
* [Learn By Example](#learn-by-example)
* [Theory](#theory)
* [Documentation](#documentation)

----------

PyEvolve is a library for genetic algorithms. Genetic algorithm is an optimization technique that has applications such as hyperparameter tuning, or any other hard search problem.

###Learn By Example
_The goal of this section is to get you hands on ASAP._

#####[Hello World](http://pyevolve.sourceforge.net/getstarted.html#final-source-code)
* Define an eval function to calculate fitness
* Genome deals with the encoding, initialization, mutation, crossover of the population
* GA deals with hyperparameters such as generations, mutation rate and crossover rate

#####[Interactive Mode](http://pyevolve.sourceforge.net/getstarted.html#the-interactive-mode)
* Visualizations of population and fitness
* Does not work on Macs, [workaround](http://blog.christianperone.com/2009/02/the-pyevolve-interactive-mode-on-mac-os/)

#####[More parameters example](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex2_realgauss.py)
* Changed range of the genome [here](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex2_realgauss.py#L18)
* Gaussian mutator [here](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex2_realgauss.py#L24)
* Selection algorithm is changed as well [here](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex2_realgauss.py#L31)

#####[Harder Eval Function](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex3_schaffer.py)
* Schaffer F6 is a harder eval func [visualization](http://www.cs.unm.edu/~neal.holts/dga/benchmarkFunction/schafferf6.html)
* Termination criteria [here](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex3_schaffer.py#L19) and [here](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex3_schaffer.py#L34)

#####[Maximize to Minimize](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex4_sigmatrunc.py)
* Minimize instead of maximize [here](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex4_sigmatrunc.py#L34)
* Scaling the fitness score to better evaluate the scores [here](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex4_sigmatrunc.py#L37)

#####[Callback](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex5_callback.py)
* Callback is called after every generation [here](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex5_callback.py#L35)

#####[2D Search](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex9_g2dlist.py)
* Good for grid based search problems such as the nqueen problem

#####[1D Binary String Instead of List](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex10_g1dbinstr.py)
* An extreme case for the normal G1DList
* Useful for binary string problems

#####[Allele Example](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex11_allele.py)
* Alleles designed for discrete and categorical data instead of real and continuous data
* Categorical data example [here](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex11_allele.py#L44)

#####[Genetic Programming Example](https://github.com/perone/Pyevolve/blob/master/examples/pyevolve_ex18_gp.py)
* Genetic programming is a branch of genetic algorithms
* Computer programs are encoded as a set of genes that are then modified to produce a target output

----------

###Theory
_The goal of this section is to explain the background behind the package_

#####Genetic Algorithm
* [GREAT GREAT tutorial](http://techeffigytutorials.blogspot.com/2015/02/the-genetic-algorithm-explained.html)
* [Also good tutorial](http://geneticalgorithms.ai-depot.com/Tutorial/Overview.html)
* [Complete and detailed tutorial](http://obitko.com/tutorials/genetic-algorithms/) (First few pages are boring though)
* [Quora discussions](https://www.quora.com/topic/Genetic-Algorithms)

#####Encoding
* [Great visualizations](http://www.obitko.com/tutorials/genetic-algorithms/encoding.php)
* [Technical poster](http://www.ijarcsse.com/docs/papers/Volume_4/1_January2014/V4I1-0373.pdf)

#####Selector
* [Great visualization](http://www.obitko.com/tutorials/genetic-algorithms/selection.php)

#####Mutator & Crossover
* [Great visualization](http://www.obitko.com/tutorials/genetic-algorithms/crossover-mutation.php)
* [Research gate discussion](https://www.researchgate.net/post/What_is_the_role_of_mutation_and_crossover_probability_in_Genetic_algorithms)
* [5 Mutations](http://www.geatbx.com/docu/algindex-04.html)

#####Genetic Programming
* [Great intro](http://www.geneticprogramming.com/Tutorial/)
* [Quora discussions](https://www.quora.com/topic/Genetic-Programming-1)


----------

###Documentation
_The goal of this section is to reference more parameters and implementation details_

* [Git Repo](https://github.com/perone/Pyevolve/tree/master/pyevolve), [Official Documentation](http://pyevolve.sourceforge.net/)
* GSimpleGA - [Code](https://github.com/perone/Pyevolve/blob/master/pyevolve/GSimpleGA.py) - [Documentation](http://pyevolve.sourceforge.net/module_gsimplega.html)
* Selectors - [Code](https://github.com/perone/Pyevolve/blob/master/pyevolve/Selectors.py) - [Documentation](http://pyevolve.sourceforge.net/0_6rc1/module_selectors.html)
* Scaling - [Code](https://github.com/perone/Pyevolve/blob/master/pyevolve/Scaling.py) - [Documentation](http://pyevolve.sourceforge.net/0_6rc1/module_scaling.html)
* Crossover - [Code](https://github.com/perone/Pyevolve/blob/master/pyevolve/Crossovers.py) - [Documentation](http://pyevolve.sourceforge.net/module_crossovers.html)
* Initializators - [Code](https://github.com/perone/Pyevolve/blob/master/pyevolve/Initializators.py) - [Documentation](http://pyevolve.sourceforge.net/module_initializators.html)
* G1DList - [Code](https://github.com/perone/Pyevolve/blob/master/pyevolve/G1DList.py) - [Documentation](http://pyevolve.sourceforge.net/module_g1dlist.html)
* G1DBinaryString - [Code](https://github.com/perone/Pyevolve/blob/master/pyevolve/G1DBinaryString.py) - [Documentation](http://pyevolve.sourceforge.net/module_g1dbinarystring.html)
* G2DList - [Code](https://github.com/perone/Pyevolve/blob/master/pyevolve/G2DList.py) - [Documentation](http://pyevolve.sourceforge.net/0_6rc1/module_g2dlist.html)

