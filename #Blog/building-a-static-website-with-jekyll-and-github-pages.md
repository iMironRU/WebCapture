# Building a static website with Jekyll and GitHub Pages

_Captured: 2017-08-08 at 18:44 from [programminghistorian.org](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages)_

**This lesson is for you if** you'd like an entirely free, easy-to-maintain, preservation-friendly, secure website over which you have full control, such as a scholarly blog, project website, or online portfolio.

**At the end of this lesson**, you'll have a basic live website where you can publish content that other people can visit--it will look like [this](http://amandavisconti.github.io/JekyllDemo/)!--and you'll also have some resources to explore if you want to further customize the site.

**Requirements:** A computer (Mac/Windows/Linux are all okay, but this lesson doesn't cover some aspects of Linux use), the ability to download and install software on the computer, an internet connection that can support downloading software. Users have reported needing between 1-3 hours to complete the entire lesson.

**Difficulty level:** Intermediate (this lesson includes use of the command line and git, _but_ walks you through anything needed to complete this lesson). Forthcoming lessons in the basics of git/GitHub and GitHub Pages will be linked here when available, and provide a good background for anyone wishing for deeper understanding of the technology used in this lesson.

**Up to date?:** This lesson was last updated on _May 2, 2017_ to fix issues caused by Jekyll version 3.2.

  * [Installing dependencies ](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages)

_This tutorial is built on the [official Jekyll Documentation](http://jekyllrb.com/docs/home/) written by the Jekyll community. See the "[Read more"](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages) section below if you'd like to know even more about these terms!_

_Dynamic websites_, such as those created and managed by a content management system such as [Drupal](https://www.drupal.com/), [WordPress](https://wordpress.org/), and [Omeka](https://omeka.org/), pull information from a database to fill in the content on a webpage. When you search for a book on Amazon.com, for example, the search results page you are shown didn't already exist as a full HTML page; instead, Amazon.com has a template for search results page that includes things all results pages share (like the main menu and Amazon logo), but it queries the database to insert the results of that search you initiated into that template.

_Static websites_, on the other hand, do not use a database to store information; instead, all information to be displayed on each webpage is already contained in an HTML file for that webpage. The HTML pages that make up a static site can be completely written by hand, or you can offload some of this work using something like Jekyll.

_Jekyll_ is software that helps you "generate" or create a _static website_ (you may see Jekyll described as a "static site generator"). Jekyll takes page templates--those things like main menus and footers that you'd like shared across all the web pages on your site, where manually writing the HTML to include them on every webpage would be time-consuming. These templates are combined with other files with specific information (e.g. a file for each blog post on the site) to generate full HTML pages for website visitors to see. Jekyll doesn't need to do anything like querying a database and creating a new HTML page (or filling in a partial one) when you visit a webpage; it's already got the HTML pages fully formed, and it just updates them when/if they ever change.

Note that when someone refers to a "Jekyll website", they really mean a static (plain HTML) website that has been created using Jekyll. Jekyll is software that creates websites. Jekyll isn't actually "running" the live website; rather, Jekyll is a "static site generator": it helps you create the static site files, which you then host just as you would any other HTML website.

Because static sites are really just text files (no database to complicate matters), you can easily _version_ a static site--that is, use a tool to keep track of the different versions of the site over time by tracking how the text files that compose the site have been altered. Versioning is especially helpful when you need to merge two files (e.g. two students are writing a blog post together, and you want to combine their two versions), or when you want compare files to look for differences among them (e.g. "How did the original About page describe this project?"). Versioning is great when working with a team (e.g. helps you combine and track different people's work), but it's also useful when writing or running a website on your own.

_[GitHub Pages](https://pages.github.com/)_ is a free place to store the files that run a website and host that website for people to visit (it only works for particular types of website, like basic HTML sites or Jekyll sites, and does not host databases).

_[GitHub](https://github.com/)_ is a visual way to use _[git](https://git-scm.com/documentation)_, a system for _versioning_: keeping track of changes to computer files (including code and text documents) over time (as explained [above](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages)). If you're curious, here's [a friendly lesson for exploring GitHub](https://guides.github.com/activities/hello-world/).

Options like [Drupal](https://www.drupal.com/), [WordPress](https://wordpress.org/), and [Omeka](https://omeka.org/) are good for the needs of complex, interactive websites like Amazon or an interactive digital edition of a novel--but for many blogs, project websites, and online portfolios, a static website (such as a website created using Jekyll) can do everything you need while providing some nice perks:

  * **Maintenance**: Updates and maintenance are needed far less often (less than once a year vs. weekly-monthly).

  * **Preservation:** No database means that the text files making up your site are all you need to save to preserve and replicate your site. It's easy to back your site up or submit it to an institutional repository.

  * **Learning:** Because there isn't a database and there aren't a bunch of code files providing features you might not even need, there are far fewer actual pieces of your website--it's easier to go through them all and actually know what each does, should you be so inclined. Therefore, it's much easier to become both a basic and an advanced Jekyll user.

  * **More customization possible**: Since learning to master your website is easier, things you'll definitely want to do, like changing the look (the "theme") of a Jekyll-created site, are much easier than altering the look of a WordPress or Drupal site.
  * **Free hosting:** While many website tools like Drupal, WordPress, and Omeka are free, hosting them (paying for someone to serve your website's files to site visitors) can cost money.
  * **Versioning:** Hosting on GitHub Pages means your site is linked into GitHub's visual interface for git versioning, so you can track changes to your site and always roll back to an earlier state of any blog post, page, or the site itself if needed. This includes uploaded files you might want to store on the site, like old syllabi and publications. (Versioning is [explained in more detail above](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages).)
  * **Security:** There's no database to protect from hackers.
  * **Speed:** Minimal website files and no database to query mean a faster page-loading time.

Creating a static website using Jekyll offers more perks in addition to all the benefits of a hand-coded HTML static website:

  * **Learning:** It's easier to get started customizing your site and writing its content, since you won't need to learn or use HTML.
  * **Built for blogging:** Jekyll was built to support blog posts, so it's easy to blog (add new, date-sorted content) and do related tasks like display an archive of all blog posts by month, or include a link to the three most recent blog posts at the bottom of each post.
  * **Templating automates repeated tasks:** Jekyll makes it easy to automate repeated website tasks via its "templating" system: you can create content that should, for example, appear on the header and footer of every page (e.g. logo image, main menu), or following the title of every blog post (e.g. author name and publication date). This templated information will automatically be repeated on every appropriate webpage, instead of forcing you to manually rewrite that information on every webpage where you want it to appear. Not only does this save a lot of copying and pasting--if you ever want to change something that appears on every page of your website (e.g. a new site logo or a new item in the main menu), changing it once in a template will change in on every place it appears on your website.

We're ready to get to work! In the rest of this lesson, we're going to get a few programs installed on your computer, use the command line to install a few things that can only be installed that way, look at and customize a private version of your website, and finally make your website publicly accessible on the Web. If you run into problems at any point in this lesson, see the [help section](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages) for how to ask questions or report issues.

In this section, we'll make sure you have a couple things ready on your computer for when we need them later in the lesson by covering what operating system you can use (i.e. Mac/Windows/Linux), creating a GitHub account and installing the GitHub app, why you should use a "text editor" program to work on your website, and how to use the command line.

Everything this lesson has you install is a standard and trusted web development tool, so it isn't important to know exactly what each of these things do before installing it. I'll try to balance more information about the things it's most useful for you to fully understand, with providing a brief explanation for each piece and also link to further information in case you'd like to know more about what you're putting on your computer.

This tutorial should be usable by both Mac and Windows users. Jekyll can also work for Linux; this tutorial uses the GitHub Desktop software (Mac and Windows only) for simplicity, but Linux users will need to use git over the command line instead (not covered here).

Jekyll isn't officially supported for Windows, which means none of the official Jekyll documentation (the pages that walk you through setting up Jekyll and what its different pieces do, which you could consult instead of or in addition to this lesson) addresses Windows use. I've used [David Burela's Windows instructions](https://davidburela.wordpress.com/2015/11/28/easily-install-jekyll-on-windows-with-3-command-prompt-entries-and-chocolatey/) to note the places in the "[Installing Dependencies" section](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages) when Windows users should do something different; the rest of the lesson should work the same for both Mac and Windows users, though note that screenshots throughout the lesson are all from a Mac (so thing may look slightly different for a Windows user).

_A GitHub user account will let you host your website (make it available for others to visit) for free on GitHub (we'll cover how in a later step). As a bonus, it will also let you keep track of versions of the website and its writing as it grows or changes over time._

  1. Visit [GitHub.com](https://github.com/) and click on the "Sign up" button on the upper right. Write your desired username. This will be visible to others, identify you on GitHub, and also be part of your site's URL; for example, the author's GitHub username is amandavisconti and her demo Jekyll site's URL is http://amandavisconti.github.io/JekyllDemo/. (_Note you can also purchase your own domain name and use it for this site, but that won't be covered in this tutorial_). Also write your desired email address and password, then click "Create an account".
  2. On the next page, click the "Choose" button next to the "Free" plan option, ignore the "Help me set up an organization next" checkbox, and click "Finish sign up".
  3. _Optional_: Visit https://github.com/settings/profile to add a full name (can be your real name, GitHub user name, or something else) and other public profile information, if desired.

_The GitHub Desktop app will make updating your live website (one we set it up) easy--instead of using the command line every time you want to update your site, you'll be able to use an easier visual tool to update your site._

  1. Visit the [GitHub Desktop site](https://desktop.github.com/) and click on the "Download GitHub Desktop" button to download the GitHub Desktop software to your computer (Mac and Windows only; Linux users will need to use git just via the command line, which is not covered in this version of the tutorial).
  2. Once the file has completely downloaded, double-click on it and use the following directions to install GitHub Desktop…
  3. Enter the username and password for the GitHub.com account you created using the steps above. (Ignore the "Add an Enterprise Account" button.) Click "Continue".
  4. Enter the name and email address you want the work on your site to be associated with (probably just your public name and work email address, but it's up to you!).
  5. On the same page, click the "Install Command Line Tools" button and enter your computer's username and password if prompted (then click the "Install Helper" button on the prompt). After you get a popup message that all command line tools have successfully installed, click continue.
  6. The last page will ask "Which repositories would you like to use?". Ignore this and click the "Done" button.
  7. _Optional:_ Follow the walkthrough of the GitHub Desktop app that will appear (this isn't necessary; we will cover anything you need to do with GitHub in this lesson).

You'll need to download and install a "text editor" program on your computer for making small customizations to your Jekyll site's code. Good free options include [TextWrangler](http://www.barebones.com/products/textwrangler/download.html) (Mac) or [Notepad++](https://notepad-plus-plus.org/) (Windows). Software aimed at word processing, like Microsoft Word or Word Pad, isn't a good choice because it's easy to forget how to format and save the file, accidentally adding in extra and/or invisible formatting and characters that will break your site. You'll want something that specifically can save what you write as plaintext (e.g. HTML, Markdown).

_Optional:_ See [the "Authoring in Markdown" section below](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages) for notes on a Markdown-specific editing program, which you may also wish to install when you get to the point of authoring webpages and/or blog posts.

The command line is a way to interact with your computer using text: it lets you type in commands for actions from simpler things such as "show me a list of the files in this directory" or "change who is allowed to access this file", to more complex behavior. Sometimes there are nice visual ways to do things on your computer (e.g. the GitHub Desktop app [we installed above](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages)), and sometimes you'll need to use the command line to type out commands to get your computer to do things. The Programming Historian has [an in-depth lesson exploring the command line written](https://programminghistorian.org/lessons/intro-to-bash) by Ian Milligan and James Baker if you want more information than provided here, but this lesson will cover everything you need to know to complete the lesson (and we'll only use the command line when it's necessary or much easier than a visual interface).

Where the command line uses text commands, a "graphical user interface" (aka GUI) is what you probably normally use to work with your computer: anything where commands are given through a visual interface containing icons, images, mouse-clicking, etc. is a GUI. Often it's simpler and faster to type in (or cut and paste from a tutorial) a series of commands via the command line, than to do something using a GUI; sometimes there are things you'll want to do for which no one has yet created a GUI, and you'll need to do them via the command line.

The default command line program is called "Terminal" on Macs (located in _Applications > Utilities_), and "Command Prompt", "Windows Power Shell", or "Git Bash" on Windows (these are three different options that each differ in the type of commands they accept; we'll go in detail on which you should use later in the lesson).

Below is what a command line window looks like on the author's Mac (using Terminal). You'll see something like the _Macbook-Air:~ DrJekyll$_ below in your command line window; that text is called the "prompt" (it's prompting you to input commands). In the screenshot, _Macbook-Air_ is the name of my computer, and _DrJekyll_ is the user account currently logged in (the prompt will use different names for your computer and username).

[ ![What the command prompt looks like on a Mac](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-0.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-0.png)

> _What the command prompt looks like on a Mac_

When asked to open a command line window and enter commands in this lesson, keep the following in mind:

  1. **Commands that you should type (or copy/paste) into the command line are formatted like this:** `example of code formatting`. Each formatted chunk of code should be copied and pasted into the command line, followed by pressing enter.

  2. **Let installation processes run _completely_ before entering new commands.** Sometimes typing a command and pressing enter produces an instantaneous result; sometimes lots of text will start to fill up the command line window, or the command line window will seem to not be doing anything (but something is actually happening behind the scenes, like downloading a file). **When you've typed a command and hit enter, you'll need to wait for that command to completely finish before typing _anything else_**, or you might stop a process in the middle, causing problems. {0}. You'll know your command has completed when the command line spits out the prompt again (e.g. _Macbook-Air:~ DrJekyll$_ on the author's computer). See the screenshot below for an example of inputting a command, followed by some text showing you what was happening while that command was processed (and sometimes asking you to do something, like enter your password), and finally the reappearance of the command prompt to let you know it's okay to type something else.

[ ![An example of inputting a command, followed by some text showing you what was happening while that command was processed \(and sometimes asking you to do something, like enter your password\), and finally the reappearance of the command prompt to let you know it’s okay to type something else](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-4.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-4.png)

> _An example of inputting a command, followed by some text showing you what was happening while that command was processed (and sometimes asking you to do something, like enter your password), and finally the reappearance of the command prompt to let you know it's okay to type something else_

If you need to do something else at the command line and don't want to wait, just open a separate command line window (on a Mac, hit command-N or go to _Shell > New Window > New Window with Settings-Basic_) and do things there while waiting for the process in the other command line window to finish.

  1. Typing or pasting in the same commands a lot, or want to remember something you typed earlier? You can type the **↑** (up arrow) at the command line to scroll through recently typed commands; just press enter after the one you want to use appears.

_We'll install some software dependencies (i.e. code Jekyll depends on to be able to work), using the command line because there isn't a visual interface for doing this. This section is divided into instructions for if you're [On a Mac](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages) or [On Windows](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages), so skip down to [On Windows](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages) now if you're using Windows._

_If you're using a Mac computer, follow the instructions below until you hit a line that says the Windows-specific instructions are beginning._

Open a command line window (Applications > Utilities > Terminal) and enter the code shown in the steps below (_`code is formatted like this`_), keeping [the command line tips from above](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages) in mind.

You'll need to first install the Mac "command line tools" suite to be able to use [Homebrew](http://brew.sh/) (which we'll install next). Homebrew lets you download and install open-source software on Macs from the command line (it's a "package manager"), which will make installing Ruby (the language Jekyll is built on) easier.

  1. In Terminal, paste the following code then press enter:

`xcode-select --install`

You'll see something like the following text, followed by a popup:

[ ![After entering the code at the command prompt, you'll see a message stating 'install requested for command line developer tools'](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-1.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-1.png)

> _After entering the code at the command prompt, you'll see a message stating 'install requested for command line developer tools'_

In the popup, click the "Install" button (_not_ the "Get Xcode" button, which will install code you don't need that may take hours to download):

[ ![A popup appears with an install button](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-2.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-2.png)

> _A popup appears with an install button_

You'll see a message that "The software was installed" when the installation is complete:

[ ![Popup message stating the software was installed](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-2.5.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-2.5.png)

> _Popup message stating the software was installed_

After the command line tools suite has completed installation, return to your command line window and enter the following to install [Homebrew](http://brew.sh/):
    
    
    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
    

You'll need to press enter when prompted and enter your computer password when asked. For reference, below is a screenshot of the command entered into the author's command line, followed by all the text that appeared (including the prompt to press enter, and to enter my password).

> _ 

The command entered into the author's command line, followed by all the text that appeared (including the prompt to press enter, and to enter my password)

_

Jekyll is built from the [Ruby coding language](https://en.wikipedia.org/wiki/Ruby_%28programming_language%29). [Ruby Gems](https://rubygems.org/) makes setting up Ruby software like Jekyll easy (it's a package manager, just like Homebrew--instead of making installation easy on Macs, it adds some stuff to make Ruby installations simpler).

`brew install ruby`

Don't forget to wait until the command prompt appears again to type the following command:

`gem install rubygems-update`

[NodeJS](https://nodejs.org/en/) (or Node.js) is a development platform (in particular, a "runtime environment") that does things like making Javascript run faster.

`brew install node`

[Jekyll](https://jekyllrb.com/) is the code that creates your website (i.e. "site generation"), making it easier to do certain common tasks such as using the same template (same logo, menu, author information…) on all your blog post pages. There's more info on [what Jekyll and static sites are](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages), and on [why you'd want to use Jekyll to make a static website](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages), above.

`gem install jekyll`

**Skip the following steps (which are for Windows users only) and jump down to [Setting up Jekyll](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages).**

_Instructions for Windows users differ from those for Mac users just in this one "Installing dependencies" section. Only do the following if you're using Windows._

  1. We need a command line tool that recognizes the same commands Macs and Linux computers (i.e. Unix operating systems) do. Visit <https://git-scm.com/downloads> and click on the "Windows" link under "Downloads". Once the download has finished, double-click on the downloaded file and follow the steps to install Git Bash (leave all options the way they already are).

  2. Open "Command Prompt" (open your Start Menu and search for "Command Prompt" and an app you can open should come up).

  3. Chocolatey is a "package manager": code that lets you download and install open-source software on Windows easily from the command line. We'll now install Chocolately (_make sure to highlight and copy the whole club of text below together, not as separate lines_). Enter the code shown in the steps below (_`code is formatted like this`_), keeping [the command line tips from above](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages) in mind:

`@powershell -NoProfile -ExecutionPolicy unrestricted -Command "(iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))) >$null 2>&1" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin`

  4. Close the "Command Prompt" app and open "Git Bash" (which you recently installed) instead. **You'll now use Git Bash any time the command line is called for.**

  5. Jekyll is built from the [Ruby coding language](https://en.wikipedia.org/wiki/Ruby_%28programming_language%29). [Ruby Gems](https://rubygems.org/) makes setting up Ruby software like Jekyll easy (it's a package manager, just like Homebrew--instead of making installation easy on Macs, it adds some stuff to make Ruby installations simpler). We'll now install Ruby (this will take a few minutes):

`choco install ruby -y`

  6. Close the command line program and restart (Ruby won't work until you've done this once)

  7. [Jekyll](https://jekyllrb.com/) is the code that creates your website (i.e. "site generation"), making it easier to do certain common tasks such as using the same template (same logo, menu, author information…) on all your blog post pages. There's more info on [what Jekyll and static sites are](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages), and on [why you'd want to use Jekyll to make a static website](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages), above. We'll now install Jekyll (if Windows Security gives you a warning popup, ignore it):

`gem install jekyll`

​

**From now on, all instructions are for both Mac and PC users!**

_You've now installed everything needed to make your website. In this section, we'll use Jekyll to generate a new folder full of the files that constitute your website. We'll also locate this folder in a place accessible to the GitHub Desktop app so they're in the right place when we want to publish them as a public website later in the lesson._

  1. You'll need to know the file path to the GitHub folder created by installing the GitHub Desktop app (this is some text that says where a specific folder or file is within the directory tree on your computer, e.g. /Desktop/MyRecipes/Spaghetti.doc). If you don't know the GitHub folder file path, click on the magnifying glass icon in the top right of your computer screen (on a Mac) or use the search field on the Start Menu (Windows).
[ ![The magnifying glass icon that lets you search a Mac computer is in the top right of your computer screen](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-5.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-5.png)

> _The magnifying glass icon that lets you search a Mac computer is in the top right of your computer screen_

On Macs, a search box will appear in the middle of the screen; type in "GitHub", then double-click on the "GitHub" option that appears under "Folders" to reveal the GitHub folder in Finder (this may look slightly different on Windows, but should function the same).

Note that on some computers, this folder is instead labeled "GitHub for Macs" and may not show up on a search; if the previous steps didn't locate a GitHub folder for you, navigate to Library > Application Support in Finder and check if a "GitHub for Mac" folder is located there.

[ ![After searching for 'GitHub', a “GitHub” option appears under the 'Folders' heading; double-click 'GitHub' to reveal the GitHub folder in Finder](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-6.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-6.png)

> _After searching for 'GitHub', a "GitHub" option appears under the 'Folders' heading; double-click 'GitHub' to reveal the GitHub folder in Finder_

Right-click on the "GitHub" folder and choose "Copy 'GitHub'". The GitHub folder file path is now copied to your clipboard.

  1. At the command line, write `cd`, followed by a space, followed by the file path to your GitHub folder (either type it in if known, or press Command-v to paste in the file path you copied in the previous step). On the author's computer (logged in as the user _DrJekyll_) this command looks like:
[ ![The author's computer after entering cd, followed by a space, followed by the file path to their GitHub folder](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-7.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-7.png)

> _The author's computer after entering cd, followed by a space, followed by the file path to their GitHub folder_

command (**c**hange **d**irectory) tells your computer to look at the place in the computer's folder system you specify by the path typed after it--in this case, the path to the GitHub folder created by installing the GitHub Desktop app.

Don't forget to wait until the command prompt appears again to move to the next step.

  1. Your site's public URL will take the form http://amandavisconti.github.io/JekyllDemo/, with _amandavisconti_ being the author's GitHub username and _JekyllDemo_ the name of the site I entered at this step (_an option to purchase and use your own [custom URL](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages) is possible, but not covered in this lesson_). **Lowercase and uppercase website names do _not_ point to the same website automatically**, so unlike my _JekyllDemo_ example you might wish to pick an all-lowercase name to make sure people who hear about the site tend to type its URL correctly.

At the command line, type in the following (but replace _JekyllDemo_ with whatever you want your site to be called):

`jekyll new JekyllDemo`

This command told _jekyll_ to create a _new_ site by installing all the necessary files in a folder named _JekyllDemo_. **The folder you create at this step (e.g. _JekyllDemo_) will be referred to as the "website folder" for the rest of this tutorial.**

  2. At the command line, type in the following to navigate into your site folder (through the rest of this lesson, always replace _JekyllDemo_ with whatever name you chose for your site in the previous step):

`cd JekyllDemo`

If you look in the _GitHub > JekyllDemo_ folder in Finder, you'll see that a bunch of new files--the files that will run your website!--have been installed (we'll describe what each does [further on in the lesson](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages)):

[ ![In Finder, we can see that bunch of new files—the files that will run your website!—have been installed](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-9.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-9.png)

> _In Finder, we can see that bunch of new files--the files that will run your website!--have been installed_

_This section will describe how to run your website_ **_locally_**_--meaning you'll be able to see what your website will look like in a web browser just on your computer (aka locally), but not anywhere else. Working on a "local" version of a website means that it's private to your computer; no one else can see your website yet (your website isn't "live" or "public": no one can type in the URL and see it in their browser)._

_This means you can experiment all you want, and only publish your site for the world to see when it's ready. Or, once you've made your site live, you can continue to experiment locally with new writing, design, etc. and only add these to the public site once you're happy with how they look on the local site._

  1. At the command line, type:

`bundle exec jekyll serve --watch`

This is the command you'll run whenever you want to view your website locally:

_jekyll serve_ tells your computer to run Jekyll locally.

_-watch_ together with _bundle exec_ tells Jekyll to watch for changes to the website's files, such as you writing and saving a new blog post or webpage, and to include these changes on refreshing your web browser. **An exception to this** is the _config.yml file, which I'll discuss in more detail in the next section (any changes made there _won't_ show up until you stop and restart Jekyll).

  2. After typing in the command in the previous step, you'll notice that the process never finishes. Remember how on the command line, if you type in anything while the previous command is still processing, you can cause problems? Jekyll is now being run from this command line window, so you'll need to open a new command line window if you want to type other commands while your local site is still accessible to you (see [the section on command line usage above](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages).)

[ ![The command line after entering the command to start serving your Jekyll website](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-10.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-10.png)

> _The command line after entering the command to start serving your Jekyll website_

Reports and error messages caused by changes you make to the files in the website folder will appear in this command line window, and are a good first place to check if something isn't working.

  1. To stop running the site locally, press **control-c** (this frees up the command line window for use again). Just enter `bundle exec jekyll serve --watch` again to start running the site locally again.

  2. View your locally-running site by visiting **localhost:4000**. You'll see a basic Jekyll website with boilerplate text:

[ ![A basic Jekyll website with boilerplate text](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-11.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-11.png)

> _A basic Jekyll website with boilerplate text_

  * Type `bundle exec jekyll serve --watch` at the command line to start running your website locally. You'd visit **localhost:4000** in a browser to see your local site now, but in the next section we'll be changing things such that you'll need to visit **localhost:4000/JekyllDemo/** to see the site from then on (filling in your website folder name for _JekyllDemo_, and making sure to include the last slash).

  * Hit **control-c** at the command line to stop running the website locally.

  * While the site is running, after making changes to website files: save the files and refresh the webpage to see the changes--**except for the _config.yml file**, for which you must stop running the website and restart running the website to see changes.

  * Typing or pasting in `bundle exec jekyll serve --watch` a lot? Instead, you can type the ↑ (up arrow) at the command line to scroll through recently typed commands; just press enter after the command you want to use appears.

_You now have a basic, private website accessible only on your computer. In this section, we'll begin to customize your site by changing the website title and author information, and giving a brief overview of what the different website files do._

  1. Navigate to your website folder in Finder (Macs) or the directory folder (Windows. The author's website at _/Users/DrJekyll/GitHub/JekyllDemo_ (_DrJekyll_ is my logged in username, and _JekyllDemo_ is the name of my website folder). [Return to the "Setting up Jekyll" section](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages) if you need help locating your website folder.

You'll notice that generating and running your site in the previous section added a new "_site" folder. This is where Jekyll puts the HTML files it generates from the other files in your website folder. Jekyll works by taking various files like your site configuration settings (_config.yml) and files that just contain post or page content without other webpage information (e.g. about.md), putting these all together, and spitting out HTML pages that a web browser is able to read and display to site visitors.

[ ![Locating the website folder on the author's computer](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-18.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-18.png)

> _Locating the website folder on the author's computer_

  1. We'll start by customizing the main settings file, **_config.yml**. You'll want to open this and any future website files using your text editor (e.g. TextWrangler on Macs or Notepad++ on Windows).
[ ![Opening the text editor program TextWrangler on the author's Mac](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-14.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-14.png)

> _Opening the text editor program TextWrangler on the author's Mac_

[ ![The new _config.yml file](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-15.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-15.png)

> _The new _config.yml file_

file is a file "meant for settings that affect your whole blog, values for which your are expected to set up once and rarely need to edit after that" (as it says inside the file!). __config.yml_ is the place where you can set the title of your site, share information like your email address that you want associated with the site, or add other "basic settings"-type information you want available across your website.

The _.yml_ file type refers to how the file is written using [YAML](https://en.wikipedia.org/wiki/YAML) (the acronym standing for "YAML Ain't Markup Language"); YAML is a way of writing data that is both easy for humans to write and read, and easy for machines to interpret. You won't need to learn much about YAML, besides keeping the __config.yml_ formatted the way it originally is even as you customize the text it contains (e.g. the title information is on a separate line from your email).

  1. You can change the text in this file, save the file, and then visit your local website in a browser to see the changes. **Note that changes to _config.yml**, unlike the rest of your website files, will not show up if made while the website is already running; you need to make them while the website isn't running, _or_ after making changes to _config.yml stop then start running the website, to see changes made to this particular file. (_Changes to the _config.yml file were left out of the ability to refresh because this file can be used to declare things like the structure of site links, and altering these while the site is running could badly break things._)

Making small changes to website files (one at a time to start with), saving, and then refreshing to see the effect on your site means if you mess anything up, it will be clear what caused the issue and how to undo it.

    * Note that any line that starts with a **#** sign is a _comment_: comments aren't read as code, and instead serve as a way to leave notes about how to do something or why you made a change to the code.

    * Comments can always be deleted without effect to your website (e.g. you can delete the commented lines 1-6 in __config.yml_ if you don't want to always see this info about Jekyll use).

  2. Edit the __config.yml_ file according to these instructions:

    * **title**: The title of your website, as you want it to appear in the header of the webpage.
    * **email**: Your email address.
    * **description**: A description of your website that will be used in search engine results and the site's RSS feed.
    * **baseurl**: Fill in the quotation marks with a forward slash followed by the name of your website folder (e.g. "/JekyllDemo") to help locate the site at the correct URL.
    * **url**: Replace "http://yourdomain.com" with "localhost:4000" to help locate your local version of the site at the correct URL.
    * **twitter_username**: Your Twitter username (do not include @ symbol).
    * **github_username**: Your GitHub username.

The changes you made to the _baseurl_ and _url_ lines will let your site run from the same files both locally on your computer and live on the Web, but **doing this changed the URL where you'll see your local site from now on** (while [Jekyll is running](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages)) from localhost:4000 to **localhost:4000/JekyllDemo/** (substitute your website folder name for _JekyllDemo_ and remembering the last slash mark).

In the screenshot below, I have deleted the initial commented lines 1-9 and 12-15, as well as the commented text stating what "description" does (not necessary, just to show you can delete comments that you don't care about seeing!) and customized the rest of the file as instructed above:

[ ![The author's customized _config.yml file](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-16.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-16.png)

> _The author's customized _config.yml file_

  1. Save the file, and start (or stop and restart if it's currently running) the website, then visit **localhost:4000/JekyllDemo/** (substituting your website folder name for _JekyllDemo_ and remembering the last slash mark) to see your customized local site:
[ ![The author's customized local website](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-17.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-17.png)

> _The author's customized local website_

To get a sense of how your site works and what files you'd experiment with to do more advanced things, here are some notes on what each folder or file in your current website folder does. Remember to always open and edit any files with a text editor (e.g. TextWrangler) and not a word processor (e.g. not Microsoft Word or anything that lets you add formatting like italic and bold); this prevents invisible formatting characters from being saved in the file and messing up the website. If you just want to start adding content to your site and make it public, you can [skip to the next section](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages).

> _ 

A Finder window showing the default files and folders in a Jekyll website folder

_

  * **_config.yml** is discussed [above](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages); it provides basic settings information about your site, such as the site's title and additional possibilities we won't cover here, like how to structure links to posts (e.g. should they follow the pattern MySite.com/year/month/day/post-title?).
  * **_includes** folder has files that get included on all or certain pages (e.g. code to make the header contain your site title and main menu on every page of the site)
  * **_layouts** folder contains code that controls how the pages on your site look (default.html), as well as customizations of that code to further style blog posts (post.html) and pages (page.html)
  * **_posts** folder holds the individual files that each represent a blog post on your website. Adding a new post to this folder will make a new blog post appear on your website, in reverse chronological order (newest post to oldest). We'll cover adding blog posts in the [next section](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages).
  * **_sass** folder holds SCSS files that control the visual design of the site
  * **_site** folder is where the HTML pages that appear on the web are generated and stored (e.g. you'll write and save posts as Markdown files, but Jekyll will convert these to HTML for display in a web browser)
  * **index.md** is a place to add content that you want to appear on your homepage, such as a biography blurb to appear above the "Posts" list
  * **about.md** is an example of a Jekyll _page_. It's already linked in the header of your website, and you can customize its text by opening and writing in that file. We'll cover adding more site pages in the [next section](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages).
  * **css** folder holds CSS converted from SCSS that controls the visual design of the site
  * **feed.xml** lets people follow the RSS feed of your blog posts
  * **index.html** controls the structuring of content on your site's homepage

_This section will describe how to create pages and blog posts on your website._

**Pages** and **posts** are just two types of written content that's styled differently. Pages are content (like an "About" page) that isn't organized or displayed chronologically, but might be included in your website's main menu; posts are meant to be used for content best organized by publication date. The URLs (links) for pages and posts are also different by default (although you can change this): page URLs look like _MySite.com/about/_, while post URLs look like _MySite.com/2016/02/29/my-post-title.html._

Markdown is a way of formatting your writing for reading on the web: it's a set of easy-to-remember symbols that show where text formatting should be added (e.g. a # in front of text means to format it as a heading, while a * in front of text means to format it as a bulleted list item). For Jekyll in particular, Markdown means you can write webpages and blog posts in a way that's comfortable to authors (e.g. no need to look up/add in HTML tags while trying to write an essay), but have that writing show up formatted nicely on the web (i.e. a text-to-HTML convertor).

We won't cover Markdown in this lesson; if you're not familiar with it, for now you can just create posts and pages with no formatting (i.e. no bold/italic, no headers, no bulleted lists). But these are easy to learn how to add: there's a handy markdown [reference](http://kramdown.gettalong.org/quickref.html), as well as [a Programming Historian lesson by Sarah Simpkin on the hows and whys of writing with Markdown](https://programminghistorian.org/lessons/getting-started-with-markdown). Check out these links if you'd like to format text (italics, bold, headings, bullet/numbered lists) or add hyperlinks or embedded images and other files.

Make sure any Markdown cheatsheets you look at are for the "[kramdown](http://kramdown.gettalong.org/quickref.html)" flavor of Markdown, which is what GitHub Pages (where we'll be hosting our website) supports. (_There are [various "flavors" of Markdown](https://github.com/jgm/CommonMark/wiki/Markdown-Flavors) that have subtle differences in what various symbols do, but for the most part frequently used symbols like those that create heading formatting are the same--so you're actually probably okay using a markdown cheatsheet that doesn't specify it's kramdown, but if you're getting errors on your site using symbols that aren't included in kramdown might be why_).

You might be interested in "markdown editor" software such as [Typora](http://www.typora.io/) (OS X and Windows; free during current beta period), which will let you use popular keyboard shortcuts to write Markdown (e.g. highlight text and press command-B to make it bold) and/or type in Markdown but have it show as it will look on the web (see headings styled like headings, instead of like normal text with a # in front of them).

  1. To see an existing page on your website (created as a default part of a Jekyll website [when you created the rest of your website's files](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages)), navigate to your website folder and open the **about.md** file either in a text editor (e.g. TextWrangler) or a Markdown editor (e.g. Typora) to see the file that creates the "About" page. Also click on the "About" link in the top-right of your webpage to see what the webpage the file creates looks like in a browser.

  2. The stuff between the -- dashes is called "front matter" (_note that opening the file in a Markdown editor might make the front matter appear on a gray background instead of between dashes_). The front matter tells your site whether to format the content below the front matter as a page or blog post, the title of the post, the date and time the post should show it was published, and any categories you'd like the post or page listed under.

You can change things in the front matter of a page:

    * **layout:** Keep this as-is (it should say page).
    * **title:** Change this to the desired page title (unlike posts, no quotation marks around the title). In the screenshot below, I added a page with the title "Resume".
    * **permalink:** change the text between the two forward slash marks to the word (_or phrase--but you'll need to use hyphens and not spaces!_) that you want to follow your site's main URL to reach the page. For example, **permalink: /about/** locates a page at **localhost:4000/yourwebsitefoldername/about/**
  3. The space below the front matter's second -- dashes (or below the front matter's gray box, if using a Markdown editor) is where you write the content of your page, using [the Markdown formatting described above](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages).

  4. To create a new page in addition to the "About" page that already exists on the site (and can be customized or deleted), create a copy of the _about.md_ file in the same folder (the main website folder) and change its filename to the title you wish, using hyphens instead of spaces (e.g. _resume.md_ or _contact-me.md_). Also change the title and permalink in the file's front matter, and the content of the file. The new page should automatically appear in the main menu in the site's header:

[ ![After adding a new page file to the website folder, the new page appears in the website's header menu](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-22.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-22.png)

> _After adding a new page file to the website folder, the new page appears in the website's header menu_

For reference, you can check out [an example of a page](http://amandavisconti.github.io/JekyllDemo/resume/) on my demo site, or see [the file that's behind that page](https://raw.githubusercontent.com/amandavisconti/JekyllDemo/gh-pages/resume.md).

  1. In Finder, navigate to your website folder (e.g. _JekyllDemo_) and the __posts_ folder inside it. Open the file inside it with either a text editor (e.g. TextWrangler) or a Markdown editor (e.g. Typora). The file will be named something like _2016-02-28-welcome-to-jekyll.markdown_ (the date will match when you created the Jekyll site).
[ ![An example Jekyll website blog post file opened in a text editor](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-19.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-19.png)

> _An example Jekyll website blog post file opened in a text editor_

As with pages, with posts the stuff between the -- lines is called "front matter" (_note that opening the file in a Markdown editor might make the front matter appear on a gray background instead of between dashes_). The front matter tells your site whether to format the content below the front matter as a page or blog post, the title of the post, the date and time the post should show it was published, and any categories you'd like the post or page listed under.

  1. We're going to write a second post so you can see how multiple posts look on your site. Close the _20xx-xx-xx-welcome-to-jekyll.markdown_ file that was open, then right-click on that file in Finder and choose "Duplicate". A second file named _20xx-xx-xx-welcome-to-jekyll copy.markdown_ will appear in the _sites folder.

  2. Click once on the _20xx-xx-xx-welcome-to-jekyll copy.markdown_ file name so that you can edit the file name, then alter it to show today's date and contain a different title, such as _2016-02-29-a-post-about-my-research.markdown_ (use hyphens between words, **not** spaces).

  3. Now open your renamed file in your text or markdown editor, and customize the following:

    * **layout:** Keep this as-is (it should say _post_).
    * **title:** Change "Welcome to Jekyll!" to whatever title you'd like for your new post (keeping the quotation marks around the title). It's the norm to make the title the same as the words in the filename (except with added spaces and capitalization). This is how the title will appear on the post's webpage).
    * **date:** Change this to when you want the post to show as its publication date and time, making sure to match the date that's part of the filename. (The date _and_ time should have occurred already, for your post to show up.)
    * **categories:** Delete the words "jekyll update" for now, and don't add anything else here--the current theme doesn't use these and they mess up the post URLs. (_Other themes can use this field to sort blog posts by categories_.)
    * **The space below the second -- (or below the gray box, if using a Markdown editor):** This is where you write your blog post, using [the Markdown formatting described above](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages).

After saving, you should now be able to see your second post on the front page of your site, and clicking on the link should take you to the post's page:

[ ![The author's website, where the recently added blog post now appears on the front page](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-20.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-20.png)

> _The author's website, where the recently added blog post now appears on the front page_

[ ![The webpage for the recently added blog post on the author's site](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-21.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-21.png)

> _The webpage for the recently added blog post on the author's site_

Notice that **the URL of the post** is your local website URL (e.g. _localhost:4000/JekyllDemo/_) followed by the year/month/date of publication, followed by the title as written in your filename and ending with .html (e.g. _localhost:4000/JekyllDemo/2016/02/29/a-post-about-my-research.html_). Jekyll is converting the Markdown file you authored in the _posts folder into this HTML webpage.

**Deleting a file** from the _posts folder removes it from your website (you can try this with the "Welcome to Jekyll!!" sample post).

**To create further posts**, duplicate an existing file, then remember to change not just the front matter and content inside the post as described above, but also the file name (date and title) of the new file.

For reference, you can check out [an example of a post](https://amandavisconti.github.io/JekyllDemo/2016/11/12/a-post-about-my-research.html) on my demo site, or see [the code running that post](http://raw.githubusercontent.com/amandavisconti/JekyllDemo/gh-pages/_posts/2016-02-29-a-post-about-my-research.markdown).

_You now know how to add text pages and posts to your website. In this section. we'll move your local site live so that others can visit it on the Web._ **At this point, we are making a version of your website publicly viewable** _(e.g. to search engines and to anyone who knows of or happens on the link)._

_[Earlier in the lesson,](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages) you installed the GitHub Desktop app. We'll now use this app to easily move your website files to a place that will serve them to visitors as webpages (GitHub Pages), where the public can then visit them online. This first time, we'll move all your website's files to the Web since none of them are there yet; in the future, you'll use this app whenever you've adjusted the website's files (added, edited, or deleted content or files) on your local version of the website and are ready for the same changes to appear on the public website (there's [a cheatsheet at the end of this section](https://programminghistorian.org/lessons/building-static-sites-with-jekyll-github-pages) for this)._

  1. Open the GitHub Desktop app. Click the **+** icon in the top left corner, and click on the "Add" option along the top of the box that appears (if "Add" isn't already selected).

  2. Click on the "Choose…" button and choose the folder (_JekyllDemo_ in my example) containing your website files (if on a Mac and unable to locate this folder, your Library folder may be hidden; [use these directions](http://www.macobserver.com/tmo/article/mavericks-easily-make-user-library-folder-visible) to make it visible so the GitHub Desktop app can look navigate inside it).

  3. Then, click on the "Create & Add Repository" button (Mac) or the "Create Repository" button (Windows). You'll now see a list of the files to which you've made changes (additions or deletions to and of files) since the last time you copied your website code from your computer to GitHub (_in this case, we've never copied code to GitHub before, so all files are listed here as new_).

  4. In the first field, type a short description of the changes you've made since you last moved your work on the website to GitHub (space is limited). In this first case, something along the lines of "My first commit!" is fine; in the future, you might want to be more descriptive to help you locate when you made a given change--e.g. writing "Added new 'Contact Me' page".

You can use the larger text area below this to write a longer message, if needed (_it's optional_).

[ ![Screenshot of the author's Jekyll website repository open in the GitHub app. On the left, we see our Jekyll website folder selected; in the middle, we see a list of files we've changed since the last time we changed the live website; and at the bottom we see fields for a short description of the changes you've made and for a longer description \(if necessary\)](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-23.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-23.png)

> _ 

Screenshot of the author's Jekyll website repository open in the GitHub app. On the left, we see our Jekyll website folder selected; in the middle, we see a list of files we've changed since the last time we changed the live website; and at the bottom we see fields for a short description of the changes you've made and for a longer description (if necessary)

_

  1. At the top of the app window, click on the third icon from the left (it will say "Add a branch" if you hover over it). Type _gh-pages_ in the "Name" field, then click the "Create branch" button.
[ ![Type gh-pages in the 'Name' field, then click the 'Create branch' button](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-24.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-24.png)

> _Type gh-pages in the 'Name' field, then click the 'Create branch' button_

  1. Click on the "Commit to gh-pages" button near the bottom-left of the app window.
[ ![The 'Commit to gh-pages' button near the bottom-left of the app window](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-25.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-25.png)

> _The 'Commit to gh-pages' button near the bottom-left of the app window_

  1. Click on the "Publish" button in the top-right.
[ ![Click on the “Publish” button in the top-right](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-26.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-26.png)

> _Click on the "Publish" button in the top-right_

  1. In the popup, leave everything as-is and click the "Publish repository" button in the lower-right (_your window may not show the options related to private repositories shown in the screenshot_).
[ ![In the popup, leave everything as-is and click the 'Publish repository' button in the lower-right](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-27.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-27.png)

> _In the popup, leave everything as-is and click the 'Publish repository' button in the lower-right_

  1. Click the "Sync" button in the upper-right.
[ ![Click the 'Sync' button in the upper-right](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-28.png) ](https://programminghistorian.org/images/building-static-sites-with-jekyll-github-pages/building-static-sites-with-jekyll-github-pages-28.png)

> _Click the 'Sync' button in the upper-right_

  1. You can now visit (and share the link to!) your live website. The URL will follow the pattern of _your GitHub username DOT github.io SLASH name of your website SLASH_. (For example, the author's URL is [amandavisconti.github.io/JekyllDemo/](http://amandavisconti.github.io/JekyllDemo/).)

In the future when you want to move changes you've made locally to your live site, just follow these steps:

  1. Open the GitHub Desktop app and type a short description of your changes (and optionally a longer description in the second text box).
  2. Click the "commit" button underneath the text box.
  3. Once the commit has finished, click the "Sync" button in the top-right.
  4. Give GitHub a little time to receive these changes (about 10-90 seconds) before refreshing your live site to see your changes there.

_This lesson won't cover advanced work like changing the visual appearance of your site or adding new functionality, but here is some information to get you started on your own._

The visual design of a website is often referred to as its _theme_ (more properly, a theme is a set of code and image files that together make a major change to the appearance of a website).

You can customize the current theme of your website by making changes to the files in the __sass_ and _css_ folders (unfortunately, the most recent version of Jekyll's move to use SASS instead of plain CSS makes learning to customize things a bit more difficult for non-designers).

Or, you can add in (and further customize, if desired) a theme already created by someone else by searching for "Jekyll themes" or trying one of these resources:

  * [Jekyll plugins](http://jekyllrb.com/docs/plugins/) allow you to add small bits of code that add functionality to your site such as [full-text search](https://github.com/PascalW/jekyll_indextank), [emoji support](https://github.com/yihangho/emoji-for-jekyll), and [tag clouds](https://gist.github.com/ilkka/710577).

    * If you want to host your site on GitHub Pages as we did in this lesson, you can only use the Jekyll plugins already included in the GitHub Pages gem we installed (here's [a full list of what you installed](https://pages.github.com/versions/) when adding the GitHub Pages gem to your Gemfile earlier).

    * If you choose to host your Jekyll website elsewhere than GitHub Pages, you can use any Jekyll plugin (instructions to self-host vary by web host and won't be covered here, but [this](http://jekyllrb.com/docs/plugins/) is a page about how to install plugins once you've set up your self-hosted Jekyll site). You can search for "Jekyll plugin" plus the functionality you need to see if one is available, or check out the "Available plugins" section near the bottom of [this page](http://jekyllrb.com/docs/plugins/) for a list of plugins.

  * You can keep GitHub Page's free hosting of your Jekyll website, but give the site a **custom domain name** (domain names are purchased for a reasonable yearly fee--usually around $10--from a "domain name registrar" such as [NearlyFreeSpeech.net](https://www.nearlyfreespeech.net/services/domains)). For example, the author's LiteratureGeek.com blog is built with Jekyll and hosted on GitHub Pages just like the site you built with this lesson, but it uses a custom domain name I purchased and configured to point to my site. Instructions on setting up a custom domain name can be found [here](https://help.github.com/articles/using-a-custom-domain-with-github-pages/).

  * You can **migrate an existing blog** from many other systems including WordPress, Blogger, Drupal, and Tumblr by following the links on the right side of [this page](https://import.jekyllrb.com/docs/home/). When migrating a site, make sure to back up your original site in case it takes a couple tries to get posts living at the same URL as before (so search engine results and bookmarks don't break).

**To test stuff locally** (new plugin, theme, how a new blog post looks):

  * _Start local site_: Type `bundle exec jekyll serve --watch` at the command line
  * _Visit local site_: Open **localhost:4000/yourwebfoldername/** in a web browser (e.g. _localhost:4000/JekyllDemo/_). Don't forget the trailing slash!
  * _See changes on the local site as you make them:_ While the site is running, after making changes to website files: save the files and refresh the webpage to see the changes--**except for the _config.yml file**, for which you must stop running the website and restart running the website to see changes.
  * _Stop local site:_ Hit **control-c** on the command line.

**To move local changes to your live site** (new post, settings tweak, etc.):

  * Make the desired changes to your website's local files.
  * Open the GitHub Desktop app, make sure your website is chosen in the left sidebar's list of repositories, and write your commit message summary (and description if desired).
  * Click "Commit to gh-pages" in the lower left.
  * After the commit has completed, click "Sync" in the upper right.
  * Allow 10-90 seconds for your changes to reach GitHub's web servers, then visit your website and refresh the page to see your changes live.

If you run into an issue, [Jekyll has a page on troubleshooting](https://jekyllrb.com/docs/troubleshooting/) that might help. If you're working on the command line and get an error message, don't forget to try searching for that specific error message online. Besides search engines, [the StackExchange site](http://stackexchange.com/) is a good place to find questions and answers from people who have run into the same problem as you in the past.

Thanks to _Programming Historian_ Editor Fred Gibbs for editing, discussing, and reviewing this lesson; Paige Morgan and Jaime Howe for reviewing this lesson; Scott Weingart and students for testing the lesson with Windows; and Tod Robbins and Matthew Lincoln for suggestions on the [DH Slack](http://tinyurl.com/DHSlack) on what to cover in this lesson.

Check out the following links for documentation, inspiration, and further reading about Jekyll:

  * Jekyll "unofficially" links to two Windows + Jekyll resources: <http://jekyll-windows.juthilo.com/> and <https://davidburela.wordpress.com/2015/11/28/easily-install-jekyll-on-windows-with-3-command-prompt-entries-and-chocolatey/>
  * [Join the Digital Humanities Slack](http://tinyurl.com/DHslack) (anyone can join, even if you have no DH experience) and check out the #publishing channel for discussions of Jekyll and other DH publishing platforms
