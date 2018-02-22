>Under Development
# Robust Adversarial Reinforcement Learning

This repo contains code for training RL agents with adversarial disturbance agents.

## Installation instructions

Since we build upon the [rllab](https://github.com/openai/rllab) package for the optimizers, the installation process is similar to `rllab's` manual installation. Most of the packages are virtually installated in the anaconda `rllab3-adv` enivronment.

- Dependencies for scipy:

```
sudo apt-get build-dep python-scipy
```

- Install python modules:

```
conda env create -f environment.yml
```

- [Install MuJoCo](https://github.com/openai/mujoco-py)

- Add `rllab-adv` to your `PYTHONPATH`.

```
export PYTHONPATH=<PATH_TO_RLLAB_ADV>:$PYTHONPATH
```

- Install `gym-adv` in the attached file. See the README in the gym-adv

## Usage for main scripts

- `adversarial/scripts/evaluate.py` is for evaluating a trained baseline policy with different adversarial noises
- `adversarial/scripts/train_adversary_anneal.py` is used for
    + training baseline
    + adversary generating noises based on protagonist's OBSERVATION and adding noises on **only** OBSERVATION or ACTION
- `adversarial/scripts/train_adversary_A_A.py` is used for adversary's generating noises based on protagonist's ACTION and adding noises on ACTION
- `adversarial/scripts/train_adversary_AO_A.py` is used for adversary's generating noises based on protagonist's **both** OBSERVATION **and** ACTION and adding noises on ACTION
- `adversarial/scripts/train_adversary_box2d.py` is used for adversary's learning in **BOX2d** environment instead of mujoco
- `adversarial/scripts/train_adversary_continue.py` is used for continuing training from crashed one
- `adversarial/scripts/train_adversary_state_ctrl.py` is used for adverary's generating noises based on protagonist's OBSERVATION and adding noises on **both** OBSERVATION adn ACTION 

