# B: Running Jupyter Notebooks on Cori

Jupyter notebooks are quickly becoming an indispensable tool for doing computational science. In some cases, you might want to (or need to) harness NERSC computing power inside of a jupyter notebook. To do this, you can use NERSC’s new Jupyterhub system at https://jupyter.nersc.gov/. These notebooks are run on a large memory node of Cori and can also submit jobs to the batch queues (see [https://docs.nersc.gov/services/jupyter/](https://docs.nersc.gov/services/jupyter/) for details). All of your files and the project directory will be accessible from the Jupyterhub, but your conda envs won’t be available before you do some configuration.&#x20;

To set up a conda environment so it is accessible from the Jupyterhub, activate the environment and setup an ipython kernel. To do this, run the command “pip install ipykernel”. More info can be found at [http://bit.ly/2yoKAzB](http://bit.ly/2yoKAzB). If that did not work, you can also manually add your environment. Assuming your environment is my\_env in Python 3:&#x20;

`source activate my_env`&#x20;

`python -m ipykernel install --user --name my_env --display-name "aj_te (py3)"`
