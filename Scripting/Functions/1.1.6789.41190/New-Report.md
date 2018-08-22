---
external help file: PSReports-help.xml
Module Name: PSReports
online version: 
schema: 2.0.0
---

# New-Report

## SYNOPSIS
Crea una configuración para la generación de archivos a partir de la ejecucion de un script de SQL Server.

## SYNTAX

### StringSet (Default)
```
New-Report -InputObject <PSObject> -Name <String> -SqlPath <String> -SqlKey <String> [-OutputPath <String>]
 [-Delimiter <Char>] -FileNameFormat <String> [-ParametersReport <String[]>] [-ParametersMandatory]
 [-ExportHeader]
```

### ScriptSet
```
New-Report -InputObject <PSObject> -Name <String> -SqlPath <String> -SqlKey <String> [-OutputPath <String>]
 [-Delimiter <Char>] -FileNameScript <ScriptBlock> [-ParametersReport <String[]>] [-ParametersMandatory]
 [-ExportHeader]
```

## DESCRIPTION
Ejecuta las instrucciones T/SQL de un archivo y exporta los resultados.
En la carpeta del parámetro SqlPath debe existir un archivo con el nombre Script.sql.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
$Target=New-Target -FtpKey 'JobMonitor' -RemotePath '/Ruta'
```

$Target | New-Report -Name 'Test' -SqlPath 'C:\MyFolder' -SqlKey 'MySqlKey' -FileNameFormat 'MyFile{0:yyyy-MM-dd}.txt'  -ExportHeader

### -------------------------- EXAMPLE 2 --------------------------
```
New-Target -FtpKey 'JobMonitor' -RemotePath '/Ruta'| New-Report -Name 'Test' -SqlPath 'C:\MyFolder' -SqlKey 'MySqlKey' -FileNameFormat 'MyFile{0:yyyy-MM-dd}.txt' -ExportHeader
```

### -------------------------- EXAMPLE 3 --------------------------
```
$Target=New-Target -FtpKey 'JobMonitor' -RemotePath '/Ruta'
```

$Target | New-Report -Name 'Test' -SqlPath 'C:\MyFolder' -SqlKey 'MySqlKey' -FileNameFormat 'MyFile{0:yyyy-MM-dd}.txt' -ParametersReport 'fecha1','fecha2'

### -------------------------- EXAMPLE 4 --------------------------
```
$Target=New-Target -FtpKey 'JobMonitor' -RemotePath '/Ruta'
```

$Target | New-Report -Name 'Test' -SqlPath 'C:\MyFolder' -SqlKey 'MySqlKey' -FileNameFormat 'MyFile{0:yyyy-MM-dd}.txt' -ParametersReport 'fecha1','fecha2' -ParametersMandatory

## PARAMETERS

### -InputObject
Objeto que representa los valores de configuracion para encripcion, envio por s/ftp y envio por correo.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### -SqlPath
Ruta de la carpeta donde se buscará el archivo con nombre "Script.sql" para generar el archivo.

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

### -SqlKey
Nombre de la llave que contiene la cadena de conexión con la base de datos.
Este valor se configura a través de la función Set-SqlConnection del módulo PSProcessa.

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
Ruta de la carpeta donde se deja el archivo resultante del proceso.
Si omite este parámetro al final del proceso se eliminará el archivo resultante.

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

### -Delimiter
Especifica un delimitador para separar los valores de cada propiedad en el resultado de la ejecución del script T/SQL.
El valor predeterminado es una coma (,)

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

### -FileNameFormat
Formato de cadena compuesto que se utiliza para el nombre del archivo resultante.
Ejemplos: MyFile.csv, MyFile{0:yyyyMMdd}.csv.
Valor predeterminado: Output_{0:yyyyMMdd}.csv, donde se reemplazará yyyymmdd con la fecha del día anterior a la ejecución del reporte.

```yaml
Type: String
Parameter Sets: StringSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileNameScript
Script que se utiliza para generar un nombre dinámico para el archivo.
Si se establece FormatName y ScriptName al mismo tiempo, tendrá precedencia ScriptName.
Ejemplo: {'MyFile_{0}-{1:yyyy-mm}.txt' -f 'MiEntidad', (Get-Date).AddDays(-3)}

```yaml
Type: ScriptBlock
Parameter Sets: ScriptSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParametersReport
Array de String con los nombres de los parametros para la ejecucion del reporte.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParametersMandatory
Si esta presente indica que los parametros indicados son obligatorios para la ejecucion del reporte.

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

### -ExportHeader
Cuando está presente, incluye los encabezados generados por el script de T/SQL en el archivo resultante.

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

### Ninguno.

## OUTPUTS

### System.Void

## NOTES
-- ======================================================================================================
-- Author       : jarodriguezc
-- Update date  : 03/08/2018
-- Description  : Se agregan los parametros (ParametersReport,ParametersMandatory) ya que se ven necesarios
--                para la ejecucion de algunos reportes y se agrega escritura en el archivo de log. 
-- ======================================================================================================

## RELATED LINKS

[[Get-Report](Get-Report.md)
[Invoke-Report](Invoke-Report.md)
[Update-Report](Update-Report.md)
[New-Target](New-Target.md)]()

