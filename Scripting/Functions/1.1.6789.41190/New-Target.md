---
external help file: PSReports-help.xml
Module Name: PSReports
online version: 
schema: 2.0.0
---

# New-Target

## SYNOPSIS
Representa los datos de configuración de un reporte.

## SYNTAX

```
New-Target [[-FtpKey] <String>] [[-RemotePath] <String>] [[-TransferMode] <TransferMode>] [[-SmtpKey] <String>]
 [[-EmailTo] <String[]>] [[-Template] <String>] [[-PGPKey] <String>]
```

## DESCRIPTION
Representa los datos de configuración de un reporte.

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -FtpKey
Nombre de la llave que contiene la configuración para la publicación del archivo en un repositorio S/FTP.
Este valor se configura a través de la función Set-FtpConnection del módulo PSProcessa.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemotePath
Ruta en el repositorio S/FTP en donde será publicado el archivo.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransferMode
Modo de transferencia del archivo al S/FTP.
Los valores posibles son Binary, Ascii y Automatic.
Valor predeterminado es Automatic (basado en la extensión del archivo).

```yaml
Type: TransferMode
Parameter Sets: (All)
Aliases: 
Accepted values: Binary, Ascii, Automatic

Required: False
Position: 3
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### -SmtpKey
Nombre de la llave que contiene la configuración para el envió de correo, a donde se envia una notificación de finalización del proceso.
Este valor se configura a través de la función Set-SmtpConnection del módulo PSProcessa.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmailTo
Especifica las direcciones a las que se envía el correo de notificación de finalización del proceso.
Puede especificar varias direcciones.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Template
Ruta de la plantilla personalizada para el envio de correo electronico.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PGPKey
Nombre de la llave que contiene la configuración para encriptar el archivo.
Este valor se configura a través de la función Set-PGPKeyStore del módulo PSProcessa.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### System.Management.Automation.PSObject

## NOTES
-- ======================================================================================================
-- Author Create: Atorres 
-- Author       : jarodriguezc
-- Update date  : 03/08/2018
-- Description  : Se agrega parametro para la personalizacion de plantillas para el envio de correo.                 
-- ======================================================================================================

## RELATED LINKS

[[New-Report](New-Report.md)]()

