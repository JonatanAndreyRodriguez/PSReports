---
external help file: PSReports-help.xml
Module Name: PSReports
online version: 
schema: 2.0.0
---

# Get-Config

## SYNOPSIS
Obtiene las configuraciones para la generación de archivos.

## SYNTAX

```
Get-Config [[-Name] <String>]
```

## DESCRIPTION
Obtiene las configuraciones establecidas para la generación de archivos a partir de la ejecucion de un script de SQL Server.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-Config -Name 'Ejemplo_1'
```

### -------------------------- EXAMPLE 2 --------------------------
```PowerShell
Get-Config -Name 'Ejemplo*'
```

## PARAMETERS

### -Name
Nombre de la configuración.
Se admiten expresiones con el caracter comodin (\*).
Por ejemplo: 'Prueba\*'.
Valor predeterminado \*.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: *
Accept pipeline input: False
Accept wildcard characters: True
```

## INPUTS

## OUTPUTS

### Processa.Management.Automation.PSReports.ConfigObject

## NOTES
Autor: Jarodriguezc

## RELATED LINKS

[[Set-Config](Set-Config.md)]()

