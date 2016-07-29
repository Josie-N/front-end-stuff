Front End Resources
===================

This is a quick reference of links and tools I refer to on a semi-regular basis. Feel free to fork, clone or otherwise use as you wish.


##TOC
* [Architecture & Best Practices](#architecture--best-practices)
* [Bash](#bash)
* [Code Editors](#editors)
* [CSS](#css)
* [Design](#design)
* [HTML](#html)
* [Javascript](#javascript)
* [Media](#media)
* [Performance](#performance)
* [Ruby on Rails](#ruby-on-rails)
* [Sass](#sass)
* [Source Control](#source-control)
* [Terminal](#terminal-resources)
* [Tutorial Sites](#tutorial-sites)


##Architecture & Best Practices
* [BEM](http://bem.github.io/bem-method/html/all.en.html)
* [Google Web Fundamentals](https://developers.google.com/web/fundamentals/)

[[ ⬆ Top ]](#toc)

##Bash

###Show Git branch, and RVM Gemset

```
function __parse_git_branch {
 git branch --no-color 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}

function __my_rvm_ruby_version {
 local gemset=$(echo $GEM_HOME | awk -F'@' '{print $2}')
 [ "$gemset" != "" ] && gemset="@$gemset"
 local version=$(echo $MY_RUBY_HOME | awk -F'-' '{print $2}')
 [ "$version" == "1.8.7" ] && version=""
 local full="$version$gemset"
 [ "$full" != "" ] && echo "$full "
}

# via http://tammersaleh.com/posts/a-better-rvm-bash-prompt
bash_prompt() {
 local NONE="\[\033[0m\]"    # unsets color to term's fg color

 # regular colors
 local K="\[\033[0;30m\]"    # black
 local R="\[\033[0;31m\]"    # red
 local G="\[\033[0;32m\]"    # green
 local Y="\[\033[0;33m\]"    # yellow
 local B="\[\033[0;34m\]"    # blue
 local M="\[\033[0;35m\]"    # magenta
 local C="\[\033[0;36m\]"    # cyan
 local W="\[\033[0;37m\]"    # white

 local UC=$W                 # user's color
 [ $UID -eq "0" ] && UC=$R   # root's color

 PS1="$G\$(__my_rvm_ruby_version)$R\w $Y\$(__parse_git_branch)$R\$(__git_dirty)${NONE}$ "
}

bash_prompt
unset bash_prompt


function __git_dirty {
  git diff --quiet HEAD &>/dev/null
  [ $? == 1 ] && echo "!"
}
```

### Edit dot files

```
alias editbash='sublime ~/.bash_profile'
alias edithosts='sublime /etc/hosts'
alias editssh='sublime subl ~/.ssh/id_rsa'
alias editgit='sublime ~/.gitconfig'
```

### Local Server

```
alias pythonserver='python -m SimpleHTTPServer 8000'
alias l8000='open http://localhost:8000'
```

##Browser Compatibility
* [Can I Use](http://caniuse.com/)

###Testing Tools
* [ievms](https://github.com/xdissent/ievms)
* [iectrl](https://www.npmjs.org/package/iectrl)

[[ ⬆ Top ]](#toc)

##Code Editors
* [Atom](http://www.atom.io)
* [Sublime Text](http://www.sublimetext.com)

[[ ⬆ Top ]](#toc)

##CSS

###Animation
* [Animation Principles in UI](https://medium.com/design-ux/bea05243fe3)
* [Cubic Bezier](http://cubic-bezier.com/)
* [Matthew Lein Ceaser](http://matthewlein.com/ceaser/)

###Best Practices
* [CSS Guidelines](http://cssguidelin.es/)
* [Code Guide by @mdo](http://codeguide.co/)
* [Principals of Writing Idiomatic Sass](https://github.com/anthonyshort/idiomatic-sass)

###Calculators
* [Grid Calculator](http://gridcalculator.dk/)

###Clipping Masks
* [Clip Path Generator](http://cssplant.com/clip-path-generator)
* [Clippy](http://bennettfeely.com/clippy/)

###Libraries & Frameworks
* [Compass](http://compass-style.org/)
* [Ionic](http://ionicframework.com/docs/components/)
  * [Building Mobile Apps with Ionic Framework - (tutorial)](http://beta.pluralsight.com/courses/building-mobile-apps-ionic-framework-angularjs)
  * [Ionic Formulas - (tutorial)](http://learn.ionicframework.com/formulas/)
  * [Ionic Icons - Animated](http://ionicons.com/animation.html)
  * [Ionic Icons - Standard](http://ionicons.com/)
  * [NPM Package](https://www.npmjs.org/package/meanio)
* [Mobile AngularUI](http://mobileangularui.com/)

###Preprocessors
* [Sass](http://sass-lang.com/)
  * [Susy Grid](http://susy.oddbird.net/)
    * [Susy 2.0 Tutorials](https://www.youtube.com/playlist?list=PLLnpHn493BHF-TxB5PqpKfJ_XjTwP5utB)
  * [Breakpoint](http://breakpoint-sass.com/)

[[ ⬆ Top ]](#toc)

##Design

###Calculators
* [Aspect Ratio Calculator](http://andrew.hedges.name/experiments/aspect_ratio/)

###Mock Tools
* [Android px to dp Converter](http://labs.rampinteractive.co.uk/android_dp_px_calculator/)
* [iPad GUI](http://www.teehanlax.com/tools/ipad/)
* [iPhone GUI](http://www.teehanlax.com/tools/iphone/)
* [iPhone Mockuuups](http://www.mockuuups.com/)
* [iOS Cheat Sheet](http://ivomynttinen.com/blog/the-ios-design-cheat-sheet-volume-2/)

###Principles
* [Codepen Design Patterns](http://codepen.io/patterns/?mkt_tok=3RkMMJWWfF9wsRonuavJZKXonjHpfsX66e8rWKa%2BlMI%2F0ER3fOvrPUfGjI4ATsFlI%2BSLDwEYGJlv6SgFTLHGMbdlwLgJWBj0TD7slJfbfYRPf6Ba2Jw1qw%3D%3D)
* [Dribbble UI](https://dribbble.com/search?q=interface)
* [Google Material Design](http://www.google.com/design/spec/material-design/introduction.html)
* [IBM Design](http://ibm.com/design)
* [IBM Mobile First](http://ibm.com/mobilefirst)
* [iOS Human Interface Guidelines](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/index.html#//apple_ref/doc/uid/TP40006556)

###Typography
* [CSS Tricks - HTML Glyphs](http://css-tricks.com/snippets/html/glyphs/)
* [Paul Irish Bulletproof Font Face](http://www.paulirish.com/2009/bulletproof-font-face-implementation-syntax/)
* [CSSLint Bulletproof Font Face](https://github.com/CSSLint/csslint/wiki/Bulletproof-font-face)
* [Font2Web](http://www.font2web.com/)

###Vertical Rhythm
* [Basehold.it](http://basehold.it)

[[ ⬆ Top ]](#toc)

##HTML

###Best Practices
* [Code Guide by @mdo](http://codeguide.co/) (repeat from above)

###Content Generators
* [Lipsum Generator](http://www.lipsum.pro/)
* [Lorem Pixel](http://lorempixel.com/)
* [Placehold.it](http://placehold.it/)

###Preprocessors
* [Haml](http://haml.info/)
* [Jade](http://naltatis.github.io/jade-syntax-docs/)

###Web Components
* [WebComponents.org](http://webcomponents.org/)

###Tools
* [Unicode Character Table](http://unicode-table.com/en/)
* [Word 2 Clean HTML](http://word2cleanhtml.com/)

[[ ⬆ Top ]](#toc)

##Javascript

###Angular
* [AngularJS Hub](http://www.angularjshub.com/)
* [Angular Material Design - (Based on Google Material Design)](https://github.com/angular/material)
* [AngularJS Recipes](http://fdietz.github.io/recipes-with-angular-js/)
* [Angular Seed Web Starter Kit](https://github.com/rafriki/angular-seed-web-starter-kit)
* [AngularStrap](http://mgcrea.github.io/angular-strap/)
* [Coming from JQuery Background](http://stackoverflow.com/questions/14994391/how-do-i-think-in-angularjs-if-i-have-a-jquery-background/15012542#15012542)
* [Famo.us Angular Integration](http://famo.us/integrations/angular/)

###Build Tools
* [Gulp](http://gulpjs.com/)
* [Bower](http://bower.io/)
* [Yeoman](http://yeoman.io)
  * [AngularFire Generator](https://github.com/firebase/generator-angularfire)
  * Angular Generator Issues
    * [Github Generator Angular](https://github.com/yeoman/generator-angular/issues/841)
    * [Stack Overflow](http://stackoverflow.com/questions/25709324/grunt-wiredepapp-no-such-file-or-directory-bower-json)

###DOM
* [DOM API](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)

###JSON
* [JSON API](http://jsonapi.org/)
* [JSON Generator](http://www.json-generator.com/)
* [JSON Lint](http://www.jsonlint.com)

###Modernizr Hooks for oldIE
* [ie7] - screw IE7
* [ie8] - `no-backgroundsize`
* [ie9] - `no-csstransforms3d`

###Package Managers
* [NPM](https://www.npmjs.org/)

[[ ⬆ Top ]](#toc)

##Media
* [Youtube Player Demo](https://developers.google.com/youtube/youtube_player_demo)
* [WebVTT Validation](https://quuz.org/webvtt/)

[[ ⬆ Top ]](#toc)

##Performance
* [Addy Osmani Critical CSS](https://github.com/addyosmani/critical)
 * [LoadCSS.js](https://github.com/filamentgroup/loadCSS)
* [Chrome Dev Tools Network Monitor](https://developer.chrome.com/devtools/docs/network)
* [kaaes/timing tool](http://kaaes.github.io/timing/)
* [Navigation Timing API](https://dvcs.w3.org/hg/webperf/raw-file/tip/specs/NavigationTiming/Overview.html)
* [Page Speed](https://developers.google.com/speed/pagespeed/)
* [UnCSS](https://github.com/ben-eb/gulp-uncss)
* [Web Page Test](http://www.webpagetest.org/)

[[ ⬆ Top ]](#toc)

##Podcasts
* [Adventures in Angular](http://devchat.tv/adventures-in-angular/)
* [Shop Talk Show](http://shoptalkshow.com/)

[[ ⬆ Top ]](#toc)

##Ruby on Rails
* [Layouts](http://guides.rubyonrails.org/layouts_and_rendering.html)

[[ ⬆ Top ]](#toc)

## Sass
* [Compass Flexbox](http://compass-style.org/reference/compass/css3/flexbox/)
* [Microsoft Flexbox](http://msdn.microsoft.com/en-us/library/ie/hh673531(v=vs.85).aspx)
* [Ultimate Flexbox Cheatsheet](http://www.sketchingwithcss.com/samplechapter/cheatsheet.html)

### Useful Sass Media Queries
```
@mixin media-range($from, $to) {
  @media (min-width: $from) and (max-width: $to) {
    @content;
  }
}
@mixin media-min($width) {
  @media (min-width: $width) {
    @content;
  }
}
@mixin media-max($width) {
  @media (max-width: $width) {
    @content;
  }
}
```

### Sass Mixins to Target specific Browsers
```
@mixin iphone-5 {
  @media only screen and (min-device-width: 320px) and (max-device-width: 568px) and (-webkit-min-device-pixel-ratio: 2) {
    @content;
  }
}

@mixin iphone-6 {
  @media only screen and (min-device-width: 375px) and (max-device-width: 667px) and (-webkit-min-device-pixel-ratio: 2) {
    @content;
  }
}

@mixin iphone-6-plus {
  @media only screen and (min-device-width: 414px) and (max-device-width: 736px) and (-webkit-min-device-pixel-ratio: 3) {
    @content;
  }
}

@mixin iphone-all {
  @media only screen and (min-device-width: 320px) and (max-device-width: 568px) and (-webkit-min-device-pixel-ratio: 2) {
    @content;
  }

  @media only screen and (min-device-width: 375px) and (max-device-width: 667px) and (-webkit-min-device-pixel-ratio: 2) {
    @content;
  }

  @media only screen and (min-device-width: 414px) and (max-device-width: 736px) and (-webkit-min-device-pixel-ratio: 3) {
    @content;
  }
}

@mixin ms-ie-10-11-only {
  @media screen and (-ms-high-contrast: active), (-ms-high-contrast: none) {
    @content;
  }
}

@mixin ms-edge-only {
  @supports (-ms-accelerator: true) {
    @content;
  }
}

@mixin firefox-only {
  @-moz-document url-prefix() {
    @content;
  }
}
```
[[ ⬆ Top ]](#toc)


##Source Control
* [Deploying a subfolder to GitHub Pages](https://gist.github.com/cobyism/4730490)
* [Pro Git](http://git-scm.com/book)
* [GH-Pages and GoDaddy](https://medium.com/@LovettLovett/github-pages-godaddy-f0318c2f25a)

### .gitconfig
```
[user]
  name = YOUR_NAME
  email = YOUR_EMAIL
[core]
  editor = sublime -n -w
[github]
  user = YOUR_USER_NAME
[color]
  ui = true
[alias]
  acom = commit -am
  co = checkout
  st = status
  pom = push origin master
  pog = push origin gh-pages
  pulm = pull origin master
  pulg = pull origin gh-pages
  dist = subtree push --prefix dist origin gh-pages
[credential "UNFUDDLE_GIT_REP"]
  username = YOUR_USER_NAME
[credential "https://github.com"]
  username = YOUR_USER_NAME
[credential]
  helper = osxkeychain
[mergetool]
  keepBackup = false
[merge]
  summary = true
  tool = opendiff
  log = true
```

[[ ⬆ Top ]](#toc)

##Terminal
* [Console.log() Updates](https://developer.chrome.com/devtools/docs/tips-and-tricks?mkt_tok=3RkMMJWWfF9wsRonuavJZKXonjHpfsX66e8rWKa%2BlMI%2F0ER3fOvrPUfGjI4ATsFlI%2BSLDwEYGJlv6SgFTLHGMbdlwLgJWBj0TD7slJfbfYRPf6Ba2Jw1qw%3D%3D)

[[ ⬆ Top ]](#toc)

##Tutorials

###Angular Tutorials
* [A Better Way to Learn Angular](http://www.thinkster.io/angularjs/GtaQ0oMGIl/a-better-way-to-learn-angularjs)
* [AngularJS Tutorial: A Comprehensive 10,000 Word Guide](http://www.airpair.com/angularjs)
* [AngularJS For Absolute Beginners](http://medialoot.com/blog/angularjs-for-absolute-beginners/)
* [Shaping Up With Angular](https://www.codeschool.com/courses/shaping-up-with-angular-js)

###ES6 Tutorials
* [ES6.io](https:/es6.io)

###Flexbox Tutorials
* [Flexbox Froggy](http://flexboxfroggy.com/)
* [Flexbox.io](http://flexbox.io/)

###React Tutorials
* [React For Beginners](https://reactforbeginners.com/)
* [Learn Redux](https://learnredux.com/)

###General Learning Sites

####Free
* [Channel9 Javascript](http://channel9.msdn.com/Series/Javascript-Fundamentals-Development-for-Absolute-Beginners?page=2)
* [Codecademy](http://www.codecademy.com/)
* [Codrops](http://tympanus.net/codrops/)
* [Coursera](https://www.coursera.org/)
* [How To Learn Javascript Properly](http://javascriptissexy.com/how-to-learn-javascript-properly/)
* [Learn Code the Hard Way](http://learncodethehardway.org/)
* [MDN Javascript](https://developer.mozilla.org/en-US/learn/javascript)
* [Thinkster.io Angular Tutorials](https://thinkster.io)

####Paid
* [Code School](http://www.codeschool.com)
* [Digital Tutors](http://www.digitaltutors.com/)
* [Lynda.com](http://www.lynda.com)
* [Pluralsight](http://www.pluralsight.com/)
* [Team Treehouse](http://www.teamtreehouse.com)
* [Udacity](http://www.udacity.com)
* 


[[ ⬆ Top ]](#toc)
