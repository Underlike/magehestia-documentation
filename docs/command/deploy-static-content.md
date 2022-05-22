---
sidebar_position: 2
---

# Deploy Static Content

Dans cette documentation nous allons parler de la commande `setup:static-content:deploy` c'est une commande qui va vous servir très souvent dans le développement d'un site Magento 2, elle permet de déployer les assets de votre site internet c'est à dire les fichiers CSS, JS et les images que vous avez pu mettre durant vos développements.

Pour vous en servir il faur simplement taper cette commande :

```bash
bin/magento setup:static-content:deploy -h
```

Vous aurez accès à l'ensemble des arguments disponibles avec cette commande mais également leurs descriptions.

```output
Description:
  Deploys static view files

Usage:
  setup:static-content:deploy [options] [--] [<languages>...]

Arguments:
  languages                                      Space-separated list of ISO-639 language codes for which to output static view files.

Options:
  -f, --force                                    Deploy files in any mode.
  -s, --strategy[=STRATEGY]                      Deploy files using specified strategy. [default: "quick"]
  -a, --area[=AREA]                              Generate files only for the specified areas. [default: ["all"]] (multiple values allowed)
      --exclude-area[=EXCLUDE-AREA]              Do not generate files for the specified areas. [default: ["none"]] (multiple values allowed)
  -t, --theme[=THEME]                            Generate static view files for only the specified themes. [default: ["all"]] (multiple values allowed)
      --exclude-theme[=EXCLUDE-THEME]            Do not generate files for the specified themes. [default: ["none"]] (multiple values allowed)
  -l, --language[=LANGUAGE]                      Generate files only for the specified languages. [default: ["all"]] (multiple values allowed)
      --exclude-language[=EXCLUDE-LANGUAGE]      Do not generate files for the specified languages. [default: ["none"]] (multiple values allowed)
  -j, --jobs[=JOBS]                              Enable parallel processing using the specified number of jobs. [default: 0]
      --max-execution-time[=MAX-EXECUTION-TIME]  The maximum expected execution time of deployment static process (in seconds). [default: 900]
      --symlink-locale                           Create symlinks for the files of those locales, which are passed for deployment, but have no customizations.
      --content-version=CONTENT-VERSION          Custom version of static content can be used if running deployment on multiple nodes to ensure that static content version is identical and caching works properly.
      --refresh-content-version-only             Refreshing the version of static content only can be used to refresh static content in browser cache and CDN cache.
      --no-javascript                            Do not deploy JavaScript files.
      --no-js-bundle                             Do not deploy JavaScript bundle files.
      --no-css                                   Do not deploy CSS files.
      --no-less                                  Do not deploy LESS files.
      --no-images                                Do not deploy images.
      --no-fonts                                 Do not deploy font files.
      --no-html                                  Do not deploy HTML files.
      --no-misc                                  Do not deploy files of other types (.md, .jbf, .csv, etc.).
      --no-html-minify                           Do not minify HTML files.
      --no-parent                                Do not compile parent themes. Supported only in quick and standard strategies.
  -h, --help                                     Display this help message
  -q, --quiet                                    Do not output any message
  -V, --version                                  Display this application version
      --ansi                                     Force ANSI output
      --no-ansi                                  Disable ANSI output
  -n, --no-interaction                           Do not ask any interactive question
  -v|vv|vvv, --verbose                           Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug
```

Vous pouvez également raccourcir la commande, ça c'est une petite astuce de ma part :)

```bash
bin/magento set:st:dep -h
```

Voilà vous savez comment déployer vos assets sur votre site Magento 2.