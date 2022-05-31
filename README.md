# How to setup DBT

## Main
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
3) Install dbt with the specific adapter you want to use for the project
    ```bash
    pip install dbt-<adapter_name>

    # An example using the snowflake adapter:
    pip install dbt-snowflake
    ```
4) Initialise Git
    ```bash
    git init
    ```
5) Create a gitignore file and a README
6) If `venv` was used to create the virtual environment, add the folder name to the gitignore file so it would not be tracked
7) Initialise dbt
    - This is done with a simple `init` command
        ```bash
        dbt init <project_name>
        ```
    - The configuration options are specific to each adapter
        - [Postgres](#postgres)
        - [Snowflake](#snowflake) 
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
## Postgres
1. Which database would you like to use?
    - For the database, pick the number corresponding to **postgres**

## Snowflake
1. Which database would you like to use?
    - For the database, pick the number corresponding to **snowflake**
2. account `(https://<this_value>.snowflakecomputing.com)`:
    - Copy this value from the link of your snowflake environment
3. user (dev username):
    - Enter your snowflake username
4. 
    ```
    [1] password
    [2] keypair
    [3] sso
    Desired authentication type option (enter a number):
    ```
    - For option 1, enter the password of your snowflake account
5. role (dev role):
    - Enter the development role you created for your project
6. warehouse (warehouse name):
    - Enter warehouse name of your project
7. database (default database that dbt will build objects in):
    - Enter the default database where you'll build your models
8. schema (default schema that dbt will build objects in):
    - Enter the default schema e.g public
9. threads (1 or more) [1]:
    - Choose the number of threads you believe your project would need
    > The number of threads would determine the number of processes that can run in parallel