---
layout: post
title: Self-Deployed GitHub Stats
---

# Self-Deployed GitHub Stats

After creating the [Dynamic GitHub Profile](2023-04-30-dynamic-github-profile.md) in the previous post, I noticed
that my profile widgets were broken the next morning. Very strange, but I looked into the repo's
[issues](https://github.com/anuraghazra/github-readme-stats/issues/1471) and discovered that this can happen when
the host's Vercel instance that is running the stats tracker gets rate limited from getting more uncached requests
than their GitHub Personal Access Tokens can allow.

![Broken Stats](/assets/self-deployed-github-stats/broken-stats.png)

To be clear, the downtime is only for an hour, but if you want to be sure that a potential employer can see your
profile in its full glory, that could be a problem.

Luckily, there is an easy fix. The project is open-source, and it is very easy to host our own free Vercel instance
running the stats tracker with our own GitHub Personal Access Token.

## Table of Contents
- [Dynamic GitHub Profile](#dynamic-github-profile)
  - [Table of Contents](#table-of-contents)
- [What is a GitHub profile README](#what-is-a-github-profile-readme)
- [How to make a dynamic profile README](#how-to-make-a-dynamic-profile-readme)
  - [Make the profile README repository](#make-the-profile-readme-repository)
  - [Header + Emojis](#header--emojis)
  - [Profile Widgets](#profile-widgets)
    - [GitHub Statistics Widget](#github-statistics-widget)
      - [Widget Code](#widget-code)
      - [Widget Appearance](#widget-appearance)
    - [Top Languages Widget](#top-languages-widget)
      - [Widget Code](#widget-code-1)
      - [Widget Appearance](#widget-appearance-1)
  - [Badges](#badges)
    - [Badges Code](#badges-code)
    - [Badges Appearance](#badges-appearance)
  - [Dynamic GitHub + Blog Activity Tracking](#dynamic-github--blog-activity-tracking)
    - [GitHub Pages RSS Tracking](#github-pages-rss-tracking)
    - [GitHub Contributions Tracking](#github-contributions-tracking)
- [Full dynamic README generation template](#full-dynamic-readme-generation-template)
- [Automatic README generation GitHub action workflow](#automatic-readme-generation-github-action-workflow)
  - [Add personal access token to action](#add-personal-access-token-to-action)


## Fork the GitHub Stats repository

Navigate to https://github.com/anuraghazra/github-readme-stats and click the `fork` button at the top right to create
a fork that you can use for the Vercel instance.

*** If you choose the free Vercel tier, make sure that the `maxDuration`
flag in `vercel.json` is set to 10.


## Create a new GitHub Personal Access Token

1. Navigate to the personal access tokens page
   1. This can be found by going to settings > Developer Settings > Personal Access Tokens or by
[this link](https://github.com/settings/tokens).
2. Click `Generate a new token`
   1. It does **NOT** need any permissions to function, so do not select any
3. Copy the generated token


## Create Vercel instance

1. Navigate to https://vercel.com/
2. Create a new account with your GitHub account
3. Select Hobby (unless you want to pay for Pro for other projects)
4. Click `Create a new project`
5. Install to your GitHub account and select `Only select repositories`
6. Select the `github-readme-stats` fork you made
7. Click install
8. Click `Import` on the GitHub repo that you just added to the project
9. Add the Personal Access Token as an Environment Variable
   1. Name the variable `PAT_1`
   2. Paste the personal access token you generated as the value
   3. Click `Add`
10. Click `Deploy`


## Update the GitHub profile README template

1. Click `Continue to dashboard` once the Vercel app has been successfully
deployed
2. Copy the domain provided
3. Replace the original stats domain with the one we just deployed
   1. Originally it was `github-readme-stats.vercel.app`
   2. Replace only this portion with your new app's domain for both of
the widgets
4. Push the updated template to GitHub


That's all there is to it. They have made it super easy to get it set up and
running on your own free deployment. This should fix any potential issues
with downtime on your profile widgets.
