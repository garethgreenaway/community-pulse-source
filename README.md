This is the thing that drives the new Community Pulse website.

## Contributing

Here are the steps to follow to get going as a Community Pulse content contributor (or heck, even a code contributor)

1. Install [Hugo](http://gohugo.io) - *NOTE: Please make sure it is at least version 0.16*
2. Clone this repo
3. If you want to fire up a local copy to see your changes as you go, enter this command `hugo server -w --baseUrl="http://localhost:1313"`
4. You probably want to do the previous thing in another pane/window, as it needs to keep running. The -w watches for any changes and rebuilds on the fly. You have to reset the baseUrl or it will try to go to new.communitypulse.io
5. If you want to make a new episode, type in `hugo new episode/my-episode-name.md` *Note - it is highly recommended that you follow this pattern rather than duplicating an existing file, as this will ensure you get the latest and greatest required frontmatter elements*

## Episodes

When you create a new episode, Hugo will populate the front-matter of the .md file with a bunch of stuff for you. These are the required items to be sure to populate:
* **Description** - A string in double quotes. Please make sure that any double quotes are escaped, as such: `\"Community\"`
* **podcast** - this is the URL to the podcast MP3. You may not have this at the time you are creating an epiosde page, so that's okay.
* **guests** - a comma separated list of the guests, in the format first initial, last name (i.e., `"cjones", "jyee"`). The names should line up to .yml files in `data/guests`
* **friendly** - this is the shortname of the episode. It should be the name of the file minus the .md extension. I tried to automate this without success so far. Sorry :(
* **explicit** - this is a "yes" or "no" (in quotes) value depending on if the episode has explicit language. If you are not sure, please set it to "yes".
* **episode** - a string for the episode number, i.e., `"42"`
* **title** - the title of the episode. It's a string inside double quotes.
* **images** - Array of images for social sharing. You should be able to just take the default and replace the slug with the "friendly" for that episode.
* **author** - A string that contains either "Jason", "Mary", or "PJ"
* **aliases** - Array of strings for redirects. The only one you should ever need is for the episode number, i.e., `aliases = ["/27"]`
* **youtube** - the URL of the YouTube video, if there is one. If not, delete this line from the frontmatter of the episode.

## Guests

**Guest image(s)** - These need to be JPG, 500px x 500px, and named after the guest data file name (i.e., `mthengvall.jpg`). They are stored in the `static/img/guests` folder.

**Guest links** - You'll notice that the layout for each single episode (themes > community-pulse > layouts > episode > single.html) has a string of {{ if }} clauses toward the bottom of the page. This allows for guests to have various links to social media & websites if they wish. These can include Facebook, Twitter, Github, LinkedIn, and their personal website. These links, along with their bio, are pulled from their guest file (data > guests > `pjhagerty.yml`).

## Show Notes

When writing show notes, here are a few things to consider:

### Avoid using plain-text URL's
Just pasting in a URL is much worse for us SEO-wise, and it's also less delightful for the reader. For example, `[Jessica’s awesome talk about mindfulness](http://www.thing.com/stuff)` is better than `http://www.thing.com/stuff`

### Embedding tweets
If you are referencing a tweet, please use the built-in shortcode to create a pretty embed for the tweet. You can do this by using the code `{{< tweet 666616452582129664 >}}` where the number is the ID of the tweet (which is the end of the tweeet's URL, for example, `https://twitter.com/spf13/status/666616452582129664`.

The exception to this rule is if you suspect that the tweet might be deleted due to controversy; at that point you might consider a screenshot of the tweet.

## Contributing Code

Until you get your legs under you with the code (you'll need things like a LESS compiler, etc), I highly recommend just sticking with the content items. However, if you want to fix/enhance any of the Hugo code or CSS/Bootstrap stuff, please fork the repo and submit a PR for evaluation.


### Credits

Thanks to the [Arrested DevOps](https://www.arresteddevops.com/) crew for [this repo](https://github.com/arresteddevops/ado-hugo) that we borrowed heavily from.
