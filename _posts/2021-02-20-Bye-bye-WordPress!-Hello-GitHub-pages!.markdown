---
layout: post
title: Bye Bye WordPress! Hello GitHub Pages!
date: 2021-02-20 13:37:00 +0100
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: Bye-Bye-Wordpress-Hello-GitHub-Pages!.png # Add image post (optional)
tags: [Blog, Everything-as-Code, Code, GitHub, GithubPages, WordPress] # add tag
---
How to step up your blog using GitHub-Pages using Jekyll. The WordPress days are gone.

After realizing, as stated in my [**everything and everywhere is code**](/MakingTheAzureDevopsTransition) blog post, I just couldn't keep a blog based on WordPress. Ryan, who runs the [Go-EUCplatform](https://go-euc.com) pointed out to me that GitHub also can host [GitHub Pages](https://pages.github.com), even for your own (sub-)domain.

### Why changing over?

First of all, I like the Github repository-based 

Criteria | Github Pages | WordPress
------------ | ------------ | -------------
Git-based | - | +++++
Speed | +++++ | +++
Version control | +++++ | +++
Plugins | + | +++++
Webspace needed | $false | $true
Admin page | $false | $true


## Requirements

In this blog I use a Windows based tool chain, as this is the least steep learning curve, IMHO.

*	Microssoft Windows 10
*	[Ruby+Devkit 2.7.x (x64)](https://github.com/oneclick/rubyinstaller2/releases/download/RubyInstaller-2.7.2-1/rubyinstaller-devkit-2.7.2-1-x64.exe)
*	[GitHub Desktop](https://central.github.com/deployments/desktop/desktop/latest/win32)
*	[Microsoft Visual Studio Code](https://code.visualstudio.com/docs/?dv=win)
*	Ability to change the DNS records for your domain

Optional
*	[Github Pages Markdown Cheatsheet](/assets/pdf/markdown-cheatsheet-online.pdf) to peek at while creating content
*	[7Zip](https://www.7-zip.org/download.html) for ease of (de)crunching files
*	[GIMP](https://download.gimp.org/pub/gimp/v2.10/windows/) to beautify you visual content


### Setting up GitHub repository

1. Join Github by (creating an GitHub account)[https://github.com/join]

2. Create, as a minimal requirement, a public Github repository, see [Getting started with GitHub documentation](https://docs.github.com/en/github/getting-started-with-github/create-a-repo)

3. Download and install [GitHub Desktop](https://central.github.com/deployments/desktop/desktop/latest/win32) to be able to commit you changes.

#### Cloning your GitHub repository locally

Cloning a repository, see [GitHub reposirtory documentation](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository)

When you create a repository on GitHub, it exists as a remote repository. You can clone your repository to create a local copy on your computer and sync between the two locations. In this examply we use GitHub Desktop to sync back and forth.

#### Working with GitHub Desktop



#### Creating a local [Jekyll](https://jekyllrb.com/) instance

1.	Download the [Ruby+Devkit 2.7.x (x64)](https://github.com/oneclick/rubyinstaller2/releases/download/RubyInstaller-2.7.2-1/rubyinstaller-devkit-2.7.2-1-x64.exe)
2.	Run the setup using the default values
3.	Have the installer run the ```ridk install```, as per default installation
4.	Press "Enter" to use the default
5.	Start a new ```cmd.exe``` to ensure that the environment variables are freshly loaded.
6.  start ```gem install jekyll bundler``` on the command line interface 
7.	If needed install the missing/required gems using the command: 
	```gem install minitest tzinfo zeitwerrk activesupport gemoji nokogiri html-pipeline jekyll-paginate jekyll-sitemap jemoji racc rexml``` 

	TZInfo 2.0 incompatibility

		Version 2.0 of the TZInfo library has introduced a change in how timezone offsets are calculated. This will result in incorrect date and time for your posts when the site is built with Jekyll 3.x on Windows.

		We therefore recommend that you lock the Timezone library to version 1.2 and above by listing gem 'tzinfo', '~> 1.2' in your Gemfile.


#### Starting a local copy of the website
Navigate in the command line to the locally installed template

```cd c:\Repository\JekyllTemplate```

Start the Jekyll in webserver mode

```jekyll serve -s .```

Start a web browser for [http://127.0.0.1:4000](http://127.0.0.1:4000)

Now you can easily modify the website and the subsequent markdown files to your liking prior to uploading it to your GitHub repository.

#### Testing your website locally

Make granular changes and regular local commits. By committing locally you build up a versioning of the files so you can easily revert changes or recover lost files.

#### DNS record for online instance

Setup DNS-records for your own domain.

*	code	CNAME	berrydejager.github.io.
	

#### Setup GitHub Pages

Choose a source (branch)
	
Choose a theme
	
Use you own domain

NAME file in the repo
	
HTTPS
	
Choose theme

### Download a theme

### customize config.YAML

#### Publishing your local copy to the GitHub Pages

Start GitHub Desktop

Make sure your changes are committed locally

Push your changes to the master/main at the origin.

#### Checking the deployment of the GitHub Pages

You can see the status at [activity log](https://github.com/berrydejager/code/deployments) on GitHub.

#### Getting a 404 on your first commit?

You can either make a (dummy) change in the repo and push it to GitHub.com or either push an empty commit on the command line.

``` 
git commit --allow-empty -m "Emtpy commit to trigger GitHub Pages to build"
git push
```