<p align="center">
 <img width="100px" src="https://res.cloudinary.com/theck13/image/upload/v1594908242/logo_ccswme.svg" align="center" alt="GitHub Readme Stats" />
 <h2 align="center">GitHub Readme Stats</h2>
 <p align="center">Krijg dynamisch gegenereerde GitHub statistieken op je readme's!</p>
</p>
  <p align="center">
    <a href="https://github.com/theck13/github-readme-statistics/actions">
      <img alt="Tests Passing" src="https://github.com/theck13/github-readme-statistics/workflows/Test/badge.svg" />
    </a>
    <a href="https://github.com/theck13/github-readme-statistics/graphs/contributors">
      <img alt="GitHub Contributors" src="https://img.shields.io/github/contributors/theck13/github-readme-statistics" />
    </a>
    <a href="https://codecov.io/gh/theck13/github-readme-statistics">
      <img alt="Tests Coverage" src="https://codecov.io/gh/theck13/github-readme-statistics/branch/master/graph/badge.svg" />
    </a>
    <a href="https://github.com/theck13/github-readme-statistics/issues">
      <img alt="Issues" src="https://img.shields.io/github/issues/theck13/github-readme-statistics?color=0088ff" />
    </a>
    <a href="https://github.com/theck13/github-readme-statistics/pulls">
      <img alt="GitHub pull requests" src="https://img.shields.io/github/issues-pr/theck13/github-readme-statistics?color=0088ff" />
    </a>
    <a href="https://securityscorecards.dev/viewer/?uri=github.com/theck13/github-readme-statistics">
      <img alt="OpenSSF Scorecard" src="https://api.securityscorecards.dev/projects/github.com/theck13/github-readme-statistics/badge" />
    </a>
    <br />
    <br />
  </p>

  <p align="center">
    <a href="#demo">Bekijk Demo</a>
    ·
    <a href="https://github.com/theck13/github-readme-statistics/issues/new?assignees=&labels=bug&projects=&template=bug_report.yml">Rapporteer een Bug</a>
    ·
    <a href="https://github.com/theck13/github-readme-statistics/issues/new?assignees=&labels=enhancement&projects=&template=feature_request.yml">Vraag een nieuwe toepassing aan</a>
  </p>
  <p align="center">
    <a href="/docs/readme_fr.md">Français </a>
    ·
    <a href="/docs/readme_cn.md">简体中文</a>
    ·
    <a href="/docs/readme_es.md">Español</a>
    ·
    <a href="/docs/readme_de.md">Deutsch</a>
    ·
    <a href="/docs/readme_ja.md">日本語</a>
    ·
    <a href="/docs/readme_pt-BR.md">Português Brasileiro</a>
    ·
    <a href="/docs/readme_it.md">Italiano</a>
    ·
    <a href="/docs/readme_kr.md">한국어</a>
    .
    <a href="/docs/readme_nl.md">Nederlands</a>
    .
    <a href="/docs/readme_np.md">नेपाली</a>
    .
    <a href="/docs/readme_tr.md">Türkçe</a>
  </p>
</p>
<p align="center">Bevalt het project? <a href="https://www.paypal.me/theck13">Doneer</a> om het te verbeteren!

# Functionaliteiten <!-- omit in toc -->

- [GitHub Statistieken Kaart](#github-statistieken-kaart)
    - [Verberg individueele statistieken](#verberg-individueele-statistieken)
    - [Voeg privé contributies toe aan totale commits.](#voeg-privé-contributies-toe-aan-totale-commits)
    - [Laat icoontjes zien](#laat-icoontjes-zien)
    - [Thema's](#themas)
    - [Opmaak](#opmaak)
- [GitHub Extra Pins](#github-extra-pins)
    - [Gebruik](#gebruik)
    - [Demo](#demo)
- [Top Programmeertalen Kaart](#top-programmeertalen-kaart)
    - [Gebruik](#gebruik-1)
    - [Verberg individueele repositories](#verberg-individueele-repositories)
    - [Verberg individueele talen](#verberg-individueele-talen)
    - [Laat meer programmeertalen zien](#laat-meer-programmeertalen-zien)
    - [Compacte Talen Kaart opmaak](#compacte-talen-kaart-opmaak)
    - [Demo](#demo-1)
- [Wekelijkse WakaTime Statistieken](#wekelijkse-wakatime-statistieken)
    - [Demo](#demo-2)
    - [Alle demos](#alle-demos)
    - [Kleine tip (Verstel de repo kaart z'n positie)](#kleine-tip-verstel-de-repo-kaart-zn-positie)
  - [Deploy je eigen Vercel instatie](#deploy-je-eigen-vercel-instatie)
  - [:sparkling\_heart: Ondersteun het project](#sparkling_heart-ondersteun-het-project)

# GitHub Statistieken Kaart

Kopieer en plak dit in je markdown content, zo simpel is het!

Verander de waarde `?username=` naar jou gebruikersnaam.

```md
[![Tyler Heck's GitHub Statistics](https://github-readme-statistics-main.vercel.app/api?username=theck13)](https://github.com/theck13/github-readme-statistics)
```

_Notitie: Beschikbare rangen zijn S+ (top 1%), S (top 25%), A++ (top 45%), A+ (top 60%), and B+ (iedereen).
De waarden worden berekend met behulp van de zogeheten [cumulative distribution function](https://en.wikipedia.org/wiki/Cumulative_distribution_function) met de waardes van de commits, bijdragens, issues, sterren, PR's, volgers en eigen repositories.
De implementatie hiervan kan bekijken op [src/calculateRank.js](../src/calculateRank.js)_

### Verberg individueele statistieken

Om specifieke statistieken te verbergen, kan je een `?hide=` query parameter toevogen, verdeeld met komma\'s.


> Opties: `&hide=stars,commits,prs,issues,contribs`

```md
![Tyler Heck's GitHub Statistics](https://github-readme-statistics-main.vercel.app/api?username=theck13&hide=contribs,prs)
```

### Voeg privé contributies toe aan totale commits.

Je kan de hoeveelheid privé commits toevoegen aan je totale hoeveelheid commits door de query parameter `?count_private=true` te gebruiken.

_Notitie: Als je dit project zelf deployt, zullen de privé contributies standaard toegevoegt worden aan je totaal, omdat anders je hoeveelheid privé contributies moet delen._

> Opties: `&count_private=true`

```md
![Tyler Heck's GitHub Statistics](https://github-readme-statistics-main.vercel.app/api?username=theck13&count_private=true)
```

### Laat icoontjes zien

Om icoontjes te gebruiken kan je `show_icons=true` gebruiken in de query parameter, zoals hier:

```md
![Tyler Heck's GitHub Statistics](https://github-readme-statistics-main.vercel.app/api?username=theck13&show_icons=true)
```

### Thema\'s

Met ingebouwde thema\'s kan je het uiterlijk van de kaart aanpassen zonder enige [handmatige opmaak](#customization).

Gebruik `?theme=THEME_NAME` parameters zo :-

```md
![Tyler Heck's GitHub Statistics](https://github-readme-statistics-main.vercel.app/api?username=theck13&show_icons=true&theme=radical)
```

#### Alle ingeboude thema\'s :-

dark, radical, merko, gruvbox, tokyonight, onedark, cobalt, synthwave, highcontrast, dracula

<img src="https://res.cloudinary.com/theck13/image/upload/v1595174536/grs-themes_l4ynja.png" alt="GitHub Readme Statestieken Thema's" width="600px"/>

Je kan een preview van alle [beschikbare thema\'s](../themes/README.md) bekijken, of zie het [thema configuratie bestand](../themes/index.js) en **je kan aan nieuwe thema\'s bijdragen** als je dat leuk lijkt :D

### Opmaak

Je kan het uiterlijk van je `Statistieken kaart` of `Repo kaart` aanpassen hoe je ook maar wilt met URL parameters.

#### Veel gebruikte opties:

- `title_color` - De kleur van de titel van de kaart _(hex kleur)_
- `text_color` - Tekst kleur _(hex kleur)_
- `icon_color` - Icoon kleuren, wanneer beschikbaar _(hex kleur)_
- `bg_color` - Achtergrond kleur van de kaart _(hex kleur)_ **of** een verloop van kleuren in het formaat van _graden,start,einde_
- `hide_border` - Verbergt de rand van de kaart _(boolean)_
- `theme` - Naam van het thema, kies uit [alle beschikbare thema\'s](../themes/README.md)
- `cache_seconds` - Stel de cache header handmatig in _(min: 14400, max: 86400)_
- `locale` - Stel taal van de kaart in _(e.g. cn, de, es, etc.)_

##### Kleurenverloop in bg_color (achtergrond kleur):

Je kan meerdere komma verdeelde waarden in de bg_color optie geven om een kleurenverloop te creeëren, het formaat van het kleurenverloop is:-

```
&bg_color=GRADEN,KLEUR1,KLEUR2,KLEUR3...KLEUR10
```

> Notities i.v.b.m. cache: Repo kaarten hebben een standaard cache van 4 uur (14400 seconden) als de fork hoeveelheid en de star hoeveelheid minder is dan 1k, anders is het 2 uur (7200 seconden). Daarnaast ligt de cache vast aan een minimum van 2 uur en een maximum van 24 uur.

#### Exclusieve opties voor Statistieken Kaart:

- `hide` - Verbergt gespecificeerde items van de statistieken. _(komma gescheiden waardes)_
- `hide_title` - _(boolean)_
- `hide_rank` - _(boolean)_
- `show_icons` - _(boolean)_
- `include_all_commits` - Tel alle commits inplaats van alleen de commits van het huidige jaar _(boolean)_
- `count_private` - Tel privé commits mee _(boolean)_
- `line_height` - Stel de lijn-hoogte tussen text in _(nummer)_
- `custom_title` - Stel een aangepaste titel voor je kaart in

#### Exclusieve opties voor Repo Kaart:

- `show_owner` - Laat de eigenaar van de repo zien _(boolean)_

#### Exclusieve opties voor Programmeertaal Kaart:

- `hide` - Verbergt specifieke talen van de kaart _(komma gescheiden waardes)_
- `hide_title` - _(boolean)_
- `layout` - Kies uit de vijf beschikbare lay-outs `normal` & `compact` & `donut` & `donut-vertical` & `pie`
- `card_width` - Stelt de breedte van de kaart handmatig in. _(nummer)_
- `langs_count` - Laat meer talen op de kaart zien, waarde tussen 1-10, staat standaard op to 5 _(nummer)_
- `exclude_repo` - Verbergt specifieke repositories _(komma gescheiden waardes)_
- `custom_title` - Stelt een eigen titel voor de kaart in

> :Waarschuwing: **Belangrijk:**
> Namen van programmeertalen moeten worden geuri-escaped, zoals gespecificeerd in [Percent Encoding](https://en.wikipedia.org/wiki/Percent-encoding)
> (Oftewel: `c++` moet `c%2B%2B` worden, `jupyter notebook` moet `jupyter%20notebook` worden, enzovoort...)
> Zie [urlencoder.org](https://www.urlencoder.org/) om dit automatisch te doen.

#### Exclusieve opties voor WakaTime Kaart:

- `hide_title` - _(boolean)_
- `line_height` - Verandert de lijn hoogte tussen tekst _(nummer)_
- `hide_progress` - Verbergt de progressiebalk en het percentage _(boolean)_
- `custom_title` - Stelt een eigen titel voor de kaart in
- `layout` - Schakel tussen de twee beschikbare lay-outs `default` en `compact`

---

# GitHub Extra Pins

GitHub extra pins geven je de mogelijkheid om meer dan 6 repositories op je profiel te pinnen, doormiddel van een GitHub readme profile.

Joepie! Je bent niet langer aan 6 pins gelimiteerd!

### Gebruik

Kopieer en plak deze code in je readme en verander de links.

Eindpunt: `api/pin?username=theck13&repo=github-readme-statistics`

```md
[![Readme Card](https://github-readme-statistics-main.vercel.app/api/pin/?username=theck13&repo=github-readme-statistics)](https://github.com/theck13/github-readme-statistics)
```

### Demo

[![Readme Card](https://github-readme-statistics-main.vercel.app/api/pin/?username=theck13&repo=github-readme-statistics)](https://github.com/theck13/github-readme-statistics)

Gebruikt [show_owner](#customization) variabele om de repo\'s eigenaar toe te voegen

[![Readme Card](https://github-readme-statistics-main.vercel.app/api/pin/?username=theck13&repo=github-readme-statistics&show_owner=true)](https://github.com/theck13/github-readme-statistics)

# Top Programmeertalen Kaart

De top programmeertalen kaart laat zien welke talen een GitHub gebruiker het meest gebruikt.

_Notitie: Top programmeertalen wijzen niet op een vaardigheids niveau, het is puur een GitHub metriek over welke talen de meeste code op GitHub hebben. Het is een nieuwe funktie van github-readme-statistics._

### Gebruik

Kopieer en plak deze code in je readme en verander de links.


Eindpunt: `api/top-langs?username=theck13`

```md
[![Top Talen](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13)](https://github.com/theck13/github-readme-statistics)
```

### Verberg individueele repositories

Je kan de parameter `?exclude_repo=repo1,repo2` gebruiken om individueele repositories te verbergen.

```md
[![Top Talen](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13&exclude_repo=github-readme-statistics,theck13.github.io)](https://github.com/theck13/github-readme-statistics)
```

### Verberg individueele talen

Je kan de `?hide=taal1,taal2` parameter gebruiken om individuele programmeer talen te verbergen.

```md
[![Top Talen](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13&hide=javascript,html)](https://github.com/theck13/github-readme-statistics)
```

### Laat meer programmeertalen zien

Je kan de `&langs_count=` optie gebruiken om de hoeveelheid talen op je kaart groter en kleiner te maken. Geldige waardes zijn tussen de 1 en 10 (inclusief), en de standaard waarde is 5.

```md
[![Top Langs](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13&langs_count=8)](https://github.com/theck13/github-readme-statistics)
```

### Compacte Talen Kaart opmaak

Je kan de `&layout=compact` optie gebruiken om het kaart ontwerp aan te passen.

```md
[![Top Langs](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13&layout=compact)](https://github.com/theck13/github-readme-statistics)
```

### Demo

[![Top programmeertalen](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13)](https://github.com/theck13/github-readme-statistics)

- Compacte opmaak

[![Top programmeertalen](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13&layout=compact)](https://github.com/theck13/github-readme-statistics)

# Wekelijkse WakaTime Statistieken

Verander de `?username=` waarde naar je [WakaTime](https://wakatime.com) gebruikersnaam.

```md
[![Harlok's WakaTime stats](https://github-readme-statistics-main.vercel.app/api/wakatime?username=ffflabs)](https://github.com/theck13/github-readme-statistics)
```

### Demo

[![Harlok's WakaTime stats](https://github-readme-statistics-main.vercel.app/api/wakatime?username=ffflabs)](https://github.com/theck13/github-readme-statistics)

[![Harlok's WakaTime stats](https://github-readme-statistics-main.vercel.app/api/wakatime?username=ffflabs&hide_progress=true)](https://github.com/theck13/github-readme-statistics)

---

### Alle demos

- Standaard

![Tyler Heck's GitHub Statistics](https://github-readme-statistics-main.vercel.app/api?username=theck13)

- Verberg specifieke statestieken

![Tyler Heck's GitHub Statistics](https://github-readme-statistics-main.vercel.app/api?username=theck13&hide=contribs,issues)

- Weergeef icoontjes

![Tyler Heck's GitHub Statistics](https://github-readme-statistics-main.vercel.app/api?username=theck13&hide=issues&show_icons=true)

- Voeg alle commits toe

![Tyler Heck's GitHub Statistics](https://github-readme-statistics-main.vercel.app/api?username=theck13&include_all_commits=true)

- Thema\'s

Kies uit de [standaard thema\'s](#themes)

![Tyler Heck's GitHub Statistics](https://github-readme-statistics-main.vercel.app/api?username=theck13&show_icons=true&theme=radical)

- Kleurenverloop

![Tyler Heck's GitHub Statistics](https://github-readme-statistics-main.vercel.app/api?username=theck13&bg_color=30,e96443,904e95&title_color=fff&text_color=fff)

- Pas statistieken kaart aan

![Tyler Heck's GitHub Statistics](https://github-readme-statistics-main.vercel.app/api/?username=theck13&show_icons=true&title_color=fff&icon_color=79ff97&text_color=9f9f9f&bg_color=151515)

- Stel je kaart locale (taal) in

![Tyler Heck's GitHub Statistics](https://github-readme-statistics-main.vercel.app/api/?username=theck13&locale=es)

- Pas repo kaart aan.

![Customized Card](https://github-readme-statistics-main.vercel.app/api/pin?username=theck13&repo=github-readme-statistics&title_color=fff&icon_color=f9f9f9&text_color=9f9f9f&bg_color=151515)

- Top programmeertalen

[![Top Programmeertalen](https://github-readme-statistics-main.vercel.app/api/top-langs/?username=theck13)](https://github.com/theck13/github-readme-statistics)

- WakaTime kaart

[![Harlok's WakaTime stats](https://github-readme-statistics-main.vercel.app/api/wakatime?username=ffflabs)](https://github.com/theck13/github-readme-statistics)

---

### Kleine tip (Verstel de repo kaart z\'n positie)

Meestal kan je de afbeeldingen niet naast elkaar zetten, op deze manier wel:

```html
<a href="https://github.com/theck13/github-readme-statistics">
  <img align="center" src="https://github-readme-statistics-main.vercel.app/api/pin/?username=theck13&repo=github-readme-statistics" />
</a>
<a href="https://github.com/theck13/convoychat">
  <img align="center" src="https://github-readme-statistics-main.vercel.app/api/pin/?username=theck13&repo=convoychat" />
</a>
```

## Deploy je eigen Vercel instatie

#### [Check de stapsgewijze video tutorial door @codeSTACKr (In het Engels)](https://youtu.be/n6d4KHSKqGk?t=107)

Sinds de GitHub API alleen maar 5k verzoeken per uur toestaat, zou mijn `https://github-readme-statistics-main.vercel.app/api` mogelijk de rate limiet behalen. Als je het op je eigen Vercel server host, dan hoef je je nergens zorgen om te maken. Klik op de deploy knop om te beginnen!

NOTITIE: Sinds [#58](https://github.com/theck13/github-readme-statistics/pull/58) zouden we geen problemen meer moeten hebben de 5k verzoeken per uur, en verdere downtime :D

[![Deploy naar Vercel](https://vercel.com/button)](https://vercel.com/import/project?template=https://github.com/theck13/github-readme-statistics)

<details>
 <summary><b>Versel deploy gids:  🔨 </b></summary>

1. Ga naar [vercel.com](https://vercel.com/)
2. Klik op `Log in`
   ![](https://files.catbox.moe/tct1wg.png)
3. Meld je aan met GitHub door op `Continue with GitHub` te klikken.
   ![](https://files.catbox.moe/btd78j.jpeg)
4. Log in op GitHub en sta toegang tot alle repositories toe, wanneer dat gevraagt wordt.
5. Fork deze repo
6. Ga terug naar je [Vercel dashboard](https://vercel.com/dashboard)
7. Selecteer `Import Project`
   ![](https://files.catbox.moe/qckos0.png)
8. Selecteer `Import Git Repository`
   ![](https://files.catbox.moe/pqub9q.png)
9. Selecteer root en hou alles zoals het is, voeg alleen je environment variable genaamd PAT_1 toe (Zoals hier late zien word), die beheert over een persoonlijke toegangs token (PAT), die je gemakklijk [hier](https://github.com/settings/tokens/new) gemakkelijk kan creeëren. (Laat alles zoals het is, noem het maar iets, mag alles zijn.)
   ![](https://files.catbox.moe/0ez4g7.png)
10. Klik deploy, en alles zou moeten werken. Zie je domein om de api te gebruiken!

</details>

## :sparkling_heart: Ondersteun het project

Ik maak bijna alles open-source wat ik kan, en ik probeer iedereen te helpen die deze projecten gebruiken. Natuurlijk kost dit tijd, je mag deze services gratis gebruiken.

Hoe dan ook, als je dit project gebruikt en er blij mee bent, of mij wilt aanmoedigen om dingen te blijven maken, zijn er een paar manieren om dit te doen; -

- Credits geven aan github-readme-statistics op je readme, die terug naar het project linkt :D
- Sterren en delen van het project :rocket:
- [![paypal.me/theck13](https://ionicabizau.github.io/badges/paypal.svg)](https://www.paypal.me/theck13) - Je kan eenmalig giften via PayPal, ik koop er waarschijnlijk ~~koffie~~ thee van. :tea:

Bedankt! :heart:

---

[![https://vercel.com?utm_source=github_readme_stats_team&utm_campaign=oss](../powered-by-vercel.svg)](https://vercel.com?utm_source=github_readme_stats_team&utm_campaign=oss)

Contributies zijn welkom! <3

Gemaakt met :heart: en JavaScript.
