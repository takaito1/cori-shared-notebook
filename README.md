# cori-shared-notebook
## getting started
### login and access (do this every time you access cori)
- Once you have established an account with nersc, you have access to jupyterhub on cori supercomputer. 
- Open your web browser on your laptop. Access the jupyterhub on cori via copying this URL https://jupyter.nersc.gov.  
- Documentation for jupyterlab is at this URL https://jupyterlab.readthedocs.io/en/stable/
### setting up python environment (do this only once)
- First download "miniconda Linux 64bit" to your laptop from https://docs.conda.io/en/latest/miniconda.html 
- Use the upload icon on the jupyterhub to upload the Miniconda3-pyXXXX-Linux-x86_64.sh file to your home directory
- Next open a terminal on the jupyterhub. Execute the shell script by typing as follows and set up base of miniconda3
> bash Miniconda3-pyXXXX-Linux-x86_64.sh
- Follow the prompts. It will ask for the destination to install miniconda3. I suggest you follow the prompt and use your $HOME.   
- It will ask "Do you wish the installer to initialize Miniconda3?". Answer no to this one. 
- You can manually initialize miniconda3 by typing at the command prompt as follows: 
> source $HOME/miniconda3/etc/profile.d/conda.sh
> conda activate
- You should see (base) before the prompt now. Now you are in the "base" environment. First update the base environment and follow the prompts to completion. 
> conda update --all
- Next install mamba. This is a parallel version of conda. 
> conda install mamba -c conda-forge
-  you will upload the env-calc.yml file from this repository and create a new "calc" environment. (This might take a while, please be patient)
> mamba env create -f env-calc.yml
- Make the new "calc" environment accessible from jupyter notebook
> conda activate calc
> python -m ipykernel install --user --name calc --display-name Calc
- Now your python environment is ready!
## CMIP6 analysis example
- Some CMIP6 data is stored in shared data disk on cori. 
- Re-gridded CMIP6 data is stored in /global/cfs/cdirs/m3920/dataset/cmip6
### Ocean heat content
