---
external help file: PSReports-help.xml
Module Name: PSReports
online version: 
schema: 2.0.0
---

# Update-Report

## SYNOPSIS
Actualiza una configuración para la generación de archivos a partir de la ejecucion de un script de SQL Server.

## SYNTAX

### StringSet (Default)
```
Update-Report [-Name <String>] [-SqlPath <String>] [-SqlKey <String>] [-OutputPath <String>]
 [-Delimiter <Char>] [-FileNameFormat <String>] [-ParametersReport <String[]>] [-ParametersMandatory <String>]
 [-ExportHeader <String>]
```

### ScriptSet
```
Update-Report [-Name <String>] [-SqlPath <String>] [-SqlKey <String>] [-OutputPath <String>]
 [-Delimiter <Char>] [-FileNameScript <ScriptBlock>] [-ParametersReport <String[]>]
 [-ParametersMandatory <String>] [-ExportHeader <String>]
```

## DESCRIPTION
Actualiza una configuración para la generación de archivos a partir de la ejecucion de un script de SQL Server.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-Report -Name MyName | Update-Report -Name MyName -Delimiter '-'
```

## PARAMETERS

### -Name
Nombre con el que se identifica la configuración.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SqlPath
Ruta de la carpeta donde se buscará el archivo con nombre "Script.sql" para generar el archivo.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SqlKey
Nombre de la llave que contiene la cadena de conexión con la base de datos.
Este valor se configura a través de la función Set-SqlConnection del módulo PSProcessa.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
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
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ParametersMandatory
Si esta presente indica que los parametros indicados son obligatorios para la ejecucion del reporte.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExportHeader
Cuando está presente, incluye los encabezados generados por el script de T/SQL en el archivo resultante.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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
-- Description  : Se agregan los parametros (ParametersReport,ParametersMandatory) para que estos se 
--                puedan actualizar ya que son necesarios para algunos reportes, adicional se agrega
--                escritura en el log.                    
-- ======================================================================================================

## RELATED LINKS

[[Get-Report](Get-Report.md)
[Invoke-Report](Invoke-Report.md)
[Update-Target](Update-Target.md)]()

