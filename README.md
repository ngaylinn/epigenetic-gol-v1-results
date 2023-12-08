Project by Nate Gaylinn:
[github](https://github.com/ngaylinn),
[email](mailto:nate.gaylinn@gmail.com),
[blog](https://thinkingwithnate.wordpress.com/)

Built from [https://github.com/ngaylinn/epigenetic-gol-v1](
https://github.com/ngaylinn/epigenetic-gol-v1) on December 8, 2023. Only
six of the eight FitnessGoals are used here, because of some unresolved bugs.

This repository holds the results and analysis from a collection of experiments
testing out an "epigenetic algorithm" that searches for interesting examples of 
Conway's Game of Life. The intent was to use an evolutionary algorithm to
design the search space for an evolutionary algorithm.

For more information on the motivation, design, and execution of the project
that produced these results, check out the [README file](https://github.com/ngaylinn/epigenetic-gol-v1/README.md)
for the source repository or this [slide deck](https://docs.google.com/presentation/d/1ZIYj8Rg4xPHukQ-Glk9_IZTgimEYh5dtWsyXrbkX9Dc/edit?usp=sharing).

Overview of files:
- `random_initial_population.png`: A sample of randomly generated phenotypes
  from a random set of species with no evolution.
- `experiments`: A collection of directories, one for each FitnessGoal.
- `experiments/GOAL/state.pickle`: A record of experiment status, indicating
  completion among other things.
- `experiments/GOAL/results.pickle`: A record of experiment results, from which
  all the visualizations were generated.
- `experiments/GOAL/species_fitness.png`: A chart showing how well this
  algorithm evolved species to suit this FitnessGoal over 150 generations.
- `experiments/GOAL/best_organism_from_trial_X_fYYYY`: A video of the most fit
  phenotype (having fitness YYYY) from trial number X of this FitnessGoal.
- `experiments/GOAL/best_species_from_trial_X_fYYYY`: A directory with results
  from the Xth attempt to evolve a species for this FitnessGoal (having fitness
  YYYY).

Files in each trial directory:
- `best_organism_fXXXX`: A video of the most fit organism of this species from
  this trial (having fitness XXXX).
- `organism_fitness.png`: A chart showing how well organisms of this species
  were able to evolve to suit this FitnessGoal over 150 generations.
- `random_initial_population.png`: A sample of randomly generated unevolved
  phenotypes for this species.
- `best_organism_genotype.npy`: A numpy data file holding the genotype of the
  most fit organism of this species from this trial.
- `phenotype_program.npy`: A numpy data file holding the PhenotypeProgram for
  this species.
- `phenotype_program.txt`: A human readable text file holding the
  PhenotypeProgram for this species.
