# Pixyll

[pixyll.com](http://www.pixyll.com)

![Pixyll screenshot](./screenshot.png)

Minimal Pyxill is a simplified version of [Pixyll](http://www.pixyll.com).

## Getting Started

```
$ git clone git@github.com:johnotander/pixyll.git
$ cd pixyll
$ gem install bundler
$ bundle install
```

### Verify your Jekyll version
It's important to also check your version of Jekyll since this project uses new baseurl features that are only supported in 3.3+.

### Fork, then clone
Fork the repo, and then clone it so you've got the code locally.

### Modify the _config.yml
The _config.yml located in the root of the Pixyll directory contains all of the configuration
details for the Jekyll site. The defaults are:

```yaml
# Site settings
title: Pixyll
email: your_email@example.com
author: John Otander
description: "A simple, beautiful theme for Jekyll that emphasizes content rather than aesthetic fluff."
baseurl: ""
url: "http://pixyll.com"

# Build settings
markdown: kramdown
permalink: pretty
paginate: 3
Jekyll Serve
Then, start the Jekyll Server. I always like to give the --watch option so it updates the generated HTML when I make changes`
```

### Jekyll Serve
Then, start the Jekyll Server. I always like to give the --watch option so it updates the
generated HTML when I make changes.

```
$ jekyll serve --watch
```

Now you can navigate to localhost:4000 in your browser to see the site.

### Using Github Pages
You can host your Jekyll site for free with Github Pages. [Click here](https://pages.github.com/) for more information.

A configuration tweak if you're using a gh-pages sub-folder
In addition to your github-username.github.io repo that maps to the root url, you can
serve up sites by using a gh-pages branch for other repos so they're available at github-username.github.io/repo-name.

This will require you to modify the _config.yml like so:

```yaml
# Site settings
title: Repo Name
email: your_email@example.com
author: John Otander
description: "Repo description"
baseurl: "/repo-name"
url: "http://github-username.github.io"

# Build settings
markdown: kramdown
permalink: pretty
paginate: 3
This will ensure that the the correct relative path is constructed for your assets and posts. Also, in order to run the project locally, you will need to specify the blank string for the baseurl: $ jekyll serve --baseurl ''.
```

If you don't want the header to link back to the root url. You will also need to tweak the
header include /{{ site.baseurl }}:

```html
<header class="site-header px2 px-responsive">
  <div class="mt2 wrap">
    <div class="measure">
      <a href="{{ "/" | relative_url }}" class="site-title">{{ site.title }}</a>
      <nav class="site-nav">
        {% include navigation.html %}
      </nav>
    </div>
  </div>
</header>
A relevant Jekyll Github Issue: https://github.com/jekyll/jekyll/issues/332
```

Copyright (c) 2020 Fernanda Andrade (cutomization)

Copyright (c) 2014-2019 John Otander for Pixyll
