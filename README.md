Project by Nate Gaylinn:
[github](https://github.com/ngaylinn),
[email](mailto:nate.gaylinn@gmail.com),
[blog](https://thinkingwithnate.wordpress.com/)

This repository holds the results and analysis from a collection of experiments
testing out an "epigenetic algorithm" that searches for interesting examples of 
Conway's Game of Life. The intent was to use an evolutionary algorithm to
design the search space for an evolutionary algorithm.

For more information on the motivation, design, and execution of the project
that produced these results, check out the [README file](https://github.com/ngaylinn/epigenetic-gol-v1/blob/main/README.md)
for the source repository or this [slide deck](https://docs.google.com/presentation/d/1ZIYj8Rg4xPHukQ-Glk9_IZTgimEYh5dtWsyXrbkX9Dc/edit?usp=sharing).

This repository actually has two sets of results in two top-level directories.
The `paper` directory holds all data used for writing the scientific paper for
this experiment. The `gp_variations` holds preliminary data used to evaluate
the performance of this algorithm with different configurations. These two
directories have similar but distinct visualizations suited for different sorts
of analysis.

# Paper

Built from [https://github.com/ngaylinn/epigenetic-gol-v1](
https://github.com/ngaylinn/epigenetic-gol-v1) on February 9, 2024.

Overview of files:
- `best_ctrl_phenotypes.png`: A summary of the best control phenotypes evolved
  for each FitnessGoal.
- `best_expt_phenotypes.png`: A summary of the best control phenotypes evolved
  for each FitnessGoal.
- `organism_fitness_all_goals.png`: A chart comparing the best organism
  fitness scores for the experiment and control configurations on all
  FitnessGoals. For the paper, the experiment uses configuration B1C1S1.
- `random_initial_population.png`: A sample of randomly generated phenotypes
  from a random set of species with no evolution.
- One sub-directory per FitnessGoal

Files in each goal directory:
- `<GOAL>_<CONFIG>_f<FITNESS>.gif`: A video of the best phenotype found for
  FitnessGoal GOAL, configuration options CONFIG. The fitness score for this
  phenotype is included in the filename.
- `organism_fitness.png`: A chart comparing the fitness trajectory of organisms
  comparing the control to experiment conditions, before and after evolving
  species.
- `species_fitness.png`: A chart showing the fitness trajectory of species
  across 150 generations.
- One sub-directory for the experiment (configuration B1C1S1) and one for
  each control. Note that there are no species trials for the control, so the
  control sub-directories have the same organization as a single experiment
  trial.

For each experiment configuration directory:
- `best_organism_from_trial_<TRIAL>_f<FITNESS>.gif`: A video of the best
  phenotype found in trial TRIAL. The fitness score for this phenotype is
  included in the filename.
- `state.pickle`: A record of metadata about the experiment and how it was run.
  This is a pickled instance of `experiments.Experiment`.
- `results.pickle`: A record of experiment results across all trials, from
  which all the visualizations were generated. This is a pickled instance of
  `experiments.ExperimentData`.
- `species_fitness.png`: A chart showing how well this algorithm evolved
  species to suit this FitnessGoal over 150 generations.
- One sub-directory per species trial (trial number and species fitness are
  included in the directory name).

For each trial directory:
- `best_organism_f<FITNESS>`: A video of the most fit phenotype of this species
  from this trial. The fitness score for this phenotype is included in the
  filename.
- `best_organism_genotype.npy`: A numpy data file holding the genotype of the
  most fit organism of this species from this trial.
- `organism_fitness.png`: A chart showing how well organisms of this species
  were able to evolve to suit this FitnessGoal over 150 generations.
- `phenotype_program.npy`: A numpy data file holding the PhenotypeProgram for
  this species.
- `phenotype_program.txt`: A human readable text file holding the
  PhenotypeProgram for this species.
- `random_initial_population.png`: A sample of randomly generated unevolved
  phenotypes for this species.
- `results.pickle`: For the control, the results data goes here since there's
  only one trial.


# GP-Map Variations

Built from [https://github.com/ngaylinn/epigenetic-gol-v1](
https://github.com/ngaylinn/epigenetic-gol-v1) on December 8, 2023.

Overview of files:
- `random_initial_population.png`: A sample of randomly generated phenotypes
  from a random set of species with no evolution.
- `bias.png`: Compares algorithm performance with and without the "bias"
  configuration option set for each FitnessGoal.
- `composition.png`: Compares algorithm performance with and without the
  "composition" configuration option set for each FitnessGoal.
- `stamp_transforms.png`: Compares algorithm performance with and without the
  "stamp transforms" configuration option set for each FitnessGoal.
- One sub-directory per FitnessGoal

Files in each goal directory:
- `<GOAL>_<CONFIG>_f<FITNESS>.gif`: A video of the best phenotype found for
  FitnessGoal GOAL, configuration options CONFIG. The fitness score for this
  phenotype is included in the filename.
- One sub-directory per experiment configuration.

For each experiment configuration directory:
- `best_organism_from_trial_<TRIAL>_f<FITNESS>.gif`: A video of the best
  phenotype found in trial TRIAL. The fitness score for this phenotype is
  included in the filename.
- `state.pickle`: A record of metadata about the experiment and how it was run.
  This is a pickled instance of `experiments.Experiment`.
- `results.pickle`: A record of experiment results across all trials, from
  which all the visualizations were generated. This is a pickled instance of
  `experiments.ExperimentData`.
- `species_fitness.png`: A chart showing how well this algorithm evolved
  species to suit this FitnessGoal over 150 generations.
- One sub-directory per species trial (trial number and species fitness are
  included in the directory name).

For each trial directory:
- `best_organism_f<FITNESS>`: A video of the most fit phenotype of this species
  from this trial. The fitness score for this phenotype is included in the
  filename.
- `best_organism_genotype.npy`: A numpy data file holding the genotype of the
  most fit organism of this species from this trial.
- `organism_fitness.png`: A chart showing how well organisms of this species
  were able to evolve to suit this FitnessGoal over 150 generations.
- `phenotype_program.npy`: A numpy data file holding the PhenotypeProgram for
  this species.
- `phenotype_program.txt`: A human readable text file holding the
  PhenotypeProgram for this species.
- `random_initial_population.png`: A sample of randomly generated unevolved
  phenotypes for this species.
