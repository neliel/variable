---
title: Comment installer une distribution Eclipse
author: Sarfraz
date: April 20, 2013
---

Ce post est destiné aux membres de la Team One, mais peut servir en cas général.

Afin de tirer profit d'un IDE tel qu'Eclipse certaines manipulation sont nécesaires.

1) Télécharger une version d'Eclipse. <http://www.eclipse.org/downloads/download.php?file=/eclipse/downloads/drops4/R-4.2.2-201302041200/eclipse-SDK-4.2.2-win32.zip>
2) Extraire l'archive ou bon vous semble et lancer eclipse.exe se trouvant dans le dossier
3) Faire (File -> Export -> Install -> Software Items from file) et choisir le fichier ecole.._ide.p2f qui doit se trouver en piéce jointe de l'email qui vous a conduit ici.
4) Extraire le snapshot git dans un endroit voulu
5) Créer un nouveau projet php et le nommer de la même façon que le dossier extrait sans oublier de faire pointer le projet vers le dossier extrait
6) Suivre ce tuto: <http://wiki.eclipse.org/EGit/User_Guide#Basic_Tutorial:_Adding_a_project_to_version_control>
7) Ne pas oublier de switch sur votre branche en allant dans Clic droit (Team -> Branch -> remote...)
8) Vous pouvez coder et n'oubliez pas de commit!
