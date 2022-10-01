---
layout: post
title: "Creating a Blog with Github Pages and Jekyll"
categories: software how-to blog
---

## Hello World - Setting up Your Own Blog
Github pages is a relatively simple way to turn a github repository into a website. This can be great for blogging but there are a couple of setup and configure steps that can trip you up along the way.

### Getting Your Sub-domain
Begin by logging into your [github.com](https://github.com) account. In the top right corner there is a plus icon. Click on it and select the `New Repository` option.

<img name="create-new-repo-dropdown" src="{{site.url}}/images/hello-world/new-repo-menu.jpg">

Next under `Repository name` set the name to be `your-username.github.io`. For example this blog is hosted at [p-contorta.github.io](https://p-contorta.github.io). When you're ready hit the `Create repository button at bottom of the page`

<img name="create-repo-form" src="{{site.url}}/images/hello-world/create-repo.jpg">

Navigate to the `https://your-username.github.io` and within a minute or two you should see a simple webpage pop up.

### Jekyll Themes
Github pages let you add themes. Themes provide style to your website as well as providing some structured ways to create new posts, add plugins, and keep your blog's many posts linked together in a coherent way.

All Github themes are built using Jekyll. You can read more about Jekyll [here](https://jekyllrb.com/) but TLDR it takes a markdown document `*.md` file and turns it into a webpage.


Github has a list of themes [here](https://pages.github.com/themes/) that you can choose from. Once you find a theme you like create a `_config.yml` in your repositories root. Below is an example with the `minima` theme.
```yaml
theme: minima
```

### Add a title and description
In addition to choosing the theme you can set a title and description for your blog. To set these add the following to the top of your `_config.yaml`.
```yaml
title: My Really Cool Blog Title
description: >
    A description of what the blog is about and something compelling 
    for the reader.
```

The final `_config.yaml` will look something like this:
```yaml
title: My Really Cool Blog Title
description: >
    A description of what the blog is about and something compelling 
    for the reader.
theme: minima
```


### Creating a Home Page
The home page is rendered from an `index.md` or `README.md` at the repository root. Using `index.md` as your home page lets you later create a `README.md` for any information that is important for the setup and operation of the blog but that you don't want to display to your readers.

Once you've crated your `README.md` or `index.md` populate it with something like the markdown below.

```markdown
---
layout: home
title: My Home Page Title
---

## Top Level header

Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
sed do eiusmod tempor incididunt ut labore et dolore 
magna aliqua. Ut enim ad minim veniam, quis nostrud 
exercitation ullamco laboris nisi ut aliquip ex ea 
commodo consequat.

```

## Making the First Post

Each new post will live inside the `_posts` directory placed at the respository root. The naming of each post must have a name that matches `YYYY-MM-DD-title.md`. If the post does not have a correctly formatted name it will not link it to your homepage correctly.

Once the post has a name, we'll use `2022-02-23-hello-world.md` here, then open the post file and add a [front matter](https://jekyllrb.com/docs/front-matter/) block like below.

```markdown
---
layout: post
title: "Hello World - Why is 42 the meaning of life?"
categories: meaning-of-life 42 hitch-hikers-guide-to-the-galaxy
---
```

The only two required fields are `layout: post`and `title: Hello World - Why is 42 the meaning of life?`. The `categories` field allows for posts to be grouped by, wait for it, categories. The power of defining `categories` here in the post is that more than one category can be assigned per post. Categories can also be assigned by putting the post in a named folder but then you're limited to a single category per post.

Now fill out the rest of the post file with content you'd like to share.

```markdown
---
layout: post
title: "Hello World - Why is 42 the meaning of life?"
categories: meaning-of-life 42 hitch-hikers-guide-to-the-galaxy
---

## 6 x 7 = 42
Maths are hard. Imagine all the different ways we could get the answer 42? 
`6 x 7 = 42`, `2 x 21 = 42`, `84/2 = 42`. Just wow! 

```

Commit the changes to github and merge to the main branch. Wait a few a minutes and you should see your first blog post!


## Gotchas
1. Use `##` as the top level header instead of `#`
   - A single `#` will messup the formatting of the template
