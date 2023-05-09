
# Static site of photo wall

Photo Stream is a simpler home for your photos initially created by [@maxvoltar](https://github.com/maxvoltar) and now maintained by [@waschinski](https://github.com/waschinski), [@boerniee](https://github.com/boerniee) and [friends](https://github.com/waschinski/photo-stream/graphs/contributors). Easy to use, self hosted, no tracking, just photos.

- [Demo](#demo)
- [Live Examples](#live-examples)
- [Why?](#why)
- [How to use](#how-to-use)
- [How to deploy](#how-to-deploy)
- [How to add photos](#how-to-add-photos)
- [Customize](#customize)
    - [Basics](#basics)
    - [Advanced](#advanced)
- [Credits](#credits)

## Demo

There is a demo [https://photo-stream-muh3.onrender.com/](https://myfoto.onrender.com/) of this repository hosted on a Free Plan on [Render](https://render-web.onrender.com/).

## Live Examples

- [floremotion.de](https://floremotion.de)
- [photos.alexbaldwin.com](https://photos.alexbaldwin.com)
- [photo.silvandaehn.com](https://photo.silvandaehn.com)
- [rafa.photo](https://rafa.photo)
- [instantanes.loeuillet.org](https://instantanes.loeuillet.org)

## Why?

We like to take photos and share them. Problem is it's hard to really own your photos and how they're represented across social media these days, so we set out to make a place for them. You host it yourself, wherever you want (Netlify, Github Pages...), you're in control.

## How to use

Just fork this repository. 

## How to deploy 

Go to [https://dashboard.render.com/](https://dashboard.render.com/)

Fork this repo and add your own photos to the `photos/original` folder. Log in to your Render account or create a new one. Create a new static site on the Render Dashboard. Connect your Github account and select your photo-stream repository. Select the correct branch and adjust the Build Command (`bundle exec jekyll build`) and Publish Directory (`_site`). 

## How to add photos

Put your photos (not resized) in the `photos/original` directory. Optionally you can give them a name, which will appear as the title of the photo page.

## Customize
### Basics


First thing you want to do is edit a couple of things in `/.env`:

- `TITLE`: The title of your photo stream.
- `EMAIL`: Your email address (this line is optional, you can remove it).
- `AUTHOR_NAME`: Your name.
- `AUTHOR_EMAIL`: Your email address (optional).
- `AUTHOR_WEBSITE`: Your website (could be the address of this photo stream).
- `DESCRIPTION`: Description of your photo stream.
- `BASEURL`: Should be left empty or removed **⚠️ Do not change unless you know what you're doing**
- `URL`: Where will this photo stream live (example: `https://maxvoltar.photo`), must NOT end with / or links will be messed up.
- `SHOW_RSS_FEED`: Set to either `1` or `0` to enable or disable showing the RSS feed button.
- `SHOW_OFFICIAL_GITHUB`: Set to either `1` or `0` to enable or disable showing the link to the official github repository.
- `DEFAULT_REVERSE_SORT`: Set this to `1` to reverse the photo sort order and show oldest photos first. Defaults to `0`.
- `ALLOW_ORDER_SORT_CHANGE`: Set this to `1` to allow users to reverse the sort order of the photos.
- `ALLOW_ORIGINAL_DOWNLOAD`: Set this to `1` to allow users to download the photos in their original size.
- `ALLOW_INDEXING`: Set this to `0` to prevent crawlers from indexing your photo stream by adding meta tag `robots`. Defaults to `1`.
- `ALLOW_IMAGE_SHARING`: Set this to `1` to allow users to share images with friends. Defaults to `1`.
- `TWITTER_USERNAME`: Your Twitter username or remove/comment this line.
- `GITHUB_USERNAME`: Your Github username or remove/comment this line.
- `INSTAGRAM_USERNAME`: Your Instagram username or remove/comment this line.
- `SYNCUSER`: Your username being used by lftp/rsync in the shell scripts to sync your site to your webserver.
- `SYNCPASS`: Your password being used by lftp/rsync in the shell scripts to sync your site to your webserver.
- `SYNCSERVER`: The URL of your webserver being used by lftp/rsync in the shell scripts where your site will be synced to.
- `SYNCFOLDER`: The folder on your webserver being used by lftp/rsync in the shell scripts where your site will be synced to.

Don't include the `@`-part of your social handles. Links to your Github, Twitter and Instagram profiles are only shown when set.

The logo is generated from [SVG Favicon Generator](https://realfavicongenerator.net/svg-favicon/)

### Advanced

Before publishing your website, Jekyll will resize your photos into 3 different buckets:

- `/photos/large`: These are only shown when a user navigates to a photo page. By default these are resized to a maximum of 2048 wide and 2048 tall. If you wish, you can change these by changing the values in `/_config.yml` (by default they look something like this: `resize_to_limit: [2048, 2048]`).
- `/photos/thumbnail`: These are used in the grid. Photo Stream will load all thumbnails above the fold, then more as you scroll down; all to save bandwidth. Standard size for these is 640 by 640 (max), but you can also change this if needed.
- `/photos/tint`: What you see while the page loads its first batch of thumbnails, also used as the background for photo pages. **⚠️ Do not make changes to the tint versions in your config file.**

## Credits

- [All contributors](https://github.com/waschinski/photo-stream/graphs/contributors)
- [Carrie Cronan for the photos used for demonstration](https://unsplash.com/@ccronan)
