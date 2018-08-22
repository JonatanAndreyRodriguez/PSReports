---
external help file: PSReports-help.xml
Module Name: PSReports
online version: 
schema: 2.0.0
---

# Get-Target

## SYNOPSIS
Obtiene los target asignados de un reporte.

## SYNTAX

```
Get-Target [-InputObject] <Object> [[-IdTarget] <String>]
```

## DESCRIPTION
Obtiene los target asignados de un reporte.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-Report -Name Test | Get-Target
```

Obtiene todos los target para el reporte Test.

### -------------------------- EXAMPLE 2 --------------------------
```
Get-Report -Name Test | Get-Target -id 1
```

Obtiene el target con id 1 del reporte Test

### -------------------------- EXAMPLE 3 --------------------------
```
Get-Report -Name Test -Version 1.0.0.0 | Get-Target
```

Obtiene los target del reporte Test cuando la version sea 1.0.0.0

## PARAMETERS

### -InputObject
Objeto con la configuracion del reporte, se puede crear utilizando la funcion Get-Report.

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

### -IdTarget
Identificador del target el cual se quiere obtener.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: *
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Processa.Management.Automation.PSReports.TargetInfo

## NOTES
-- ======================================================================================================
-- Author       : jarodriguezc
-- Update date  : 03/08/2018
-- Description  : Se realiza ajuste para mostrar el nuevo parametro de configuracion del target (Template). 
-- ======================================================================================================

## RELATED LINKS

[[New-Target](New-Target.md)
[Update-Target](Update-Target.md)
[Get-Report](Get-Report.md)]()

