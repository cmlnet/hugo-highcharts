# hugo-highcharts

A (very simple) theme compoment for Hugo to display charts with the help of the [Highcharts](https://www.highcharts.com/) js library.

* [Installation](#installation)
  + [As a module](#as-a-module)
  + [As a git submodule](#as-a-git-submodule)
* [Usage](#usage)
  + [Using the shortcode](#using-the-shortcode)
* [Demo](#demo)
* [ToDo](#todo)
* [Credits](#credits)

## Installation

### As a module

Add the following line to your config:

```toml
[module]
  [[module.imports]]
    disable = false
    ignoreConfig = false
    path = "github.com/cmlnet/hugo-highcharts"
```

Then run `hugo mod get -u`.  This way you can also update the theme.

### As a git submodule

Add *hugo-highcharts* as a git submodule in your project:

```bash
git submodule add https://github.com/cmlnet/hugo-highcharts.git themes/hugo-highcharts
```

Then add in your config `theme = "hugo-highcharts"`.

In order to update the theme use the following command: 

```bash
git submodule update --remote --merge
```

## Usage

Please be aware that *hugo-highcharts* loads the required (minified) scripts and CSS files from the Highcharts servers by default.
If you want to host these files loacally – because of data privacy concerns for example – then place [highcharts.js](https://code.highcharts.com/highcharts.js) and [highcharts.css](https://code.highcharts.com/css/highcharts.css) in `assets/js/` and `assets/css/`. This will disable external loading of the files automatically.

### Using the shortcode

To embed a chart in your markdown files you have to use the following shortcode:

```go
{{< highcharts-custom chart="UNIQUE_NAME" height="123" width="123" >}}
    chart code
{{< /highcharts-custom >}}
```

You have to omit the `Highcharts.chart('container', {` part at the beginning as well as the last `});`.

`height` and `width` are optinal parameters. If not set they will default to `height="30rem"` and `width="100%"`.

## Demo

You can see examples of the different chart types [on the official Highcharts site](https://www.highcharts.com/demo). To see hugo-highcharts in action on my private blog in two posts (both in German):

- ["Frauenanteil in deutschen politischen Talkshows"](https://www.c-m-l.net/2013/02/05/frauenanteil-in-deutschen-politischen-talkshows/) ([Source on GitHub](https://github.com/cmlnet/c-m-l.net/blob/master/content/posts/2013-02-05-frauenanteil-in-deutschen-politischen-talkshows/index.de.md))
- ["StuPa Wahlbeteiligung 2005 bis 2014"](https://www.c-m-l.net/2014/12/18/stupa-wahlbeteiligung-2005-bis-2014/) ([Source on GitHub](https://github.com/cmlnet/c-m-l.net/tree/master/content/posts/2014-12-18-stupa-wahlbeteiligung-2005-bis-2014))

## ToDo

- [] Ensure js and css is loaded only once in a page
- [] Enable loading of highcharts modules via parameter
- [] Add shortcodes for generating ready made graphs
- [] Fallback image (set via param)

## Credits

- Inspiration from the [Dusky Neon Potato](https://github.com/VVelox/hugo-dusky-neon-potato) theme for Hugo by [VVelox](https://vvelox.net/)