---
external help file: PSReports-help.xml
Module Name: PSReports
online version: 
schema: 2.0.0
---

# Get-ScriptReport

## SYNOPSIS
Crea un archivo .sql con el Script que se genera un reporte.

## SYNTAX

```
Get-ScriptReport [-InputObject] <Object> [-DirectoryPath] <String> [[-Version] <Version>]
```

## DESCRIPTION
Obtiene la ultima version del script con el que se genera un reporte.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-Report | Get-ScriptReport -DirectoryPath 'C:\Ruta'
```

### -------------------------- EXAMPLE 2 --------------------------
```
Get-Report | Get-ScriptReport -DirectoryPath 'C:\Ruta' -Version '1.0.0.1'
```

### -------------------------- EXAMPLE 3 --------------------------
```
Get-Report -Name Test | Get-ScriptReport -DirectoryPath 'C:\Ruta' -Version '1.0.0.1'
```

## PARAMETERS

### -InputObject
Objeto con la configuracion del reporte.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DirectoryPath
Directorio en el cual se creara el Script.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version
Version del Script que se desea crear.

```yaml
Type: Version
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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

