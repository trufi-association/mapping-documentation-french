# Installation de JOSM sous Linux

!!! note ""
	Kokou Elolo AMEGAYIBO - AKEAmazan ([OSM Togo](https://openstreetmap.tg/)) a traduit la page en français. Oeuvre originale de Sören Reinecke ([Trufi Association](https://trufi-association.org))

Aperçu des différentes méthodes d'installation de JOSM sur les systèmes d'exploitation linux graphiques, par exemple les distributions linux basées sur Debian comme Ubuntu, Kubuntu et Debian elle-même, ou sur tout système d'exploitation non Debian disposant de Flatpak.

**Utilisez autant que possible les logithèques et autres interfaces graphiques pour vous rendre service et n'utilisez le terminal/console que s'il est plus facile pour vous de vous en servir plus rapidement.**

## 1. Méthode : Installer en utilisant Flatpak (recommandé)

[Installation à l'aide de Flatpak](https://flathub.org/apps/details/org.openstreetmap.josm) (lien externe) est notre méthode d'installation recommandée qui est la même pour la plupart des variantes de linux. Exécutez la commande

```bash
flatpak install app/org.openstreetmap.josm/x86_64/stable -y
```

ou utiliser la fonctionnalité de résolution automatique de Flatpak :

```bash
flatpak install josm
```

Vous pouvez également utiliser votre logitèque s'il est configuré pour Flatpak.

**Flatpak doit être installé sur votre système pour que cela fonctionne. Nous recommandons à tous les utilisateurs de JOSM d'utiliser cette méthode d'installation car c'est la manière la plus intelligente, la plus sûre et la plus simple d'installer des applications sous Linux. Pensez donc à installer et à configurer Flatpak si vous ne l'avez pas encore fait.**

## 2. Méthode : Utiliser notre script bash

1. Installer en utilisant notre propre script que nous avons écrit avec le support de certains systèmes linux que vous pouvez télécharger. [ici](https://trufi-association.org/installJOSM.sh) (lien externe vers notre site web).
2. Enregistrez-le quelque part sur votre disque, par exemple dans le dossier *Téléchargements*.
3. Identifiez-le comme un fichier exécutable (clic droit sur le fichier --> *Propriétés* --> *Permissions* --> cocher *Autoriser l'exécution du fichier comme un programme* ou similaire)
4. Exécutez-le en tant que super-utilisateur (utilisateur *root*) dans un terminal car votre attention est requise.
4. Après une exécution réussie, vous pouvez supprimer ce script.

## 3. Méthode : Utilisation du système de gestion des paquets (non recommandé)

**Ouvrez un terminal / console et exécutez toutes les commandes suivantes en tant que root**. Notre script d'installation bash exécute ces commandes automatiquement après avoir détecté la méthode d'installation appropriée disponible sur le système.

### Ubuntu, Debian et dérivés

Inscrire le dépôt officiel de JOSM

```bash
echo "deb https://josm.openstreetmap.de/apt alldist universe" > /etc/apt/sources.list.d/josm.list
```
   
et ensuite sa clé publique<br/>
en utilisant `wget`

```bash
wget -q https://josm.openstreetmap.de/josm-apt.key -O- > /etc/apt/trusted.gpg.d/josm.gpg
```

ou en utilisant `curl`

```bash
curl https://josm.openstreetmap.de/josm-apt.key > /etc/apt/trusted.gpg.d/josm.gpg
```

Avant de tenter l'installation, actualisez les sources

```bash
sudo apt update
```

pour pouvoir enfin installer JOSM

```bash
sudo apt install josm
```

### OpenSUSE

Récupérez la version

```bash
version=`cat /etc/os-release | grep "VERSION_ID"`
version=${version/VERSION_ID=/}
version=${version//\"/}
```

et ajouter le dépôt 'Geo'.

```bash
zypper ar -f https://download.opensuse.org/repositories/Application:/Geo/openSUSE_Leap_${version} Application:Geo
```

afin de pouvoir installer JOSM en utilisant

```bash
zypper install josm josm-fonts
```

### Debian

**Utilisez ceci uniquement lorsque les étapes de "Ubuntu, Debian et dérivés" ne fonctionnent pas pour vous.**

Obtenez d'abord le nom de code de votre installation Debian.

```bash
codename=`cat /etc/os-release | grep "VERSION_CODENAME"`
codename=${codename/VERSION_CODENAME=/}
codename=${codename//\"/}
```

pour pouvoir ajouter le bon dépôt de backports

```bash
echo "deb http://deb.debian.org/debian ${codename}-backports main" > /etc/apt/sources.list.d/backports.list
```

Avant de tenter l'installation, actualisez les sources

```bash
apt update
```

et enfin installer JOSM à partir des backports

```bash
apt install josm/${codename}-backports
```

## 4. Méthode : Utiliser la version .jar de JOSM (non recommandé)

Exécuter JOSM sur linux en utilisant son `.jar`. Mais vous devez avoir installé Java si vous ne l'avez pas déjà fait. Nous avons écrit un tutoriel que vous pouvez trouver [ici](./linux-java-jar.md) montrant comment installer Java et comment utiliser un fichier `.jar` en général.

