# Download, Install and Run PostgreSQL

There are a few parts to the PostgreSQL proper setup: Download, Installation, and Running.

  

The process is different for Mac and Windows, and ultimately the goal is to run a local PostgreSQL server on your own machine, and then create a couple of databases with which we will be working.

----------

### Mac Instructions

Run the following commands IN ORDER on your command line in order to download PostgreSQL on your computer. This install assumes you have homebrew installed on your computer.

1.  If you don't have homebrew on your mac (you can check it by running in the terminal `brew -v` and getting something like `command not found`), you can install it via [this link](https://brew.sh/). It can take time...
2.  `brew install postgresql@16`
3.  `brew services start postgresql@16` - this starts a `postgresql` server locally on your computer (you usually only have to do this once)
4.  `psql postgres` - here you are accessing the server using the default `postgres` database
5.  Now, in your psql shell run the following commands:
    - `CREATE DATABASE sql_testing;`
    - `CREATE DATABASE sql_intro;` - these commands create a couple of _databases_, which we'll talk about later
6.  To exit the psql shell, type `\q` and press Enter

  

----------

### PC Instructions

1.  Go to [this](https://www.postgresql.org/download/windows/) website and download the latest PostgreSQL installer for Windows.
2.  Once you download the installer, run it!
3.  Choose the default installation directory
4.  Make sure to include **pgAdmin** and **Command Line Tools** in the selected components
5.  Choose a password for the `postgres` superuser - remember this password!
6.  Keep the default port (5432)
7.  Finish the install - if prompted, you may need to restart your computer.
    - Make sure to allow any permissions Windows asks of you
8.  Open a terminal and run `psql -U postgres` - here you are accessing the server
    - Enter the password you chose during installation
    - In this terminal, run `CREATE DATABASE sql_intro;` and `CREATE DATABASE sql_testing;`
