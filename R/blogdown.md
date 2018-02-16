# Blogdown

## Notes from RStudio webinar by Yihui Xie

[Video](https://www.youtube.com/watch?v=CjTLN-FXiFA)

- Powered by [Hugo](https://gohugo.io/)

 - The bookdown package has features that facilitate technical writing (see [chapter 2](https://bookdown.org/yihui/bookdown/) of the book for more details). Most of these featueres are also available in Blogdown.

 - Two ways of getting started:
     - Install package -> `blogdown::new_site()`
     - New project -> Website using Blogdown

- Directory structure:
    - `content/`: where you put your markdowns or Rmarkdowns.
        - `about.md`
        - `post/`
    - `themes/`
    - `static/`: copied to `public/`
    - `public/`: website that can be uploaded to any web server

- `.toml` is sort of like `.yaml`. Easy to figure out.

- The `public/` directory will show up the first time you want to preview your website locally.

- No knitting! When you edit a `.Rmd` file, you only need to save it and the website viewer will automatically update the content.

- __Use the default theme and focus on content__ This is good advice, FOLLOW IT MARIA PAULA

- A few helper functions:
    - `new_site()`
    - `install_hugo()`/`install_theme()`
    - `serve_site()`
    - `new_post()`: creates a new post under `content/post/`

- ... Or use the __Addins__
	- "Serve site"
    - "New post"
    - "Update the metadata"

- Typical workflow:
	- Open project
	- "Serve site"
	- "New Post"
	- Write and save
	- Look at automatic preview
	- Push to Github

- If you already have a website? [Jump to minute 46 of the video](https://youtu.be/CjTLN-FXiFA?t=46m19s)
	- Jekyll: easy, copy `.md` and `.Rmd`, edit `.yaml`
	- WordPress -> Exitwp -> Jekyll -> Hugo

- Consider __Netlify__ in lieu of Github.
	- Free domain
	- Free HTTP
	- Unique preview URL for each Github PR

- Check out the [rbind](https://github.com/rbind) organisation

- `.md` files are compiled by Hugo via Blackfriday, and `.Rmd` files are compiled via Blogdown, Rmarkdown and pandoc.

- To add to RSS feed: add `index.xml` to the directory of your website.

## Other
- [Making a website with Blogdown](https://www.youtube.com/watch?v=syWAKaj-4ck)
- [blogdown: Creating Websites with R Markdown](https://bookdown.org/yihui/blogdown/), by Yihui Xie, Amber Thomas, Alison Presmanes Hill
