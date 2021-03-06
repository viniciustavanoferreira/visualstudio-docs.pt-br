---
title: Funções de propriedade | Microsoft Docs
ms.date: 02/21/2017
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, property functions
ms.assetid: 2253956e-3ae0-4bdc-9d3a-4881dfae4ddb
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d98d4069ca510cfbb288b88e0ab52b9cd1eb275d
ms.sourcegitcommit: d20ce855461c240ac5eee0fcfe373f166b4a04a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "84183646"
---
# <a name="property-functions"></a>Funções de propriedade

As funções de propriedade são chamadas para .NET Framework métodos que aparecem nas definições de Propriedade do MSBuild. Ao contrário das tarefas, as funções de propriedade podem ser usadas fora dos destinos e são avaliadas antes de qualquer destino ser executado.

Sem o uso de tarefas MSBuild, você pode ler a hora do sistema, comparar cadeias de caracteres, combinar expressões regulares e executar outras ações no script de compilação. O MSBuild tentará converter a cadeia de caracteres em número e número em cadeia de caracteres, além de fazer outras conversões, conforme necessário.

Valores de cadeia de caracteres retornados de funções de propriedade tem [caracteres especiais](msbuild-special-characters.md) de escape. Se você quiser que o valor seja tratado como se fosse colocado diretamente no arquivo do projeto, use `$([MSBuild]::Unescape())` para desfazer o escape dos caracteres especiais.

As funções de propriedade estão disponíveis com o .NET Framework 4 e posterior.

## <a name="property-function-syntax"></a>Sintaxe da função de propriedade

Três tipos de funções de propriedade estão listados abaixo. Cada função possui uma sintaxe diferente:

- Funções de propriedade de cadeia de caracteres (instância)
- Funções de propriedade estática
- Funções de propriedade MSBuild

### <a name="string-property-functions"></a>Funções de propriedade de cadeia de caracteres

Todos os valores de propriedade de compilação são apenas valores de cadeia de caracteres. Você pode usar métodos de cadeia (instância) para operar em qualquer valor de propriedade. Por exemplo, você pode extrair o nome da unidade (os três primeiros caracteres) de uma propriedade de compilação que representa um caminho completo usando este código:

```
$(ProjectOutputFolder.Substring(0,3))
```

### <a name="static-property-functions"></a>Funções de propriedade estática

No seu script de compilação, você pode acessar propriedades e métodos estáticos de muitas classes de sistema. Para obter o valor de uma propriedade estática, use a sintaxe a seguir, em que \<Class> é o nome da classe do sistema e \<Property> é o nome da propriedade.

```
$([Class]::Property)
```

Por exemplo, você pode usar o seguinte código para definir uma propriedade de compilação para a data e hora atual.

```xml
<Today>$([System.DateTime]::Now)</Today>
```

Para chamar um método estático, use a sintaxe a seguir, em que \<Class> é o nome da classe System, \<Method> é o nome do método e ( \<Parameters> ) é a lista de parâmetros para o método:

```
$([Class]::Method(Parameters))
```

Por exemplo, para definir uma propriedade de compilação para um novo GUID, você pode usar este script:

```xml
<NewGuid>$([System.Guid]::NewGuid())</NewGuid>
```

Em funções de propriedade estática, você pode usar qualquer método estático ou propriedade destas classes de sistema:

- <xref:System.Byte?displayProperty=nameWithType>
- <xref:System.Char?displayProperty=nameWithType>
- <xref:System.Convert?displayProperty=nameWithType>
- <xref:System.DateTime?displayProperty=nameWithType>
- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Double?displayProperty=nameWithType>
- <xref:System.Enum?displayProperty=nameWithType>
- <xref:System.Guid?displayProperty=nameWithType>
- <xref:System.Int16?displayProperty=nameWithType>
- <xref:System.Int32?displayProperty=nameWithType>
- <xref:System.Int64?displayProperty=nameWithType>
- <xref:System.IO.Path?displayProperty=nameWithType>
- <xref:System.Math?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.OSPlatform?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation?displayProperty=nameWithType>
- <xref:System.UInt16?displayProperty=nameWithType>
- <xref:System.UInt32?displayProperty=nameWithType>
- <xref:System.UInt64?displayProperty=nameWithType>
- <xref:System.SByte?displayProperty=nameWithType>
- <xref:System.Single?displayProperty=nameWithType>
- <xref:System.String?displayProperty=nameWithType>
- <xref:System.StringComparer?displayProperty=nameWithType>
- <xref:System.TimeSpan?displayProperty=nameWithType>
- <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>
- <xref:System.UriBuilder?displayProperty=nameWithType>
- <xref:System.Version?displayProperty=nameWithType>
- <xref:Microsoft.Build.Utilities.ToolLocationHelper?displayProperty=nameWithType>

Você pode usar também as seguintes propriedades e métodos estáticos:

- [System.Environment::CommandLine](xref:System.Environment.CommandLine*)
- [System.Environment::ExpandEnvironmentVariables](xref:System.Environment.ExpandEnvironmentVariables*)
- [System. Environment:: GetEnvironmentVariable](xref:System.Environment.GetEnvironmentVariable*)
- [System.Environment::GetEnvironmentVariables](xref:System.Environment.GetEnvironmentVariables*)
- [System.Environment::GetFolderPath](xref:System.Environment.GetFolderPath*)
- [System.Environment::GetLogicalDrives](xref:System.Environment.GetLogicalDrives*)
- [System.IO.Directory::GetDirectories](xref:System.IO.Directory.GetDirectories*)
- [System.IO.Directory::GetFiles](xref:System.IO.Directory.GetFiles*)
- [System.IO.Directory::GetLastAccessTime](xref:System.IO.Directory.GetLastAccessTime*)
- [System.IO.Directory::GetLastWriteTime](xref:System.IO.Directory.GetLastWriteTime*)
- [System.IO.Directory::GetParent](xref:System.IO.Directory.GetParent*)
- [System.IO.File::Exists](xref:System.IO.File.Exists*)
- [System. IO. arquivo:: GetCreationTime](xref:System.IO.File.GetCreationTime*)
- [System. IO. File:: GetAttributes](xref:System.IO.File.GetAttributes*)
- [System. IO. File:: GetLastAccessTime](xref:System.IO.File.GetLastAccessTime*)
- [System. IO. File:: GetLastWriteTime](xref:System.IO.File.GetLastWriteTime*)
- [System.IO.File::ReadAllText](xref:System.IO.File.ReadAllText*)

### <a name="calling-instance-methods-on-static-properties"></a>Chamar métodos de instância em propriedades estáticas

Se você acessar uma propriedade estática que retorna uma instância de objeto, poderá invocar métodos de instância desse objeto. Para invocar um método de instância, use a seguinte sintaxe, em que \<Class> é o nome da classe System, \<Property> é o nome da propriedade, \<Method> é o nome do método e ( \<Parameters> ) é a lista de parâmetros para o método:

```
$([Class]::Property.Method(Parameters))
```

O nome da classe deve ser totalmente qualificado com o namespace.

Por exemplo, você pode usar o seguinte código para definir uma propriedade de compilação para a data atual.

```xml
<Today>$([System.DateTime]::Now.ToString('yyyy.MM.dd'))</Today>
```

### <a name="msbuild-property-functions"></a>Funções de propriedade MSBuild

Vários métodos estáticos em sua compilação podem ser acessados para fornecer aritmética, lógica de bit a bit e suporte a caracteres de escape. Você acessa esses métodos usando a sintaxe a seguir, em que \<Method> é o nome do método e ( \<Parameters> ) é a lista de parâmetros para o método.

```
$([MSBuild]::Method(Parameters))
```

Por exemplo, para adicionar duas propriedades com valores numéricos, use o código a seguir.

```
$([MSBuild]::Add($(NumberOne), $(NumberTwo)))
```

Aqui está uma lista de funções da propriedade MSBuild:

|Assinatura de função|Descrição|
|------------------------|-----------------|
|double Add(double a, double b)|Adicionar dois duplos.|
|long Add(long a, long b)|Adicionar dois longos.|
|double Subtract(double a, double b)|Subtrair dois duplos.|
|long Subtract(long a, long b)|Subtrair dois longos.|
|double Multiply(double a, double b)|Multiplicar dois duplos.|
|long Multiply(long a, long b)|Multiplicar dois longos.|
|double Divide(double a, double b)|Dividir dois duplos.|
|long Divide(long a, long b)|Dividir dois longos.|
|double Modulo(double a, double b)|Modular dois duplos.|
|long Modulo(long a, long b)|Modular dois longos.|
|string Escape(string unescaped)|Escapar a cadeia de caracteres de acordo com a regras de escape do MSBuild.|
|string Unescape(string escaped)|Deixar sem escape a cadeia de caracteres de acordo com a regras de escape do MSBuild.|
|int BitwiseOr(int first, int second)|Realiza um `OR` bit a bit no primeiro e segundo (first &#124; second).|
|int BitwiseAnd(int first, int second)|Realizar um bit a bit `AND` no primeiro e segundo (primeiro e segundo).|
|int BitwiseXor(int first, int second)|Realizar um bit a bit `XOR` no primeiro e segundo (primeiro ^ segundo).|
|int BitwiseNot(int first)|Realizar um bit a bit `NOT` (~primeiro).|
|bool IsOsPlatform(string platformString)|Especifique se a plataforma do sistema operacional atual é `platformString`. `platformString` deve ser um membro do <xref:System.Runtime.InteropServices.OSPlatform>.|
|bool IsOSUnixLike()|True se o sistema operacional atual for um sistema Unix.|
|string NormalizePath(params string[] path)|Obtém o caminho completo canonizado do caminho fornecido e garante que ele contém os caracteres do separador de diretório corretos para o sistema operacional atual.|
|string NormalizeDirectory(params string[] path)|Obtém o caminho completo canonizado do diretório fornecido e garante que ele contém os caracteres do separador de diretório corretos para o sistema operacional atual, enquanto garante que tem uma barra à direita.|
|string EnsureTrailingSlash(string path)|Se o caminho especificado não tiver uma barra à direita, adicione uma. Se o caminho for uma cadeia de caracteres vazia, não a modifique.|
|string GetPathOfFileAbove(string file, string startingDirectory)|Pesquisa e retorna o caminho completo para um arquivo na estrutura de diretório acima do local do arquivo de compilação atual ou com base em `startingDirectory` , se especificado.|
|GetDirectoryNameOfFileAbove(string startingDirectory, string fileName)|Localize e retorne o diretório de um arquivo no diretório especificado ou em um local na estrutura de diretório acima desse diretório.|
|string MakeRelative(string basePath, string path)|Torna o `path` relativo a `basePath`. `basePath` deve ser um diretório absoluto. Se `path` não puder ser tornado relativo, ele será retornado de forma textual. Similar a `Uri.MakeRelativeUri`.|
|string ValueOrDefault(string conditionValue, string defaultValue)|Retorna a cadeia de caracteres no parâmetro 'defaultValue' somente se o parâmetro 'conditionValue' está vazio, caso contrário, retorna o valor conditionValue.|

## <a name="nested-property-functions"></a>Funções de propriedade aninhadas

Você pode combinar funções de propriedade para formar funções mais complexas, como mostra o exemplo a seguir.

```
$([MSBuild]::BitwiseAnd(32, $([System.IO.File]::GetAttributes(tempFile))))
```

Este exemplo retorna o valor dos bits (32 ou 0) do <xref:System.IO.FileAttributes>`Archive` do arquivo dado pelo caminho `tempFile`. Observe que os valores dos dados enumerados não podem aparecer por nome nas funções de propriedade. O valor numérico (32) deve ser usado em seu lugar.

Metadados também podem aparecer em funções de propriedade aninhadas. Para obter mais informações, consulte [Envio em lote](../msbuild/msbuild-batching.md).

## <a name="msbuild-doestaskhostexist"></a>MSBuild DoesTaskHostExist

A função de propriedade `DoesTaskHostExist` no MSBuild retorna se um host de tarefas está instalado atualmente para os valores de runtime e arquitetura especificados.

Essa função de propriedade tem a seguinte sintaxe:

```
$([MSBuild]::DoesTaskHostExist(string theRuntime, string theArchitecture))
```

## <a name="msbuild-ensuretrailingslash"></a>EnsureTrailingSlash do MSBuild

A função de propriedade `EnsureTrailingSlash` no MSBuild adicionará uma barra à direita se não houver.

Essa função de propriedade tem a seguinte sintaxe:

```
$([MSBuild]::EnsureTrailingSlash('$(PathProperty)'))
```

## <a name="msbuild-getdirectorynameoffileabove"></a>MSBuild GetDirectoryNameOfFileAbove

A função da propriedade `GetDirectoryNameOfFileAbove` procura por um arquivo nos diretórios acima do diretório atual no caminho.

 Essa função de propriedade tem a seguinte sintaxe:

```
$([MSBuild]::GetDirectoryNameOfFileAbove(string ThePath, string TheFile))
```

 O código a seguir mostra um exemplo dessa sintaxe.

```xml
<Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), EnlistmentInfo.props))\EnlistmentInfo.props" Condition=" '$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), EnlistmentInfo.props))' != '' " />
```

## <a name="msbuild-getpathoffileabove"></a>GetPathOfFileAbove do MSBuild

A `GetPathOfFileAbove` função de propriedade no MSBuild retorna o caminho do arquivo especificado, se estiver localizado na estrutura de diretório acima do diretório atual. É funcionalmente equivalente a chamar

```xml
<Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), dir.props))\dir.props" />
```

Essa função de propriedade tem a seguinte sintaxe:

```
$([MSBuild]::GetPathOfFileAbove(dir.props))
```

## <a name="msbuild-getregistryvalue"></a>MSBuild GetRegistryValue

A função da propriedade `GetRegistryValue` do MSBuild retorna o valor de uma chave de registro. Essa função usa dois argumentos, o nome da chave e o nome do valor, e retorna o valor do registro. Se você não especificar um nome de valor, o valor padrão será retornado.

Os exemplos a seguir mostram como a função é usada:

```
$([MSBuild]::GetRegistryValue(`HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\10.0\Debugger`, ``))                                  // default value
$([MSBuild]::GetRegistryValue(`HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\10.0\Debugger`, `SymbolCacheDir`))
$([MSBuild]::GetRegistryValue(`HKEY_LOCAL_MACHINE\SOFTWARE\(SampleName)`, `(SampleValue)`))             // parens in name and value
```

## <a name="msbuild-getregistryvaluefromview"></a>MSBuild GetRegistryValueFromView

A função de propriedade `GetRegistryValueFromView` do MSBuild obtém os dados de registro do sistema, dados a chave do registro, o valor e uma ou mais exibições de registro solicitada. A chave e o valor são pesquisados em cada exibição do registo em ordem até serem encontrados.

A sintaxe para essa função de propriedade é:

```
[MSBuild]::GetRegistryValueFromView(string keyName, string valueName, object defaultValue, params object[] views)
```

O sistema operacional Windows de 64 bits mantém uma chave de registro **HKEY_LOCAL_MACHINE \software\wow6432node** que apresenta uma exibição de registro de **HKEY_LOCAL_MACHINE \Software** para aplicativos de 32 bits.

Por padrão, um aplicativo de 32 bits em execução no WOW64 acessa a exibição do registro de 32 bits e um aplicativo de 64 bits acessa a exibição do registro de 64 bits.

As seguintes exibições de registro estão disponíveis:

|Exibição do Registro|Definição|
|-------------------|----------------|
|RegistryView.Registry32|A exibição do registro do aplicativo de 32 bits.|
|RegistryView.Registry64|A exibição do registro do aplicativo de 64 bits.|
|RegistryView.Default|A exibição do registro que corresponde ao processo em que o aplicativo está sendo executado.|

A seguir, é mostrado um exemplo.

 ```
$([MSBuild]::GetRegistryValueFromView('HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SDKs\Silverlight\v3.0\ReferenceAssemblies', 'SLRuntimeInstallPath', null, RegistryView.Registry64, RegistryView.Registry32))
```

Obtém os dados de **SLRuntimeInstallPath** da chave **ReferenceAssemblies** , examinando primeiro a exibição do registro de 64 bits e, em seguida, na exibição de registro de 32 bits.

## <a name="msbuild-makerelative"></a>MSBuild MakeRelative

A função de propriedade `MakeRelative` do MSBuild retorna o caminho relativo do segundo caminho relativo ao primeiro caminho. Cada caminho pode ser um arquivo ou pasta.

Essa função de propriedade tem a seguinte sintaxe:

```
$([MSBuild]::MakeRelative($(FileOrFolderPath1), $(FileOrFolderPath2)))
```

O código a seguir mostra um exemplo dessa sintaxe.

```xml
<PropertyGroup>
    <Path1>c:\users\</Path1>
    <Path2>c:\users\username\</Path2>
</PropertyGroup>

<Target Name = "Go">
    <Message Text ="$([MSBuild]::MakeRelative($(Path1), $(Path2)))" />
    <Message Text ="$([MSBuild]::MakeRelative($(Path2), $(Path1)))" />
</Target>

<!--
Output:
   username\
   ..\
-->
```

## <a name="msbuild-valueordefault"></a>MSBuild ValueOrDefault

A função de propriedade `ValueOrDefault` do MSBuild retorna o primeiro argumento, a menos que seja nulo ou esteja vazio. Se o primeiro argumento for nulo ou estiver vazio, a função retornará o segundo argumento.

Os exemplos a seguir mostram como essa função é usada.

```xml
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <PropertyGroup>
        <Value1>$([MSBuild]::ValueOrDefault('$(UndefinedValue)', 'a'))</Value1>
        <Value2>$([MSBuild]::ValueOrDefault('b', '$(Value1)'))</Value2>
    </PropertyGroup>

    <Target Name="MyTarget">
        <Message Text="Value1 = $(Value1)" />
        <Message Text="Value2 = $(Value2)" />
    </Target>
</Project>

<!--
Output:
  Value1 = a
  Value2 = b
-->
```

## <a name="msbuild-condition-functions"></a>Funções de condição do MSBuild

As funções `Exists` e `HasTrailingSlash` não são funções de propriedade. Eles estão disponíveis para uso com o `Condition` atributo. Consulte [condições do MSBuild](msbuild-conditions.md).

## <a name="see-also"></a>Veja também

- [Propriedades do MSBuild](../msbuild/msbuild-properties.md)

- [Visão geral do MSBuild](../msbuild/msbuild.md)
