# Session 1 
# Chapitre 1 : Commande basique powershell

## POWERSHELL C'EST QUOI ?

POWER SHELL : </br>
-> POWER : puissance ou avancé </br>
-> SHELL : interaction via ordinateur via des ordres (commande + scripts ou des fonctions) </br>
</br>

## Rappel

Rappel : </br>
interaction ordinateur : </br>
via GUI  : utilisation des gestes </br>
via shell : utilisation de terminal </br>
</br>
Terminal classique c'est terminal de commande par utilisation de win+command </br>
</br>
Faire du help </br>
</br>
Pour avoir un terminal powershell  : win + powershell
</br>

## Get-Command
```  
Get-Command
```  

Get-Command </br>
-> Function  </br>
-> Alias </br>
-> Cmdlet </br>
</br>
Commande est organisé par <verb>-<nouns>

## Get-Verb
```  
Get-Verb
```  
Get </br>
Set </br>
...

## Paramètres
Utilisation des tirerts pour les paramètres : </br>

## Get-Help
```  
Get-Help
```  
Get-Help <NomDuCmdlet>

eg :
```  
Get-Help Get-Command
```
```  
GelHelp Get-Verb -Verb
```  

## Manipulation de chemin et alias
Pour montrer le chemin actuel </br>

## Get-Location
Similaire à pwd (print working directory) <br>
```  
pwd
```

## Alias
```  
Get-Alias pwd
```  
```  
Get-Alias
```  
```  
Get-Alias ls
```  

## Set-Location
```  
Set-Location -Path '.\Desktop'
```  
Alias cd ou sl </br>

Verifier ? </br>

eg : </br>
.\ : Chemin relatif </br>
.. : remonter en haut avec le chemin relatif </br>
"c:\Sitraka" : Chemin Absou" </br>

## Autocomplétion
Tabulation pour l'auto-complétion
```  
Set-Location ..
```

## Manipulation des items:  
Item peut être des dossiers ou fichiers

```  
Get-Alias -Name ls
```  
```  
Get-ChildItem
```  
```  
ls
```  
```  
Get-ChildItem .\dossier4
```  



## Création un dossier
```  
New-Item -Name dossier4 -Type Directory
```  

# Remove-Item
Supprimer soit un fichier, soit un dossier
```  
Get-Alias -Name rm
```
```  
Remove-Item .\dossier4
```  
```  
ls
```  

## Nom des fichiers : name.extension
* Création de soit un répertoire soit un fichier
```  
New-Item -Type File -Name testfichier.txt
```  


* Crée un fichier "exemple.txt" et y ajoute du texte
```  
Set-Content -Path "C:\chemin\vers\exemple.txt" -Value "Voici du contenu initial"
```  


* Crée un fichier "exemple.txt" et y ajoute du texte
```  
"Voici du contenu initial" | Out-File "C:\chemin\vers\exemple.txt"
```  

* Ajoute du texte à un fichier existant
```  
"Voici du contenu supplémentaire" | Out-File "C:\chemin\vers\exemple.txt" -Append
```  

* Ajoute du texte à un fichier existant
```  
Add-Content -Path "C:\chemin\vers\exemple.txt" -Value "Voici du contenu supplémentaire"
```  
```  
Get-Item -File
```  
```  
Get-Item -Directory
```  

* Afficher uniquement les fichiers .txt dans le répertoire spécifié
```  
Get-ChildItem -Path "C:\chemin\vers\répertoire" -File -Filter "*.txt"
```  

## Affichage d'un fichier sous forme texte
```  
Get-content
```  
```  
cat
```  
```  
Get-content
```  


## Copie 
```  
Copy-Item -Path "C:\source\monfichier.txt" -Destination "C:\destination\monfichier.txt"
```  
```  
Copy-Item -Path "C:\source\MonDossier" -Destination "C:\destination\MonDossier" -Recurse
```  
```  
Copy-Item -Path "C:\source\*.txt" -Destination "C:\destination"
```  
```  
Copy-Item -Path "C:\source\monfichier.txt" -Destination "C:\destination\monfichier.txt" -Force
```  
```  
Copy-Item -Path "C:\source" -Destination "C:\destination" -Recurse -Force
```  
## Couper
```  
Move-Item -Path "C:\source\monfichier.txt" -Destination "C:\destination\monfichier.txt"
```  
```  
Move-Item -Path "C:\source\MonDossier" -Destination "C:\destination\"
```  
```  
Move-Item -Path "C:\source\*.txt" -Destination "C:\destination"
```  
```  
Move-Item -Path "C:\source\monfichier.txt" -Destination "C:\destination\"
```  

## Suppressions
```  
Remove-Item -Path "C:\destination\monfichier.txt" -Force
```
## Rénommer
```  
Rename-Item -Path "C:\source\ancien_nom.txt" -NewName "nouveau_nom.txt"
```  
```  
Rename-Item -Path "C:\source\AncienDossier" -NewName "NouveauDossier"
```  
