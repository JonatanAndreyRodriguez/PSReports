---
external help file: PSReports-help.xml
Module Name: PSReports
online version: 
schema: 2.0.0
---

# Invoke-Report

## SYNOPSIS
Realiza el proceso de crear un archivo de acuerdo a una configuración definida previamente.

## SYNTAX

### WithInputObject
```
Invoke-Report -InputObject <Object>
```

### WithName
```
Invoke-Report -Name <String>
```

## DESCRIPTION
Crea un archivo a partir de un script de SQL Server y a la configuración definida previamente.
Para más información vea las funciones (Set-ReportConfig).

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Invoke-Report -Name 'Ejemplo_1'
```

## PARAMETERS

### -InputObject
{{Fill InputObject Description}}

```yaml
Type: Object
Parameter Sets: WithInputObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nombre en la configuración para para la ejecución de los reportes.

```yaml
Type: String
Parameter Sets: WithName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### System.Void

## NOTES
Autor: Jarodriguezc

## RELATED LINKS

[[Set-Config](Set-Config.md)
[Get-Config](Get-Config.md)]()

