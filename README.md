# LEAN site template

Welcome to the GitHub repository containing all the code/files you'll need in order to start a new Local EA site!

To get a shiny new site for your local EA chapter, follow the instructions below.


## Initial Setup

1. First, [create a free GitHub account](https://github.com/join).
1. After you've signed back into GitHub with your account, hit the 'Fork' button at the top-right of this page. Forking will create a copy of this repository of code that you can work with in your GitHub account.
1. Go to [travis-ci.org/](https://travis-ci.org/) and sign in with your GitHub account.
1. Once Travis has "synced" all your repositories from GitHub, you should be able to see the "lean-site-template" on your Travis dashboard. You can enable builds on it by simply clicking on it. The "X" beside the repository name should turn into a checkmark.


## Customizing the Site

The static site comes with default values (e.g. site title, your EA group name, page content, etc) that need to be changed for your group. These values are held in one of two places:

1. The `config.toml` configuration file, which holds config such as your site name, your contact email, your Facebook/Twitter/Meetup URLs, what languages you support, what the navigation bar text is, and so on.
1. The markdown (`.md`) files inside the `content` folder. These files hold all the written copy for your pages. For example, if you want to change the information on the "Reading Materials" page, you would go to `content/reading-materials.md` and change the writing in there.

In the next few sections we'll step through changing both the `config.toml` and `.md` files in order to customize your site.


#### Editing default configuration values in `config.toml`

Go to the repo that you forked on GitHub (the link should be `www.github.com/YOUR-USERNAME/lean-site-template`) and click on the `config.toml` file. This is the file that contains your site title, button names, navigation bar text, and so on. There are reasonable defaults for English, but there will be certain things you'll need to change such as the title, registeredCharityNumber, contactEmail, and so forth.


To change the file, hit the pencil icon near the top-right of the page. Change the placeholder values to whatever applies to your group. If you need an example to follow, see the [example config.toml file](https://github.com/rtcharity/lean-site-template/blob/master/example-config.toml) as a guide. If you need multilanguage support, be sure to read the [**Multilanguage Support** section](https://github.com/rtcharity/lean-site-template/blob/master/README.md#multilanguage-support) below.


When you're done, commit your changes (the big green button at the bottom of the edit page). ‘Commit’ is the equivalent of ‘apply’ or ‘save’ in GitHub terms.


#### Editing the written content

All the written copy for the site is held in the "content" folder. If you go back to the index of your forked repository, and click on it, you should see a bunch of files such as `_footer-left.md`, `contact.md`, `reading-material.md` and so forth. Feel free to explore and change the content as you please.


Most of the files are pretty self-explanatory by their name or content. However, a few to note:
- `_footer-left.md` - This holds the content that shows up on the left-side of the footer that appears on every page. By default it holds "More on EA" links.
- `_footer-right.md` - This holds the content that shows up on the left-side of the footer that appears on every page. By default it holds "Useful links", but EA Dubai and EA NYU etc have used this section to instead link to pages more specific to their group. Perhaps you may want to as well.
- `_index.md` - This file is not used at all at the time being so feel free to ignore it.
- `contact.md` - This file needs to exist for in order for the contact page to be created, but the contents in it are not used at all. Feel free to ignore it.
- `homepage` - This folder contains the text that gets created on the front page, under the homepage section headers (that you can define in `config.toml`). If you change a homepage section header (e.g. `firstSectionHeader`) in `config.toml`, you'll probably want to change the content in a homepage .md file as well.


Please note that the .md files used here use **Github-flavoured markdown** for formatting. Markdown is a simple code for making stylistic changes to the content of your webpage. If you're not familiar with it, this [awesome Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) should help.


#### Changing banner photos

The site uses default banner photos. You can find the photos used in the [`static/img`](https://github.com/rtcharity/lean-site-template/tree/master/static/img) folder of this repository.

If you want to replace a banner photo (for example, the banner photo under "Who are we?" is usually of your city), just make sure that the **name** of the photo stays the same, since the site generator depends on the name of the file in order to display the picture.

You can do the following to replace a banner photo:
1. Go to the `static/img` folder.
1. Click on the photo file you want to replace, and click on the trash can button on the top-right to delete it.
1. Once its been deleted, go back to the `static/img` folder and click "Upload files"
1. Choose the photo you want to use as the new banner. **Make sure you name it the same thing as the file you deleted**.

Please remember that large image files can slow down your website and potentially cause other problems. We recommend using image files no larger than 5mb. If you have an image that is too large, you can easily and freely resize it using websites such as https://imgur.com/ or https://pixlr.com/express/. If you are a Mac user, the ‘Preview’ application in OSX will also allow you to resize your images.

Please also remember to pay attention to copyright permissions for images that you choose. An easy way to find free images is to search for images with creative commons licenses on https://commons.wikimedia.org/wiki/Main_Page or to use content from https://unsplash.com/.


## Deploying the Site

Deployment is the step where your content goes live and your site becomes accessible to the public on the Internet.

1. If you correctly set up your forked repo on Travis, any commit (change) to a file will trigger a 'build' on Travis – that is, Travis will turn your config and the site template into nice HTML file (set of instructions to a browser to display your content how you want it) to be served up.
1. It's time to hook up a domain to the site! If you are managing the domain name yourself, go to the 'Settings' tab in your repo and set up a custom domain for your site, following [these instructions](https://medium.com/@supriyakankure/how-to-add-a-custom-domain-to-your-github-page-with-godaddy-84495781143e). If LEAN is managing domain names for you, go to 'Settings' > 'Collaborators & teams' and add 'mondayrain' as a collaborator with 'Write' privileges. Then, contact Richenda at richenda [at] rtcharity.org and provide her a) The domain name you want to use, if you have one in mind, and b) the link to your GitHub repository.
1. Once the domain is set up, you should be able to immediately see any changes to your site anytime you change content through an edit & commit on GitHub.


## Setting up the Contact Form

The site uses [Formspree](https://formspree.io/) in order to forward Contact messages from the site to the contactEmail you define in `config.toml`. However, before they'll forward messages for you, you will need to confirm your email.

In order to do this:
1. Make sure your contact email is correctly filled in `config.toml`.
1. Go to your site's contact page.
1. Fill out the contact form and hit "Send".
1. Formspree should send you an email at your contactEmail and ask you to confirm your email address. You may need to check/change your spam filter if you don't get it.
1. Once your email is confirmed, all messages sent through the contact page should be forwarded to your contactEmail!

Remember that if you would like an official EA email address for privacy reasons, LEAN can set this up for you if we have not already. Email Richenda at richenda [at] rtcharity.org


## Multilanguage Support

Your site can support as many languages as you want. For each language you want to support, 2 things will need to be done:

1. **You'll need to add the appropriate sections to `config.toml`.** Basically what you'll need to do is duplicate everything from `[Languages.en]` onwards, but change the language code from `en` to whatever language you want to use. All you'll have to do then is fill in the parameter values as needed for that given language. See [example-config.toml](https://github.com/rtcharity/lean-site-template/blob/master/example-config.toml) for a an example `config.toml` that supports both English and German, with `de` being the German language code.
1. **You'll have to create <language-code>.md versions of every file inside the `content` and `content/homepage` folders** and populate them with translated copy as needed. This is the text that will be shown on the site for that language. For example, if I want to add German language support (and gave German the `de` code in `config.toml`), then I would have to create `_footer-left.de.md`, `faq.de.md`, `homepage/_first_section_text.de.md` and so on. You can create a file by going into the `content` folder then clicking "Create new file" at the top-right. **Make sure you get the name of the .md files right!** Aside from the extra language code, they must be the same as the English version! If the site can't find the correct translation file based on the filename, it will just fall back on the English copy.


The URLS for translated content will always be www.your-domain.com/language-code/url. So, the German version of www.your-domain.com/about will be found at www.your-domain.com/de/about.


To see an example site structure with multilingual support, see [this Hugo multilingual example](https://github.com/rayjolt/hugo-multilingual-example) or the official [Hugo documentation on Multilingual Mode](https://gohugo.io/content-management/multilingual/).
