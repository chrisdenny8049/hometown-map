# Lab 01: Working with GitHub Repositories

This lab assignment builds from the material and processes covered in lesson 01. Complete the following and submit your assignment using the URL hyperlinks indicated below to Canvas for Assignment 01 by the due date.

## Part I. Understanding the lesson (2 pts)

Create a new file named *quiz-01.md* within your *map671-module-01/lab-01/* directory,

Then write short answers (1–2 sentences) to the following questions within it. Commit the file to your repository with a good commit message.

This is a markdown file, and you'll be writing plain text or markdown within it. Be sure to checkout GitHub's [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

For example, to make a ordered list, you simply use numbers before each new line:

```markdown
1. My answer to question one ...
2. Here goes number two!
3. Mmmm ... this one is tough.
```

### Quiz:

1. What is the difference between Git and GitHub and how do they relate?
2. What is the difference between the GitHub website ([https://github.com](https://github.com)) and the GitHub Desktop Client we installed on our machine?
3. Within a Git development process, how would you go about making changes to a file and backing those changes up on a remote server? Be specific in the steps you'd take.
4. What is the purpose of the README.md file in a Git repository?

## Part II. Understanding map distortion (2 pts)

Read the first two chapters in Mark Monmonier's _How to Lie with Maps_
(The book is available on Canvas for this lesson)

Edit the file named *reading-reaction.md* that you created within lesson 01. Using Markdown, write responses to the following questions:

1. What are the three elements of a map that are sources of distortion?
2. What is a verbal scale for the ratio scale, "1:12,000"?
3. In a short paragraph, compare equal-area and conformal map projections. Which is right?

Commit your changes to the file and Push to the remote repo when complete.

## Part III. Updating your "hometown" map (6 pts)

Switch from editing files within your local copy of the *map672-module-01/* repository to your *github.com/username/hometown-map/* repository. Make the following edits to the *index.html* file, commit changes with descriptive commit messages as you work, and Push up to your GitHub repository when done:

1. Again edit the text between the two HTML tags that look like this to be the name of your hometown: `<h1></h1>`, possibly with a funny or interesting title such as "Pumpkin Center, Missouri: Home of Delicious Goats".
2. On line 108 of the *index.html* file there is JavaScript code containing two numbers: `center: [38.0406, -84.5037], // lat/lon values`. These numbers are latitude and longitude values for the center of the map. Change these values to be those of your hometown (or the city/town you're mapping if not your hometown).
3. On line 109 there is JavaScript code containing a number that is the initial zoom level of the map. Adjust this number so the extent of your city roughly fills the map when first loaded. Like in CARTO, the higher the number, the more zoomed in the map is.
4. On line 123 there is text contained within two quotations marks, "Lexington is awesome": `var message = 'Lexington is awesome!';`. Change this text so that it says something related to your map.
5. The template *index.html* file contains [Lorem Ipsum](http://www.lipsum.com/) filler text at the bottom between HTML paragraph tags (`<p></p>`). Either remove or rewrite this text.
6. The template *index.html* file contains some HTML list items at bottom, suggesting possible links to a GitHub account. Using the given HTML as an example, try updating the text and link to the GitHub account with your own. Remove any further list items (contained between HTML list tags `<li></li>`) not updated. Get into the habit of cleaning up the final web page document.
7. Finally, change the title element (`<title></title>`) to something more descriptive than what is currently titled, `<title>Web Page Template</title>`.

As you work through Map 671 and Map 672, you will occasionally revisit and update this hometown map.

## Challenge

At the heart of Git is the ability to create branches of your repo to test changes before you make them permanent. A branch is separate project within your repo that is managed the same way as the Master branch, the default main branch in GitHub. Consider the master branch as the most stable (best looking) version of your project. Your *hometown-map/index.html* GitHub Pages web page renders the master branch of your repo by default. What if you wanted to explore changes to your web page but didn't want to publish them until they were polished? The solution is to create a branch of your *hometown-map* repository and explore more exotic formatting in the *index.html* document.   

1. Create a branch of your *hometown-map* repository in GitHub Desktop and publish it to your remote repo.
2. Modify *index.html* with HTML examples from *https://www.w3schools.com/html/*, e.g., try adding images to your page.
3. Finally, commit and push the changes to your remote repo.

## Submission

Paste **two** URL links within the Canvas Assignment 1 by the due date: one to the newmapsplus/map671-module-01-username repository and one to your personal GitHub repository (e.g., *http://github.com/tastyfreeze/hometown-map*).
