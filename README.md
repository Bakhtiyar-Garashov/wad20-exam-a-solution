# WAD 2020 Exam: Project A

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```


# Setup

Fork this project!

Make sure that your newly created project is **private** 
and only **you and me** have access to it, otherwise tasks will not be graded.

To see how to change repository visibility to private 
and add collaborators click [here](https://docs.github.com/en/enterprise-server@2.21/github/administering-a-repository/setting-repository-visibility#making-a-repository-private-1) 
and [here](https://docs.github.com/en/free-pro-team@latest/github/setting-up-and-managing-your-github-user-account/inviting-collaborators-to-a-personal-repository)

My email and username on github is: `cotne.kekelia@yahoo.com` and `tsotnekekelia`

# Tasks
Modify [Entries.vue](./src/components/Entries.vue) so that it displays all the 
entry objects that are passed to it from [App.vue](./src/App.vue)

- Display title, image, text and date of each entry
- Have a computed property called `sortedEntries` that sorts received list of entries by `date` (newest to oldest by default)
- Have a filter that displays `date` values in human readable format 
example: `Thursday, December 31, 2020 2:15 PM`
- Have a button above listing that by default says "Newest to Oldest", 
on click it toggles the ordering and reorders the list to "Oldest to Newest" and vice versa,
button label has to change accordingly

Your app should look something like this: 

![img](./src/assets/screenshot1.png) ![img](./src/assets/screenshot2.png)

