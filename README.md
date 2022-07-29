# MISE EN ROUTE
Checklist des choses à faire pour une mise en ligne de projet web.
---
## Sécurité
**Mot de passe**
>S'assurer de la force de tous les mots de passe (minimum 12 caractères). Mettre en place une politique de changement de mot de passe régulier en fonction d'une clef de hachage qui elle aussi devra changer régulièrement.

:+1: Techmonster vous propose d'utiliser son générateur de mot de passe
[Générateur de mot de passe](https://techmonster.info/password-generator)

**Permission des fichiers et répertoires**
>Les permissions des fichiers et répertoires est une étape indispensable pour sécuriser votre site Internet. En premier lieu il est important de définir un chmod pour l'ensemble de votre répertoire de site

`chmod -R 750 /var/www/my-website.com/`

