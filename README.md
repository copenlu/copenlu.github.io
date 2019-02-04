This is the deployed website for the CopeNLU research group, built with [Hugo Academic](https://sourcethemes.com/academic). 

If you want to change website content, edit the [https://github.com/copenlu/academic-kickstart](Academic Kickstart) repository.

### Useful Resources

- [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)


### Guide on what to find where

Here's a short guide to where what content can be found:

- Profiles for people are in the [https://github.com/copenlu/academic-kickstart/tree/master/content/people](content/people) folder. Each person is represented with one subfolder. Simply edit Markdown file in the individual subfolder and/or add a new picture. Note that this *needs* to be called `featured.jpg` or `featured.png`, otherwise it will not be found. For adding new people, simply copy one of the existing people subfolders and edit.
- Blog posts can be found under [https://github.com/copenlu/academic-kickstart/tree/master/content/post](content/post). Note that in the `index.md`, there is an option for declaring that the blog post is a draft, in that case it will not be displayed. This is useful if you want to work on a post without it being published straight away, [https://github.com/copenlu/academic-kickstart/tree/master/content/post/getting-started](content/post/getting-started) is an example of this.


## Compiling and Deployment 

- [Install Hugo](https://gohugo.io/getting-started/quick-start/)
- Clone this repository
- Open a new terminal and run `hugo server`, then open a browser window and navigate to `http://localhost:1313`
- Edit the source code, the website will automatically refresh. If you add new folders or files as opposed to editing existing ones, you sometimes need to restart the server (i.e. terminate the hugo process and type `hugo server` again). If there are errors, an error log will be displayed. Often these are down to small syntax or naming mistakes, so stick to an existing template as closely as possible.
- When you are done, follow the instructions on [https://sourcethemes.com/academic/docs/deployment/](deployment of Hugo Academic) to recompile the code and deploy the site.
