---
external help file: PSReports-help.xml
Module Name: PSReports
online version: 
schema: 2.0.0
---

# Set-Config

## SYNOPSIS
Crea o actualiza una configuración para la generación de archivos a partir de la ejecucion de un script de SQL Server.

## SYNTAX

### WithOutputPath
```PowerShell
Set-Config -Name <String> -InputPath <String> -OutputPath <String> [-Delimiter <Char>] -SqlKey <String>
 [-FormatName <String>] [-ScriptName <ScriptBlock>] [-TransferMode <TransferMode>] [-PGPKey <String>]
 [-FtpKey <String>] [-RemotePath <String>] [-SmtpKey <String>] [-EmailTo <String[]>] [-Header] [-Force]
```

### WithRepositoryandEmail
```PowerShell
Set-Config -Name <String> -InputPath <String> [-Delimiter <Char>] -SqlKey <String> [-FormatName <String>]
 [-ScriptName <ScriptBlock>] [-TransferMode <TransferMode>] [-PGPKey <String>] -FtpKey <String>
 -RemotePath <String> -SmtpKey <String> -EmailTo <String[]> [-Header] [-Force]
```

### WithRepository
```PowerShell
Set-Config -Name <String> -InputPath <String> [-Delimiter <Char>] -SqlKey <String> [-FormatName <String>]
 [-ScriptName <ScriptBlock>] [-TransferMode <TransferMode>] [-PGPKey <String>] -FtpKey <String>
 -RemotePath <String> [-Header] [-Force]
```

### WithEmail
```PowerShell
Set-Config -Name <String> -InputPath <String> [-Delimiter <Char>] -SqlKey <String> [-FormatName <String>]
 [-ScriptName <ScriptBlock>] [-TransferMode <TransferMode>] [-PGPKey <String>] -SmtpKey <String>
 -EmailTo <String[]> [-Header] [-Force]
```

## DESCRIPTION
Crea o actualiza una configuración de una carpeta para la ejecución del "Script.sql" que se encuentra dentro de esta.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```PowerShell
Set-Config -Name 'Ejemplo_1' -InputPath 'C:\Ruta' -SqlKey 'Ejemplo_1' -FormatName 'Reporte{0:yyyy-MM-dd}.txt' -PGPKey 'PGP_Ejemplo_1' -SmtpKey 'SMTP_Ejemplo_1' -EmailTo 'ejemplo@Processa.com' -Header
```

### -------------------------- EXAMPLE 2 --------------------------
```PowerShell
Set-Config -Name 'Ejemplo_1' -InputPath 'C:\Ruta' -OutputPath 'C:\Ruta' -Delimiter '|' -SqlKey 'Ejemplo_1' -FormatName 'Reporte.txt' -TransferMode Binary -SmtpKey 'SMTP_Ejemplo_1' -EmailTo 'ejemplo@Processa.com' -Header
```

### -------------------------- EXAMPLE 3 --------------------------
```PowerShell
Set-Config -Name 'Ejemplo_1' -InputPath 'C:\Ruta' -OutputPath 'C:\Ruta' -Delimiter '|' -SqlKey 'Ejemplo_1' -FormatName 'Reporte{0:yyyy-MM-dd}.txt' -TransferMode Binary -FtpKey 'sftp_Ejemplo_1' -RemotePath '\Ruta\' -SmtpKey 'SMTP_Ejemplo_1' -EmailTo 'ejemplo@Processa.com'
```

### -------------------------- EXAMPLE 4 --------------------------
```PowerShell
Set-Config -Name 'Ejemplo_1' -InputPath 'C:\Ruta' -Delimiter '|' -TransferMode Binary -SqlKey 'Ejemplo_1' -FormatName 'Reporte.txt ' -PGPKey 'PGP_Ejemplo_1' -FtpKey 'sftp_Ejemplo_1' -RemotePath '\Ruta\'
```

### -------------------------- EXAMPLE 5 --------------------------
```PowerShell
Set-Config -Name 'Ejemplo_1' -InputPath 'C:\Ruta' -OutputPath 'C:\Ruta' -Delimiter '|' -TransferMode Binary -SqlKey 'Ejemplo_1' -ScriptName {'Reporte_{0:yyyyMMdd}.csv' -f ((Get-Date).AddDays(-1))} -PGPKey 'PGP_Ejemplo_1' -FtpKey 'sftp_Ejemplo_1' -RemotePath '\Ruta\' -SmtpKey 'SMTP_Ejemplo_1' -EmailTo 'ejemplo@Processa.com'
```

## PARAMETERS

### -Name
Nombre con el que se identifica la configuración.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputPath
Ruta de la carpeta donde se buscara el archivo "Script.sql" para generar el archivo.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputPath
Ruta de la carpeta donde se dejara el archivo, por si se desea conservar.

```yaml
Type: String
Parameter Sets: WithOutputPath
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Delimiter
Especifica un delimitador para separar los valores de propiedad.
El valor por defecto es una coma (,).

```yaml
Type: Char
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: ,
Accept pipeline input: False
Accept wildcard characters: False
```

### -SqlKey
Nombre de la llave que contiene la conexión a la base de datos, esta debe ser creada previamente.
Para más información vea las funciones de PSProcessa (Set-SqlConnection o Get-SqlConnection).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FormatName
Nombre con el cual se genera el archivo.
Recibe el nombre del archivo completo o el nombre más una cadena de formato de 
fecha de C#.
Ejemplo: prueba.csv, prueba{0:yyyyMMdd}.csv, Tiene el Valor por defecto Output_{0:yyyyMMdd}.csv y por defecto 
la fecha es el día anterior a la ejecución del reporte.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Output_{0:yyyyMMdd}.csv
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptName
Script de Powershell con el cual se genera el nombre del archivo.
Este tiene relevancia sobre el parámetro 'ReportName'.

```yaml
Type: ScriptBlock
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### -PGPKey
Nombre de la llave que contiene la configuración para encriptar el archivo.
Para más información vea las funciones de 
PSProcessa (Set-PGPKeyStore o Get-PGPKeyStore).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FtpKey
Nombre de la llave que contiene la configuración para publicación del archivo en un repositorio S/FTP.
Para más información 
vea las funciones de PSProcessa (Set-FtpConnection o Get-FtpConnection).

```yaml
Type: String
Parameter Sets: WithOutputPath
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: WithRepositoryandEmail, WithRepository
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemotePath
Ruta en el repositorio S/FTP en donde será publicado el archivo.

```yaml
Type: String
Parameter Sets: WithOutputPath
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: WithRepositoryandEmail, WithRepository
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SmtpKey
Nombre de la llave que contiene la configuración para el envió de correo, notificando como termino la ejecución del script. 
Para más información vea las funciones de PSProcessa (Set-SmtpConnection o Get-SmtpConnection).

```yaml
Type: String
Parameter Sets: WithOutputPath
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: WithRepositoryandEmail, WithEmail
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmailTo
Cuentas de correo electrónico a las cuales se enviara la notificación de como termino la ejecución del archivo.
Si desea enviar mas de una cuenta
las puede separar por el carácter de coma (,).

```yaml
Type: String[]
Parameter Sets: WithOutputPath
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String[]
Parameter Sets: WithRepositoryandEmail, WithEmail
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header
Cuando está presente determina que el archivo debe contener encabezados.
Tener en cuenta que los encabezados serán los generados por el Script.sql.

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

### -Force
Cuando está presente sobrescribe la configuración con el mismo nombre.
Parametro: 'Name'.

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

System.Void

## NOTES
- Autor: Jarodriguezc

## RELATED LINKS

[Get-Config](Get-Config.md)
[Remove-Config](Remove-Config.md)

