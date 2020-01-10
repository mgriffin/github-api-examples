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

### Okay, that's wonderful, but how do I find out about a user?

You can get back public information on any user on GitHub.com by requesting the [get a single user](https://developer.github.com/v3/users/#get-a-single-user) endpoint.

```
curl https://api.github.com/users/octocat
```

When you run this, this is the sort of information you will get back:

```
$ curl https://api.github.com/users/octocat
{
  "login": "octocat",
  "id": 583231,
  "node_id": "MDQ6VXNlcjU4MzIzMQ==",
  "avatar_url": "https://avatars3.githubusercontent.com/u/583231?v=4",
  "gravatar_id": "",
  "url": "https://api.github.com/users/octocat",
  "html_url": "https://github.com/octocat",
  "followers_url": "https://api.github.com/users/octocat/followers",
  "following_url": "https://api.github.com/users/octocat/following{/other_user}",
  "gists_url": "https://api.github.com/users/octocat/gists{/gist_id}",
  "starred_url": "https://api.github.com/users/octocat/starred{/owner}{/repo}",
  "subscriptions_url": "https://api.github.com/users/octocat/subscriptions",
  "organizations_url": "https://api.github.com/users/octocat/orgs",
  "repos_url": "https://api.github.com/users/octocat/repos",
  "events_url": "https://api.github.com/users/octocat/events{/privacy}",
  "received_events_url": "https://api.github.com/users/octocat/received_events",
  "type": "User",
  "site_admin": false,
  "name": "The Octocat",
  "company": "GitHub",
  "blog": "http://www.github.com/blog",
  "location": "San Francisco",
  "email": null,
  "hireable": null,
  "bio": null,
  "public_repos": 8,
  "public_gists": 8,
  "followers": 2910,
  "following": 9,
  "created_at": "2011-01-25T18:44:36Z",
  "updated_at": "2020-01-02T15:35:57Z"
}
```
