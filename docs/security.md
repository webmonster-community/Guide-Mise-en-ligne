
## Sécurité
**Mot de passe**
>S'assurer de la force de tous les mots de passe (minimum 12 caractères). Mettre en place une politique de changement de mot de passe régulier en fonction d'une clef de hachage qui elle aussi devra changer régulièrement.

[**Techmonster**](https://techmonster.info) vous propose d'utiliser son générateur de mot de passe

:link: [Générateur de mot de passe](https://techmonster.info/password-generator)

**Générateur passphrase**
> Pour le hashage de vos mots de passe il est important d'utiliser une clef de hash
> 
:link: [Générateur de passphrase](https://techmonster.info/passphrase-generator)


**Permission des fichiers et répertoires**
>Les permissions des fichiers et répertoires est une étape indispensable pour sécuriser votre site Internet. En premier lieu il est important de définir un chmod pour l'ensemble de votre répertoire de site

Utiliser chmod pour définir récursivement les droits 750 à votre répertoire source

`chmod -R 750 /var/www/html/mon-site.com/`

Utiliser chmod pour définir les propriétaires d'un répertoire crée par le serveur, il portera ainsi les propriétés de son parent.

`chmod g+s /var/www/html/mon-site.com/`

Il arrive parfois que vous utilisiez des répertoires d'upload ou de cache. Il faut s'assurer que vous avez des droits spécifiques sur ces répertoires en utilisant encore une fois la commande chmod

`chmod g+w /var/www/httml/mon-site.com/<repertoire>`

````
Si vous utilisez Wordpress, il faudra changer les permissions de votre fichier wp-config.php
````

`chmod -v 660 /var/www/httml/mon-site.com/wp-config.php`


**Cacher les backend/admin**
> Pour des raisons de sécurité évidentes il est important de masquer l'administration, des robots ou de personnes malveillantes

### Etape 1 - Changer le nom du répertoire
> Pour masquer le répertoire de votre backend/admin la méthode la plus rapide serait de renommer ce répertoire pour qu'il devienne impossible à repérer. Nous allons donc éviter adm, admin, administration, administrator, root, webroot, back, backend, backoffice...
> Vous pouvez par exemple renommer le répertoire ou les routes en 9a7d2m1 dans la console.

`# mv admin 9a7d2m1`

### Etape 2 - Empecher l'indexation
> Pour empecher l'indexation, nous vous donnons la méthode pour Apache et Nginx

**Nginx**
`location ~ .*/(?:archive|filter|topic)/.* {
    add_header X-Robots-Tag "noindex, follow" always;      
}`
