# HRX (Hot Reload X)

HRX is a versatile hot-reloading tool written in Zsh, designed to streamline the development process by automatically restarting applications upon file changes. It leverages Git to monitor file changes within a project and utilizes the ps command to monitor long-running processes. When a change is detected in the Git repository, HRX spawns a new instance of the application, ensuring that it reflects the latest updates without manual intervention.

## Features

1. **Hot Reloading**: Automatically restarts applications upon file changes.
2. **Git Integration**: Monitors changes in the Git repository respecting `.gitignore` file
3. **Process Monitoring**: Uses the `ps` command to monitor long-running processes.
4. **Language Agnostic**: Works with applications developed in various programming languages.
5. **Easy to Use**: Simple command-line interface.

## Installation

HRX can be installed by cloning the repository and adding the hrx executable to your system's PATH. Alternatively, you can install it via a package manager once it becomes available.

```
git clone https://github.com/locnguyenvu/hrx.git
cd hrx
chmod +x hrx
sudo mv hrx /usr/local/bin
```

## Usage

To start using HRX, simply run the following command:

```
hrx -c '<cmd to start application>'
```

Replace `<cmd to start application>` with the command used to start your application. HRX will then monitor the specified command and automatically restart it whenever changes are detected in the Git repository.

Stop the application by pressing `Ctrl + C`

## Example

Reload a Python web server

```
# Download example
git clone https://github.com/render-examples/flask-hello-world.git
cd flask-hello-world
pip install -r requirements.txt

# use HRX
hrx -c 'gunicorn app:app'
```

This command tells HRX to monitor the `app.py` file and restart the gunicorn server whenever changes occur.
