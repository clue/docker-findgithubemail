# docker-FindGitHubEmail

[FindGitHubEmail](https://github.com/hodgesmr/FindGitHubEmail) - a simple script to find the email address of any GitHub user.
This is a [docker](https://www.docker.io) image that eases setup.

## About FindGitHubEmail

> *From [the official readme](https://github.com/hodgesmr/FindGitHubEmail#readme):*

It's a well-known fact (or at least it should be) that everything you push to a public GitHub repository is *public*.
This includes a lot of information other than just source files.
Since both Git and GitHub require you to provide an email address, it should be no surprise that this information is public as well.
**FindGitHubEmail** (catchy title, I know) is a simple script that queries the [GitHub API](http://developer.github.com/v3/)
and guesses a given user's email address based on their public activity.
The script is a bit of a hack; sorry if your eyes are bleeding.

**FindGitHubEmail** makes it easy to get in contact with open source developers. Please use it for good, not evil.

## Install

This docker image is available as a [trusted build on the docker index](https://index.docker.io/u/clue/findgithubemail/),
so using it is as simple as running:

```bash
$ docker run clue/findgithubemail
```

Running this command for the first time will download the image automatically.
Further runs will be immediate, as the image will be cached locally.

To further ease running, it's recommended to set up a much shorter `alias`
so that you can easily execute it as just `github-email`:

```bash
$ alias github-email='docker run -it --rm clue/findgithubemail'
```

This will create a temporary alias. In order to make it persist reboots,
you can append this exact line to your `~/.bashrc` (or similar) like this:

```bash
$ alias github-email >> ~/.bashrc
```

## Usage

Once [installed](#install), running FindGitHubEmail is as simple as invoking it like this:

```bash
$ github-email clue
```

> *From [the official usage help](https://github.com/hodgesmr/FindGitHubEmail#usage):*

The above will return the best guess of the email based on the user's event log.
If you're not looking for me, replace `clue` with another GitHub user.

Print all emails in the user's event log:

```bash
$ github-email -e clue`
```

Or cross-check the discovered emails with the user's Gravatar ID:

```bash
$ github-email -g clue`
```

Or if you're unsure and need the usage info:

```bash
$ github-email
```
