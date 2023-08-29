# CHESTER Application: skeleton

Create a directory for the **West** workspace and switch into it:

```
mkdir chester-app
cd chester-app
```

> Note: The word `chester-app` in the title and command above should be replaced with your workspace name (and preferrably match a path/name of your **Git** repository). If you only have one application in the workspace, the name should contain the application name. Once done, do not forget to delete this note to avoid any future confusion.

Create **Python** virtual environment in the workspace:

```
python3 -m venv .venv
```

> Note: If the command `python3` cannot be found on your system, use `python` instead.

Activate the **Python** virtual environment:

```
source .venv/bin/activate
```

> Note: This command should be `.venv\Scripts\Activate.ps1` in **Windows Powershell**. Also, in case of the **Fish** shell, it is important to run the command as `source .venv/bin/activate.fish`.

Upgrade the **Python** package installer:

```
pip install --upgrade pip
```

Install the **West** tool:

```
pip install west
```

Initialize the **West** workspace:

```
west init -m https://github.com/hardwario/chester-skeleton.git --manifest-rev main
```

Synchronize the **West** workspace:

```
west update
```

Configure the default board:

```
west config build.board chester_nrf52840
```

Install the required **Python** packages:

```
pip install -r zephyr/scripts/requirements.txt
pip install -r nrf/scripts/requirements.txt
pip install -r bootloader/mcuboot/scripts/requirements.txt
pip install -r chester/scripts/requirements.txt
```

Go to the application directory:

```
cd vendor/application
```

Build the application:

```
west build
```

Flash the application:

```
west flash
```

Debug the application:

```
west debug
```
