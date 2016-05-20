##The DIY Guide to PyEvolve

[![Analytics](https://ga-beacon.appspot.com/UA-61611403-2/jxieeducation/pyevolve?pixel)](https://github.com/igrigorik/ga-beacon)

_Please make [Pull Requests](https://github.com/jxieeducation/DIY-Data-Science/pulls) for good resources, or create [Issues](https://github.com/jxieeducation/DIY-Data-Science/issues) for any feedback! Thanks!_

----------
###Table Of Contents
* [Learn By Example](#learn-by-example)
* [Theory](#theory)
* [Documentation](#documentation)

----------

PyEvolve is a genetic algorithm library, which is a biologically-inspired optimization technique. This library enables us to solve search problems such as hyperparameter tuning.

###Learn By Example
_The goal of this section is to get you hands on ASAP. If the hello world example confuses you, try out the theory section first._

```pip install pyevolve```

#####[Hello World](http://bit.ly/23Zhyum)
* Define an eval function to calculate fitness
* Genome defines the encoding, initialization, mutation, crossover of the population
* GA assigns the search hyperparameters such as generations, mutation rate and crossover rate

#####[Interactive Mode](http://bit.ly/1TiD0uo)
* Visualizations of population and fitness
* Does not work on Macs, [workaround](http://bit.ly/1Tr00V1)

#####[More Parameters](http://bit.ly/1TiCRY0)
* Changed the range of the genomes [here](http://bit.ly/1TKf2CK)
* Gaussian mutator example [here](http://bit.ly/23ZhLO0)
* Selection algorithm is changed as well [here](http://bit.ly/1rXZjcI)

#####[Harder Search Problem](http://bit.ly/1OCJMEa)
* Schaffer F6 is a harder eval func [visualization](http://bit.ly/1rXYXTz)
* Termination criteria for early stopping [here](http://bit.ly/23ZhJ8P) and [here](http://bit.ly/1Xng5O8)

#####[Maximize to Minimize](http://bit.ly/22hMaYP)
* Minimize instead of maximize [here](http://bit.ly/1sv6Q2F)
* Scaling the fitness scores to better distinguish the good from the bad [here](http://bit.ly/1VcJfQ0)

#####[Callback](http://bit.ly/1TiDfFW)
* Callback is called after every generation [here](http://bit.ly/1Rcm5SM)
* Good for logging statistics of the population

#####[2D Problem Example](http://bit.ly/22hM7fk)
* Good for grid search problems such as the N-Queen problem

#####[1D Binary String Example](http://bit.ly/1TnvKrW)
* An extreme case for the normal G1DList
* Useful for binary string problems

#####[Allele Example](http://bit.ly/1sv6WHQ)
* Alleles are designed for discrete and categorical data instead of real and continuous data
* Categorical data example [here](http://bit.ly/1OCK51D)

#####[Genetic Programming Example](http://bit.ly/1U2PgMG)
* Genetic programming is a branch of genetic algorithms
* Computer programs are encoded as a set of genes that are then modified to produce a target output

----------

###Theory
_The goal of this section is to explain the background behind the package_

#####Genetic Algorithm
* [Awesome tutorial](http://bit.ly/1TtivJR)
* [Complete and detailed tutorial](http://bit.ly/1WFrZV2) (First few pages are boring though)
* [Quora discussions](http://bit.ly/1TnvFVl)

#####Encoding
* [Great visualizations](http://bit.ly/20djgaq)
* [Technical poster](http://bit.ly/22hMmXX)

#####Selector
* [Great visualization](http://bit.ly/1sv74qF)

#####Mutator & Crossover
* [Great visualization](http://bit.ly/1OQeXB6)
* [Research gate discussion](http://bit.ly/25cZAKQ)
* [5 Mutations](http://bit.ly/1TiDuAY)

#####Genetic Programming
* [Great intro](http://bit.ly/25cZD9q)
* [Quora discussions](http://bit.ly/1qxL9Oh)


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

