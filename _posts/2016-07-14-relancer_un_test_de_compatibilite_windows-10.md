---
layout: post
title:  "Relancer un test de compatibilité Windows 10"
date:   2016-07-14 19:24:00 +0100
comments: true
categories: windows
---

Cette semaine, c'était l'heure de mon formatage bisannuel : à force de considérer mon desktop comme un dossier temporaire j'ai commencé à remplir mon deuxième screen, et dans ces cas-là j'ai coutume de nettoyer par la destruction. Ça a généralement le double avantage de vider mon bureau et de virer les logiciels que je n'utilise plus. Le même résultat qu'un bon CCleaner allaité à la bombe H quoi.

C'est sur cette belle réflexion que je me suis dit : "Foutu pour foutu, je vais tenter la migration vers Windows 10". Stupide que je suis.

# Test de compatibilité

Je lance donc tout guilleret l'utilitaire d'update. Sauf que pas de bol, selon lui, je peux pas à cause d'un problème de compatibilité. Joie.

<br>
![Impossible de blablabla]({{ site.url }}/img/win10-1.jpg)

*<center> Impossible de Blablabla </center>* <br>

Jusque là je m'en sors sans trop de casse : le seul problème de compatibilité vient d'[iDisplay](http://getidisplay.com/), un utilitaire me permettant d'utiliser mon [iChose]({{ site.url }}/img/ichose.jpeg) comme troisième écran d'appoint.

J'ai donc pris la lourde décision de désinstaller le driver. C'est pas comme si j'avais de toutes façons prévu de tout désinstaller. *Oh wait!*

# Relancer le test

Une fois tous les conflits de compatibilité résolus (pour moi ça a été rapide, mais il peut y en avoir plusieurs), on essaie de relancer l'analyse.

*Comment on relance cette daube ?*

Ouep. Voilà donc le réel problème. Aucun bouton pour relancer l'analyse. J'ai bien essayé de redémarrer la machine, mais que dalle. Pas la peine non plus de suivre divers tutos expliquant qu'il faut replanifier la tâche avec la commande `schtasks.exe /Run /TN "\Microsoft\Windows\Application Experience\Microsoft Compatibility Appraiser"`, ça ne servira qu'à vous faire patienter dans le vent.



<br>
![Kill le process]({{ site.url }}/img/win10-2.jpg)

*<center>J'ai même essayé de kill le processus et le relancer a la mano</center>* <br>

# La solution

En désespoir de cause, j'ai directement contacté Microsoft. Leur politique a énormément changé depuis quelques années : à l'écoute des utilisateurs, et surtout avec des CM réactifs et efficaces. Leur compte twitter [@MSVousAide](https://twitter.com/MSVousAide) a été très prompt à répondre à mon problème. Je vous livre donc en vrac la solution :

- Supprimer le contenu du dossier `C:\Windows\SoftwareDistribution\Download`
- Lancer l'invit'de commande en administrateur
- Exécuter `wuauclt /updatenow`

Voilà, c'est tout. Il ne reste que quelques jours pour profiter de la migration gratuite vers win10 (jusqu'au 29 juillet), donc autant en profiter sans payer ! 
