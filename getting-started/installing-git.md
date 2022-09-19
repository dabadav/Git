# Environment Setup

### Installing Git

First of all, download the last version of git:

```bash
sudo apt install git-all
```

### Creating a GitHub account

After installing Git, [go to GitHub’s website](https://github.com/) and create an account with your email address.

### Setting up GitHub for CLI

```
git config --global user.name "dav-esci"
git config --global user.email networkdav.x@gmail.com
```

* [Verify your email address](https://docs.github.com/en/github/getting-started-with-github/verifying-your-email-address), if it hasn't been verified yet.
*   In the upper-right corner of any page, click your profile photo, then click **Settings**.



    <figure><img src="https://docs.github.com/assets/cb-34573/images/help/settings/userbar-account-settings.png" alt=""><figcaption></figcaption></figure>
* In the left sidebar, click

1. **Developer settings**.
2.  In the left sidebar, click **Personal access tokens**.&#x20;

    <figure><img src="https://docs.github.com/assets/cb-7169/images/help/settings/personal_access_tokens_tab.png" alt=""><figcaption></figcaption></figure>
3.  Click **Generate new token**.&#x20;

    <figure><img src="https://docs.github.com/assets/cb-6922/images/help/settings/generate_new_token.png" alt=""><figcaption></figcaption></figure>
4.  Give your token a descriptive name.&#x20;

    <figure><img src="https://docs.github.com/assets/cb-3880/images/help/settings/token_description.png" alt=""><figcaption></figcaption></figure>
5.  To give your token an expiration, select the **Expiration** drop-down menu, then click a default or use the calendar picker.&#x20;

    <figure><img src="https://docs.github.com/assets/cb-39847/images/help/settings/token_expiration.png" alt=""><figcaption></figcaption></figure>
6.  Select the scopes, or permissions, you'd like to grant this token. To use your token to access repositories from the command line, select **repo**.



    <figure><img src="https://docs.github.com/assets/cb-43299/images/help/settings/token_scopes.gif" alt=""><figcaption></figcaption></figure>
7.  Click **Generate token**.&#x20;



    **Warning:** Treat your tokens like passwords and keep them secret. When working with the API, use tokens as environment variables instead of hardcoding them into your programs.

    <figure><img src="https://docs.github.com/assets/cb-10912/images/help/settings/generate_token.png" alt=""><figcaption></figcaption></figure>

    <figure><img src="https://docs.github.com/assets/cb-33474/images/help/settings/personal_access_tokens.png" alt=""><figcaption></figcaption></figure>

#### Using a token on the command line <a href="#using-a-token-on-the-command-line" id="using-a-token-on-the-command-line"></a>

Once you have a token, you can enter it instead of your password when performing Git operations over HTTPS.

For example, on the command line you would enter the following:

```shell
$ git clone https://github.com/username/repo.git
Username: your_username
Password: your_token
```

