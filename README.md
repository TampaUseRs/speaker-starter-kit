# Starter Kit for Tampa R Users Group Speakers

<a href="https://tampausers.github.io"><img align="right" src="https://raw.githubusercontent.com/TampaUseRs/TampaUseRs/master/assets/hex-logo/trug-hex-800.png" width="250px"></a>

## How to Use This Kit

This kit provides starter files for preparing for your Tampa R Users Group talk that will make it easier for you to prepare, for the attendees to follow along, and for the organizers to stay organized.

If you're comfortable with git and GitHub, you can fork this kit and use it as a starting place for you talk development.
You could also just clone this repo locally and start there.

If you'd rather not deal with git or GitHub, you can [download this repo as a zip file](https://github.com/TampaUseRs/speaker-starter-kit/archive/master.zip) and start there.

This document contains some instructions and guidelines for speakers based on best practices learned from previous presentations.

Aim to provide three files with your presentation:

1. Your slides
2. A companion R script
3. A short README with
    - a summary of your talk,
    - links to data files (if needed), and
    - a list of required packages to run the script.

More details and tips for each of these files are included below.
Also included are templates for your talk description that will be published on Meetup and sent out to the @TampaUseRs group.

## Talk Prep Checklist

- [ ] Choose a [presentation topic](#planning-your-talk-topic)
- [ ] Send @tgerke or @jhcreed your [talk description](#talk-description)
- [ ] [Prepare your slides](#slides-and-presentation-tips)
- [ ] Write a [companion R script](#companion-script)
- [ ] If using this speaker kit, rename or remove the speaker kit's `README.md`
- [ ] Create a [README for your talk](#talk-readme)
- [ ] [Submit your talk materials](#submit-your-talk-materials)

## Planning Your Talk Topic

Plan for a 20-30 minute talk.
This will give plenty of time for you to present on your topic, field questions, and digress into the details.

To keep your talk focused, start by focusing on a single take-away for the audience:

> After my talk, participants **will be able to...**

You don't need to cover every corner or possible use case of your chosen methodology or package.
If you are presenting about a package, stick to the most important functions or features. 
If you'll be discussing a technique or methodology, focus on the most tricky aspects that are hard to understand and can benefit from your expertise.

Working through an example is an excellent way to demonstrate a package or technique.
If using an external dataset or data source in your examples, try to use only one dataset.
That way, you'll only have to explain your data structure one time in your talk.
Remember: you'll be presenting to data enthusiasts who love to poke around a good dataset and will certainly want to ask questions about the dataset you choose.

## Talk Description

You can use this template as a starting point for your talk description.
This will be published on Meetup and our website and may be included in announcement emails sent by Meetup.
You only need to replace the parts in `{}`, or feel free to use the template as a starting point.

```plain
Learn {how to|about} {package|method|skill|approach|etc.}!
{Package|Method|Skill} {provides functions|can be used} to {complete exciting task}.
{Your Name} will walk us through an example demonstrating {key task}.

{Your Name} is an {occupation} at {company}, and uses R to {do fun things}.
{More interesting things about yourself}.
{He|She|They} can be found online at {Twitter}, {Linkedin}, or {personal website}.
```

When you've settled on your talk topic, send your description to @jhcreed so that we can announce your talk.
If you include your Twitter handle, we'll be sure to include you in any posts.

## Slides and Presentation Tips

### Using R Markdown to Prepare Your Slides

In addition to traditional slide-creation software like Microsoft PowerPoint or Apple Keynote, there are several R-centric, literate programming frameworks available based on [R Markdown][rmarkdown].

R Markdown is a plain-text markup language that lets you style regular text (like making a word **bold** with `**asterisks**`).
More importantly, it also allows you to blend R code into your documents and slides, showcasing both the code and its results.
RStudio's [Introduction to R Markdown](https://rmarkdown.rstudio.com/lesson-1.html) is an excellent place to get started.

RStudio's markdown guide also includes a section on [Slide Presentations](https://rmarkdown.rstudio.com/lesson-11.html), where they demonstrate using R Markdown do render:

- [PDF presentations with beamer](http://rmarkdown.rstudio.com/beamer_presentation_format.html)
- [HTML presentations with ioslides](http://rmarkdown.rstudio.com/ioslides_presentation_format.html)
- [HTML presentations with slidy](http://rmarkdown.rstudio.com/slidy_presentation_format.html)
- [HTML presentations with reveal.js](http://rmarkdown.rstudio.com/revealjs_presentation_format.html)
- [PowerPoint presentations](https://bookdown.org/yihui/rmarkdown/powerpoint-presentation.html)

We also recommend the [xaringan] package for creating HTML and CSS-based presentations -- and you can customize your slide styles using the [xaringanthemer] package from a Tampa UseR.

### Presentation Tips

In our current environment, we use flat screen televisions in a medium-sized room.

- Use a wide-screen 16:9 format.

- Use large fonts that are easily readable at a distance. (Definitely increase the default size of whatever presentation software/package you use.)

- Format your R code for easy readability and understandability, using descriptive variable names, extra lines, whitespace, etc.

- Favor easy to understand code structures over esoteric one-liners.

- Clearly indicate the packages required for the demo code. If you can get away with a single `library(tidyverse)`, it's a great place to start.

If you're brave, live coding is encouraged.

- Practice your examples before your talk.

- Type out your example code when possible. Live coding doesn't work as well if you simply run lines of code from a document because it's too easy to go too fast. In this case, it may be better to move your code to a slide where it's easier to read.

- Increase the viewing size of your RStudio or terminal window using <kbd>Ctrl</kbd>/<kdb>&#8984;</kbd> + <kbd>+</kdb>.

## Companion Script

Including a companion script with your talk will help participants follow along both during your talk and afterwards at home.

If you've used an R Markdown based framework to build your slides, you can create a companion script from the code included in your slides by using the [knitr] function `purl()` to extract the R code chunks in your slide into a single script.

```r
knitr::purl("slides.Rmd")
# Writes out: slides.R
```

Otherwise, keep track of the code you demonstrate in a single script.

It's important to also keep track of the packages that you use.
Try to use packages that are popular and that are hosted on CRAN or BioConductor.
Think carefully about including packages that are custom, difficult to setup, or not common for standard R installations, unless they are necessary or central to the topic of your talk.

At the top of your companion slide, include the `install.packages()` or `devtools::install_github()` code that installs the packages required to run your scripts, but comment them out.
This information will be duplicated in your talk README.

## Talk README

The speaker starter kit includes an example README file called [`README_example.md`](README_example.md) that you can use as a starting point.
Remove or rename these speaker instructions and rename `README_example.md` to `README.md`.

GitHub automatically renders README files at a folder root, so meetup participants who view your slides folder in [TampaUseRs/TampaUseRs/meetups](https://github.com/TampaUseRs/TampaUseRs/tree/master/meetups) will get an overview of your talk, the files they need to download, and packages they need to install before your presentation.
For an example of how this looks, see the meetup from [2018-06-19](https://github.com/TampaUseRs/TampaUseRs/tree/master/meetups/20180619-machine-learning).

In essence, this README should contain

- The title of your talk
- Description of your topic
- Links to data files required
- List of packages required
- Your contact information (optional)

## Submit Your Talk Materials

The Tampa R Users Group hosts copies of slides and accompanying materials online at <https://github.com/TampaUseRs/TampaUseRs>.

There are three ways to have your slides included in this repository:

1. Submit a [Pull Request](https://help.github.com/articles/creating-a-pull-request/) to the [TampaUseRs/TampaUseRs](https://github.com/TampaUseRs/TampaUseRs) repo. To do this:

    1. Fork the [TampaUseRs/TampaUseRs](https://github.com/TampaUseRs/TampaUseRs) repo into your GitHub account.
    1. Clone the repo to your local computer.
    1. Create a new branch for your slides. Inside the repo folder, run

        `git checkout -b my-presentation`

    1. Create a folder in `meetups` with the date and short description of your talk:

        `meetups/YYYYMMDD-talk-topic`

    1. Add your slides, code and additional files.

    1. Commit these files to your local repo and push to your fork on GitHub

        ```bash
        git add -u
        git commit -m "Add slides for my talk topic"
        git push -u origin my-presentation
        ```

    1. Navigate to your fork on GitHub, choose your new branch from the "Branch" drop down menu near the top of the page, and then select "New Pull Request". By default, GitHub will choose the master branch of the TampaUseRs repo, but check that this is the "base" branch. Enter a short description and click "Create Pull Request".

1. Send the slide materials by email to one of [the group admins](https://github.com/orgs/TampaUseRs/people?utf8=%E2%9C%93&query=+role%3Aowner).

1. Host your slide materials online (GitHub, personal website, etc.) and send the link to one of [the group admins](https://github.com/orgs/TampaUseRs/people?utf8=%E2%9C%93&query=+role%3Aowner).

[knitr]: https://yihui.name/knitr
[xaringan]: https://github.com/yihui/xaringan
[xaringanthemer]: https://pkg.garrickadenbuie.com/xaringanthemer
[rmarkdown]: https://rmarkdown.rstudio.com/
