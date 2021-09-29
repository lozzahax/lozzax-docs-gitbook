# 🐧 Installing on Linux \(GUI\)

### Initial setup

#### 1. Computer Preparation

Begin by updating your package lists. The below command downloads package lists from your repositories and "updates" them to get information on the newest versions of packages and their dependencies. It will do this for all repositories and PPAs.

Run the following command:

```text
sudo apt-get update
```

You'll notice a bunch of package lists were downloaded. Once this is complete, run the below command to fetch new versions of any packages we currently have installed on the system:

```text
sudo apt-get upgrade
```

You'll be prompted to authorise the use of disk space. Type `y` and press Enter to authorise.

If you do not have `curl` installed on your computer, now is also a good time to install it, as we will use it later:

```text
sudo apt install curl
```

#### 2. Installation

You only need to do this step the first time you want to set up the Lokinet repository. After you've done it once, the repository will automatically update whenever you fetch new system updates.

This first command installs the public key used to sign official Lokinet binaries.
