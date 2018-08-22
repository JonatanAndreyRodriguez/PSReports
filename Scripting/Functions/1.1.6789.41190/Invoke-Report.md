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

```
Invoke-Report [-InputObject] <Object> [[-ParametersReport] <PSObject>]
 [[-Encoding] <FileSystemCmdletProviderEncoding>] [[-FieldDelimiter] <String>] [-PassThru]
```

## DESCRIPTION
Crea un archivo a partir de un script de SQL Server y a la configuración definida previamente.
Para más información vea las funciones (New-Report).

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-Report -Name 'Text' | Invoke-Report
```

### -------------------------- EXAMPLE 2 --------------------------
```
Get-Report -Name 'Text' -Version 1.0.0.0 | Invoke-Report
```

### -------------------------- EXAMPLE 3 --------------------------
```
$Object = @{
```

fecha1 = '2018-01-01'
    fecha2 = '2018-01-01'
}
Get-Report -Name 'Text' -Version 1.0.0.0 | Invoke-Report -ParametersReport $Object

### -------------------------- EXAMPLE 4 --------------------------
```
$Object = @{
```

fecha1 = '2018-01-01'
    fecha2 = '2018-01-01'
}
Get-Report -Name 'Text' -Version 1.0.0.0 | Invoke-Report -ParametersReport $Object -FieldDelimiter '"'

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

### -ParametersReport
Objeto que contiene los parametros y los valores necesarios para la ejecucion del reporte.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Encoding
Encoding con el que se leera el Script.

```yaml
Type: FileSystemCmdletProviderEncoding
Parameter Sets: (All)
Aliases: 
Accepted values: Unknown, String, Unicode, Byte, BigEndianUnicode, UTF8, UTF7, UTF32, Ascii, Default, Oem, BigEndianUTF32

Required: False
Position: 3
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -FieldDelimiter
Caracter con el que se delimitara el texto del archivo.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: [string]::Empty
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
si es enviado indica donde se encuentra el reporte.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### System.Void

### System.IO.DirectoryInfo

### System.IO.FileInfo

## NOTES
-- ======================================================================================================
-- Author       : jarodriguezc
-- Update date  : 03/08/2018
-- Description  : Se agrega parametro ParametersReport para aquellos reportes que necesiten parametros 
--                para su ejecucion, adicional se toma el codigo que realizaba los target, se consolida
--                en la nueva funcion Invoke-TargetReport, adicional a esto se agregan sentencias para 
--                escribir en un archivo de log.
-- ======================================================================================================

## RELATED LINKS

[[New-Report](New-Report.md)
[Get-Report](Get-Report.md)
[Update-Report](Update-Report.md)]()

