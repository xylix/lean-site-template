# LEAN site template

To get a shiny new site for your local EA chapter, follow the instructions below.


## Initial Setup

1. First, [create a free GitHub account](https://github.com/join).
1. After you've signed back into GitHub with your account, you'll need to fork this repository by hitting the 'Fork' button at the top-right of this page. Forking will create a copy of this repo that you can work with.
1. Go to [travis-ci.org/](https://travis-ci.org/) and sign in with your GitHub account.
1. Once Travis has "synced" all your repositories from GitHub, you should be able to see the "lean-site-template" on your Travis dashboard. You can enable builds on it by simply clicking on it. The "X" beside the repository name should turn into a checkmark.


## Customizing the Site

#### Editing placeholder values in `config.toml`

Go to your forked repo on GitHub (the link should be `www.github.com/YOUR-USERNAME/lean-site-template`) and click on the `config.toml` file. This is the file that contains your site title, button names, navigation bar text, and so on. There are reasonable defaults for English, but there will be certain things you'll need to change such as the title, registeredCharityNumber, contactEmail, and so forth.


To change the file, hit the pencil icon on the top-right of the file. Change the placeholder values to whatever applies to your group. If you need an example to follow, see the [example config.toml file](https://github.com/rtcharity/lean-site-template/blob/master/example-config.toml) as a guide. If you need multilanguage support, be sure to see the **Multilanguage Support** section below.


When you're done, commit your changes (the big green button at the bottom of the edit page).
Make sure you commit directly to the master branch.


#### Editing the default content

All the written copy for the site is held in the "content" folder. If you click on it, you should see a bunch of files such as `_footer-left.md`, `contact.md`, `reading-material.md` and so forth. Feel free to explore and change the content as you please.


Most of the files are pretty self-explanatory by their name or content. However, a few to note:
- `_footer-left.md` - This holds the content that shows up on the left-side of the footer that appears on every page. By default it holds "More on EA" links.
- `_footer-right.md` - This holds the content that shows up on the left-side of the footer that appears on every page. By default it holds "Useful links", but EA Dubai and EA NYU etc have used this section to instead link to pages more specific to their group. Perhaps you may want to as well.
- `_index.md` - This file is not used at all at the time being so feel free to ignore it.
- `contact.md` - This file needs to exist for the framework to render the contact page, but the contents in it are not used at all. Feel free to ignore it.
- `homepage` - This folder contains the text that gets rendered on the front page, under the homepage section headers (that you can define in `config.toml`). If you change a homepage section header (e.g. `firstSectionHeader`) in `config.toml`, you'll probably want to change the content in a homepage .md file as well.


Please note that .md uses **Github-flavoured markdown** for formatting. If you're not familiar with it, this [awesome Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) should help.


## Deploying the Site

1. If correctly set up your forked repo on Travis, any commit to a file will trigger a 'build' on Travis – that is, Travis will turn your config and the site template into nice HTML to be served up.
1. It's time to hook up a domain to the site! If you are managing the domain name yourself, go to the 'Settings' tab in your repo and set up a custom domain for your site, following [these instructions](https://medium.com/@supriyakankure/how-to-add-a-custom-domain-to-your-github-page-with-godaddy-84495781143e). If LEAN is managing domain names for you, go to 'Settings' > 'Collaborators & teams' and add 'mondayrain' as a collaborator with 'Write' privileges. Then, contact Richenda at richenda [at] rtcharity.org and provide her a) The domain name you want to use, and b) the link to your GitHub repository.
1. Once the domain is set up, you should be able to immediately see any changes to your site anytime you change content through an edit & commit on GitHub.


## Multilanguage Support

Your site can support as many languages as you want. For each language you want to support, 2 things will need to be done:

1. You'll need to add the appropriate sections to `config.toml`. Basically what you'll need to do is duplicate everything from `[Languages.en]` onwards, but change the language code from `en` to whatever language you want to use. All you'll have to do then is fill in the parameter values as needed for that given language. See `example-config.toml` for a `config.toml` that supports both English and German, with `de` being the German language code.
1. You'll have to create <language-code>.md versions of every file inside the `content` and `content/homepage` folders and populate them with translated copy as needed. This is the text that will be shown on the site for that language. For example, if I want to add German language support (and gave German the `de` code in `config.toml`), then I would have to create `_footer-left.de.md`, `faq.de.md`, `homepage/_first_section_text.de.md` and so on. You can create a file by going into the `content` folder then clicking "Create new file" at the top-right. **Make sure you get the name of the .md files right!** Aside from the extra language code, they must be the same as the English version!


To see an example site structure with multilingual support, see [this Hugo multilingual example](https://github.com/rayjolt/hugo-multilingual-example) or the official [Hugo documentation on Multilingual Mode](https://gohugo.io/content-management/multilingual/).
