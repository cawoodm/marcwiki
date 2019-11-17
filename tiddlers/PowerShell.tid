# PowerShell Snippets

##Security
`set-executionpolicy remotesigned; get-executionPolicy`

##Getting Help
* Run as admin: Update-Help
* help about_operators
* help "replace"
* help about_redirection -showwindow
* help Select-String -showwindow

## Error Handling
* Pass param `-ErrorAction SilentlyContinue` to ignore erros
* `2> stderr.log`

## Good Code
* `Set-PSDebug -Strict`
* `Set-StrictMode -Version 3.0`

##Global variables
* Automatic Variables: https://technet.microsoft.com/en-us/library/hh847768.aspx
* `Get-Variable`
* `$PSVersionTable.PSVersion`
* `$PSScriptRoot`

##Objects
* New-Object –TypeName PSObject –Prop (@{name="Marc";age="38"})

##Text Files
* `Get-Content -raw` (cat,type,gc)
* `Get-Process | select id,name,starttime | Export-Csv "c:\temp\ip.csv"`

###Searching Files for Strings
* `Select-String` (sls)
* `Select-String *.js -pattern "var"

###Sorting
`"a","c","b","a" | sort -unique`
`gps | sort -property id`

###Remove Duplicates
`cat c:\temp\ip.txt | sort -unique`

##Dictionaries aka Hash Tables
* `$reg=@{ CA="California";"NY" = "New York"}`
* `reg.add("NJ", "New Jersey")`
* `reg.'NJ'`
* `reg.set_item("GA", "Georgia")`
* `remove()`
* ``$hashtable.GetEnumerator() | ForEach-Object { … }`

## Snapins

- `Get-PSSnapin | ft`

##Splatting

```powershell	
$services = @{Name = "a","s"}
Get-Service @services
```

##Listing Stuff
get-childitem (ls,dir,gci)
get-childitem registry::hklm\software
dir -name
List of Powershell Aliases
dir alias:*
List of environment variables
dir env:
Get PATH Value
(get-item env:path).value
(get-item env:path).value.split(";")
List objects:
Get-Process | select -first 5

##Counting and Measuring
dir | Measure-Object -Property length -Maximum -Minimum -sum -Average
[System.Math]::Round() OR 1.2 -as [int]

##GUI Stuff
Import-Csv .\ip.csv | Out-GridView
Get-History | Out-GridView -PassThru  | Invoke-Expression
Get-Help about*  | Out-GridView  -PassThru |  Get-Help -ShowWindow

##Modules
* `Get-Module`
* `$Env:PSModulePath -split ';'`
* Reload a module: `Import-Module -Name SQLInstance`


* `ForEach-Object` (aka `%`)
* `ForEach($a in @("a","b","c")) {$a}` loop with no pipe input
* `1..10 | %{$_}` or `1, 2, 3, 5 | %{$_}`

##Remoting
`invoke-command -computername Server64 -scriptblock {get-executionpolicy}`

##Web/REST/JSON
```powershell
(Invoke-WebRequest https://torrentapi.org/pubapi_v2.php?get_token=get_token).content |  
  ConvertFrom-Json |
  select -expand token
```

