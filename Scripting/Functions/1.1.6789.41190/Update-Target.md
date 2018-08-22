---
external help file: PSReports-help.xml
Module Name: PSReports
online version: 
schema: 2.0.0
---

# Update-Target

## SYNOPSIS
Actualiza los target de una configuracion para la generación de archivos a partir de la ejecucion de un script de SQL Server.

## SYNTAX

```
Update-Target [-Report] <String> [-IdTarget] <String> [[-FtpKey] <String>] [[-RemotePath] <String>]
 [[-TransferMode] <TransferMode>] [[-SmtpKey] <String>] [[-Template] <String>] [[-EmailTo] <String[]>]
 [[-PGPKey] <String>]
```

## DESCRIPTION
Actualiza los target de una configuracion para la generación de archivos a partir de la ejecucion de un script de SQL Server.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-Report -Name Test | Get-Target -Id 1 | Update-Target -FTPKey Prueba -RepmotePath '\Ruta'
```

## PARAMETERS

### -Report
Nombre del reporte al cual esta asociado el target.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdTarget
Identificador del target que se actualizara.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FtpKey
Llave de la conexion a S/FTP al cual se publicara el reporte.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemotePath
Ruta del repositorio en la cual se dejara el archivo.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TransferMode
Tipo de transferencia del reporte.
Los valores posibles son Binary, Ascii y Automatic.
Valor predeterminado es Automatic (basado en la extensión del archivo).

```yaml
Type: TransferMode
Parameter Sets: (All)
Aliases: 
Accepted values: Binary, Ascii, Automatic

Required: False
Position: 5
Default value: Automatic
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SmtpKey
Llave de conexion a SMTP para el envio de correo.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Template
Ruta de la plantilla personalizada para el envio de correo electronico.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EmailTo
Correos electronicos a los cuales se les respondera la notificacion del proceso.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PGPKey
Llave que de la configuracion de encriptado en PSProcessa.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### Ninguno.

## OUTPUTS

### System.Void

## NOTES
-- ======================================================================================================
-- Author       : jarodriguezc
-- Update date  : 03/08/2018
-- Description  : Se agregan los parametros (Template) para enviar correo electronico con plantilla 
--                personalizada. adicional a esto se agrega escritura en el log.
-- ======================================================================================================

## RELATED LINKS

[[Get-Report](Get-Report.md)
[Invoke-Report](Invoke-Report.md)
[Get-Target](Get-Target.md)]()

