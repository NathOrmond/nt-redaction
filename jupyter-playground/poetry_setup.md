# Migrating to Poetry

## Why?
- Current personal installation of python is a bit of a mess.
- It's fun.

## Pyenv set up
###  1. Installation using `homebrew`
```bash
brew install pyenv
brew install pyenv-virtualenv
brew install pyenv-virtualenvwrapper
```
### 2. Add stuff to bash / zsh profile
```bash
echo $SHELL # to find out which shell
```
If bash then write in `~/.bash_profile`, if zsh then `~/.zshrc`. Add these to lines to the files:
```bash
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```
Save!
### 3. Set up global python installation
```bash
pyenv install 3.7.9
pyenv global 3.7.9
```
- Other versions of Python are ok - not Python 2, you want the global version to be one that's up to date. We can downgrade for projects if / when it's required.
- If you don't do this the default will be Python 2.7 👎

## Poetry
### 1. Install Poetry 
```bash
curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python -
```
### 2. Add stuff to bash / zsh profile
```bash
echo $SHELL # to find out which shell
```
If bash then write in `~/.bash_profile`, if zsh then `~/.zprofile`. Add this to lines to the file:
```bash
export PATH="$HOME/.poetry/bin:$PATH"
```
and save!
### 3. Usage
[📁 **Documentation**][docs]
#### Creating a new project
```bash
poetry new project_name
```
#### Using poetry in a previously non poetry project
```bash
cd name-of-project/
poetry init
```

[docs]: https://python-poetry.org/docs/ "Poetry Documentation"