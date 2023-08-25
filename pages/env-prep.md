<!-- omit from toc -->
# Preparing the Environment - Mac

I've documented my order of operations here from top-to-bottom, step-by-step. Following along accordingly should put you in a great spot to get started!

Alternatively, if you would like to review some other great guides I've come across, please see the following:

- <https://www.roguelynn.com/words/m1-dev-setup/#step-4-native-installation>
- <https://developer.cisco.com/learning/modules/dev-setup/>

<!-- omit from toc -->
## Content

- [Install and run iTerm](#install-and-run-iterm)
- [Install XCODE](#install-xcode)
  - [Verify XCODE](#verify-xcode)
- [Install brew](#install-brew)
  - [Verify brew](#verify-brew)
  - [Update brew](#update-brew)
  - [Brew on Mac M1](#brew-on-mac-m1)
- [Set up zsh and ohmyzsh](#set-up-zsh-and-ohmyzsh)
  - [Install zsh](#install-zsh)
  - [Set zsh as shell](#set-zsh-as-shell)
  - [Restart shell and verify it's zsh](#restart-shell-and-verify-its-zsh)
  - [Install ohmyzsh](#install-ohmyzsh)
- [Install tldr](#install-tldr)
  - [Verify tldr](#verify-tldr)
  - [Update tldr](#update-tldr)
- [Install Python / pip](#install-python--pip)
  - [Verify Python / pip](#verify-python--pip)
  - [Update pip](#update-pip)
- [Set up pyenv](#set-up-pyenv)
  - [Install pyenv packages](#install-pyenv-packages)
  - [Install pyenv](#install-pyenv)
  - [Verify pyenv](#verify-pyenv)
- [Configure Python with pyenv](#configure-python-with-pyenv)
  - [Check available version](#check-available-version)
  - [Install stable version](#install-stable-version)
  - [View installed versions](#view-installed-versions)
  - [Set global version and verify](#set-global-version-and-verify)

## Install and run iTerm

Which terminal you decide to use moving forward is a matter of personal preference; however, for this guide I will be using and recommending **iterm** for Mac, which can be downloaded via:

- <https://iterm2.com/downloads.html>

> [!NOTICE]
>
> The rest of this guide will assume you're working from a terminal command line.

## Install XCODE

```bash
xcode-select --install
```

- You may be prompted to install additional software after. Please go ahead and accept.

- Installation of XCODE and the developer tools can take a long time to install, this is normal.

> [!NOTE]
>
> You can also install xcode via the App Store; however, this is a much bigger package and only `xcode-select` is needed for what we're doing.

### Verify XCODE

```bash
xcode-select -v
xcode-select -p
```

- A version number should follow the `-v` command.
  - Ex: `xcode-select version 2397.`
- A  common XCODE path should return from `-p`.
  - Ex: `/Library/Developer/CommandLineTools`

> [!NOTE]
>
> Another way to install the full package of XCODE would be via the Apple App Store; however, this is not required/recommended and may change your XCODE path.

**[- Back to Top -](#content)**

## Install brew

<https://brew.sh/>

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

> [!NOTE]
>
> The brew installer will have some additional 'Next Steps' that you will need to follow to correctly configure path variables.

### Verify brew

```bash
which brew
brew list
```

### Update brew

```bash
brew update
```

### Brew on Mac M1

<https://stackoverflow.com/questions/64963370/error-cannot-install-in-homebrew-on-arm-processor-in-intel-default-prefix-usr>

1. Install Rosetta2 emulator for the new ARM silicon (M1 chip):

    ```bash
    /usr/sbin/softwareupdate --install-rosetta --agree-to-license
    ```

2. Use the Homebrew cmd and install Homebrew for ARM M1 chip:  

    ```bash
    arch -x86_64 /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
    ```

    > [!IMPORTANT]
    >
    > Do NOT complete the 'Next Steps' when prompted by the installer. This will break your brew path! 


**[- Back to Top -](#content)**

## Set up zsh and ohmyzsh

### Install zsh

<https://opensource.com/article/19/9/getting-started-zsh>

```bash
brew install zsh
```

### Set zsh as shell

<https://ohmyz.sh/>

```bash
chsh -s /bin/zsh
```

### Restart shell and verify it's zsh

```bash
exec $SHELL
echo $SHELL
```

- echo shell should report `zsh` and not `bash`: </br> `/bin/zsh`

> [!NOTE]
>
> zsh will create a `.zshrc` file which can be edited to adjust your shell configuration. Moreover, once you have [VSCode set up](vscode.md), it can be edited through that via: `code -n .zshrc`

### Install ohmyzsh

<https://ohmyz.sh/>

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

> [!NOTE]
>
> onmyzsh will create a `.oh-my-zsh` file which can be edited to adjust your shell themes and extensions. Moreover, once you have [VSCode set up](vscode.md), it can be edited through that via: `code -n .oh-my-zsh`

**[- Back to Top -](#preparing-the-environment---mac)**

## Install tldr

<https://tldr.sh/>

```bash
brew install tldr
```

### Verify tldr

```bash
brew list
tldr tldr
tldr brew
```

### Update tldr

```bash
tldr -u
```

**[- Back to Top -](#content)**

## Install Python / pip

```bash
brew install python
```

### Verify Python / pip

```bash
brew list
# python
python3 -V
tldr python
# pip
pip --version
pip3 --version
pip list
pip3 list
tldr pip
```

> [!NOTE]
>
> If you're seeing `pip3` vs `pip` per example, that factor is dependant on the package alias and installation process. Using [pyenv](#set-up-pyenv) will resolve these discrepancies.

### Update pip

```brew
/Library/Developer/CommandLineTools/usr/bin/python3 -m pip install --upgrade pip
```

**[- Back to Top -](#content)**

## Set up pyenv

<https://github.com/pyenv/pyenv#installation>

### Install pyenv packages

```bash
brew install openssl readline sqlite3 xz zlib tcl-tk
```

### Install pyenv

```bash
brew install pyenv
```

### Verify pyenv

```bash
pyenv -v
tldr pyenv
```

**[- Back to Top -](#content)**

## Configure Python with pyenv

<https://github.com/pyenv/pyenv/wiki>

### Check available version

```bash
 pyenv install --list
 ```

### Install stable version

```bash
pyenv install 3.10.0
```

### View installed versions

```bash
pyenv versions
 ```

### Set global version and verify

```bash
pyenv global 3.10.0
# verify:
pyenv version
```

**[- Back to Top -](#content)**

---

**[- Notes / NetDevOps -](../..)**

**[- Notes / Home -](../../..)**
