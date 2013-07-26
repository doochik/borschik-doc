# Borschik
[![Build Status](https://secure.travis-ci.org/bem/borschik.png?branch=master)](http://travis-ci.org/bem/borschik)
[![NPM version](https://badge.fury.io/js/borschik.png)](http://badge.fury.io/js/borschik)

Borschik is an extendable builder for text-based file formats.
It's main purpose is the assembly of static files for web projects (CSS, JS, etc.).

You can get more info in [article at bem.info](http://bem.info/articles/borschik)

Also docs are [available in russian](README.ru.md).

## Examples
### Include files
`page.js`
```js
var myProjectNamespace = {};
/* borschik:include:js/module1.js */
```

`js/module1.js`
```js
myProjectNamespace.module1 = {}
```

The result file will be
```js
var myProjectNamespace = {};
myProjectNamespace.module1 = {}
```

### Links process
Borschik can change urls from relative to relative or absolute
```css
.a {
   background: url("i/bg.png")
}
```

Can be processed to
```css
.a {
   background: url("//yandex.ru/project/1.0.0/i/bg.png")
}
```

Or event process path as file hash sum
```css
.a {
   background: url("//yandex.ru/project/_freezes/wFPs-e1B3wMRud8TzGw7YHjS08I.png")
}
```

## Install

Prerequisites:

* nodejs >= 0.6.x&nbsp;— [http://nodejs.org](http://nodejs.org)
* npm&nbsp;— [http://github.com/isaacs/npm/](http://github.com/isaacs/npm/)

From NPM for use as a command line app:

    npm install borschik -g

From Git:

    git clone git://github.com/bem/borschik.git

## Usage

```
borschik [OPTIONS] [ARGS]
```

The available options are:

    -h, --help                          Help

    -v, --version                       Current version

    -t TECH, --tech=TECH                Path to technology (default: file extenstion)
                                                                          [string]
    -i INPUT, --input=INPUT             Input file (required)
                                                                          [string]
    -o OUTPUT, --output=OUTPUT          Output file (required)
                                                                          [string]
    -f FREEZE, --freeze=FREEZE          Freeze links to static files (default: yes)
                                                                          [boolean]
    -m MINIMIZE, --minimize=MINIMIZE    Minimize resulting content (default: yes)
                                                                          [boolean]
    -c COMMENTS, --comments=COMMENTS    Wrap included files with comments (default: yes)
                                                                          [boolean]

## Technologies support


<!-- Yandex.Metrika counter -->
<img src="https://mc.yandex.ru/watch/12831025" style="position:absolute; left:-9999px;" alt="" />
<!-- /Yandex.Metrika counter -->
