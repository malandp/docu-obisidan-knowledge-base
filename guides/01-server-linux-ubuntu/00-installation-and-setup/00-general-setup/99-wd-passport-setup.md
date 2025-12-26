>[!note]
>This is only relevant if you plan on operating WD passport portable USB hard drives on the server

# WD Passport setup on linux ubuntu server

A utility called [wdpassport-utils](https://github.com/0-duke/wdpassport-utils) is available to unlock WD passport hard drive on linux, however, on linux ubuntu server, when you try to install the `py3_sg` dependancy with `sudo python3 -m pip install py3_sg`, you are presented with an error:

```bash
malandp@malan-server:~$ sudo python3 -m pip install py3_sg
error: externally-managed-environment

× This environment is externally managed
╰─> To install Python packages system-wide, try apt install
    python3-xyz, where xyz is the package you are trying to
    install.
    
    If you wish to install a non-Debian-packaged Python package,
    create a virtual environment using python3 -m venv path/to/venv.
    Then use path/to/venv/bin/python and path/to/venv/bin/pip. Make
    sure you have python3-full installed.
    
    If you wish to install a non-Debian packaged Python application,
    it may be easiest to use pipx install xyz, which will manage a
    virtual environment for you. Make sure you have pipx installed.
    
    See /usr/share/doc/python3.12/README.venv for more information.

note: If you believe this is a mistake, please contact your Python installation or OS distribution provider. You can override this, at the risk of breaking your Python installation or OS, by passing --break-system-packages.
hint: See PEP 668 for the detailed specification.

```

## Why?

The "externally-managed-environment" error in Linux, particularly when using `pip` to install Python packages, indicates that you are attempting to modify a Python environment that is controlled by your operating system's package manager (e.g., `apt`, `dnf`, `pacman`).

This error serves as a protective measure, enforced by Python's PEP 668, to prevent conflicts and potential system instability. Your Linux distribution often relies on specific versions of Python packages for its own internal tools and functionalities. Directly installing, upgrading, or removing these packages with `pip` outside of the system's package manager can:

- **Break system dependencies:** 
    
    Critical system applications or even the operating system itself might cease to function if their required Python packages are altered or removed.
    
- **Create version conflicts:** 
    
    System tools might expect one version of a library, while `pip` installs a different, incompatible version.
    
- **Lead to an unmanageable state:** 
    
    The system's package manager loses track of the state of Python packages, making future updates or dependency resolution difficult.
    

Causes:

- Trying to install system-wide Python packages with `pip`: 
    
    This is the most common cause, as `pip` is designed for user-level package management, while system-wide packages should be handled by the distro's package manager.
    
- Mixing `pip` and system package managers: 
    
    Installing a package with `apt` (or equivalent) and then trying to manage it with `pip`, or vice-versa, can lead to this error.

## Solution:

An obvious solution to this would be to use a virtual environment like so:

```bash
python3 -m venv my_project_env  
source my_project_env/bin/activate  
pip install package_name
```

However, because `wdpassport-utils` requires access to system busses, this is not a viable solution.

So, for `wdpassport-utils`, we have another solution, 