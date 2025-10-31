---
layout: post
title: "Git starter guide"
date: 2025-10-30
categories: [github, git]
tags: [git, cli, guide, source-control, version-control]
toc: true
description: "A starter guide on what version-control, Git and GitHub is, how each differ as well as what and how they're used."
---

### Context
- This is for someone with no previous experience with version control. The purpose of this guide is to explain what version control is, why it's important and how it's used.

## Version control (the concept)
#### What is version control
- Version control is a fancy way of saying the history of a document. This is the same as the Microsoft functionality "restore version" which is available on Word documents or files hosted within SharePoint.
#### Purpose
- This allows you to make changes without fear of permanently ruining your file. It's a concept created to allow the restore of previous versions of a file.

## Git (the tool)
#### Background
- **Git** was created by Linus Torvalds (the same person who created Linux) in 2005. The name "Git" is British slang for "unpleasant person" - Linus has a sense of humor and named it after himself as a joke.
#### What is Git
- Version control is the concept, Git is the tool that is installed locally to provide the functionality described.
### Why is Git used
- Single user
	- Provides version history to rollback a failed change
- Multiple users
	- To allow someone to submit a change, the change be reviewed, if approved, it's then merged into the existing project - this is called either a pull or merge request (depending on the tool you're using)

## GitHub (the hosting platform)
### Background
- **GitHub** was created by different people (Tom Preston-Werner, Chris Wansteth, and PJ Hyett) in 2008, three years later. They named it "GitHub" because:
	- "Git" = the tool they were building a service for
	- "Hub" = a central place where people gather/share
#### What is GitHub
- GitHub is the website that hosts your files, the same way Dropbox, iCloud, Google Drive etc host files. GitHub has additional features that make it a better platform for working collaboratively with code.

---

## Git deeper dive
- Git goes way further into detail than what's above, however the details in the first section are enough to understand the difference between the concept (version control), the tool (Git), and the file hosting platform (GitHub). Let's get into the detail.

#### Git lifecycle stages
1. **Working Directory** - When you're working within an IDE (Visual Studio Code for example), you first open the files you're working on from you local file directory. The folder that stores the files you're working on is known as the working directory. Currently these files are only stored on your local machine and not tracked by Git.
2. **Staging Area** - The staging area is essentially a preview of what files you're going to be committing. The purpose of the staging area is to give you a preview of what files are within scope for the commit so that you can clarify you're not about to take a snapshot of incorrect files (a sensitive file like an API key for example).
3. **Local Repository** - A repository is essentially just a folder. Each time you want to backup your project, this creates a new version known as a snapshot which is saved to this local repo. This is still currently only saved on your local device.
4. **Remote Repository** - This is the first of the 4 stages which relates to GitHub (the online platform). This is the stage where you push the various saves versions (snapshots) of your project to an online repo. Pushing your snapshots to an online repo now means that other members of the repo can view them.


<html> 
	<head> 
		<meta charset="UTF-8"> 
			<style> 
				body { margin: 20px; font-family: Arial, sans-serif; } 
				svg { max-width: 100%; height: auto; } 
			</style> 
		</head> 
		<body> 
			<svg viewBox="0 0 1200 400" xmlns="http://www.w3.org/2000/svg"> 
			<!-- Arrow marker --> 
			<defs> 
				<marker id="arrow" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto"> 
					<polygon points="0 0, 10 3, 0 6" fill="#333" /> 
				</marker> 
			</defs> 
			
			<!-- LOCAL container --> 
			<rect x="30" y="80" width="800" height="240" fill="#e3f2fd" stroke="#1976d2" stroke-width="3" rx="10"/> 
			<text x="430" y="60" font-size="24" font-weight="bold" fill="#1976d2" text-anchor="middle">LOCAL</text> 
			
			<!-- REMOTE container --> 
			<rect x="900" y="80" width="260" height="240" fill="#fff3e0" stroke="#f57c00" stroke-width="3" rx="10"/> 
			<text x="1030" y="60" font-size="24" font-weight="bold" fill="#f57c00" text-anchor="middle">REMOTE</text> 
			
			<!-- Stage 1: Working Directory --> 
			<rect x="60" y="150" width="180" height="100" fill="white" stroke="#333" stroke-width="2" rx="5"/> 
			<text x="150" y="195" font-size="16" font-weight="bold" text-anchor="middle">Working</text> 
			<text x="150" y="215" font-size="16" font-weight="bold" text-anchor="middle">Directory</text> 
			
			<!-- Stage 2: Staging Area --> 
			<rect x="310" y="150" width="180" height="100" fill="white" stroke="#333" stroke-width="2" rx="5"/> 
			<text x="400" y="195" font-size="16" font-weight="bold" text-anchor="middle">Staging</text> 
			<text x="400" y="215" font-size="16" font-weight="bold" text-anchor="middle">Area</text> 
			
			<!-- Stage 3: Local Repository --> 
			<rect x="560" y="150" width="180" height="100" fill="white" stroke="#333" stroke-width="2" rx="5"/> 
			<text x="650" y="195" font-size="16" font-weight="bold" text-anchor="middle">Local</text> 
			<text x="650" y="215" font-size="16" font-weight="bold" text-anchor="middle">Repository</text> 
			
			<!-- Stage 4: Remote Repository --> 
			<rect x="930" y="150" width="200" height="100" fill="white" stroke="#333" stroke-width="2" rx="5"/> 
			<text x="1030" y="195" font-size="16" font-weight="bold" text-anchor="middle">Remote</text> 
			<text x="1030" y="215" font-size="16" font-weight="bold" text-anchor="middle">Repository</text> 
			<text x="1030" y="235" font-size="14" fill="#666" text-anchor="middle">(GitHub)</text> 

			<!-- Curved arrow 1: git add --> 
			<path d="M 240 180 Q 275 120 310 180" fill="none" stroke="#333" stroke-width="2" marker-end="url(#arrow)"/> 
			<text x="275" y="120" font-size="14" fill="#333" font-family="monospace" text-anchor="middle">git add</text> 

			<!-- Curved arrow 2: git commit --> 
			<path d="M 490 180 Q 525 120 560 180" fill="none" stroke="#333" stroke-width="2" marker-end="url(#arrow)"/> 
			<text x="525" y="120" font-size="14" fill="#333" font-family="monospace" text-anchor="middle">git commit</text> 

			<!-- Curved arrow 3: git push --> 
			<path d="M 740 180 Q 835 120 930 180" fill="none" stroke="#333" stroke-width="2" marker-end="url(#arrow)"/> 
			<text x="785" y="120" font-size="14" fill="#333" font-family="monospace" text-anchor="middle">git push</text> 
		</svg> 
	</body> 
</html>

### Workflow
#### Initial setup (creating a local repository)
1. create new folder locally (can do this from within your IDE)
2. create files in the folder
3. initialise git within the folder- `git init`
	1. this creates an invisible folder called .git

#### Connecting your local repo to GitHub (setting up the connection)
1. create new github repo (from github.com via the web UI)
2. copy the url for the repo - (example: https://github.com/user-name/user-name.github.io)
3. connect your local repo to the remote repo - `git remote add origin {github url}`
	1. git remote - this is used to manage connections
	2. add - used to add a new connection
	3. origin - this is nickname you're assigning the url to

#### First commit and push (initial upload to GitHub)
1. add the files to the staging area - `git add {file name}`
	1. Tip: To add all files - `git add .`
2. save the files to a local repo (commit) - `git commit -m {message to add with the commit}`
	1. at this point the files are now "tracked"
3. upload the snapshots from your local to the remote repo - `git push -u origin main`
	1. git push = push changes to remote repo
	2. -u = the -u flag is short for (--set-upstream). This creates a tracking relationship so Git knows where to push in the future
	3. origin = push changes to your GitHub remote repo
	4. main = the branch name

#### Regular workflow (when saving changes)
1. Same workflow as the initial workflow
2. As we used the -u flag when pushing initially, this means every future push only requires the following - `git push`