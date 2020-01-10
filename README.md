# GitHub API examples

## Introduction

### What's the simplest thing I can do?

```
curl https://api.github.com/zen
```

Running this from your command line will show something like this:

```
$ curl https://api.github.com/zen
Anything added dilutes everything else.
```

### But I use GitHub Enterprise, how do I do that there?

Let's assume that your GitHub Enterprise instance is hosted on `https://example.com`.
The GitHub Enterprise API starts with `/api/v3/` which makes the simplest call this one:

```
curl https://example.org/api/v3/zen
```

### But my GitHub Enterprise instance is running in private mode

In that case you will need to authenticate to get a reply back from the API.
There are a [few ways to do this](https://developer.github.com/enterprise/v3/#authentication) but we'll only look at using a [personal access token](https://help.github.com/en/enterprise/user/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line).


```
curl -H 'Authorization token [your-token]' https://example.org/api/v3/zen
```
