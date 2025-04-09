# Session 2
## Chapitre 1 (suite)
```  
Get-Help
```
```  
Get-command *alias*
```  
```  
Get-Help New-Alias
```  
ou 
```  
Get-Help Set-Alias
```  
```  
Get-Help New-Alias -examples
```  
```  
Remove-Item alias:ls
```  
```  
Remove-Item alias:ls, alias:rm, alias:cp
```  
```  
New-Alias -Name "List" Get-ChildItem
```  
```  
Get-Alias List
```
```  
Stop-Computer
```  
```  
echo "salut"
```
Obtenir l'alias de echo ?
```  
Clear-Host
```
```  
cls
```
```  
Write-Output "TOTO" | Out-File test.txt
```
```  
Get-Service
```  
```  
Get-Service | Format-List
```  


## Instruction de comparaison
```  
1 -eq 1
```  
```  
1 -eq 2
```  
```  
1 -ne 1
```  
```  
1 -ne 2
```  

1 -gt 2
2 -gt 1


2 -lt 1
1 -lt 2

"toto" -eq "TOTO"
"toto" -ceq "TOTO"

"toto" -eq "TOTO" -and 1 -eq 1

"toto" -eq "TOTO" -and 1 -eq 2

("toto" -eq "TOTO") -and (1 -eq 2)

("toto" -eq "TOTO") -or (1 -eq 2)

("toto" -eq "titi") -or (1 -eq 2)

V- Powersehll est objet :
Powershell est basé sur le modèl objet
Powershell a aussi ses méthodes et ses méthodes s'appliquest sur ces objets

Eg : Remove-Adduser , Remove est la méthode et adduser est l'objet


Pour afficher ses methodes et ses propriétés il faut passer par cmdlet get-member


Get-Printer
Get-Printer | Get-Member
Get-Printer s*
Get-Printer | Select-Object name,computername, driver

Avec -like :
* remplace n'importe quel nombre de caractères.
? remplace un seul caractère.

-match    
* : Zero ou plusieurs
+ : un ou plusieurs
() : groupés
\ : Pour designér les caractère speciaux
. : remplace n'importe qu'elle caractère
{} : cardinalité 

Expression régulière (Regex)    "abc" -match "^a.*c$"
"aaaa" -match "a*"
"abracadabraabracadabra" -match "^(abracadabra)*$"


Get-PrinterDriver
Get-PrinterDriver m*
Get-PrinterDriver | Where-Object -FilterScript {$_.Manufacturer -eq "EPSON" -and $_.PrinterEnvironment -like "*x64"}
-FilterScript :  c'est optionnel

Lister les fichiers .txt
Get-ChildItem  | Where-Object { $_.Name -like "*.txt" }

Lister les processus commencant par notepad
Get-Process | Where-Object { $_.ProcessName -like "notepad*" }

Filtrer les processus par nom
Get-Process | Where-Object { $_.ProcessName -eq "notepad" }


Get-Service a* | Where-Object -FilterScript {$_.status -eq "Stopped"}



Trouver des fichiers de plus de 1 Mo
Get-ChildItem C:\MonDossier | Where-Object { $_.Length -gt 1MB }

Alternative simplifiée (? comme alias de Where-Object) :
Get-Process | ? { $_.CPU -gt 10 }
