# Unity ML-Agents Trainers - [FORK]

The `mlagents` Python package is part of the
[ML-Agents Toolkit](https://github.com/Unity-Technologies/ml-agents). `mlagents`
provides a set of reinforcement and imitation learning algorithms designed to be
used with Unity environments. The algorithms interface with the Python API
provided by the `mlagents_envs` package. See [here](../docs/Python-API.md) for
more information on `mlagents_envs`.

The algorithms can be accessed using the: `mlagents-learn` access point. See
[here](../docs/Training-ML-Agents.md) for more information on using this
package.

## Installation

Uninstall current version of `mlagents` and `mlagents-envs`, and install depenedncise:
```sh
pip uninstall -y mlagents mlagents-envs
pip install mlagents-envs==0.27.0
```

Then, install this fork with:

```sh
pip install git+https://github.com/Ending2015a/mlagents-fork.git@master
```

## Usage & More Information

This fork adds gradeint clipping to PPO and SAC to stablize training porcesses.

You can set the max norm of the gradient cilpping in the `hyperparametres` section of `config.yaml`
```yaml
hyperparameters:
  actor_clip_norm: 0.5
  critic_clip_norm: 0.5
```


## Limitations

- `mlagents` does not yet explicitly support multi-agent scenarios so training
  cooperative behavior among different agents is not stable.
- Resuming self-play from a checkpoint resets the reported ELO to the default
  value.
