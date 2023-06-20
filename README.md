- #### Set a mirror in Docker
    - `doas vi /etc/docker/daemon.json`
      ```
      {
        "registry-mirrors": ["https://docker.nju.edu.cn/"]
      }
      ```
    - `doas systemctl restart docker` # Restart docker to apply changes
- ***Notes***
    - `https://docker.nju.edu.cn/` # Replace it with a registry mirror in your country
    - `docker info` # Check the information about 'Registry Mirrors'
    - Because to improve the speed of downloading Docker images.
        - https://github.com/docker/for-linux/issues/1430 # Another way
- ***References***
    - https://sci.nju.edu.cn/9e/05/c30384a564741/page.htm
    - Google # `registry mirrors site:edu.cn`
- ---
- #### Set the environment variable EDITOR in Nix
    - `echo 'export EDITOR="/home/yaoniplan/.nix-profile/bin/vi"' >> ~/.bashrc`
- ***Notes***
    - `source ~/.bashrc` # Remember to make it effective
    - `/home/yaoniplan/.nix-profile/bin/vi` # Replace it with your desired editor
        - `which vi` # Get it
        - `echo $EDITOR` # Check it
    - Solve the problem
      ```
      [yaoniplan@tux ~]$ crontab -e
      no crontab for yaoniplan - using an empty one
      /bin/sh: line 1: /usr/bin/vi: No such file or directory
      crontab: "/usr/bin/vi" exited with status 127
      [yaoniplan@tux ~]$
      ```
        - `EDITOR=$(which vi) crontab -e` # Try to use other editor (e.g. *emacs*, *nano*, etc.)
- ***References***
    - ChatGPT
- ---
- #### Use "emacs"
    - Delete the current line
        - `Ctrl-a` # Move the cursor to the beginning of the line
        - `Ctrl-k` # Delete to end of line
    - `Ctrl-x u` # Undo
    - `Ctrl-e` # Move the cursor to the the end of a line
    - `Ctrl-x Ctrl-c` # Quit the emacs
- ***Notes***
    - `nix shell nixpkgs#emacs` # Install dependencies temporarily
- ***References***
    - ChatGPT
- ---
- #### Use "nano"
    - `Ctrl-c` # Break the current operation (Like Shell)
    - `Alt-u` # Undo (Like Vi's `u`)
    - `Ctrl-h` # Delete one letter to the left (Like Vi)
    - `Ctrl-x` # Exit the nano
- ***Notes***
    - `nix shell nixpkgs#nano` # Install dependencies temporarily
- ***References***
    - ChatGPT
- ---
- #### Use "less"
    - `less ~/.bashrc ~/.bash_profile`
- ***Notes***
    - `:n` # Next file
    - `:p` # Previous file
- ***References***
    - `h`
- ---
