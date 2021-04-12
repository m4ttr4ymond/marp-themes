# Marp Themes

This is an unofficial repository of themes for the [Marp](https://marp.app/) (Markdown Presentation) ecosystem. It is not endorsed by the Marp Team in any way. I just like the project and want to share my themes.

Hopefully soon I'll be creating some tutorials on making themes.

## Themes
- `umich`
    - A theme based off of the University of Michigan's branding requirements. This theme is heavily derived from the beautiful [Gaia](https://github.com/marp-team/marp-core/tree/main/themes) theme by [@yhatt](https://github.com/yhatt).
    - CDN Link: `https://gitcdn.link/repo/m4ttr4ymond/marp-themes/master/themes/umich/css/umich.min.css`
    - Features
      - Classes
        - `title`: A new class for the title page of the slide. There's probably a way to set the first slide to always be the title, but I'm not sure how to do that yet.

## Usage

### VS Code

1. Open the settings for the Marp extension

2. Scroll down to `Markdown > Marp: Themes`

3. Click `Add Item` and enter the CDN for the theme that you want to use

4. When making your slides, put the associated name in the yaml metadata at the top of your markdown file:

   ```yaml
   ---
   theme: <theme_name>
   ---
   
   # Etc
   ```

   

## Want to make your own theme?

Great! All you have to do is fork this repo and makes some edits. Or, if you want, you can clone the repo, add a pull request, and I'll add the theme to this repo.

Most of the important content is on the Marp docs. However, there are a few things that weren't entirely clear to me, and I haven't had time to add clarification to the Marp documentation. Hopefully I'll get to it this summer.

### Importing Files

[According to the Marp Team's policy](https://github.com/marp-team/marp/discussions/86#discussion-3308324), local file access is restricted for Marp themes. This means that using local assets is a real pain. Fortunately, we can use a remote CDN for hosting instead. For most files, you should just be able to use the following:

```css
@import url('https://...');
```

> Note that because of their dedication to security, HTTP requests will *not* work. You have to use HTTPS.

This is usually fine. However, some hosting services won't work as a CDN (probably because of server-side HTTPS settings), which prevents you from loading their hosted assets into your css. Github is the main site you'll run into issues with, but I'm sure there are others. To get around this, you just have to use a service like [GitCDN](https://gitcdn.link/) to create a cached CDN version of your `raw.githubusercontent.com...` link. If you need further instructions on using GitCDN, you can visit their repo [here](https://github.com/schme16/gitcdn.xyz).

According to the repo:

> GitCDN works by creating a short-cached (~2 hours cache time) lookup of the latest commit of the specified file, then redirecting you to a long-cached (~1 week cache time on edge servers, and ~1 year cache time on primary servers) version of that file.

This means that GitCDN will lag a bit behind any commits you make, so be careful to make any necessary updates far in advance of when you'll actually need to use the updated file. I suggest designing themes on your local machine using relative filepaths, then creating GitCDN links only when you're finished.

## Credits

- [Marp](https://github.com/marp-team)
- [HighlightJS](https://github.com/highlightjs/highlight.js)
- [GitCDN](https://github.com/schme16/gitcdn.xyz)