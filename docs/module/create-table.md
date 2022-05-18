---
sidebar_position: 3
---

# Créer une table de données

Dans cette documentation nous allons voir ensemble comment créer une nouvelle table dans la base de données avec un module Magento 2.

## Sommaire

Pour créer une nouvelle table dans la base de données Magento 2 nous allons suivre les étapes ci-dessous :
- Etape N°1 : Créer le fichier etc/db_schema.xml
- Etape N°2 : Actualiser la base de données

## Etape N°1 : Créer le fichier etc/db_schema.xml

Afin de pouvoir ajouter une table dans la base de données Magento ou même en modifier une existante vous allez pouvoir utiliser le fichier `etc/db_schema.xml` pour réaliser cette action. Dans ce tutoriel nous allons voir ensemble la création d'une nouvelle table.

```file
app/code/Magehestia/Hello/etc/db_schema.xml
```

Le contenu de ce fichier est disponible ci-dessous, dans le cas présent nous allons juste créer une table avec un **hello_id**, un **hello_text**, un **hello_date** pour l'exemple.

```xml title="etc/db_schema.xml"
<?xml version="1.0" ?>
<schema xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:Setup/Declaration/Schema/etc/schema.xsd">
    <table comment="Magehestia Hello Table" engine="innodb" name="magehestia_hello" resource="default">
        <!-- Déclaration des champs de la table -->
        <column xsi:type="int" name="hello_id" unsigned="true" nullable="false" identity="false" default="0" comment="Hello ID"/>		
        <column xsi:type="varchar" name="hello_text" nullable="true" length="255" comment="Hello Text"/>
        <column xsi:type="timestamp" name="hello_date" comment="Hello Date"/>

        <!-- Déclaration du ou des champs avec des "constraint" -->
        <constraint referenceId="PRIMARY" xsi:type="primary">
			<column name="entity_id"/>
		</constraint>
    </table>
</schema>
```

## Etape N°2 : Actualiser la base de données

Maintenant que notre fichier est créé il faut tout simplement exécuter la commande ci-dessous pour créer la table dans la base de données.

```bash
bin/magento setup:upgrade
```

C'est une des manières de faire pour ajouter une table dans la base de données Magento et c'est pour moi la plus simple, cependant cette méthode n'implémente pas les Models dans votre code.
Voilà vous avez ajouté une nouvelle table dans la base de données Magento.