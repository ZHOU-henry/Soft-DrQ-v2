# Soft DrQ and transfer learning 

Soft DrQ-v2: Maximum Entropy RL framework based on Data-Augmented DrQ-v2 algorithm, aim transfering muti-tasks.

Code implementation of the [Soft DrQ-v2][paper] algorithm in Pytorch.

Maximum Entropy RL method is based on the Soft Actor-Critic(SAC): [[ArXiv]](https://arxiv.org/abs/1812.05905).

Part code based on original DrQ-v2 implementation code from the facebook AI research:
[[Mastering Visual Continuous Control: Improved Data-Augmented Reinforcement Learning]](https://arxiv.org/abs/2107.09645)

@article{yarats2021drqv2,
  title={Mastering Visual Continuous Control: Improved Data-Augmented Reinforcement Learning},
  author={Denis Yarats and Rob Fergus and Alessandro Lazaric and Lerrel Pinto},
  journal={arXiv preprint arXiv:2107.09645},
  year={2021}
}

<p align="center">
  <img width="22%" src="https://imgur.com/O5Va3NY.gif">
  <img width="22%" src="https://imgur.com/PCOR9Mm.gif">
  <img width="22%" src="https://imgur.com/H0ab6tz.gif"> </p>


## Method
Soft DrQ-v2 is a model-free and off-policy RL algorithm for continuous control tasks based on the image-vision input. This is an actor-critic method with data-augmentation and maximum entropy loss function. Aim to learn to control the agent only from images pixels.

DrQ-v2 use DDPG as the backbone, and achieve nice performance in several continuous tasks.

Here Soft DrQ-v2 use Soft-actor-critics as the backbone of the whole algorithm, and this modification is for transfering the model from previous tasks to current tasks, maximum entropy shows better transfer learning and continuous learning property under several control tasks.

For example, after we trained the policy model parameters for the task of walker_walk, if we want the walker start to run, we need train the walker model from scratch.

And if we reuse the previous 'walk' parameters to learn the 'run' parameters, this will be more efficiency. It means we can save and reload 'walk' model for learning harder similar tasks like 'run' based on the previous 'walk' task.

This is the concept of transfer learning, hierarchical learning and continuous learning (life-long learning).

Continuous reinforcement learning should help agent overcome task-specific problem and master multi-tasks.

## Instruction

Tasks are based on the MuJoCo, install [MuJoCo](http://www.mujoco.org/) 

## License
Soft DrQ-v2 is licensed under the MIT license.
