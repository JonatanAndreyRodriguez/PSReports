---
external help file: PSReports-help.xml
Module Name: PSReports
online version: 
schema: 2.0.0
---

# Remove-Config

## SYNOPSIS
Elimina una configuración para la ejecución de reportes.

## SYNTAX

### WithInputObject
```PowerShell
Remove-Config -InputObject <Object>
```

### WithName
```PowerShell
Remove-Config -Name <String>
```

## DESCRIPTION
Este Command-Let elimina una configuración para la ejecución de reportes.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```PowerShell
Remove-ReportConfig -Name 'Ejemplo_1'
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
Nombre en la configuración a eliminar.

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
- Autor: Jarodriguezc

## RELATED LINKS

[Set-Config](Set-Config.md)
[Get-Config](Get-Config.md)

