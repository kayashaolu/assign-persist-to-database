# Assignment: Persist app to database
## Using an external database to persist data

Your task is to move the content of your website to a service that stores data and use that service to source data. You will need to save the html data and title of the five blog posts you have created in assignment 2 into your Google Firebase database, and have your web application retrieve the page data when your web page requests for it (instead of it being embedded in your javascript files)

## Set up your environment
 - In order to activate this environment, you will need to redownload the node_modules from the package.json file
 - Run `npm install` to install the node packages
 - Run `npm start` to start your webserver
 - Note that the firebase libraries are already being used so you do not need to expliclty download them again
 - This should be it: you can make all of your changes in the src/index.js file and your main 
 
## Set up Google firebase
 1. Go to Google Firebase and create your own realtime database following [these instructions](https://css-tricks.com/intro-firebase-react/#article-header-id-4). You want to complete the *Creating our Firebase Database* section and the *Hooking up our App to Firebase* section. It is okay to leave your database open.
 2. Ensure that you have everything working by looking at the relevant sample code given in lecture and determining if it works in your setup.
 3. Note that you can go to the [firebase console](https://console.firebase.google.com/) to see what data is currently stored in your database

## Requirements

1. Load the html data and title of your five blog posts into your Google Firebase database. You will need to do this so that your application can then get the data by calling the firebase API. You can do this directly in the [firebase console](https://console.firebase.google.com/).

The data for each of your blog posts can be broken down to the following items:
 - **id**: the unique slug of the blog post. For example, the blog post: A Mindful Shift of Focus should have the slug: a-mindful-shift-of-focus. This should be your key for the json entry
 - **title**: the title of the blog post. For example for the "A Mindful Shift of Focus.md" post, the title should be: "A Mindful Shift of Focus"
  - **content**: the content of the blog post. This should contain all of the HTML content that is after the title of your pages. The goal is to grab the content of the blog post from this api instead of hard coding it in your web server.

For example, the json of your database could look like the following:

```
{
  "blogs" : {
    "8-elements" : {
      "content" : "<h1>More Dummy Content</h1>",
      "title" : "8 elements"
    },
    "a-mindful-shift-of-focus" : {
      "content" : "<h1>Dummy Content</h1>",
      "title" : "A Mindful Shift of Focus"
    }
  }
}
```

2. Modify your assignment 2 code to call your database to load the data for the five pages. You should use the firebase api to get that information.
3. (Extra Credit) Create a new page where you can edit the content for the five pages. You would need to create a form that would be populated with the data from the database, and on submit be able to edit the content of those pages.
