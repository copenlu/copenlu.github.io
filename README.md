This is the deployed website for the CopeNLU research group, built with [Hugo Academic](https://sourcethemes.com/academic). 

If you want to change website content, edit the [CopeNLU fork of the Academic Kickstart](https://github.com/copenlu/academic-kickstart) repository.


### Useful Resources

- [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
- [Hugo Academic Widgets](https://sourcethemes.com/academic/docs/widgets/) 


### Guide on what to find where

Here's a short guide to where what content can be found:

- Profiles for people are in the [content/people](https://github.com/copenlu/academic-kickstart/tree/master/content/people]folder). Each person is represented with one subfolder. Simply edit Markdown file in the individual subfolder and/or add a new picture. Note that this *needs* to be called `featured.jpg` or `featured.png`, otherwise it will not be found. For adding new people, simply copy one of the existing people subfolders and edit. Note that you can add a number of different social links for each person, such as their Google Scholar, Github or personal website.
- Blog posts can be found under [content/post](https://github.com/copenlu/academic-kickstart/tree/master/content/post). Note that in the `index.md`, there is an option for declaring that the blog post is a draft, in that case it will not be displayed. This is useful if you want to work on a post without it being published straight away, [content/post/getting-started](https://github.com/copenlu/academic-kickstart/tree/master/content/post/getting-started) is an example of this.
- Publications can be modified or added under [content/publication](https://github.com/copenlu/academic-kickstart/tree/master/content/publication). As for profiles and blog posts, one subfolder per publication has to be created, and file names should not be changed.
- News can be modified or added under [content/talk](https://github.com/copenlu/academic-kickstart/tree/master/content/talks). As for profiles, blog posts and publications, one subfolder per news item has to be created, and file names should not be changed.


## Installing dependencies

- [Docker](https://www.docker.com/)
- [Hugo](https://gohugo.io/). Note that the CopeNLU website is only compatible with Hugo >= 0.54.0. To install it, you can e.g. run `docker pull klakegg/hugo:0.54.0`.

## Compiling and Deployment -- with native Hugo [deprecated]
- Clone the [CopeNLU fork of the Academic Kickstart](https://github.com/copenlu/academic-kickstart) repository: `git clone https://github.com/copenlu/academic-kickstart.git CopeNLU_Website`
- Open a new terminal and navigate to the folder containing this repository. Run `hugo server`, then open a browser window and navigate to `http://localhost:1313`.
- Edit the source code, the website will automatically refresh. If you add new folders or files as opposed to editing existing ones, you sometimes need to restart the server (i.e. terminate the hugo process and type `hugo server` again). If there are errors, an error log will be displayed. Often these are down to small syntax or naming mistakes, so stick to an existing template as closely as possible.
- When you are done, follow the instructions on [deployment of Hugo Academic](https://sourcethemes.com/academic/docs/deployment/) to recompile the code and deploy the site. Here's a short version for if you've already done this once:

```
rm -r public
git submodule add -f -b master https://github.com/copenlu/copenlu.github.io public
git add .
git commit -m "My commit message"
git push -u origin master
hugo
cd public
git add .
git commit -m "My commit message"
git push origin master
```
## Compiling and Deployment -- with Docker version of Hugo
- Clone the [CopeNLU fork of the Academic Kickstart](https://github.com/copenlu/academic-kickstart) repository: `git clone https://github.com/copenlu/academic-kickstart.git CopeNLU_Website`
- Open a new terminal and navigate to the folder containing this repository. Run `docker run --rm -it -p 1313:1313 -v $(pwd):/src klakegg/hugo:0.54.0 server`, then open a browser window and navigate to `http://localhost:1313`.
- Edit the code, the website will automatically refresh.
- When you are done, push the changes to the code as follows:
```
rm -r public
git submodule add -f -b master https://github.com/copenlu/copenlu.github.io public
git add .
git commit -m "My commit message"
git push -u origin master
```
- Now, you also need to push the `public` folder. To do that, you need to run hugo from inside the Docker container. To do that...
- Start a hugo Docker container process in the background: `docker run -d --rm -it -p 1313:1313 -v $(pwd):/src klakegg/hugo:0.54.0 server`
- Check that the Docker container is actually running: `docker ps`
- Copy the CONTAINER_ID, then paste it into this command: `docker exec -it CONTAINER_ID sh`
- You are now inside the Docker container
- Run hugo from inside the container: `hugo`
- Confirm that there is now a public folder: `ls public`
- Exit the Docker container again by pressing Ctrl + A D
- Stop the Docker container: `docker stop CONTAINER_ID`
- You can now push the public repository as well:
```
cd public
git add .
git commit -m "My commit message"
git push origin master
```
