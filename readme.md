# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Deploying Your App to Github, Using Canvas for Graphics (3:00)

| Timing | Type | Topic |

tktk

### Objectives

_After this lesson, students will be able to:_

- Understand what the git version control system is.
- Push their code to Github.
- Deploy their app to GitHub Pages.
- Make basic shapes using Canvas
- Make an interactive drawing app using Canvas and Firebase.

### Preparation

_Before this lesson, students should already be able to:_

- Explain deployment, and deploy to Firebase.


---

## Recap: Firebase Database, Firebase Hosting (5 min)

So we learned last week how to use the Firebase Backend-as-a-service database system, and also how to deploy an app to Firebase, with its own URL that people can point to with their browsers to see your app.

It's important to reiterate that the connection between these two things (Firebase database and Firebase hosting) is not actually technical; it's a marketing connection. You don't have to use the Firebase database to deploy your app to Firebase hosting, and you also can use Firebase database and deploy your app to some other hosting service. It works fine.



<a name = "demo1"></a>
## Intro to git/Github (20 min)

Speaking of deploying elsewhere -- Github!

Another good option for deployment is Github Pages, which is kind of a side benefit of Github, whose main purpose is hosting the code itself so others can read it.

Github is basically a social network for code display and collaboration between programmers. It takes its name from, and makes great use of, a command-line program called "git".

git is a tool for version control. Think of git as like the "track-changes" feature in Microsoft Word, but on steroids. It saves an annotated history of what changes were made at which point in time, and makes it easy to share and manage code and for multiple engineers to collaborate on the same project.

You can make any folder into a git project. It starts being tracked for changes, and all its files and subfolders are also tracked.

And Github, as we mentioned, is a social network -- a place to store code that is being tracked by git. On Github, your git projects can be stored and seen by others.

We're going to talk about one small fraction of the git version control system today, just enough to get your a project up on Github, but git is ubiquitous in software projects these days, so it's worth learning more about it.

To track our code using git, and to upload it to Github, we'll be using a desktop program called Github Desktop. If you haven't done the following two things yet, do them now:

1. Go to [Github](https://github.com) and create an account. Remember your username.
2. Download [Github Desktop](https://desktop.github.com/).

### git vocabulary

- __git:__ A version control program that saves the state of your project's files and folders; basically, it takes a "snapshot" of what all your files look like at that moment and stores a reference to that “snapshot".
- __repository:__ A folder that is being tracked by git version control (along with all its files and subfolders).
- __commit:__ Make a “snapshot” of your project -- with a brief message explaining what you did -- and add that to the history of other commits.
- __push:__ Make a copy of your repo on another machine, in a "remote repository". We will be using Github for storing all of our remote copies of our repo.



## Github Desktop (45 min)

### Creating a new repo

Let's create our first repo. 

- Go to File -> New Repository, and you'll be presented with the choices Add, Create, and Clone.
- Choose "Create". 
- Navigate to a new `~/GA-JS/lesson18` folder, and make a new repo called `<your-user-name>.github.io`. 
>(You can actually call it anything you want if you just want to store your code on Github, but you have to call it exactly `<your-user-name>.github.io` if you want to use Github Pages to deploy it as a hosted app)

![](images/creating_a_new_repo.png)


You are now in your new repo, which is really just a folder that is being tracked by git. If you go into the Finder you can see it.

Now we're almost ready to start making commits. First we need to create at least one file.

### Adding files

***For Mac people only (but everybody else do it too just for this example because it can't hurt):*** The first commit we should make is a housekeeping one: We need to have git ignore certain files, because we're not interested in keeping track of them.

One such file is something that gets added to every single folder in the Mac operating system all the time, called ".DS_Store". You can't usually see it because the Mac doesn't show you files that begin with a dot, by default. But it's there.

- To tell git not to track this file, go into your terminal and type:

```
cd ~/GA-JS/lesson18/your_username.github.io
touch .gitignore
subl .
```

Then type one line into the .gitignore file: ".DS_Store". This tells git NOT to track all files that are called ".DS_Store".

Now you should see your change, with the new lines in green, ready to be committed:

![](images/one_uncommitted_change.png)

### Making commits

To make a commit:

- Click where it says "Summary"
- Type a short message like "my first commit"
- Click "Commit to master".

Now notice it brings you to the "History" view, where you can see the history of all your commits (so far there's only one):

![](images/history_view.png)


Now let's add some real files. Create two new files in Sublime in your new folder: `index.html` and `app.js`:

**index.html:**
```html
<!DOCTYPE html>
<html>
<head>
  <title></title>
</head>
<body>

  <script type="text/javascript" src="app.js"></script>
</body>
</html>
```

**app.js:**
```js
alert("hello world")
```

Now go back to Github Desktop and see what's there. 

- Click on "2 Uncommitted Changes" at the top. 
- Commit them! (with a message in the "Summary" box, like "added app.js and index.html").
- Click on History. See you have two history items there!

![](images/two_history_items.png)

Now make a change that's not an addition of a file:

- Go into the `app.js` file
- Edit the alert to say "hi planet" instead of "hello world".
- Go back to Github Desktop and click on "1 Uncommitted Change"
- Make another commit, with a message like "edited alert text".
- Click on History:

![](images/three_history_items.png)

### Pushing to Github

The way that you create a remote repo on Github and push a copy of your local repo to it, using Github Desktop, is:

- Click "Publish".
- The first time you do this it will open up your preferences and make you log into Github:

![](images/login.png)

- Now click Publish again. 
- It will ask you to confirm the name of your repo (you can actually choose a different name than the name of your local folder, but that gets confusing, so don't do that).

- Now go to that website address, and you should see an alert, "hi planet"!

### Code sharing on Github

So that was Github hosting. Now let's take a look at what Github gives us that Firebase does not: a place for ourselves -- and other people -- to look at our code.

Go to https://github.com/your-username and let's go on a little tour.

You can:
- Look at the contents of all the files.
- Look at a history of the commits.
- Look at all the commits in which a particular file has been edited.
- And many, many, many other things.

### Syncing between local and remote

You can make changes either on your local machine or on Github, and then press the "sync" button in Github Desktop (where the "Publish" button used to be) and it should sync them up.


![](images/syncing.png)

And you can also do it the other way around: You can edit files in Github itself, complete with commit messages, and then go back to Github Desktop and click "sync", and it will download your changes from Github and put them in your local.

## Practice on your own: Practice with Github (20 min)

- Make a few more commits, syncing them with Github and going to Github to see the changes. (If you want you can also make some changes from Github, and sync them to your local to see the changes there.)

- tktk add more here? A more specific exercise, or a more extended exercise?

- Bonus: Create another new repo (with a different name, like `my-new-repo`), add a couple files and publish it to Github.

## Last couple of git/Github loose ends (10 min)

### Deleting repos from Github

To delete repos from Github: 

- Go into "Settings"
- Scroll to the very bottom to the red "Danger Zone", and it will let you delete the repo. 
- This is useful when learning, as you may end up creating a lot of test repos.
- In particular, if your special `your-username.github.io` repo is being taken up with some code you don't want to be your only hosted app on Github (you only get one), you may need to delete the repo on Github, and then delete (or change the name of) your local version, so that you can start fresh with something else.

### Turning existing folders into git repos

To turn an existing folder into a git repo:

- Go to File -> New Repository
- Instead of "Create", click "Add" 
- It will take that folder, place it under the git tracking systetm, and add the new repo in your left rail
- ***Note:*** This will work with existing git repos as well, if you have removed them from the left rail and want to get them back.

### Many, many more things you can do with git

This has scratched the tip of the iceberg of what you can do with git. 

- tktk add some stuff here
- tktk add some more stuff here

I encourage you to learn more about it, at your own pace. I find it extremely helpful not just for collaborating with others, but also for organizing my own thoughts.


## Firebase vs. Github wrapup, and Heroku (10 min)

***Q:*** What does Firebase provide that Github does not?

***Answer:*** A database, authentication, and a few other ancillary services

***Q:*** What does Github provide that Firebase does not?

***Answer:*** A place to store git repositories and display them in a convenient way, meaning you can give people a link to look at your code.

***Q:*** What if I need to run a Node application server, or a Rails server, for my app to function?

***Answer:*** For that you'd need Heroku, the third easiest hosting service out there for deploying apps. You can give Heroku instructions and it will run a server for you.

***Q:*** What if you don't want anyone to see your API keys, but you want to show your code on Github so people can see it?

***Answer:*** For that you'd also need Heroku. You can go into their web console and set what are called "environment variables" like API keys which get injected into your code at runtime so that you don't have to have them in your code, and then you can show the code itself on Github without that secret information.

>**Note:** In an ideal world things like API keys wouldn't be in your publicly available code, but I wouldn't worry at all about that for your projects. These are not social security numbers. The purpose of API keys is for the API owner to keep track of you, and limit your use of their API. If the keys get hacked, all that does is mess up the company's analytics.


---

## Canvas

tktk

---


## Conclusion

tktk