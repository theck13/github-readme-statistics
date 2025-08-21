GitHub `README` Statistics
====
- [Statistics Card](#statistics-card)
    - [Hide Default Statistics](#hide-default-statistics)
    - [Show Extra Statistics](#show-extra-statistics)
    - [Show Statistic Icons](#show-statistic-icons)
    - [Change Style Theme](#change-style-theme)
    - [Customize Style Colors](#customize-style-color)
        - [Common Options](#common-options)
        - [Statistics Options](#statistics-options)
        - [Repository Options](#repository-options)
        - [Gist Options](#gist-options)
        - [Language Options](#language-options)
        - [Time Options](#time-options)
- [Pins Card](#pins-card)
    - [Extra](#extra)
    - [Gist](#gist)
- [Languages Card](#languages-card)
    - [Language Percentage Algorithm](#language-percentage-algorithm)
    - [Exclude Default Repositories](#exclude-default-repositories)
    - [Hide Default Languages](#hide-default-languages)
    - [Show Extra Languages](#show-extra-languages)
    - [Hide Progress Bars](#hide-progress-bars)
    - [Compact Layout](#compact-layout)
    - [Donut Layout](#donut-layout)
        - [Horizontal](#horizontal)
        - [Vertical](#vertical)
    - [Pie Layout](#pie-layout)
    - [Layout Comparisons](#layout-comparisons)
- [Times Card](#times-card)
- [Deploy Your Instance](#deploy-your-instance)
  - [On Vercel](#on-vercel)
  - [On Others](#on-others)
  - [Disable Rate Limits](#disable-rate-limits)
  - [Sync Your Fork](#sync-your-fork)

> [!IMPORTANT]\
> Since the GitHub API only [allows 5,000 requests per hour per user account](https://docs.github.com/en/graphql/overview/resource-limitations), the public Vercel instance hosted on `https://github-readme-stats.vercel.app/api` could possibly hit the rate limiter (see [#1471](https://github.com/anuraghazra/github-readme-stats/issues/1471)).  We use caching to prevent this from happening (see https://github.com/anuraghazra/github-readme-stats#common-options).  You can turn off these rate limit protections by [deploying your own](#deploy-your-own) Vercel instance.

***

# Statistics Card

Copy and paste this into your markdown and change the `USERNAME` value to your GitHub username.  Done!

```md
![GitHub Statistics](https://github-readme-statistics.vercel.app/api?username=USERNAME)
```

> [!WARNING]\
> The statistics card only shows stars, commits, and pull requests from public repositories.  To include statistics from private repositories, [deploy your instance](#deploy-your-instance) using your own GitHub API token.

> [!NOTE]\
> Available ranks are S (top 1%), A+ (12.5%), A (25%), A- (37.5%), B+ (50%), B (62.5%), B- (75%), C+ (87.5%) and C (everyone).  This ranking scheme is based on the [Japanese academic grading](https://wikipedia.org/wiki/Academic_grading_in_Japan) system.  The global percentile is calculated as a weighted sum of percentiles for each statistic (number of commits, pull requests, reviews, issues, stars, and followers) based on the cumulative distribution function of the [exponential](https://wikipedia.org/wiki/exponential_distribution) and the [log-normal](https://wikipedia.org/wiki/Log-normal_distribution) distributions.  The implementation can be investigated at [src/calculateRank.js](https://github.com/anuraghazra/github-readme-stats/blob/master/src/calculateRank.js).  The dark ring around the rank shows 100 minus the global percentile.

### Hide Default Statistics

Default statistics can be hidden with the `hide` query parameter using comma-separated values.

#### Options

Value | Label
-|-
`commits` | Total Commits
`contribs` | Contributed to (last year)
`issues` | Total Issues
`prs` | Total PRs
`stars` | Total Stars Earned

#### Example

```md
![GitHub Statistics Hide Defaults](https://github-readme-statistics.vercel.app/api?username=USERNAME&hide=commits,contribs,issues,prs,stars)
```

### Show Extra Statistics

Extra statistics can be shown with the `show` query parameter using comma-separated values.

#### Options

Value | Label
-|-
`discussions_answered` | Total Discussions Answered
`discussions_started` | Total Discussions Started
`prs_merged` | Total PRs Merged
`prs_merged_percentage` | Merged PRs Percentage
`reviews` | Total PRs Reviewed

#### Example

```md
![GitHub Statistics Show Extras](https://github-readme-statistics.vercel.app/api?username=USERNAME&show=discussions_answered,discussions_started,prs_merged,prs_merged_percentage,reviews)
```

### Show Statistic Icons

Icons can be shown next to statistics with the `show_icons` query parameter using the `true` value.

#### Example

```md
![GitHub Statistics Show Icons](https://github-readme-statistics.vercel.app/api?username=USERNAME&show_icons=true)
```

### Change Style Theme

The style can be change with the `theme` query parameter using a value from the [built-in themes](themes/README.md).

#### Example

```md
![GitHub Statistics Change Theme](https://github-readme-statistics.vercel.app/api?username=USERNAME&theme=github_dark)
```

#### Mode

The browser mode cannot be determined from the server side since GitHub uploads the cards and serves the cards from their [content delivery network](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/about-anonymized-urls).  To show a theme based on the mode, use one of the methods below to change the card on the client side.

##### Transparent Theme

The `transparent` theme is optimized for GitHub's dark and light modes with a transparent background.  Use it with the `&theme=transparent` parameter and value.

```md
![GitHub Statistics Transparent Theme](https://github-readme-statistics.vercel.app/api?username=USERNAME&theme=transparent)
```

![GitHub Statistics Transparent Theme](https://github-readme-statistics-main.vercel.app/api?username=theck13&show_icons=true&theme=transparent)

##### Alpha Channel

The `bg_color` parameter can make any of the [built-in themes](themes/README.md) transparent by setting the value to `00000000`.

```md
![GitHub Statistics Alpha Channel](https://github-readme-statistics.vercel.app/api?username=USERNAME&bg_color=00000000)
```

![GitHub Statistics Alpha Channel](https://github-readme-statistics-main.vercel.app/api?username=theck13&bg_color=00000000)

##### Context Tag

[GitHub's context tags](https://github.blog/changelog/2021-11-24-specify-theme-context-for-images-in-markdown/) can be used to switch the theme based on the user GitHub theme automatically by appending `#gh-dark-mode-only` or `#gh-light-mode-only` to the end of an image source.  Images with `#gh-dark-mode-only` will only be shown for GitHub dark mode.  Images with `#gh-light-mode-only` will only be shown for GitHub light mode.

```md
![GitHub Statistics Context Tag Dark](https://github-readme-statistics.vercel.app/api?username=USERNAME&show_icons=true&theme=dark#gh-dark-mode-only)
![GitHub Statistics Context Tag Light](https://github-readme-statistics.vercel.app/api?username=USERNAME&show_icons=true&theme=default#gh-light-mode-only)
```

![GitHub Statistics Context Tag Dark](https://github-readme-statistics-main.vercel.app/api?username=theck13&show_icons=true&theme=dark#gh-dark-mode-only)
![GitHub Statistics Context Tag Light](https://github-readme-statistics-main.vercel.app/api?username=theck13&show_icons=true&theme=default#gh-light-mode-only)

##### Media Feature

[GitHub's media feature](https://github.blog/changelog/2022-05-19-specify-theme-context-for-images-in-markdown-beta/) can be used in HTML to specify whether to display images for dark or light mode by using the `<picture>` tag with the `prefers-color-scheme` element and `dark` or `light` value.

```html
<picture>
    <source
        media="(prefers-color-scheme: dark)"
        srcset="https://github-readme-statistics.vercel.app/api?username=USERNAME&show_icons=true&theme=dark"
    />
    <source
        media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
        srcset="https://github-readme-statistics.vercel.app/api?username=USERNAME&show_icons=true&theme=default"
    />
    <img
        alt="GitHub Statistics Show Icons"
        src="https://github-readme-statistics.vercel.app/api?username=USERNAME&show_icons=true"
    />
</picture>
```

<picture>
    <source
        media="(prefers-color-scheme: dark)"
        srcset="https://github-readme-statistics-main.vercel.app/api?username=theck13&show_icons=true&theme=dark"
    />
    <source
        media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
        srcset="https://github-readme-statistics-main.vercel.app/api?username=theck13&show_icons=true&theme=default"
    />
    <img
        alt="GitHub Statistics Show Icons"
        src="https://github-readme-statistics-main.vercel.app/api?username=USERNAME&show_icons=true"
    />
</picture>

### Customize Style Color

The card colors can be customized with query parameters.

#### Common Options

Name | Description | Type (Options) | Default
-|-|-|-
`bg_color` | background color | string (hex: `rgb`, `rrggbb`, `rrggbbaa`, or [gradient](#gradient-background)) | `fffefe`
`border_color` | border color | string (hex: `rgb`, `rrggbb`, or `rrggbbaa`) | `e4e2e2`
`border_radius` | corner radius | float (min: `0.0`, max: `248.0`) | `4.5`
`cache_seconds` | cache header | integer (min: `21600`, max: `86400`) | `21600`
`hide_border` | hide border | boolean (`false` or `true`) | `false`
`icon_color` | icons color | string (hex: `rgb`, `rrggbb`, or `rrggbbaa`) | `4c71f2`
`locale` | text language | enum ([locales](#text-locales)) | `en`
`show_icons` |  show icons | boolean (`false` or `true`) | `false`
`text_color` | body color | string (hex: `rgb`, `rrggbb`, or `rrggbbaa`) | `434d58`
`theme` | theme name | enum ([themes](themes/README.md)) | `default`
`title_color` | title color | string (hex: `rgb`, `rrggbb`, or `rrggbbaa`) | `2f80ed`

> [!WARNING]\
> Caching decreases the load on servers (see <https://github.com/anuraghazra/github-readme-stats/issues/1471#issuecomment-1271551425>).  Cards have a default cache of 6 hours (21600 seconds).  Note the cache is clamped to a minimum of 6 hours and a maximum of 24 hours.  To update the data more often, [deploy your instance](#deploy-your-instance) and set the [environment variable](#disable-rate-limit-protections) `CACHE_SECONDS` to another value.

##### Gradient Background

A gradient background color can be set with the `bg_color` parameter using multiple comma-separated values in the `DEGREE,COLOR1,COLOR2,COLOR3...COLOR10` format.

##### Example

```md
![GitHub Statistics Gradient Background](https://github-readme-statistics.vercel.app/api?username=USERNAME&bg_color=30,e96443,904e95&title_color=ffffff&text_color=ffffff)
```

![GitHub Statistics Gradient Background](https://github-readme-statistics-main.vercel.app/api?username=theck13&bg_color=30,e96443,904e95&title_color=ffffff&text_color=ffffff)

##### Text Locales

Here is a list of all available locales.

Locale | Code
-|-
Arabic | `ar`
Bengali | `bn`
Burmese | `my`
Chinese | `cn`
Chinese (Taiwan) | `zh-tw`
Czech | `cs`
Dutch | `nl`
English | `en`
French | `fr`
German | `de`
Greek | `el`
Hungarian | `hu`
Indonesian | `id`
Italian | `it`
Japanese | `ja`
Korean | `kr`
Malayalam | `ml`
Nepali | `np`
Polish | `pl`
Portuguese (Brazil) | `pt-br`
Portuguese (Portugal) | `pt-pt`
Russian | `ru`
Slovak | `sk`
Spanish | `es`
Swedish | `se`
Turkish | `tr`
Ukrainian | `uk-ua`
Uzbek | `uz`
Vietnamese | `vi`

If your language isn't supported, please consider contributing!  You can find more information in the [contributing guidelines](CONTRIBUTING.md#translations-contribution).

#### Statistics Options

Name | Description | Type (Options) | Default
-|-|-|-
`card_width` | card width | integer | `500`
`custom_title` | card title | string | `<USERNAME> GitHub Stats`
`disable_animations` | disable animations | boolean (`false` or `true`) | `false`
`exclude_repo` | excludes repositories | string (comma-separated values) | `null`
`hide` | hide [defaults](#hide-default-statistics) | string (comma-separated values) | `null`
`hide_rank` | hide rank | boolean (`false` or `true`) | `false`
`hide_title` | hide title | boolean (`false` or `true`) | `false`
`include_all_commits` | all-time commits | boolean (`false` or `true`) | `false`
`line_height` | line height | integer | `25`
`number_format` | number format | enum ([formats](#number-formats)) | `short`
`rank_icon` | rank icon | enum ([icons](#rank-icons)) | `default`
`ring_color` | rank circle | string (hex: `rgb`, `rrggbb`, or `rrggbbaa`) | `2f80ed`
`show` | show [extras](#show-extra-statistics) | string (comma-separated values) | `null`
`show_icons` | Shows icons near all stats. | boolean (`false` or `true`) | `false`
`text_bold` | Uses bold text. | boolean (`false` or `true`) | `true`

##### Number Formats

Value | Example
-|-
`long`|`1337`
`short`|`1.3k`

##### Rank Icons

Value | Description
-|-
`default`|letter from [grading system](https://wikipedia.org/wiki/Academic_grading_in_Japan)
`github`|GitHub [invertocat icon](https://github.githubassets.com/assets/GitHub-Mark-ea2971cee799.png)
`percentile`|weighted sum of statistics

> [!NOTE]\
> When `hide_rank` is `true`, the minimum card width is 270px plus the title length and padding.

#### Repository Options

Name | Description | Type (Options) | Default
-|-|-|-
`description_lines_count` | description lines | number (min: `1`, max: `3`) | `null`
`show_owner` | repository owner | boolean (`false` or `true`) | `false`

#### Gist Options

Name | Description | Type (Options) | Default
-|-|-|-
`show_owner` | gist owner | boolean (`false` or `true`) | `false`

#### Language Options

Name | Description | Type (Options) | Default
-|-|-|-
`card_width` | card width | integer | `300`
`count_weight` | count weight ([language algorithm](#language-percentage-algorithm)) | float (min: `0.0`) | `0.0`
`custom_title` | card title | string | `Most Used Languages`
`disable_animations` | disable animations | boolean (`false` or `true`) | `false`
`exclude_repo` | excludes repositories | string (comma-separated values) | `null`
`hide` | hide [defaults](#hide-default-statistics) | string (comma-separated values) | `null`
`hide_progress` | hide percentages | boolean (`false` or `true`) | `false`
`hide_title` | hide title | boolean (`false` or `true`) | `false`
`langs_count` | languages count | integer (min: `1`, max: `20`) | `5` for `normal` and `donut`, `6` for others
`layout` | layout style | enum ([layouts](#language-layouts)) | `normal`
`size_weight` | size weight ([language algorithm](#language-percentage-algorithm)) | float (min: `0.0`) | `1.0`

##### Language Layouts

Value | Description
-|-
`compact`| single horizontal progress bar with all languages
`donut`| circular progress bar next to languages
`donut-vertical`| circular progress bar above languages
`normal`| horizontal progress bar for each language
`pie`| circular progress with wedge for each language

> [!WARNING]\
> Language names should be URI-escaped, as specified in [percent encoding](https://en.wikipedia.org/wiki/Percent-encoding)
> (i.e. `c++` should be `c%2B%2B` and `visual basic` should be `visual%20basic`).  Use
> [urlencoder.org](https://www.urlencoder.org/) to help encode text automatically.

#### Time Options

Name | Description | Type (Options) | Default
-|-|-|-
`api_domain` | api domain | string (e.g. [Hakatime](https://github.com/mujx/hakatime) or [Wakapi](https://github.com/muety/wakapi)) | `wakatime.com`
`custom_title` | card title | string | `WakaTime Stats`
`display_format` | display format | enum ([formats](#time-formats)) | `time`
`disable_animations` | disable animations | boolean (`false` or `true`) | `false`
`hide` | hide languages | string (comma-separated values) | `null`
`hide_progress` | hide percentages | boolean (`false` or `true`) | `false`
`hide_title` | hide title | boolean (`false` or `true`) | `false`
`langs_count` | languages count | integer (min: `1`) | `null`
`layout` | layout style | enum ([layouts](#time-layouts)) | `default`
`line_height` | Sets the line height between text. | integer | `25`

##### Time Formats

Name | Description
-|-
`percent`|percentage
`time`|time

##### Time Layouts

Name | Description
-|-
`compact`| single horizontal progress bar with all languages
`default`| horizontal progress bar for each language

***

# Pins Card

Both extra and gist pins are allowed in profile `README.md` files to pin more than 6 repositories and gists.

## Extra

```md
![Extra Card](https://github-readme-statistics.vercel.app/api/pin/?username=USERNAME&repo=REPOSITORY)
```

Default Layout | With Owner
-|-
![Readme Card Default Layout](https://github-readme-statistics-main.vercel.app/api/pin/?username=theck13&repo=github-readme-statistics)|![Readme Card With Owner](https://github-readme-statistics-main.vercel.app/api/pin/?username=theck13&repo=github-readme-statistics&show_owner=true)

## Gist

```md
![Gist Card](https://github-readme-statistics.vercel.app/api/gist?id=HASH)
```

Default Layout | With Owner
-|-
![Gist Card](https://github-readme-statistics-main.vercel.app/api/gist?id=211627)|![Gist Card](https://github-readme-statistics-main.vercel.app/api/gist?id=211627\&show_owner=true)

***

# Languages Card

The top languages card shows a GitHub user's most frequently used languages.

> [!WARNING]\
> The language card only shows languages from public repositories.  To include languages used in private repositories, [deploy your instance](#deploy-your-instance) using your own GitHub API token.

> [!WARNING]\
> The language card only shows usage inside your own non-forked repositories, not depending on who the author of the commits.  It does not include your contributions into another users/organizations repositories.  Currently, there is no way to get that data from the GitHub API.  If you want that behavior to be improved, you can support [this feature request](https://github.com/orgs/community/discussions/18230) created by [@rickstaa](https://github.com/rickstaa) inside the GitHub Community.

> [!WARNING]\
> The language card only shows data only about first 100 repositories because of GitHub API limitations which cause downtimes of public instances (see [#1471](https://github.com/anuraghazra/github-readme-stats/issues/1471)).  In the future, this behavior will be improved by releasing GitHub actions or providing environment variables for users' own instances.

> [!NOTE]\
> The number and type of languages does not indicate the user's skill level.  It's a metric to determine which languages have the most code on GitHub.

```md
![Languages Card](https://github-readme-statistics.vercel.app/api/top-langs/?username=USERNAME)
```

![Languages Card](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13)

## Language Percentage Algorithm

The following algorithm is used to calculate the percentages on the language card.

```js
ranking_index = (byte_count ^ size_weight) * (repo_count ^ count_weight)
```

Only the byte count is used for determining the percentages shown on the language card by default (i.e. `count_weight=0` and `size_weight=1`).  The `count_weight` and `size_weight` options with positive, real number values can be used to weight the language calculation.  More details about the algorithm can be found [here](https://github.com/anuraghazra/github-readme-stats/issues/1600#issuecomment-1046056305).

Example | Description
-|-
`&count_weight=0&size_weight=1` | ordered by byte count only (default)
`&count_weight=0.5&size_weight=0.5` | uses both byte and repository count (recommended)
`&count_weight=1&size_weight=0` | ordered by repository count only

```md
![Languages Card With Weights](https://github-readme-statistics.vercel.app/api/top-langs/?username=USERNAME&count_weight=0.5&size_weight=0.5)
```

![Languages Card With Weights](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13&count_weight=0.5&size_weight=0.5)

## Exclude Default Repositories

Default repositories can be excluded with the `exclude_repo` query parameter using comma-separated values.

```md
![Languages Card Excluding Repositories](https://github-readme-statistics.vercel.app/api/top-langs/?username=USERNAME&exclude_repo=github-readme-statistics,USERNAME.github.io)
```

## Hide Default Languages

Default languages can be hidden with the `hide` query parameter using comma-separated values.

```md
![Languages Card Hiding Languages](https://github-readme-statistics.vercel.app/api/top-langs/?username=USERNAME&hide=html,javascript)
```

## Show Extra Languages

Extra languages can be shown with the `langs_count` query parameter using an interger value between 1 and 20 inclusive.  The default values are `5` for `normal` and `donut` layouts and `6` for others.

```md
![Languages Card Showing Languages](https://github-readme-statistics.vercel.app/api/top-langs/?username=USERNAME&langs_count=8)
```

## Hide Progress Bars

The progress bars can be hidden with the `hide_progress` query parameters and the `true` value, which will also set the layout to [`compact`](#compact-layout) automatically.

```md
![Languages Card Hide Progress](https://github-readme-statistics.vercel.app/api/top-langs/?username=USERNAME&hide_progress=true)
```

### Compact Layout

The compact layout can be used with the `layout` query parameter and `compact` value.

```md
![Languages Card Compact Layout](https://github-readme-statistics.vercel.app/api/top-langs/?username=USERNAME&layout=compact)
```

### Donut Layout

The donut layout can be used in [horizontal](#horizontal) and [vertical](#vertical) variations.

#### Horizontal

The horizontal donut layout can be used with the `layout` query parameter and `donut` value.

```md
![Languages Card Donut Horizontal](https://github-readme-statistics.vercel.app/api/top-langs/?username=USERNAME&layout=donut)
```

#### Vertical

The vertical donut layout can be used with the `layout` query parameter and `donut-vertical` value.

```md
![Languages Card Donut Vertical](https://github-readme-statistics.vercel.app/api/top-langs/?username=USERNAME&layout=donut-vertical)
```

### Pie Layout

The pie layout can be used with the `layout` query parameter and `pie` value.

```md
![Languages Card Pie Layout](https://github-readme-statistics.vercel.app/api/top-langs/?username=USERNAME&layout=pie)
```

## Layout Comparisons

Layout | Example
-|-
Default | ![Languages Card Default Layout](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13)
Hide Progress | ![Languages Card Hide Progress](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13&hide_progress=true)
Compact | ![Languages Card Compact Layout](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13&layout=compact)
Donut Horizontal | ![Languages Card Donut Horizontal](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13&layout=donut)
Donut Vertical | ![Languages Card Donut Horizontal](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13&layout=donut-vertical)
Pie | ![Languages Card Donut Horizontal](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13&layout=pie)

# Times Card

The times card uses the `wakatime` path with the `username` query parameter and your [WakaTime](https://wakatime.com) username for the value.

```md
![Times Card](https://github-readme-statistics.vercel.app/api/wakatime?username=USERNAME)]
```

> [!WARNING]\
> Only data from WakaTime profiles that are public is shown currently.  Therefore, make sure that ***both*** `Display code time publicly` and `Display languages, editors, os, categories publicly` are enabled.

***

# Deploy Your Instance

An instance of the GitHub Readme Statistics can be deployed on [Vercel](#on-vercel) and [other](#on-others) platforms.

## On Vercel

Since the GitHub API only allows 5,000 requests per hour, `https://github-readme-statistics.vercel.app/api` could hit the rate limit and start failing.  To avoid that, host it on your own Vercel server by following the steps below.

> [!NOTE]\
> Since [#58](https://github.com/anuraghazra/github-readme-stats/pull/58), `https://github-readme-statistics.vercel.app/api`  should be able to handle more than 5,000 requests and have fewer issues with downtime.

> [!NOTE]\
> If you are on the [Vercel Pro plan](https://vercel.com/pricing), the [maxDuration](https://vercel.com/docs/concepts/projects/project-configuration#value-definition) value found in the [vercel.json](https://github.com/theck13/github-readme-statistics/blob/master/vercel.json) can be increased when your Vercel instance frequently times out during the card request.  You are advised to keep this value lower than `30` seconds to prevent high memory usage.

1.  [Fork this repository](https://github.com/theck13/github-readme-statistics/fork).
    <kbd>
        <picture>
            <source
                media="(prefers-color-scheme: dark)"
                srcset="https://github.com/user-attachments/assets/ba6f9e09-0a83-4709-889f-9571f1b92cb2"
            />
            <source
                media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
                srcset="https://github.com/user-attachments/assets/4a2b7be0-6170-4d56-aaba-cc231f140de9"
            />
            <img
                alt="Fork This Repository"
                src="https://github.com/user-attachments/assets/ba6f9e09-0a83-4709-889f-9571f1b92cb2"
            />
        </picture>
    </kbd>
2.  Replace `USERNAME` below with your username then go to URL.
    ```
    https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2FUSERNAME%2Fgithub-readme-statistics%2Ftree%2Fvercel&env=PAT_1&envDescription=GitHub+Personal+Access+Token+(no+scopes+required)&envLink=https%3A%2F%2Fgithub.com%2Fsettings%2Ftokens%2Fnew%3Fdescription%3DGitHub%2520Readme%2520Statistics&project-name=github-readme-statistics&repository-name=github-readme-statistics&teamSlug=github-readme-statistics
    ```
3.  Click ***Continue with GitHub*** button.
    <kbd>
        <picture>
            <source
                media="(prefers-color-scheme: dark)"
                srcset="https://github.com/user-attachments/assets/f2bce2b5-6f69-47b8-bf6a-da1497effcf6"
            />
            <source
                media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
                srcset="https://github.com/user-attachments/assets/5e2f2302-5cc5-4648-a7a6-395c6c588307"
            />
            <img
                alt="Continue With GitHub Button"
                src="https://github.com/user-attachments/assets/5e2f2302-5cc5-4648-a7a6-395c6c588307"
            />
        </picture>
    </kbd>
4.  Enter ***Username of Email Address*** and ***Password*** then click ***Sign In*** button in GitHub.
    <kbd>
        <picture>
            <source
                media="(prefers-color-scheme: dark)"
                srcset="https://github.com/user-attachments/assets/f6b4c34a-a89f-4301-9fb8-bb9890ffcda4"
            />
            <source
                media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
                srcset="https://github.com/user-attachments/assets/1ce855e0-fb99-47e7-b487-2183fee4e024"
            />
            <img
                alt="Sign In with GitHub"
                src="https://github.com/user-attachments/assets/f6b4c34a-a89f-4301-9fb8-bb9890ffcda4"
            />
        </picture>
    </kbd>
5.  Click ***Git Scope*** dropdown and ***Add GitHub Account*** option in Vercel.
    <kbd>
        <picture>
            <source
                media="(prefers-color-scheme: dark)"
                srcset="https://github.com/user-attachments/assets/c7f55de9-890f-4334-b50d-57652ae42223"
            />
            <source
                media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
                srcset="https://github.com/user-attachments/assets/171f7d7d-a537-4246-86b0-9a93d185d9f2"
            />
            <img
                alt="Add GitHub Account"
                src="https://github.com/user-attachments/assets/c7f55de9-890f-4334-b50d-57652ae42223"
            />
        </picture>
    </kbd>
6.  Click ***Only Select Repositories*** option, ***Select Repositories*** dropdown, ***USERNAME/github-readme-statistics*** repository where `USERNAME` is your GitHub username, and ***Install*** button in GitHub.
    <kbd>
        <picture>
            <source
                media="(prefers-color-scheme: dark)"
                srcset="https://github.com/user-attachments/assets/4a5f286d-3007-4de7-b0c5-7f1c323637ee"
            />
            <source
                media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
                srcset="https://github.com/user-attachments/assets/a2829e0a-828d-4b53-9d38-ed2e1f1dcc66"
            />
            <img
                alt="Install Vercel on GitHub"
                src="https://github.com/user-attachments/assets/4a5f286d-3007-4de7-b0c5-7f1c323637ee"
            />
        </picture>
    </kbd>
7.  Click ***Create*** button in Vercel.
    <kbd>
        <picture>
            <source
                media="(prefers-color-scheme: dark)"
                srcset="https://github.com/user-attachments/assets/2dc4d9d4-8dfe-49a3-8b03-c9f62739410e"
            />
            <source
                media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
                srcset="https://github.com/user-attachments/assets/ee084a43-4242-4a7c-958d-4ecae2ec5a13"
            />
            <img
                alt="Create Vercel Project"
                src="https://github.com/user-attachments/assets/2dc4d9d4-8dfe-49a3-8b03-c9f62739410e"
            />
        </picture>
    </kbd>
8.  Click ***Learn More*** link in ***Add Environment Variables*** section.
    <kbd>
        <picture>
            <source
                media="(prefers-color-scheme: dark)"
                srcset="https://github.com/user-attachments/assets/f7fbe13f-4726-457a-b031-bfae750e8177"
            />
            <source
                media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
                srcset="https://github.com/user-attachments/assets/81fd03df-1a69-47ab-8e89-8dd6a90834ec"
            />
            <img
                alt="Learn More Link"
                src="https://github.com/user-attachments/assets/f7fbe13f-4726-457a-b031-bfae750e8177"
            />
        </picture>
    </kbd>
9.  Click ***Expiration*** dropdown to select date, ***repo:status***, ***public_repo***, ***read:user***, and ***Generate Token*** button in GitHub.
    <kbd>
        <picture>
            <source
                media="(prefers-color-scheme: dark)"
                srcset="https://github.com/user-attachments/assets/647283dd-ab5d-4d5b-93ae-f282a2bc5c9e"
            />
            <source
                media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
                srcset="https://github.com/user-attachments/assets/23548ff7-1932-4096-9f19-6188573be0c9"
            />
            <img
                alt="Generate GitHub Personal Access Token"
                src="https://github.com/user-attachments/assets/647283dd-ab5d-4d5b-93ae-f282a2bc5c9e"
            />
        </picture>
    </kbd>
10. Copy token in GitHub.
    <kbd>
        <picture>
            <source
                media="(prefers-color-scheme: dark)"
                srcset="https://github.com/user-attachments/assets/c70743e0-b1c9-45a8-b5eb-49711bf3b4dd"
            />
            <source
                media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
                srcset="https://github.com/user-attachments/assets/a089e8f2-ae39-4ced-a14d-bfd4789e4c85"
            />
            <img
                alt="Copy GitHub Personal Access Token"
                src="https://github.com/user-attachments/assets/c70743e0-b1c9-45a8-b5eb-49711bf3b4dd"
            />
        </picture>
    </kbd>
11. Paste token in Vercel.
    <kbd>
        <picture>
            <source
                media="(prefers-color-scheme: dark)"
                srcset="https://github.com/user-attachments/assets/11ff5f3e-6240-44d1-8daa-7379df41e93e"
            />
            <source
                media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
                srcset="https://github.com/user-attachments/assets/413c5331-1407-41c0-b130-01bcacdc28cd"
            />
            <img
                alt="Paste GitHub Personal Access Token"
                src="https://github.com/user-attachments/assets/11ff5f3e-6240-44d1-8daa-7379df41e93e"
            />
        </picture>
    </kbd>
12. Click ***Continue to Dashboard*** button in Vercel.
    <kbd>
        <picture>
            <source
                media="(prefers-color-scheme: dark)"
                srcset="https://github.com/user-attachments/assets/352516e3-8f9b-458b-8723-97e29be30c92"
            />
            <source
                media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
                srcset="https://github.com/user-attachments/assets/3394e2e7-666c-4294-bd3f-ded8c6947e64"
            />
            <img
                alt="Continue to Dashboard"
                src="https://github.com/user-attachments/assets/352516e3-8f9b-458b-8723-97e29be30c92"
            />
        </picture>
    </kbd>
13. Copy domain in Vercel.
    <kbd>
        <picture>
            <source
                media="(prefers-color-scheme: dark)"
                srcset="https://github.com/user-attachments/assets/e28dd27b-08e3-4427-b53a-fdf509f31fe4"
            />
            <source
                media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)"
                srcset="https://github.com/user-attachments/assets/39f551b1-0ddf-4e3c-b4e7-e28565448653"
            />
            <img
                alt="GitHub Readme Statistics Domain"
                src="https://github.com/user-attachments/assets/e28dd27b-08e3-4427-b53a-fdf509f31fe4"
            />
        </picture>
    </kbd>
14. Replace `DOMAIN` with Vercel domain and `USERNAME` with GitHub username.
    ```md
    ![GitHub Readme Statistics](https://DOMAIN/api?username=USERNAME)
    ```

## On Others

> [!WARNING]\
> This way of using GRS is not officially supported and was added to cater to some particular use cases where Vercel could not be used (e.g. [#2341](https://github.com/anuraghazra/github-readme-stats/discussions/2341)).  Therefore, support for this method is limited.

1.  [Fork this repository](https://github.com/theck13/github-readme-statistics/fork).
2.  Add `express` to the [dependencies section of `package.json`](https://github.com/theck13/github-readme-statistics/blob/ba7c2f8b55eac8452e479c8bd38b044d204d0424/package.json#L54-L61).
3.  Run `npm i`.
4.  Run `node express.js` to start the server, or set the [entry point to `express.js` in `package.json`](https://github.com/theck13/github-readme-statistics/blob/ba7c2f8b55eac8452e479c8bd38b044d204d0424/package.json#L11) if deploying on a managed service.

## Disable Rate Limits

Github Readme Stats contains several Vercel environment variables that can be used to remove the rate limit protections:

*   `CACHE_SECONDS`: This environment variable takes precedence over our cache minimum and maximum values and can circumvent these values for self-hosted Vercel instances.

See [the Vercel documentation](https://vercel.com/docs/concepts/projects/environment-variables) on adding these environment variables to your Vercel instance.

## Sync Your Fork

You can keep your fork, and thus your private Vercel instance, up-to-date with the upstream using GitHub's [***Sync Fork*** button](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork).
