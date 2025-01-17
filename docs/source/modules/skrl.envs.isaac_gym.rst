Isaac Gym environments
======================

.. note::

   Isaac Gym environments implement a functionality to get their configuration from the command line. Because of this feature, setting the :literal:`headless` option from the trainer configuration will not work.  In this case, it is necessary to invoke the scripts as follows: :literal:`python script.py headless=True` for Isaac Gym environments (preview 3) or :literal:`python script.py --headless` for Isaac Gym environments (preview 2)

.. raw:: html

   <hr>

Environments (preview 3)
------------------------

The repository https://github.com/NVIDIA-Omniverse/IsaacGymEnvs provides the example reinforcement learning environments for Isaac Gym (preview 3).

These environments can be easily loaded and configured by calling a single function provided with this library. This function also makes it possible to configure the environment from the command line arguments (see `configuration-and-command-line-arguments <https://github.com/NVIDIA-Omniverse/IsaacGymEnvs#configuration-and-command-line-arguments>`_) or from its parameters as a python dictionary.

.. note::

   Only the configuration related to the environment will be used. The configuration related to RL algorithms are discarded since they do not belong to this library

Basic usage
^^^^^^^^^^^

* **Load an environment from the function parameters:**

   .. code-block:: python
      :linenos:

      # import the environment loader
      from skrl.envs.torch import load_isaacgym_env_preview3

      # load environment
      env = load_isaacgym_env_preview3(task_name="Cartpole")

* **Load an environment from the command line arguments (priority over the function parameters):**
   
   Include the following snippet

   .. code-block:: python
      :linenos:

      # import the environment loader
      from skrl.envs.torch import load_isaacgym_env_preview3

      # load environment
      env = load_isaacgym_env_preview3()

   and run the main script passing the configuration as command line arguments. For example:

   .. code-block:: bash

      python main.py task=Cartpole

API
^^^

.. autofunction:: skrl.envs.torch.loaders.load_isaacgym_env_preview3

.. raw:: html

   <hr>

Environments (preview 2)
------------------------

The example reinforcement learning environments for Isaac Gym (preview 2) are located within the same package (in the :code:`python/rlgpu` directory). 

These environments can be easily loaded and configured by calling a single function provided with this library. This function also makes it possible to configure the environment from the command line arguments or from its parameters as a python dictionary.


Basic usage
^^^^^^^^^^^

* **Load an environment from the function parameters:**

   .. code-block:: python
      :linenos:

      # import the environment loader
      from skrl.envs.torch import load_isaacgym_env_preview2

      # load environment
      env = load_isaacgym_env_preview2(task_name="Cartpole")

* **Load an environment from the command line arguments (priority over the function parameters):**
   
   Include the following snippet

   .. code-block:: python
      :linenos:

      # import the environment loader
      from skrl.envs.torch import load_isaacgym_env_preview2

      # load environment
      env = load_isaacgym_env_preview2()

   and run the main script passing the configuration as command line arguments. For example:

   .. code-block:: bash

      python main.py --task Cartpole

API
^^^

.. autofunction:: skrl.envs.torch.loaders.load_isaacgym_env_preview2
