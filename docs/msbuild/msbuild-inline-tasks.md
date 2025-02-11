---
title: Vložené úlohy nástroje MSBuild | Microsoft Docs
ms.date: 09/21/2017
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, tasks
ms.assetid: e72e6506-4a11-4edf-ae8d-cfb5a3b9d8a0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 37597d1e1f4fde2b2e81e7aa7868c0aaff935337
ms.sourcegitcommit: 59e5758036223ee866f3de5e3c0ab2b6dbae97b6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2019
ms.locfileid: "68416849"
---
# <a name="msbuild-inline-tasks"></a>Vložené úlohy nástroje MSBuild
Úlohy nástroje MSBuild jsou obvykle vytvořeny kompilací třídy, která implementuje <xref:Microsoft.Build.Framework.ITask> rozhraní. Další informace najdete v tématu [úlohy](../msbuild/msbuild-tasks.md).

 Počínaje verzí .NET Framework 4 můžete vytvořit úlohy vložené do souboru projektu. Pro hostování úlohy není nutné vytvářet samostatné sestavení. To usnadňuje sledování zdrojového kódu a jednodušší nasazení úlohy. Zdrojový kód je integrovaný do skriptu.

 V MSBuild 15,8 byl přidán [RoslynCodeTaskFactory](../msbuild/msbuild-roslyncodetaskfactory.md) , který může vytvářet .NET Standard vložené úkoly pro různé platformy.  Pokud potřebujete použít vložené úlohy pro .NET Core, je nutné použít rozhraní RoslynCodeTaskFactory.
## <a name="the-structure-of-an-inline-task"></a>Struktura vložené úlohy
 Vložená úloha je obsažena v prvku [UsingTask](../msbuild/usingtask-element-msbuild.md) . Vložená úloha a `UsingTask` element, který obsahuje, jsou obvykle zahrnuty do souboru *. targets* a importovány do jiných souborů projektu podle potřeby. Zde je základní vložená úloha. Všimněte si, že nedělá nic.

```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <!-- This simple inline task does nothing. -->
  <UsingTask
    TaskName="DoNothing"
    TaskFactory="CodeTaskFactory"
    AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.Core.dll" >
    <ParameterGroup />
    <Task>
      <Reference Include="" />
      <Using Namespace="" />
      <Code Type="Fragment" Language="cs">
      </Code>
    </Task>
  </UsingTask>
</Project>
```

 `UsingTask` Element v příkladu má tři atributy, které popisují úlohu a vložený objekt pro vytváření úloh, který jej zkompiluje.

- Atribut pojmenuje úlohu, v tomto `DoNothing`případě. `TaskName`

- `TaskFactory` Atribut vyjmenovává třídu, která implementuje vložený objekt pro vytváření úloh.

- `AssemblyFile` Atribut poskytuje umístění vloženého objektu pro vytváření úloh. Alternativně můžete použít `AssemblyName` atribut k určení plně kvalifikovaného názvu vložené třídy úlohy Factory, která se obvykle nachází v globální mezipaměti sestavení (GAC).

Zbývající prvky `DoNothing` úkolu jsou prázdné a jsou k dispozici k ilustraci pořadí a struktury vložené úlohy. Robustnější příklad je uveden dále v tomto tématu.

- `ParameterGroup` Element je nepovinný. Je-li tento parametr zadán, deklaruje parametry pro úlohu. Další informace o vstupních a výstupních parametrech naleznete v části [vstupní a výstupní parametry](#input-and-output-parameters) dále v tomto tématu.

- `Task` Element popisuje a obsahuje zdrojový kód úkolu.

- `Reference` Element určuje odkazy na sestavení .NET, která používáte ve svém kódu. To je ekvivalentní přidání odkazu na projekt v aplikaci Visual Studio. `Include` Atribut určuje cestu odkazovaného sestavení.

- `Using` Element vypíše obory názvů, ke kterým chcete získat přístup. To se `Using` podobá příkazu ve vizuálu C#. `Namespace` Atribut určuje obor názvů, který se má zahrnout.

`Reference`a `Using` elementy jsou Language-nezávislá. Vložené úkoly lze zapsat v libovolném z podporovaných jazyků rozhraní .NET CodeDom, například Visual Basic nebo vizuálu C#.

> [!NOTE]
> Prvky obsažené `Task` v elementu jsou specifické pro objekt pro vytváření úloh, v tomto případě objekt pro vytváření úloh kódu.

### <a name="code-element"></a>Element kódu
 Poslední podřízený element, který se má zobrazit `Task` v rámci elementu `Code` , je element. `Code` Element obsahuje nebo vyhledá kód, který chcete zkompilovat do úlohy. Co vložíte do `Code` prvku závisí na tom, jak chcete vytvořit úlohu.

 `Language` Atribut určuje jazyk, ve kterém je kód napsán. Přijatelné hodnoty jsou `cs` `vb` pro C#Visual Basic.

 Atribut určuje typ kódu, který se nachází `Code` v elementu. `Type`

- Pokud `Type` je `Class`hodnota, pak `Code` element obsahuje kód <xref:Microsoft.Build.Framework.ITask> pro třídu, která je odvozena z rozhraní.

- Pokud `Type` je `Method`hodnota, pak kód definuje přepsání `Execute` metody <xref:Microsoft.Build.Framework.ITask> rozhraní.

- Pokud `Type` je `Fragment`hodnota, pak kód definuje obsah `Execute` `return` metody, ale ne signaturu nebo příkaz.

Samotný kód se obvykle objevuje mezi `<![CDATA[` značkou `]]>` a značkou. Vzhledem k tomu, že kód je v oddílu CDATA, nemusíte se starat o rezervované znaky, například\<"" nebo ">".

Alternativně můžete použít `Source` atribut `Code` prvku k určení umístění souboru, který obsahuje kód pro úlohu. Kód ve zdrojovém souboru musí být typu, který je určen `Type` atributem. Pokud je přítomen `Type` `Class`atribut, výchozí hodnota je. `Source` Pokud `Source` není k dispozici, je výchozí `Fragment`hodnota.

> [!NOTE]
> Při definování třídy Task ve zdrojovém souboru musí souhlasit název třídy s `TaskName` atributem odpovídajícího elementu [UsingTask](../msbuild/usingtask-element-msbuild.md) .

## <a name="helloworld"></a>Hell
 Tady je robustnější vložená úloha. V úloze HelloWorld se zobrazí text Hello, World! na výchozím zařízení pro protokolování chyb, což je obvykle systémová konzola nebo okno **výstup** sady Visual Studio. `Reference` Element v příkladu je zahrnut pouze pro ilustraci.

```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <!-- This simple inline task displays "Hello, world!" -->
  <UsingTask
    TaskName="HelloWorld"
    TaskFactory="CodeTaskFactory"
    AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.Core.dll" >
    <ParameterGroup />
    <Task>
      <Reference Include="System.Xml"/>
      <Using Namespace="System"/>
      <Using Namespace="System.IO"/>
      <Code Type="Fragment" Language="cs">
<![CDATA[
// Display "Hello, world!"
Log.LogError("Hello, world!");
]]>
      </Code>
    </Task>
  </UsingTask>
</Project>
```

 Můžete uložit úlohu HelloWorld v souboru s názvem *HelloWorld. targets*a potom ji vyvolat z projektu následujícím způsobem.

```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="HelloWorld.targets" />
  <Target Name="Hello">
    <HelloWorld />
  </Target>
</Project>
```

## <a name="input-and-output-parameters"></a>Vstupní a výstupní parametry
 Vložené parametry úlohy jsou podřízené prvky `ParameterGroup` elementu. Každý parametr přebírá název elementu, který ho definuje. Tento parametr `Text`definuje následující kód.

```xml
<ParameterGroup>
  <Text />
</ParameterGroup>
```

 Parametry mohou mít jeden nebo více z těchto atributů:

- `Required`je volitelný atribut, který je `false` ve výchozím nastavení. Pokud `true`je, pak je vyžadován parametr a před voláním úlohy musí být předána hodnota.

- `ParameterType`je volitelný atribut, který je `System.String` ve výchozím nastavení. Může být nastaven na libovolný plně kvalifikovaný typ, který je buď položka, nebo hodnota, která může být převedena na řetězec a z řetězce pomocí System. Convert. ChangeType. (Jinými slovy, jakýkoli typ, který lze předat do a z vnějšího úkolu.)

- `Output`je volitelný atribut, který je `false` ve výchozím nastavení. Pokud `true`, pak musí být parametru předána hodnota před návratem z metody Execute.

Například

```xml
<ParameterGroup>
  <Expression Required="true" />
  <Files ParameterType="Microsoft.Build.Framework.ITaskItem[]" Required="true" />
  <Tally ParameterType="System.Int32" Output="true" />
</ParameterGroup>
```

definuje tyto tři parametry:

- `Expression`je požadovaný vstupní parametr typu System. String.

- `Files`je požadovaný vstupní parametr seznamu položek.

- `Tally`je výstupní parametr typu System. Int32.

`Code` Pokud máelement`Fragment` atribut nebo`Method`, pak se automaticky vytvoří vlastnosti pro každý parametr. `Type` V opačném případě musí být vlastnosti explicitně deklarovány ve zdrojovém kódu úlohy a musí přesně odpovídat definicím parametrů.

## <a name="example"></a>Příklad
 Následující vložená úloha nahradí všechny výskyty tokenu v daném souboru zadanou hodnotou.

```xml
<Project xmlns='http://schemas.microsoft.com/developer/msbuild/2003' ToolsVersion="15.0">

  <UsingTask TaskName="TokenReplace" TaskFactory="CodeTaskFactory" AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.Core.dll">
    <ParameterGroup>
      <Path ParameterType="System.String" Required="true" />
      <Token ParameterType="System.String" Required="true" />
      <Replacement ParameterType="System.String" Required="true" />
    </ParameterGroup>
    <Task>
      <Code Type="Fragment" Language="cs"><![CDATA[
string content = File.ReadAllText(Path);
content = content.Replace(Token, Replacement);
File.WriteAllText(Path, content);

]]></Code>
    </Task>
  </UsingTask>

  <Target Name='Demo' >
    <TokenReplace Path="C:\Project\Target.config" Token="$MyToken$" Replacement="MyValue"/>
  </Target>
</Project>
```

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Návod: Vytvoření vložené úlohy](../msbuild/walkthrough-creating-an-inline-task.md)
