# Terminal Extended

This is the theme I use for my personal website.
It is a fork of the amazing [Hugo theme named Terminal by panr](https://github.com/panr/hugo-theme-terminal), adding more features and some differences that I need.

![Terminal Extended](https://github.com/Louisload/hugo-theme-terminal-extended/blob/master/images/links-list.jpg?raw=true)
![Terminal Extended](https://github.com/Louisload/hugo-theme-terminal-extended/blob/master/images/portfolio1.png?raw=true)

#### Barebones demo - https://www.luisrodriguesalves.dev/hugo-theme-terminal-extended
#### Real life demo - https://luis.zip

## List of Features:
- [Portfolio](#portfolio)
- [Link list](#link-list) (similar to paid services that provide a link aggregator)

## List of differences
- Language menu always visible below the top header bar
- Posts list is simpler, not being expanded and therefore not showing content
- Customisable dates for the post list (set `ListDateFormat` to your desired format in `config.toml`)
- Allow overriding theme with Sass (create a file `assets/css/override.scss`)
- Hide footer default credit (set `HideDefaultCredit` to `true` in your `config.toml`)

### Quick setup
[Please visit the original fork page for the complete readme with the basic instructions of how to use the base theme.](https://github.com/panr/hugo-theme-terminal)

**Visit the folder `exampleSite` to check the code for an example site**

## Features
### Portfolio
A portfolio works as any normal section would. Consider the example below, of a section called "portfolio" with three items:

```
- exampleSite
-- content
--- portfolio
---- _index.md
---- portfolio_item1.md
---- portfolio_item2.md
---- portfolio_item3.md
```

In the `\_index.md` file to your section, add the following to the header:
``type = "portfolio"`` 

Then, for each portfolio item, add an image to your static files. I recommend them being square as per the example screenshots, although other resolutions might work too (they might look funky tho 😶). Link the images to your portfolio items by adding the following to their header:
``portfolioCover = "path_to_image.png"``

If you want to add icons, add them to the header too:
``portfolioIcons=["icon1.svg", "icon2.svg", "icon3.svg"]``

I recommend getting icons from [SimpleIcons](https://simpleicons.org/)

Using the steps above, you can have as many portfolios in your site as you want. As an example, you could have a "Photography" section with photos and a "Drawings" with drawings.

#### Sub sections
You can also organise your portfolio with subsections. Just add them as subfolders of the original section. For instance:
```
- exampleSite
-- content
--- portfolio
---- Mona Lisas
----- _index.md
----- portfolio_item1.md
----- portfolio_item2.md
----- portfolio_item3.md
---- Earrings
----- _index.md
----- portfolio_item1.md
----- portfolio_item2.md
----- portfolio_item3.md
```

![Terminal Portfolio with subsections](https://github.com/Louisload/hugo-theme-terminal-extended/blob/master/images/portfolio2.png?raw=true)

## Link List
Any page can be rendered as a Link List, including the index page if you so wish. It also supports social media links and text containers.

![Terminal Link List](https://github.com/Louisload/hugo-theme-terminal-extended/blob/master/images/links-list.jpg?raw=true)

You'll need to create a data file to save the links. It should be under the `data` folder. Here's an example, made in json, called `linklist.json`. The parameters should be self-explanatory:
```
{
    "Name": "My Link List",
    "Description": "Link List of Luís Arnaldo",
    "Image": "../photo.jpg",
    "Socials": [
        {
            "Link": "https://instagram.com/Louisload",
            "Icon": "/icon/instagram.svg",
            "AltText": "Instagram"
        },
        {
            "Link": "https://www.twitter.com/Louisload",
            "Icon": "/icon/twitter.svg",
            "AltText": "Twitter"
        }
    ],
    "List": [
        {
            "Type": "text",
            "Content": "Helloooo! and welcome to my personal web space ✨🌈  \nI'm a dev who likes to write esoteric code, compose out-of-tempo music, produce weird films and draw petit pixel art monsters. 💾 🎹 🎞️ 👾",
            "HtmlClasses": "anotherClassSoICanOverrideStyles"
        },
        {
            "Type": "link",
            "Link": "https://distrokid.com/hyperfollow/louisload/memrias-de-peixe-2",
            "Icon": "/lt/memorias.jpg",
            "AltText": "Memórias de Peixe",
            "Content": "My latest album: Memórias de Peixe",
            "OpenNewTab": true
        },
        {
            "Type": "link",
            "Link": "https://demising.faith",
            "Icon": "/lt/demisingfaith.jpg",
            "AltText": "Demising Faith",
            "Content": "Demising Faith",
            "OpenNewTab": true
        },
        {
            "Type": "link",
            "Link": "https://youtube.com/@louisload",
            "Icon": "/icon/film.svg",
            "AltText": "Film Reel",
            "Content": "Weird films",
            "OpenNewTab": true
        }
    ]
}
```

Then, on the page that you want to be a link list, add the following to the header:
```
type: "link-list"
linkListData: "linklist"
```
