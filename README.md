[![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg?style=for-the-badge)](https://github.com/hacs/integration)

# Toggle Card to HACS

![graphical editor](img/intro.png)

Bringing the toggle card to HACS

***

* @published: May 2023
* @author: Elmar Hinz
* @workspace: `conf/www/tutor`
* @name: `toggle-card-to-hacs`
* @id: `tcth`

You learn:

* how to layout the Github repository for a custom HACS card
* how to use the HACS repository

## Goal

The goal of this tutorial is to bring you card to HACS by preparing a repository
on Github according to the requirements of HACS. It will be a custom repository.
We don't register it as a default repository.

## Prerequisites

* tutorial 06: toggle with graphical configuration
* you have an account on github
* you have HACS installed into homeassistant
* you know how to register `card.js` as a resource
* you know how to create the helper entity of type boolean aka toggle
* you know how to add and edit a card
* you know how to reload `card.js` and dashboard after editing

In doubt revisit tutorial 02 and 04.

## Setup

Take the same steps as in the previous tutorial. Name the helper entity
`tcth` this time.

## Code

The code `cardjs` is the same as in the previous tutorial. All names and ids
have been adjusted.

## HACS

The requirements of HACS are [documented
here](https://hacs.xyz/docs/publish/start).

Some requirements are stored as files into the repository.  Other requirements
like *description*, *topics* and *version* are edited with the tools of your
github repository.

### The `hacs.json` file

This is the configuration file of the HACS repository.

```js
{
    "name": "Simple Toggle Card",
    "render_readme": true,
    "filename": "card.js"
    "content_in_root": true
  }
```

The `name` is the minimal requirement of HACS. It is displayed in the frontend.
`render_readme` tells HACS to render `README.md` instead of `info.md` in the
frontend. `filename` is the name of the card's file we want to ship.

`content_in_root` informs HACS not to expect a `dist/` directory.  If you run a
toolchain to generate from a `src/` directory you will likely use a `dist/`
directory which is the default location.

### The `README.md` file

The README by chance is the file containing this turial. HACS points to
[this address] (https://github.com/matiassingers/awesome-readme) for suggestions
how to do a good README.

A badge in the *README* advertises the repository as a HACS repository. The code
string is given on the page with the documentation.

```js
[![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg?style=for-the-badge)](https://github.com/hacs/integration)
```

### Description and topics

The HACS documentation suggestes to add a discription and topics by the
administration interface of Github.

![setup on github](img/description-topcis.png)

The description is displayed in the frontend. I didn't find that the topics
would be used somewhere.

### Version

Bei default the frontend will display the latest git hash of the main branch.

![git hash](img/git-hash.png)

If you want to show a version number instead the HACS documentation advises
to create a tag with the version PLUS making a realse of it.
As this tutorials are not versionized, I don't show this.

## Using the custom card

Assuming you have HACS installed an you have first experiences how to use it.

![step 1](img/1-hacs-in-menu.png)

Open HACS in the menu on the left.

![step 2](img/2-frontend-selection.png)

Select frontend in the list.

![step 3](img/3-custom-repository-selection.png)

In the upper right hand corner select custom repositories.

![step 4](img/4-url-insertion.png)

Insert the *URL* and select the catergory *Lovelace*. The *URL* may be the *URL* of
this tutorial or your fork of it i.e. `https://github.com/home-assistant-tutorials/07.toggle-card-to-hacs`.

![step 5](img/5-new-repository.png)

After clicking *ADD* the card is registered as a new repository.

![step 6](img/6-readme.png)

Select it and this *README* will be displayed.

![step 7](img/7-downoad-button.png)

At the lower right hand corner, there is the download button.

![step 8](img/8-download-popup.png)

A download popup asks for confirmation and tells you the target directory.

![step 9](img/9-reload-popup.png)

After download you have to reload the browser.

![step 10](img/10-custom-card-selection.png)

Now change to your dashboard to add a card as usual. You find the new
card in the thumbnails selection.