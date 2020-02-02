# NgContentProjection

With GitHub Pages, you can create a free website for your repository. It’s super easy and I will show you step-by-step how to deploy your Angular application to GitHub Pages.
First of all, you must create a new repository in GitHub.

Now, go to the folder that you want to contain the project and execute:
git clone repository-url
Replace repository-url with the actual repository URL.
Now open the generated project folder with Visual Studio Code. Delete the Readme.MD file and commit it to check that the connection with GitHub works.
If everything works, open the terminal in Visual Studio Code (Ctrl + `) and execute:
ng new appName --directory ./
Replace appName with the application name.
Commit and push the generated files.
Next, in the package.json we must create a new npm script command.
"githubpage": "ng build --outputPath=docs"
Save the package.json and execute:
npm run githubpage
This command will generate a docs folder. Commit and push the changes.
In the repository settings of the project in GitHub, in the GitHub Pages section, choose as the source: master branch/docs folder.
When you choose this option, GitHub will refresh the page and will display the URL of the GitHub Page inside a light-blue alert. E.g.:
“Your site is ready to be published at https://georgeroubie.github.io/deploy-angular-application-to-githubpages/.”
Copy only the URL and update the npm script command like this:
"githubpage": "ng build --outputPath=docs --base-href=url-of-page"
Replace the url-of-page with the copied URL.
Execute:
npm run githubpage
Commit and push the changes to see your GitHub Page work.
Normally, it needs two to three minutes before you see the changes.
