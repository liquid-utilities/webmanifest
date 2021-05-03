# Web Manifest
[heading__top]:
  #web-manifest
  "&#x2B06; Build `webmanifest` file from FrontMatter or YAML"


Build `webmanifest` file from FrontMatter or YAML


## [![Byte size of Site Webmanifes][badge__main__site_webmanifes__source_code]][site_webmanifes__main__source_code] [![Open Issues][badge__issues__webmanifest]][issues__webmanifest] [![Open Pull Requests][badge__pull_requests__webmanifest]][pull_requests__webmanifest] [![Latest commits][badge__commits__site_webmanifes__main]][commits__site_webmanifes__main]


---


- [:arrow_up: Top of Document][heading__top]

- [:building_construction: Requirements][heading__requirements]

- [:zap: Quick Start][heading__quick_start]

  - [:memo: Edit Your ReadMe File][heading__your_readme_file]
  - [:floppy_disk: Commit and Push][heading__commit_and_push]

- [&#x1F9F0; Usage][heading__usage]

- [:symbols: API][heading__api]
  - [`filter`][heading__filter]
  - [`background_color`][heading__background_color]
  - [`categories`][heading__categories]
  - [`description`][heading__description]
  - [`dir`][heading__dir]
  - [`display`][heading__display]
  - [`iarc_rating_id`][heading__iarc_rating_id]

  - **[`icons`][heading__icons]**
    - [`filter`][heading__iconsfilter]
    - [`icons[0].filter`][heading__icons0filter]
    - **[`icons[0].src`][heading__icons0src]**
    - [`icons[0].sizes`][heading__icons0sizes]
    - [`icons[0].type`][heading__icons0type]
    - [`icons[0].purpose`][heading__icons0purpose]

  - [`lang`][heading__lang]
  - **[`name`][heading__name]**
  - [`orientation`][heading__orientation]
  - [`prefer_related_applications`][heading__prefer_related_applications]

  - [`protocol_handlers`][heading__protocol_handlers]
    - **[`protocol_handlers[0].url`][heading__protocol_handlers0url]**
    - **[`protocol_handlers[0].protocol`][heading__protocol_handlers0protocol]**

  - [`related_applications`][heading__related_applications]
    - [`related_applications[0].platform`][heading__related_applications0platform]
    - [`related_applications[0].url`][heading__related_applications0url]
    - [`related_applications[0].id`][heading__related_applications0id]

  - [`scope`][heading__scope]

  - [`screenshots`][heading__screenshots]
    - [`screenshots.filter`][heading__screenshotsfilter]
    - [`screenshots[0].filter`][heading__screenshots0filter]
    - **[`screenshots[0].src`][heading__screenshots0src]**
    - [`screenshots[0].sizes`][heading__screenshots0sizes]
    - [`screenshots[0].type`][heading__screenshots0type]

  - [`short_name`][heading__short_name]

  - [`shortcuts`][heading__shortcuts]
    - [`shortcuts.filter`][heading__shortcutsfilter]
    - [`shortcuts[0].filter`][heading__shortcuts0filter]
    - **[`shortcuts[0].name`][heading__shortcuts0name]**
    - [`shortcuts[0].short_name`][heading__shortcuts0short_name]
    - [`shortcuts[0].description`][heading__shortcuts0description]
    - **[`shortcuts[0].url`][heading__shortcuts0url]**
    - [`shortcuts[0].icons`][heading__shortcuts0icons]

  - [`start_url`][heading__start_url]

  - [`theme_color`][heading__theme_color]

- [&#x1F5D2; Notes][heading__notes]

- [:chart_with_upwards_trend: Contributing][heading__contributing]

  - [:trident: Forking][heading__forking]
  - [:currency_exchange: Sponsor][heading__sponsor]

- [:card_index: Attribution][heading__attribution]

- [:balance_scale: Licensing][heading__license]


> Note, bold API properties are _Mandatory_ within a given scope


---



## Requirements
[heading__requirements]:
  #requirements
  "&#x1F3D7; Prerequisites and/or dependencies that this project needs to function properly"


This repository depends upon [Jekyll][jekyll_rb__home] which is supported by [GitHub Pages][github_docs__github_pages__jekyll], further details about setup can be found from [documentation][jekyll_rb__github_pages] published by the Jekyll maintainers regarding GitHub Pages.


______


## Quick Start
[heading__quick_start]:
  #quick-start
  "&#9889; Perhaps as easy as one, 2.0,..."


This repository encourages the use of Git Submodules to track dependencies


**Bash Variables**


```Bash
_module_name='webmanifest'
_module_https_url="https://github.com/liquid-utilities/webmanifest.git"
_module_base_dir='_layouts/modules'
_module_path="${_module_base_dir}/${_module_name}"
```


**Bash Submodule Commands**


```Bash
cd "<your-git-project-path>"

git checkout gh-pages

mkdir -vp "${_module_base_dir}"

git submodule add -b main\
                  --name "${_module_name}"\
                  "${_module_https_url}"\
                  "${_module_path}"
```


---


### Your ReadMe File
[heading__your_readme_file]:
  #your-readme-file
  "&#x1F4DD; Suggested additions for your ReadMe.md file so everyone has a good time with submodules"


Suggested additions for your _`ReadMe.md`_ file so everyone has a good time with submodules


```MarkDown
Clone with the following to avoid incomplete downloads


    git clone --recurse-submodules <url-for-your-project>


Update/upgrade submodules via


    git submodule update --init --merge --recursive
```


### Commit and Push
[heading__commit_and_push]:
  #commit-and-push
  "&#x1F4BE; It may be just this easy..."


```Bash
git add .gitmodules
git add "${_module_path}"


## Add any changed files too


git commit -F- <<'EOF'
:heavy_plus_sign: Adds `liquid-utilities/webmanifest#1` submodule



**Additions**


- `.gitmodules`, tracks submodules AKA Git within Git _fanciness_

- `README.md`, updates installation and updating guidance

- `_modules_/webmanifest`, Build `webmanifest` file from FrontMatter or YAML
EOF


git push origin gh-pages
```


**:tada: Excellent :tada:** your project is now ready to begin unitizing code from this repository!


______


## Usage
[heading__usage]:
  #usage
  "&#x1F9F0; How to utilize this repository"


**`site.webmanifest`**


```YAML
---
layout: modules/webmanifest/webmanifest

name: Liquid Utilities -- Site Web Manifest Example
short_name: Site Web Manifest Example

icons:
  filter: relative_url

  - src: assets/images/icons/android-chrome-192x192.png
    purpose: monochrome

    sizes: 192x192
    type: image/png

  - src: assets/images/icons/android-chrome-384x384.png
    filter: absolute_url
    type: image/png
---
```


## Example Output


```JSON
{
    "name": "Liquid Utilities -- Site Web Manifest Example",
    "short_name": "Site Web Manifest Example",
    "icons": [
        {
            "src": "/webmanifest/assets/images/icons/android-chrome-192x192.png",
            "sizes": "192x192",
            "type": "image/png"
        },
        {
            "src": "https://liquid-utilities.github.io/webmanifest/assets/images/icons/android-chrome-384x384.png",
            "sizes": "384x384",
            "type": "image/png"
        }
    ],
    "theme_color": "#ffffff",
    "background_color": "#ffffff",
    "display": "standalone"
}
```


______


## API
[heading__api]:
  #api
  "&#x1F523; Documentation of available FrontMatter/YAML configurations"


> Documentation of available FrontMatter/YAML configurations


### `filter`
[heading__filter]: #filter "Liquid filter `absolute_url` or `relative_url` to use for `src` and `url` keys"


Liquid filter `absolute_url` or `relative_url` to use for `src` and `url` keys


Type: **`absolute_url`** | **`relative_url`** | **`false`**
Mandatory: false


```yaml
filter: relative_url
```


https://jekyllrb.com/docs/liquid/filters/


### `background_color`
[heading__background_color]: #background_color "Background color for application prior to loading stylesheet"


Background color for application prior to loading style-sheet


Type: **string**
Mandatory: false


```yaml
background_color: red
```


[MDN -- background_color][link__mdn__background_color]


---


### `categories`
[heading__categories]: #categories "List of categories that application belongs to"


List of categories that application belongs to


YAML Type: **string** | **array**
Result Type: **string[]**
Mandatory: false


```yaml
categories:
  - books
  - education
  - medical
```


[MDN -- categories][link__mdn__categories]


---


### `description`
[heading__description]: #description "Explanation of what the application does"


Explanation of what the application does


Type: **string**
Mandatory: false


```yaml
description: Example PWA (Progressive Web Application) configured by `liquid-utilities/webmanifest`
```


[MDN -- description][link__mdn__description]


---


### `dir`
[heading__dir]: #dir "Direction of text, `auto`, `ltr` (left-to-right), or `rtl` (right-to-left)"


Direction of text, `auto`, `ltr` (left-to-right), or `rtl` (right-to-left)


Type: **`auto`** | **`ltr`** | **`rtl`**
Mandatory: false


```yaml
dir: ltr
```


[MDN -- dir][link__mdn__dir]


---


### `display`
[heading__display]: #display "Preferred display mode for website; `'fullscreen'`, `'standalone'`, `'minimal-ui'`, or `'browser'`"


Preferred display mode for website; `fullscreen`, `standalone`, `minimal-ui`, or `browser`


Type: **`fullscreen`** | **`standalone`** | **`minimal-ui`** | **`browser`**
Mandatory: false


```yaml
display: standalone
```


[MDN -- display][link__mdn__display]


---


### `iarc_rating_id`
[heading__iarc_rating_id]: #iarc_rating_id "Certification code from IARC (International Age Rating Coalition) for application"


Certification code from IARC (International Age Rating Coalition) for application


Type: **string**
Mandatory: false


```yaml
iarc_rating_id: e84b072d-71b3-4d3e-86ae-31a8ce4e53b7
```


[MDN -- iarc_rating_id][link__mdn__iarc_rating_id]


https://www.globalratings.com/for-developers.aspx


---


### `icons`
[heading__icons]: #icons "Array of dictionaries that describe image assets used by application"


Array of dictionaries that describe image assets used by application


Type: **dictionary**
Mandatory: true


```yaml
icons:
  filter: relative_url

  - src: assets/images/icons/android-chrome-192x192.png
    purpose: monochrome
    sizes: 192x192
    type: image/png

  - src: assets/images/icons/android-chrome-384x384.png
    filter: absolute_url
    type: image/png
```


[MDN -- icons][link__mdn__icons]


#### `icons.filter`
[heading__iconsfilter]: #iconsfilter "Overwrite or set `filter` for `icons` scoped data"


Overwrite or set `filter` for `icons` scoped data


Type: [`filter`][heading__filter]
Mandatory: false


```yaml
icons:
  filter: relative_url
```


#### `icons[0].filter`
[heading__icons0filter]: #icons0filter "Overwrite or set `filter` for specific icon"


Overwrite or set `filter` for specific icon


Type: [`filter`][heading__filter]
Mandatory: false


```yaml
icons:
  - src: '...'
    filter: absolute_url
```


#### `icons[0].src`
[heading__icons0src]: #icons0src "Path to image file, if relative the base URL will be of the manifest file"


Path to image file, if relative the base URL will be of the manifest file


Type: **string**
Mandatory: true


```yaml
icons:
  - src: assets/images/icons/android-chrome-192x192.png
```


#### `icons[0].sizes`
[heading__icons0sizes]: #icons0sizes "Space-separated string of image dimensions"


Space-separated string of image dimensions


Type: **string**
Mandatory: false


```yaml
icons:
  - src: '...'
    sizes: 192x192
```


#### `icons[0].type`
[heading__icons0type]: #icons0type "Media type of image which allows user agent to quickly ignore unsupported types"


Media type of image which allows user agent to quickly ignore unsupported types


Type: **MIME**
Mandatory: false


```yaml
icons:
  - src: '...'
    type: image/png
```


[MDN -- Image_types][link__mdn__image_types]


#### `icons[0].purpose`
[heading__icons0purpose]: #icons0purpose "Space-separated string of hints as to image special purpose"


Space-separated string of hints as to image special purpose


Type: **`monochrome`** | **`maskable`** | **`any`**
Mandatory: false


```yaml
icons:
  - src: '...'
    purpose: monochrome
```


https://w3c.github.io/manifest/#purpose-member


---


### `lang`
[heading__lang]: #lang "Specify primary language for the manifest values"


Specify primary language for the manifest values


Type: **string**
Mandatory: false


```yaml
lang: en-US
```


[MDN -- lang][link__mdn__lang]



---



### `name`
[heading__name]: #name "Name of the application"


Name of the application


Type: **string**
Mandatory: true


```yaml
name: Liquid Utilities -- Site Web Manifest Example
```


[MDN -- name][link__mdn__name]


---


### `orientation`
[heading__orientation]: #orientation


Type: **string**
Mandatory: false


- `any`
- `natural`
- `landscape`
- `landscape-primary`
- `landscape-secondary`
- `portrait`
- `portrait-primary`
- `portrait-secondary`


```yaml
orientation: any
```


[MDN -- orientation][link__mdn__orientation]


---


### `prefer_related_applications`
[heading__prefer_related_applications]: #prefer_related_applications "If `true` the user agent might suggest installing on of the `related_applications` listed"


If `true` the user agent might suggest installing on of the `related_applications` listed


Type: **boolean**
Mandatory: false


```yaml
prefer_related_applications: true
```


[MDN -- prefer_related_applications][link__mdn__prefer_related_applications]


---


### `protocol_handlers`
[heading__protocol_handlers]: #protocol_handlers


Type: **dictionary[]**
Mandatory: false


```yaml
protocol_handlers:
  filter: relative_url

  - protocol: web+jngl
    url: lookup?type%s

  - protocol: web+jnglstore
    filter: absolute_url
    url: shop?for=%s
```


[MDN -- protocol_handlers][link__mdn__protocol_handlers]


#### `protocol_handlers.filter`
[heading__protocol_handlersfilter]: #protocol_handlersfilter "Overwrite or set `filter` for `protocol_handlers` scoped data"


Overwrite or set `filter` for `protocol_handlers` scoped data


Type: [`filter`][heading__filter]
Mandatory: false


```yaml
icons:
  filter: relative_url
```


#### `protocol_handlers[0].url`
[heading__protocol_handlers0url]: #protocol_handlers0url "HTTPS URL within the application scope, not `%s` will be replaced by the URL"


HTTPS URL within the application scope, not `%s` will be replaced by the URL


Type: **string**
Mandatory: true


```yaml
protocol_handlers:
  - protocol: '...'
    url: lookup?type%s
```


#### `protocol_handlers[0].protocol`
[heading__protocol_handlers0protocol]: #protocol_handlers0url "Protocol to be handled, eg `mailto`, `ms-word`, `web+jngl`"


Protocol to be handled, eg `mailto`, `ms-word`, `web+jngl`


Type: **string**
Mandatory: true


```yaml
protocol_handlers:
  - protocol: web+jngl
    url: '...'
```


---


### `related_applications`
[heading__related_applications]: #related_applications "Array of objects of applications that are installable or accessible to platform"


Array of objects of applications that are installable or accessible to platform


Type: **dictionary[]**
Mandatory: false


```yaml
related_applications:
  - platform: play
    url: https://play.google.com/store/apps/details?id=com.example.app1
    id: com.example.app1

  - platform: itunes
    url: https://itunes.apple.com/app/example-app1/id123456789
```


[MDN -- related_applications][link__mdn__related_applications]


#### `related_applications[0].platform`
[heading__related_applications0platform]: #related_applications0platform "Platform an equivalent application may be found"


Platform an equivalent application may be found


- `chrome_web_store`
- `play`
- `itunes`
- `webapp`
- `windows`


```yaml
related_applications:
  - platform: play
```


https://github.com/w3c/manifest/wiki/Platforms


#### `related_applications[0].url`
[heading__related_applications0url]: #related_applications0url "URL at which the application can be found"


URL at which the application can be found


```yaml
related_applications:
  - platform: '...'
    url: https://play.google.com/store/apps/details?id=com.example.app1
```


#### `related_applications[0].id`
[heading__related_applications0id]: #related_applications0id "ID used to represent the application on the specified platform"


ID used to represent the application on the specified platform


```yaml
related_applications:
  - platform: '...'
    id: com.example.app1
```


---


### `scope`
[heading__scope]: #scope "Defines the navigation scope of web application context"


Defines the navigation scope of web application context


Type: **string**
Mandatory: false


```yaml
scope: app
```


> Note, if path is **not** an absolute URL then `filter` may be used to transmute path into a relative or absolute URL


[MDN -- scope][link__mdn__scope]


---


### `screenshots`
[heading__screenshots]: #screenshots "Array of dictionaries that define screenshots to showcase application"


Array of dictionaries that define screenshots to showcase application


Type: **dictionary[]**
Mandatory: false


```yaml
screenshots:
  filter: relative_url

  - src: assets/images/screenshots/screenshot1.webp
    sizes: 1280x780
    type: image/webp

  - src: assets/images/screenshots/screenshot2.webp
    filter: absolute_url
    sizes: 1280x720
    type: image/webp
```


[MDN -- screenshots][link__mdn__screenshots]


#### `screenshots.filter`
[heading__screenshotsfilter]: #screenshotsfilter "Overwrite or set `filter` for `screenshots` scoped data"


Overwrite or set `filter` for `screenshots` scoped data


Type: [`filter`][heading__filter]
Mandatory: false


```yaml
screenshots:
  filter: relative_url
```


#### `screenshots[0].filter`
[heading__screenshots0filter]: #screenshots0filter

Overwrite or set `filter` for specific screenshot


Type: [`filter`][heading__filter]
Mandatory: false


```yaml
screenshots:
  - src: '...'
    filter: absolute_url
```


#### `screenshots[0].src`
[heading__screenshots0src]: #screenshots0src "Path to image file"


Path to image file


Type: **`string`**
Mandatory: true


```yaml
screenshots:
  - src: assets/images/screenshots/screenshot1.webp
```


#### `screenshots[0].sizes`
[heading__screenshots0sizes]: #screenshots0sizes "Image dimensions"


Image dimensions


Type: **`string`**
Mandatory: false


```yaml
screenshots:
  - src: '...'
    sizes: 1280x720
```


#### `screenshots[0].type`
[heading__screenshots0type]: #screenshots0type "Media type of image which allows user agent to quickly ignore unsupported types"


Media type of image which allows user agent to quickly ignore unsupported types


```yaml
screenshots:
  - src: '...'
    type: image/webp
```


---


### `short_name`
[heading__short_name]: #short_name "Displayed if there is not enough space to display `name`"


Displayed if there is not enough space to display `name`


Type: **string**
Mandatory: false


```yaml
short_name: Site Web Manifest Example
```


[MDN -- short_name][link__mdn__short_name]


---

### `shortcuts`
[heading__shortcuts]: #shortcuts "Array of dictionaries that may build context menu displayed by Operating System"


Array of dictionaries that may build context menu displayed by Operating System


Type: **dictionary[]**
Mandatory: false


```yaml
shortcuts:
  filter: absolute_url

  - name: "Today's agenda"
    filter: relative_url
    short_name: Agenda
    description: List of events planned for today
    url: today

    icons:
      filter: relative_url

      - purpose: monochrome
        sizes: 120x120
        src: assets/images/shortcuts/agenda/medium.webp
        type: image/webp

      - src: assets/images/shortcuts/agenda/small.webp
        filter: absolute_url
        sizes: 90x90
        type: image/webp

  - name: New event
    url: create/event

  - name: New reminder
    url: create/reminder
```


[MDN -- shortcuts][link__mdn__shortcuts]


#### `shortcuts.filter`
[heading__shortcutsfilter]: #shortcutsfilter


Overwrite or set `filter` for `shortcuts` scoped data


Type: [`filter`][heading__filter]
Mandatory: false


```yaml
shortcuts:
  filter: relative_url
```


#### `shortcuts[0].filter`
[heading__shortcuts0filter]: #shortcuts0filter


Overwrite or set `filter` for specific shortcut


Type: [`filter`][heading__filter]
Mandatory: false


```yaml
shortcuts:
  - name: "..."
    filter: relative_url
```


#### `shortcuts[0].name`
[heading__shortcuts0name]: #shortcuts0name "Displayed in context menu"


Displayed in context menu


Type: **string**
Mandatory: true


```yaml
shortcuts:
  - name: "Today's agenda"
```


#### `shortcuts[0].short_name`
[heading__shortcuts0short_name]: #shortcuts0short_name "Displayed when there is insufficient space to display `name` for shortcut"


Displayed when there is insufficient space to display `name` for shortcut


Type: **string**
Mandatory: false


```yaml
shortcuts:
  - name: "..."
    short_name: Agenda
```


#### `shortcuts[0].description`
[heading__shortcuts0description]: #shortcuts0description "Describes purpose of shortcut, may be exposed via assistive technology"


Describes purpose of shortcut, may be exposed via assistive technology


Type: **string**
Mandatory: false


```yaml
shortcuts:
  - name: "..."
    description: List of events planned for today
```


#### `shortcuts[0].url`
[heading__shortcuts0url]: #shortcuts0url "URL within application that is opened by shortcut"


URL within application that is opened by shortcut


Type: **string**
Mandatory: true


```yaml
shortcuts:
  - name: "..."
    url: today
```


#### `shortcuts[0].icons`
[heading__shortcuts0icons]: #shortcuts0icons "Icons that may be used in the context menu for shortcut"


Icons that may be used in the context menu for shortcut


Type: **[`icons`][heading__icons]**
Mandatory: false


---


### `start_url`
[heading__start_url]: #start_url "Base URL of application that should be loaded on launch of application"


Base URL of application that should be loaded on launch of application


Type: **string**
Mandatory: false


```yaml
start_url: /
```


> Note, if path is **not** an absolute URL then `filter` may be used to transmute path into a relative or absolute URL


[MDN -- start_url][link__mdn__start_url]


---


### `theme_color`
[heading__theme_color]: #theme_color "Default theme color for application, sometimes shown in task switcher"


Default theme color for application, sometimes shown in task switcher


Type: **string**
Mandatory: false


```yaml
theme_color: red
```


[MDN -- theme_color][link__mdn__theme_color]


______


## Notes
[heading__notes]:
  #notes
  "&#x1F5D2; Additional things to keep in mind when developing"


This repository may not be feature complete and/or fully functional, Pull Requests that add features or fix bugs are certainly welcomed.



______


## Contributing
[heading__contributing]:
  #contributing
  "&#x1F4C8; Options for contributing to webmanifest and liquid-utilities"


Options for contributing to webmanifest and liquid-utilities


---


### Forking
[heading__forking]:
  #forking
  "&#x1F531; Tips for forking webmanifest"


Start making a [Fork][site_webmanifes__fork_it] of this repository to an account that you have write permissions for.


- Add remote for fork URL. The URL syntax is _`git@github.com:<NAME>/<REPO>.git`_...


```Bash
cd ~/git/hub/liquid-utilities/webmanifest

git remote add fork git@github.com:<NAME>/webmanifest.git
```


- Commit your changes and push to your fork, eg. to fix an issue...


```Bash
cd ~/git/hub/liquid-utilities/webmanifest


git commit -F- <<'EOF'
:bug: Fixes #42 Issue


**Edits**


- `<SCRIPT-NAME>` script, fixes some bug reported in issue
EOF


git push fork main
```


> Note, the `-u` option may be used to set `fork` as the default remote, eg. _`git push -u fork main`_ however, this will also default the `fork` remote for pulling from too! Meaning that pulling updates from `origin` must be done explicitly, eg. _`git pull origin main`_


- Then on GitHub submit a Pull Request through the Web-UI, the URL syntax is _`https://github.com/<NAME>/<REPO>/pull/new/<BRANCH>`_


> Note; to decrease the chances of your Pull Request needing modifications before being accepted, please check the [dot-github](https://github.com/liquid-utilities/.github) repository for detailed contributing guidelines.


---


### Sponsor
  [heading__sponsor]:
  #sponsor
  "&#x1F4B1; Methods for financially supporting liquid-utilities that maintains webmanifest"



______


## Attribution
[heading__attribution]:
  #attribution
  "&#x1F4C7; Resources that where helpful in building this project so far."


- [GitHub -- `github-utilitiess/make-readme`](https://github.com/github-utilitiess/make-readme)

- [MDN -- Web app manifests](https://developer.mozilla.org/en-US/docs/Web/Manifest)


______


## License
[heading__license]:
  #license
  "&#x2696; Legal side of Open Source"


```
Build `webmanifest` file from FrontMatter or YAML
Copyright (C) 2021 S0AndS0

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published
by the Free Software Foundation, version 3 of the License.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
```


For further details review full length version of [AGPL-3.0][branch__current__license] License.



[branch__current__license]:
  /LICENSE
  "&#x2696; Full length version of AGPL-3.0 License"


[badge__commits__site_webmanifes__main]:
  https://img.shields.io/github/last-commit/liquid-utilities/webmanifest/main.svg

[commits__site_webmanifes__main]:
  https://github.com/liquid-utilitiess/webmanifest/commits/main
  "&#x1F4DD; History of changes on this branch"


[site_webmanifes__community]:
  https://github.com/liquid-utilities/webmanifest/community
  "&#x1F331; Dedicated to functioning code"

[site_webmanifes__gh_pages]:
  https://github.com/liquid-utilities/webmanifest/tree/
  "Source code examples hosted thanks to GitHub Pages!"

[badge__gh_pages__webmanifest]:
  https://img.shields.io/website/https/liquid-utilities.github.io/webmanifest/index.html.svg?down_color=darkorange&down_message=Offline&label=Demo&logo=Demo%20Site&up_color=success&up_message=Online

[gh_pages__webmanifest]:
  https://liquid-utilities.github.io/webmanifest/index.html
  "&#x1F52C; Check the example collection tests"

[issues__webmanifest]:
  https://github.com/liquid-utilities/webmanifest/issues
  "&#x2622; Search for and _bump_ existing issues or open new issues for project maintainer to address."

[site_webmanifes__fork_it]:
  https://github.com/liquid-utilities/webmanifest/
  "&#x1F531; Fork it!"

[pull_requests__webmanifest]:
  https://github.com/liquid-utilities/webmanifest/pulls
  "&#x1F3D7; Pull Request friendly, though please check the Community guidelines"

[site_webmanifes__main__source_code]:
  https://github.com/liquid-utilities/webmanifest/
  "&#x2328; Project source!"

[badge__issues__webmanifest]:
  https://img.shields.io/github/issues/liquid-utilities/webmanifest.svg

[badge__pull_requests__webmanifest]:
  https://img.shields.io/github/issues-pr/liquid-utilities/webmanifest.svg

[badge__main__site_webmanifes__source_code]:
  https://img.shields.io/github/repo-size/liquid-utilities/webmanifest


[jekyll_rb__home]:
  https://jekyllrb.com/
  "Jekyll home page"

[jekyll_rb__github_pages]:
  https://jekyllrb.com/docs/github-pages/
  "Jekyll documentation for GitHub Pages setup"

[github_docs__github_pages__jekyll]:
  https://docs.github.com/en/github/working-with-github-pages/setting-up-a-github-pages-site-with-jekyll
  "GitHub Pages documentation on Jekyll setup"


[link__mdn__background_color]: https://developer.mozilla.org/en-US/docs/Web/Manifest/background_color

[link__mdn__categories]: https://developer.mozilla.org/en-US/docs/Web/Manifest/categories

[link__mdn__description]: https://developer.mozilla.org/en-US/docs/Web/Manifest/description

[link__mdn__dir]: https://developer.mozilla.org/en-US/docs/Web/Manifest/dir

[link__mdn__display]: https://developer.mozilla.org/en-US/docs/Web/Manifest/display

[link__mdn__iarc_rating_id]: https://developer.mozilla.org/en-US/docs/Web/Manifest/iarc_rating_id

[link__mdn__icons]: https://developer.mozilla.org/en-US/docs/Web/Manifest/icons

[link__mdn__image_types]: https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types

[link__mdn__lang]: https://developer.mozilla.org/en-US/docs/Web/Manifest/lang

[link__mdn__name]: https://developer.mozilla.org/en-US/docs/Web/Manifest/name

[link__mdn__orientation]: https://developer.mozilla.org/en-US/docs/Web/Manifest/orientation

[link__mdn__prefer_related_applications]: https://developer.mozilla.org/en-US/docs/Web/Manifest/prefer_related_applications

[link__mdn__protocol_handlers]: https://developer.mozilla.org/en-US/docs/Web/Manifest/protocol_handlers

[link__mdn__related_applications]: https://developer.mozilla.org/en-US/docs/Web/Manifest/related_applications

[link__mdn__scope]: https://developer.mozilla.org/en-US/docs/Web/Manifest/scope

[link__mdn__screenshots]: https://developer.mozilla.org/en-US/docs/Web/Manifest/screenshots

[link__mdn__short_name]: https://developer.mozilla.org/en-US/docs/Web/Manifest/short_name

[link__mdn__shortcuts]: https://developer.mozilla.org/en-US/docs/Web/Manifest/shortcuts

[link__mdn__start_url]: https://developer.mozilla.org/en-US/docs/Web/Manifest/start_url

[link__mdn__theme_color]: https://developer.mozilla.org/en-US/docs/Web/Manifest/theme_color

