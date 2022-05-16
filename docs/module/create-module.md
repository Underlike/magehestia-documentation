---
sidebar_position: 1
---

# Créer un module

Dans cette documentation nous allons voir ensemble comment créer un nouveau module Magento 2.

## Sommaire

Pour créer un module Magento 2 nous allons suivre les étapes ci-dessous :

- Etape N°1 - Créer un dossier pour notre module
- Etape N°2 - Créer le fichier `etc/module.xml`
- Etape N°3 - Créer le fichier `registration.php`
- Etape N°4 - Activer le module

## Etape N°1 - Créer un dossier pour notre module

Le nom du dossier est définis comme ceci **Vendor_Module**. La première partie du nom du module est en général le nom de l'organisation qui le développe et la deuxième partie est le nom du module. Ce qui donne le résultat suivant :

```file
app/code/Magehestia/Hello
```

## Etape N°2 - Créer le fichier etc/module.xml

Il faut par la suite créer le fichier `etc/module.xml` c'est l'un des deux fichiers qui déclare notre module. C'est également ce fichier qui va nous permettre de gérer par la suite la version de notre module.

```file
app/code/Magehestia/Hello/etc/module.xml
```

Et vous pouvez copier coller le contenu de ce fichier ci-dessous :

```xml title="etc/module.xml"
<?xml version="1.0"?>
<config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:Module/etc/module.xsd">
    <module name="Magehestia_Hello" setup_version="1.0.0">
    </module>
</config>
```

## Etape N°3 - Créer le fichier registration.php

Pour déclarer notre module il nous faut un deuxième fichier qui est le fichier `registration.php`. 

```file
app/code/Magehestia/Hello/registration.php
```

Idem que pour le fichier `etc/module.xml` vous pouvez copier-coller le contenu du fichier ci-dessous :

```php title="registration.php"
<?php

use Magento\Framework\Component\ComponentRegistrar;

ComponentRegistrar::register(
    ComponentRegistrar::MODULE,
    'Magehestia_Hello',
    __DIR__
);
```

## Etape N°4 - Activer le module

Et pour finir nous allons activer notre nouveau module en exécutant la commande suivante : 

```bash
bin/magento module:enable Magehestia_Hello
```

Vous allez pouvoir voir si vous êtes curieux qu'une nouvelle ligne est ajouté dans le fichier `app/etc/config.php`il s'agît de notre module.

```code title="app/etc/config.php"
...
'Magehestia_Hello' => 1, 
...
```

Pour finaliser l'installation il faut exécuter la commande setup:upgrade de Magento et déployer vos assets car le **setup:upgrade** les supprimes.

```bash
bin/magento setup:upgrade
bin/magento bin/magento setup:static-content:deploy -f
```

Voilà nous avons un nouveau module tout beau !