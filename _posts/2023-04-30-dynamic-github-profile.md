---
layout: post
title: Dynamic GitHub Profile
---

# Dynamic GitHub Profile

If you are only interested in the full code, jump to the [Full dynamic README generation template](#full-dynamic-readme-generation-template) and [Automatic README generation GitHub action workflow](#automatic-readme-generation-github-action-workflow) sections after creating the profile repository in [Make the profile README repository](#make-the-profile-readme-repository)

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


# What is a GitHub profile README

A public-facing GitHub profile is one of the best ways to show a portfolio of code.
Anyone interested in hiring or collaborating can see immediately what kinds of projects you have worked on
and dive into your code to see good coding habits and well-written documentation.

The first place they will land when they navigate to your GitHub page is your profile. 
There, they can immediately see a few things by default:

1. Your profile picture and bio

    This is a great place to show a professional headshot, a brief bio, and link to a portfolio website, blog, socials (LinkedIn).

    ![GitHub Bio](/assets/dynamic-github-profile/bio.png)

2. Your pinned repositories
   
   If there are projects that you have made signifcant contributions to that you want to prioritize, they should be pinned

    ![Pinned Repositories](/assets/dynamic-github-profile/pinned-repos.png)

3. Contribution Activity
   
   Unless you are employed and working on private codebases, it is good to show that you are actively working on projects
and actively learning. Your commits, issues, pull requests, and other publicly tracked contributions will be shown here.

    ![Contribution Activity](/assets/dynamic-github-profile/contributions.png)

1. Profile README
   1. Not everyone knows that you are able to have a profile README file that shows at the top of your GitHub profile page.
This is a great way to stand out to anyone coming to your profile and provides an extra opportunity to show off projects you are proud of
and your key skills.
    1. Mine here is dynamically updated to display my current GitHub statistics, recent repo activity, and recent blog posts from GitHub pages.

    ![README Profile](/assets/dynamic-github-profile/README.png)


# How to make a dynamic profile README

## Make the profile README repository

The first step is to make the GitHub profile repository that will house the README.md file and our GitHub actions.

1. Click the New button to create a new repository. 
2. Enter your GitHub profile name as the name of the repository
   1. You will see a special message confirming that this is for the profile README
3. Make sure the repo is set to `Public`
4. Check the `Add a README file` checkbox
5. Create the repo

![Create README repository](/assets/dynamic-github-profile/create-repo.png)

Now it is ready to integrate the widgets, badges, and GitHub Actions.

## Header + Emojis

My header is very simple:

```
# Hi there, I'm Daniel! :wave:
```

Adding emojis to the markdown file is very easy. You can either copy and paste
the emoji or use the shortcode. A cheatsheet of emojis and shortcodes that can be used with GitHub can be found [here](https://github.com/ikatyang/emoji-cheat-sheet).

## Profile Widgets

I use the [GitHub Readme Stats](https://github.com/anuraghazra/github-readme-stats) widgets for my profile stats and top languages.
Check out their repo for their full array of widgets and customization options.

You can copy the code directly from them, or use my setup. 
I embed the widget in an HTML `<img>` tag in order to customize the alignment and width to ensure the two widgets line up correctly.

### GitHub Statistics Widget

1. Total Stars Earned
2. Total Commits
3. Total PRs
4. Total Issues
5. Projects Contributed To


**WARNING:** With the number of people that use this widget, it does sometimes get rate-limited and will be down for an hour.
If you want to avoid this, you can self-host your own instance of the app by following the instructions in [this post]({% post_url 2023-05-01-self-deployed-github-stats %}).

#### Widget Code

```html
<img align="left" width="54%" src="https://github-readme-stats.vercel.app/api?username=dagleaves&theme=dark&include_all_commits=true&count_private=true&show_icons=true" />
```

Make sure to replace the username flag with your username. I use the dark theme, but there are many 
[available themes](https://github.com/anuraghazra/github-readme-stats/blob/master/themes/README.md). 
I also choose to display all commits, including private ones, instead of just data from the current year.

#### Widget Appearance

![Stats Widget](https://github-readme-stats.vercel.app/api?username=dagleaves&theme=dark&include_all_commits=true&count_private=true&show_icons=true)


### Top Languages Widget

This widgets displays the percentages of your most commonly used languages across your repos.

#### Widget Code

```html
<img align="left" width="41%" src="https://github-readme-stats.vercel.app/api/top-langs/?username=dagleaves&layout=compact&theme=dark&include_all_commits=true&count_private=true" />
```

#### Widget Appearance

![Top Langs Widget](https://github-readme-stats.vercel.app/api/top-langs/?username=dagleaves&layout=compact&theme=dark&include_all_commits=true&count_private=true)


## Badges

Badges are a great way to add a pleasing visual showing off technologies you are familiar with.
There are hundreds of available badges. You can find a list of badges [here](https://github.com/Ileriayo/markdown-badges).

### Badges Code

{% raw %}
```
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
<a href="https://www.linkedin.com/in/dagleaves/"><img src="https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white"/></a>
```
{% endraw %}

If you want to turn them into clickable links, as I did for my LinkedIn profile, simply use the link as the `src` attribute in an `<img>` element and wrap it in an 
`<a>` anchor element. Set the `href` attribute to where you want it to redirect to.


### Badges Appearance

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
<a href="https://www.linkedin.com/in/dagleaves/"><img src="https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white"/></a>


## Dynamic GitHub + Blog Activity Tracking

The two sections of my profile README that I like the most are the activity tracking. The README gets automatically updated with my most recent GitHub contributions and my most recent blog posts using GitHub actions.

The way I accomplish this is by using the [readme-scribe](https://github.com/muesli/readme-scribe) GitHub action. 
This will automatically generate a README based on a provided [markscribe](https://github.com/muesli/markscribe) template, which allows us to dyamically-updated content, such as 
RSS feeds and all kinds of GitHub activity tracking. 
You can see the full list of available tracking in the markdownify link above.

### GitHub Pages RSS Tracking

In order to track the entries from this blog, which is hosted by GitHub pages with Jekyll, I use the automatically generated `atom.xml` feed. This can be found at https://dagleaves.github.io/atom.xml.

{% raw %}
```
## :book: My blog posts
{{range rss "https://dagleaves.com/atom.xml" 5}}
- [{{.Title}}]({{.URL}})
{{- end}}
```
{% endraw %}

### GitHub Contributions Tracking

Tracking GitHub contributions is handled entirely by markscribe by providing a personal access token to the readme-scribe action.

{% raw %}
```
## 👷 I'm currently working on
{{range recentContributions 5}}
- [{{.Repo.Name}}]({{.Repo.URL}}) - {{.Repo.Description}} ({{humanize .OccurredAt}})
{{- end}}
```
{% endraw %}

You can adjust the number of contributions shown by changing the `5` in the top range field. This shows the names, descriptions, and last contribution time for each of my 5 most recent public GitHub contributions.


# Full dynamic README generation template

The final two pieces are the full template and the GitHub action workflow file.

1. Clone your profile README repo:
    ```sh
    git clone https://github.com/username/username.git
    cd username
    ```
2. Make a templates folder (optional):
    ```sh
    mkdir templates
    cd templates
    ```
3. Create the README template file:
    ```sh
    touch README.md.tpl
    ```
4. Enter the full template code:


{% raw %}
```
# Hi there, I'm Daniel! :wave:

<img align="left" width="54%" src="https://github-readme-stats.vercel.app/api?username=dagleaves&theme=dark&include_all_commits=true&count_private=true&show_icons=true" />
<img align="left" width="41%" src="https://github-readme-stats.vercel.app/api/top-langs/?username=dagleaves&layout=compact&theme=dark&include_all_commits=true&count_private=true" />

<br/><br/>
<br/><br/>
<br/><br/>
<br/><br/>
<br/><br/>

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
<a href="https://www.linkedin.com/in/dagleaves/"><img src="https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white"/></a>

## About Me

🎓 Pursuing B.S. in Computer Science @ [University of South Carolina](https://sc.edu/study/majors_and_degrees/computer_science_computer_engineering.php). 

📖 Conducting research on **AI** and **Large Language Models**

💻 Currently working on LLM applications for recommender systems and automated research.

:seedling: Currently learning [LangChain](https://github.com/hwchase17/langchain) and [PyTorch Lightning](https://github.com/Lightning-AI/lightning).


## 👷 I'm currently working on
{{range recentContributions 5}}
- [{{.Repo.Name}}]({{.Repo.URL}}) - {{.Repo.Description}} ({{humanize .OccurredAt}})
{{- end}}


## :book: My blog posts
{{range rss "https://dagleaves.com/atom.xml" 5}}
- [{{.Title}}]({{.URL}})
{{- end}}
```
{% endraw %}


# Automatic README generation GitHub action workflow

The final remaining piece is to use the readme-scribe GitHub action to automatically update the profile README every hour. 

1. In the base repo directory, create the .github/workflows folder.

```sh
mkdir .github
mkdir .github/workflows
```

2. Create the `readme-scribe.yml` workflow file

{% raw %}
```yml
name: Update generated README 
on:
    schedule:
        - cron: "0 */1 * * *"
    workflow_dispatch:
permissions:
    contents: write
    

jobs:
    markscribe:
        runs-on: ubuntu-latest
        steps:
            - uses: actions/checkout@master

            - uses: muesli/readme-scribe@master
                env:
                    GITHUB_TOKEN: ${{ secrets.PERSONAL_GITHUB_TOKEN }}
                with:
                    template: "templates/README.md.tpl"
                    writeTo: "README.md"

            - uses: actions/upload-artifact@v1
                with:
                    name: README.md
                    path: README.md

            - uses: stefanzweifel/git-auto-commit-action@v4
                env:
                    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
                with:
                    commit_message: Update generated README
                    branch: main
                    commit_user_name: readme-scribe 🤖
                    commit_user_email: actions@github.com
                    commit_author: readme-scribe 🤖 <actions@github.com>
```
{% endraw %}

Two important notes: 

1. Make sure your branch name matches at the bottom of the file. I use the `main` branch. This is the branch that it will look at for the template and where it will generate the README file.
2. You must provide a personal access token to the action named `PERSONAL_GITHUB_TOKEN` in order for it to work. 

This will have GitHub run the action every hour to fetch the latest data and generate a new README file.


## Add personal access token to action

**IMPORTANT**: Do **NOT** paste a personal access token plainly into an action workflow file. Always use GitHub's secret system to ensure your token is kept encrypted and safe.

1. Generate a new token
   1. This can be found by going to settings > Developer Settings > Personal Access Tokens or by [this link](https://github.com/settings/tokens).
   2. Click generate a new token and give it the necessary permissions (per the readme-scribe documentation)
      1. `read:user`
      2. `repo:status`
      3. `public_repo`
      4. `read:org`
    3. Copy the generated token
2. Go to the profile repo's action secrets page
   1. Repo > Settings > Secrets and variables > Actions or https://github.com/username/username/settings/secrets/actions
   2. Click `New repository secret`
   3. Name it `PERSONAL_GITHUB_TOKEN`
   4. Paste the generated token
   5. Add secret

That's it! You can test the action by manually triggering it in the `Actions` tab and check to make sure your profile `README.md` file looks correct.