---
description: How-to install Hugo Framework and Coder Theme
---

# Install Hugo Framework & Coder Theme

{% embed url="https://gohugo.io/getting-started/quick-start/" %}

{% embed url="https://github.com/luizdepra/hugo-coder" %}

1. Install Hugo\
   `sudo snap install hugo --channel=extended`
2. Create new site\
   `hugo new site preventa.tech`&#x20;
3. Inside preventa.tech add theme as submodule`git submodule add https://github.com/luizdepra/hugo-coder.git themes/hugo-coder`
4. Updating theme\
   `cd themes/hugo-coder`\
   `git pull`
5. `Add theme in config.toml`\
   theme: "hugo-coder"
