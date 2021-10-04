# Hugo Quickstart on Vercel

Testing: will the Hugo quickstart be easily published on Vercel? TL;DR: yes, no problem.

https://gohugo.io/getting-started/quick-start/

First, just run through the quick start steps in a local folder to get it basically working. 

Then connect to Vercel by running `vercel` in the project folder. 

```
vercel
Setup and deploy? Y
Which scope? Rick Cogley
(pick user or org, and I picked "Rick Cogley" my account)
Link to existing project? N
Project name: hugo-quickstart
In which directory is your code located? ./
Override settings? N
Deploying...
```

Then you get some info about the deployed site. 

```
Want to override the settings? [y/N] N
🔗  Linked to rickcogley/hugo-quickstart (created .vercel and added it to .gitignore)
🔍  Inspect: https://vercel.com/rickcogley/hugo-quickstart/APeDa4... [3s]
✅  Production: https://hugo-quickstart-lilac.vercel.app [copied to clipboard] [28s]
📝  Deployed to production. Run `vercel --prod` to overwrite later (https://vercel.link/2F).
💡  To change the domain or build command, go to https://vercel.com/rickcogley/hugo-quickstart/settings
user=1.07s system=0.25s cpu=0% total=2:39.28
```

Edit your `config.toml` and add the URL that Vercel provided as a baseURL. Copy the `vercel.json` from this repo and add it to the base of your project. 

Now create a repository in Github, but _do not_ add a README or anything. Then do these commands to add the new repository as a remote, add and commit the changed / added files, and push to main. 

```
git remote add origin https://github.com/YourGithubUser/hugo-quickstart.git
git add .
git commit -m "added baseurl to config, added vercel.json"
git branch -M main
git push origin main
```

Now in your Vercel project, settings, Git menu, connect Vercel to your Github repo. 

https://vercel.com/rickcogley/hugo-quickstart/settings/git

Make an edit in the site, push to main, then check the URL that Vercel deployed on. 