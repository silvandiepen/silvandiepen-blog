# Creating a blog with Nuxt and the Github Graphql Api

After many attemps of creating blogs using different services, internally in the repository of my website, using Wordpress and many other tools. I thought it would be a good idea to just create my blog using a Github repository. A simple repo just holding the .md (markdown) files and my website which is build in Nuxt. 

The idea was simple, just create the repo, install graphql on the frontend and load the articles. Unfortunately it took a little longer than estimated, but I got it fixed!

Here is a short version step by step what to create;

## Step 1. Get Github ready

- Go to github, create a new repository and just add .md files. 
- Create a API Key.



## Step 2. Setup your app with Nuxt and install Graphql

Assuming you already setup your Nuxt app. 
- install Apollo; `npm install @nuxtjs/apollo --save`.
- Create a folder in your root with the following files; 

  > graphql
    > Apollo
      - ApolloLogger.js
      - defaultClient.js
    > query
      - articles.gql
      


## Step 3. The store

## Step 4. Filling the store

## Step 5. The components


