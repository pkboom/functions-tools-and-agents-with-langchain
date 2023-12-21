conda create -n functionToolsAgentsWithLangchain -c conda-forge ipykernel python-dotenv langchain openai

conda activatefunctionToolsAgentsWithLangchain

conda update langchain

conda deactivate

conda install <package> --update-deps

conda install -n functionToolsAgentsWithLangchain <package> --update-deps

conda install ipykernel python-dotenv langchain openai

conda list -e > requirements.txt

conda install --file requirements.txt

conda list

conda list <package>

conda remove python

- Update conda

conda update -n base -c defaults conda

- Remove an environment

conda env list
conda remove -n functionToolsAgentsWithLangchain --all
