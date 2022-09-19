# Environment Setup

### Installing Git

First of all, download the last version of git:

```bash
sudo apt install git-all
```

Install _gh_ package in order to use github from cli:

```bash
sudo snap install gh
```

### Creating a GitHub account

After installing Git, [go to GitHub’s website](https://github.com/) and create an account with your email address.

### Setting up GitHub CLi

```
git config --global user.name "dav-esci"
git config --global user.email networkdav.x@gmail.com
```

### Connect with SSH

```
ssh-keygen -t ed25519 -C "networkdav.x@gmail.com"
```

1.  Start the ssh-agent in the background.

    ```shell
    $ eval "$(ssh-agent -s)"
    > Agent pid 59566
    ```

    Depending on your environment, you may need to use a different command. For example, you may need to use root access by running `sudo -s -H` before starting the ssh-agent, or you may need to use `exec ssh-agent bash` or `exec ssh-agent zsh` to run the ssh-agent.
2.  Add your SSH private key to the ssh-agent. If you created your key with a different name, or if you are adding an existing key that has a different name, replace _id\_ed25519_ in the command with the name of your private key file.

    ```shell
    $ ssh-add ~/.ssh/id_ed25519
    ```
3. Add the SSH key to your account on GitHub. For more information, see "[Adding a new SSH key to your GitHub account](https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)."



