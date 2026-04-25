# Useful Snipes

<details open>
    <summary>Table of Contents</summary>
    <ol>
        <li><a href="#bash">Bash</a></li>
        <li><a href="#conda-environments">Conda Environments</a></li>
        <li><a href="#git">Git</a></li>
        <li><a href="#jupyter-notebook">Jupyter Notebook</a></li>
        <li><a href="#venv-environments">Venv Environments</a></li>
        <li><a href="#vs-commands">VS Commands</a></li>
        <li><a href="#mlflow">Mlflow</a></li>
    </ol>
</details>

## Bash
### General usage
Use tab to autocomplete from the directory. 
By pressing tab when cursor is on an expected directory or file field bash will show a list of directories or files under the current directory.
By pressing tab when already typing it will autocomplete if there is a match.
### Copy-paste file
* cp /origin/path /destination/path  
### Cut-paste file
* mv /origin/path /destination/path
### Rename file (equivalent to moving to same dir)
* mv oldname newname
### Delete dir
* rm -rf /path/to/delete
### Delete all files with extension.json in current dir
* rm -rf *.json
### Delete all files and dir except one in current dir
* rm -rf -- !(.gitignore)
### Zip folder with all its contents
* zip -r myfiles.zip . 

## Conda Environments
* Verify conda info, configuration files, version etc.:
  
    `conda info`
* Create conda environment:
  
    `conda create --name name_of_env python=3.7`
* Create conda environment specifying full path:
  
    `conda create --prefix /full/path python=3.7`
  
  (Note python will use the latest Python interpreter available if version unspecified but python keyword must remain)
  
  (Note python  keyword must be issued otherwise environment will be empty)
* Create conda environment from yaml file:
  
    `conda env create --file environment.yaml`
* Create yaml environment file for export:

    `conda env export > environment.yaml`
* Delete conda environment:
  
    `conda env remove --name name_of_nenv`

## Git
* Pushing to remote:
    ```
    git pull #to update merge with remote in case someone was pushing to remote, will show already up to date if no changes
    git checkout branch_name
    git add .
    git commit -m 'Updates'
    git push
    ```
* Pulling from remote:
    ```
    git checkout branch_name
    git pull 
    ```
* Merging to branch:
    ```
    git checkout branch_name_main
    git merge branch_name_develop
    git push
    ```
    (git merge acts locally, needs to be pushed to remote after)
    (a pull request process includes merge commands but needs to be done through the remote repo GUI)
* Checking if local is up to date with remote:
    ```
    git checkout branch_name
    git fetch --dry-run
    ```
    (Nothing reported means there is nothing to report)

* Create and checkout a new branch:
    ```
    git checkout -b new_branch existing_branch
    ```
    (-b flag equals to running command git branch before git checkout)
    (exiting_branch is optional the new branch will be based off the current HEAD by default)

## Jupyter Notebook
* Rendering notebook in html wthout code cells:

    `jupyter nbconvert --to html --no-input filename.ipynb`
  
    `jupyter nbconvert --to html --TemplateExporter.exclude_input=True --template classic --no-prompt filename.ipynb` 
* Installing and managing Python kernels:

     [IPython docs](https://ipython.readthedocs.io/en/latest/install/kernel_install.html)

    `jupyter kernelspec list`

    `python -m ipykernel install --user --name kernel-name`

    `jupyter kernelspec uninstall unwanted-kernel`
* Trusting a jupyter notebook:

    `jupyter trust notebook-name.ipynb`

## Venv Environments
[Python docs](https://docs.python.org/3/library/venv.html)
* Create file with all installed dependencies on the environment:
    ```
    \path\Scripts\activate
    pip freeze > requirements.txt
    ```
* Create environment and install from requirements file:
    ```
    python -m venv \path
    \path\Scripts\activate
    pip install -r requirements.txt
    ```

## VS Code Commands
* Open VS Code command window shortcut:

    **Ctrl + Shift + P**
* Open workspace folder always to give environment context to you file
* Run selected code or current line shortcut:
    
    **Shift + Enter**
* Set "justMyCode": false on the launch.json debug configuration file under a particular configuration to enable use of breakpoints on debugging mode
* Restart VS Code window after environment/setting changes:

    **Ctrl + Shift + P > Reload window**
* Open several Python terminals:

    **Ctrl + Shift + P > Python: Create Terminal**
* Fold all regions of source code

    **Ctrl + K Ctrl + 0**
* Unfold all regions of source code

    **Ctrl + K Ctrl + J**
* Debugging: Jump to cursor ctrl + F10

## Mlflow
* Initite mlflow with backend pointing at mlruns local folder
    ```
    mlflow server --backend-store-uri "sqlite:///mlflow.db" --default-artifact-root "./mlruns"
    ```
