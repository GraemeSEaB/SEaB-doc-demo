# Installation of Sphinx

Install Linux (Ubuntu 20.04) from a terminal wiindow:

```bash
wsl --install -d Ubuntu-20.04
```
(To remove an existing installation, use:)

```bash
wsl --unregister <distro_name>
```

You can view the installed distro by typing:

```bash
wsl -l
```

After installation, run Ubuntu from the Windows Start menu, and in the bash terminal upgrade to Ubuntu 22.04 LTS:

```bash
sudo do-release-upgrade -d
```
> **Note that Windows will still think Ubuntu 20.04 is installed after the update. If you need to uninstall use the original (not the upgraded) distro name.**

After the upgrade completes, a reboot may be needed. Then check the Ubuntu version and install any updates:

```bash
lsb-release -a
sudo apt update && sudo apt upgrade
```

Next, install PiP and venv:

```bash
sudo apt install pip
sudo apt install python3-venv
```

Create a virtual environment and activate it:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

From the virtual environment install Sphinx and dependencies:

```bash
python3 -m pip install sphinx
python3 -m pip install sphinx-intl
pip install furo
pip install rst2pdf
pip install matplotlib
```

Create the documentation directories and initialise Sphinx:

```bash
mkdir SEaB
mkdir SEaB/projname
cd SEaB/projname
sphinx-quickstart
```

Open Windows Explorer from bash:

```bash
explorer.exe .
```

Use Explorer to copy rst files to source directory. Conf.py will need editing.

Create content:

```bash
make html
make pdf
make gettext
```

To close the venv:

```bash
deactivate
```