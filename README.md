# Q Learning with Mountain Car

## Install Miniconda on Windows

https://docs.conda.io/projects/miniconda/en/latest/

### Anaconda Prompt(miniconda):

conda create -n gymenv

conda activeate gymenv

conda install python=3.11

## Install Gymnasium on Windows

Python 3.11 was installed for support and testing.(executable exe)

pip install gymnasium[classic-control]

pip install gymanisum[accept-rom-licence]

## Visual Studio Code for c++ build tools

https://code.visualstudio.com/  ->Desktop Development with C++

### After setups, testing following code:

import gymnasium as gym

env = gym.make("MountainCarContinuous-v0", render_mode="human")

observation, info = env.reset(seed=42)

for _ in range(1000):

   action = env.action_space.sample()  # this is where you would insert your policy
   
   observation, reward, terminated, truncated, info = env.step(action)

   if terminated or truncated:
      observation, info = env.reset()

env.close()
