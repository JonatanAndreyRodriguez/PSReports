---
external help file: PSReports-help.xml
Module Name: PSReports
online version: 
schema: 2.0.0
---

# Get-Report

## SYNOPSIS
Obtiene información de configuración para la generación de archivos.

## SYNTAX

```
Get-Report [[-Name] <String>] [[-Version] <Version>]
```

## DESCRIPTION
Obtiene información de configuración para la generación de archivos a partir de la ejecucion de un script de SQL Server.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-Report -Name 'Test'
```

Obtiene la información de configuración del reporte con nombre 'Test'

### -------------------------- EXAMPLE 2 --------------------------
```
Get-Report -Name 'Test' -Version 1.0.0.1
```

Obtiene la información de configuración del reporte con nombre 'Test' para la version 1.0.0.1

### -------------------------- EXAMPLE 3 --------------------------
```
Get-Report
```

Obtiene la información de configuración de todos los reportes.

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

### -Version
Version de la configuracion que se desea mostrar.

```yaml
Type: Version
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Processa.Management.Automation.PSReports.ReportInfo

## NOTES
-- ======================================================================================================
-- Author       : jarodriguezc
-- Update date  : 03/08/2018
-- Description  : Se realiza ajuste para que muestre los nuevos parametros agregados a la configuracion 
--                de los reportes (ParametersReport,ParametersMandatory), adicional se agrega escritura 
--                en log de errores. 
-- ======================================================================================================

## RELATED LINKS

[[New-Report](New-Report.md)
[Update-Report](Update-Report.md)]()

