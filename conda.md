conda create -n functionToolsAgentsWithLangchain -c conda-forge ipykernel python-dotenv langchain openai

conda activatefunctionToolsAgentsWithLangchain

conda update langchain

conda deactivate

conda install <package> --update-deps

conda install -n functionToolsAgentsWithLangchain <package> --update-deps

conda install ipykernel python-dotenv langchain openai

===

conda list

conda list <package>

- Update conda

conda update -n base -c defaults conda

- Remove an environment

conda env list
conda remove -n functionToolsAgentsWithLangchain --all

- List the history of each change to the current environment

conda list --revision

- Revert to revision 0

conda install --revision 0

e.g. Updating some_env with TensorFlow 1.15 from base

conda install -n some_env tensorflow==1.15

- Remove a package

conda remove python

# Config

```sh
# add the channel “conda-forge” to the .condarc
conda config --add channels conda-forge
```

# Clone an existing environment

```sh
conda create --name clone_envname --clone<env_name>
```

# Reproduces Conda environment on the same operating system

The Spec list can be created with or without the explicit option, as shown below.

```sh
conda list >spec_list.txt
#or
conda list --explicit >spec_list_exp.txt
```

An explicit spec file shows the platform where the environment was created. This platform is the one where this spec file is known to work.

```sh
conda create --name test_spec --file spec_list_exp.txt
```

# Export Conda environments using environment.yml file

To share our project conda environment with other team members, we can use an export.
The environment.yml file is not operating system specific and formatted using YAML.

```sh
# Create environment.yml file via conda
conda env export > environment.yml

# If the environment already exists, then you will get an error.
# CondaValueError: prefix already exists

# create a conda environment from a file
conda env create -f environment.yml

# specify a different install path than the one specified in the ‘prefix’.
conda env create -f environment.yml -p .

# leave out the prefix line when generating the .yml file.
conda env export | grep -v "^prefix: " > pytorch_env.yml

# update a conda environment with a file
conda env update --file environment.yml

# Remove environment and its dependencies
conda env remove -n<env_name>

# List all the conda environment available
conda env list
```

# Install the kernel to use a jupyter notebook

```sh
(<new_env>) $ ipython kernel install --user --name=<any_name_for_kernel>
```

# Uninstall a kernel

```sh
jupyter kernelspec removesome_env
```

# kernels list

```sh
jupyter kernelspec list
```

https://www.activestate.com/resources/quick-reads/how-to-manage-python-dependencies-with-conda/
