![Vercel](https://therealsujitk-vercel-badge.vercel.app/?app=hugo-quickstart&style=for-the-badge)

# Hugo Quickstart on Vercel

Testing: will the Hugo quickstart be easily published on Vercel? TL;DR: yes, no problem.

https://gohugo.io/getting-started/quick-start/

First, just run through the quick start steps in a local folder to get it basically working. 

Then connect to Vercel by running `vercel` in the project folder. This assumes you installed the `vercel` command and authenticated. 

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

The site should now be available where Vercel deployed it (it's on the clipboard, just paste into your browser)

Edit your `config.toml` and add the URL that Vercel provided as a baseURL. Copy the `vercel.json` from this repo and add it to the base of your project, and this will tell Vercel to use that version of Hugo and also set some security headers for you. 

Now create a repository in your Github, but _do not_ add a README or anything. Then execute these commands to add the new repository as a remote, add and commit the changed / added files, and push to main. 

```
git remote add origin https://github.com/YourGithubUser/hugo-quickstart.git
git add .
git commit -m "added baseurl to config, added vercel.json"
git branch -M main
git push origin main
```

Now in your Vercel project, settings, Git menu, connect Vercel to your Github repo. This was mine:

https://vercel.com/rickcogley/hugo-quickstart/settings/git

Then to test, make an edit in the site, push to main, then check the URL that Vercel deployed on. 

What my Vercel project settings look like: 

<img width="1187" alt="image" src="https://user-images.githubusercontent.com/512328/135782841-be27797c-bf58-459e-868b-b0909f4e79f5.png">
