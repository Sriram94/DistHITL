# Distributional Reinforcment Learning with Humans In The Loop 

This repository contains the code for the paper: Distributional Reinforcement Learning with Humans in the Loop. Follow the instructions here to install and run the code. 


## Installation

1. Install [Python](https://www.python.org/) 3.8, 3.9, or 3.10. 


2. Install pip requirements:

        pip install -e .

5. If you want to run RL experiments, install `stable-baselines3` and `imitation` by running:

        pip install -e .[sb3]


## Data

The Atari-Head dataset can be downloaded here: https://zenodo.org/records/10966777. The download contains a [README](./data/bridge_dataset/README.md) with more information about the format of the data.

### Environments

All of the environments are made available as gym environments.

**Atari:** Atari environments follow the naming convention `$ROM_$HORIZON_fs$FRAMESKIP-v0`. For instance, Pong with a horizon of 50 and frameskip of 30 can be instantiated via `gym.make("pong_50_fs30-v0")`.

**SMARTS:** Smarts environments follow the naming convention `$GAME_$DIFFICULTY_l$LEVEL_$HORIZON_fs$FRAMESKIP-v0`. 



### RL training


**DQN:** To train DQN on the environments in Atari-Head, run:

    python -m effective_horizon.sb3.train with algo=DQN \
    env_name="pong_50_fs30-v0" \
    gamma=1 seed=0 algo_args.exploration_fraction=0.1 algo_args.learning_starts=0

