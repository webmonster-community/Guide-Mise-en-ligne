
## Sécurité
**Mot de passe**
>S'assurer de la force de tous les mots de passe (minimum 12 caractères). Mettre en place une politique de changement de mot de passe régulier en fonction d'une clef de hachage qui elle aussi devra changer régulièrement.

Techmonster vous propose d'utiliser son générateur de mot de passe

:link: [Générateur de mot de passe](https://techmonster.info/password-generator)

**Permission des fichiers et répertoires**
>Les permissions des fichiers et répertoires est une étape indispensable pour sécuriser votre site Internet. En premier lieu il est important de définir un chmod pour l'ensemble de votre répertoire de site

Utiliser chmod pour définir récursivement les droits 750 à votre répertoire source

`chmod -R 750 /var/www/html/mon-site.com/`

Utiliser chmod pour définir les propriétaires d'un répertoire crée par le serveur, il portera ainsi les propriétés de son parent.

`chmod g+s /var/www/html/mon-site.com/`

Il arrive parfois que vous utilisiez des répertoires d'upload ou de cache. Il faut s'assurer que vous avez des droits spécifiques sur ces répertoires en utilisant encore une fois la commande chmod

`chmod g+w /var/www/httml/mon-site.com/<repertoire>`

