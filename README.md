# dbt-demo
Setting up DBT with the Postgres Adapter

## Steps
1) Create a virtual environment
    - conda
        ```bash
        conda create -n <venv_name> python=<python_version>
        ```
    - venv
        ```bash
        python -m venv <venv_name>
        ```
2) Activate the virtual environment
    - conda
        ```bash
        conda activate <venv_name>
        ```
    - venv
        - Linux/Mac
            ```bash
            source <venv_name>/bin/activate
            ```
        - Windows
            ```bash
            <venv_name>/Scripts/activate
            ```
3) Install dbt with the postgres adapter
    ```bash
    pip install dbt-postgres
    ```
4) Initialise Git
    ```bash
    git init
    ```
5) Create a gitignore file and a README
6) If `venv` was used to create the virtual environment, add the folder name to the gitignore file so it would not be tracked
7) Initialise dbt
    ```bash
    dbt init <project_name>
    ```
    - Choose `1` for the postgres database when asked
8) Add the dbt logs folder `logs` to gitignore
9) Add and commit your files with Git
    ```bash
    git add .
    git commit -m "Initalised DBT" 
    ```
10) You can always push your commits to a remote repository like Github
    - Create a new repository
    - Add the remote to local
        ```bash
        git remote add origin <https-or-ssh-link>
        ```
    - If you made any commits on Github, pull the changes to local
        ```bash
        git pull --rebase origin main
        ```
    - Push your commits to Github
        ```
        git push -u origin main
        ```