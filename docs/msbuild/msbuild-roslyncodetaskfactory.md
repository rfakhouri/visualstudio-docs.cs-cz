---
title: Úlohy nástroje MSBuild vložené s RoslynCodeTaskFactory | Microsoft Docs
ms.custom: ''
ms.date: 09/21/2017
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, tasks
ms.assetid: e72e6506-4a11-4edf-ae8d-cfb5a3b9d8a0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b12d0ae775d37a436898bb34acca0c7f4a50e649
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37059335"
---
# <a name="msbuild-inline-tasks-with-roslyncodetaskfactory"></a>Vložené úlohy nástroje MSBuild s RoslynCodeTaskFactory
Podobně jako [CodeTaskFactory](../msbuild/msbuild-inline-tasks.md), RoslynCodeTaskFactory používá ke generování sestavení úloh v paměti pro použití jako vložené úlohy kompilátory Roslyn napříč platformami.  Úlohy RolynCodeTaskFactory zacílit .NET Standard a může pracovat na rozhraní .NET Framework a .NET Core moduly runtime a také jiné platformy jako Linux a Mac OS.

**Poznámka:** `RolynCodeTaskFactory` je k dispozici v MSBuild 15.8 a výše pouze.
  
## <a name="the-structure-of-an-inline-task-with-roslyncodetaskfactory"></a>Struktura vložené úlohy s RoslynCodeTaskFactory
 Vložené úlohy RoslynCodeTaskFactory jsou deklarovány stejným způsobem jako [CodeTaskFactory](../msbuild/msbuild-inline-tasks.md). Jediným rozdílem je, že cílí .NET Standard.  Vložené úlohy a `UsingTask` element, který jej obsahuje obvykle součástí souboru .targets a naimportovat do jiných souborů projektu podle potřeby. Zde je základní vložené úlohy. Všimněte si, že ho neprovede žádnou akci.  
  
```xml  
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- This simple inline task does nothing. -->  
  <UsingTask  
    TaskName="DoNothing"  
    TaskFactory="RoslynCodeTaskFactory"  
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
  
 `UsingTask` Element v příkladu má tři atributy, které popisují úlohy a úkolů vložený objekt factory, který zkompiluje ho.  
  
-   `TaskName` Názvy atributů, úlohy, v takovém případě `DoNothing`.  
  
-   `TaskFactory` Třídu, která implementuje objektu pro vytváření úloh vložené názvy atributů.  
  
-   `AssemblyFile` Atribut poskytuje umístění objektu pro vytváření úloh vložené. Alternativně můžete použít `AssemblyName` atribut zadat plně kvalifikovaný název vloženého třídu objektů factory úloh, která se obvykle nachází v globální mezipaměti sestavení (GAC).  
  
 Zbývající prvků `DoNothing` úloh jsou prázdné a je určen k objasnění pořadí a struktura vložené úlohy. Robustnější příkladu je uvedené dále v tomto tématu.  
  
-   `ParameterGroup` Prvek je volitelný. -Li zadána, deklaruje parametry úlohy. Další informace o vstupní a výstupní parametry najdete v části "Vstupní a výstupní parametry" dál v tomto tématu.  
  
-   `Task` Element popisuje a obsahuje zdrojový kód úloh.  
  
-   `Reference` Element určuje odkazy na sestavení .NET, které používáte ve svém kódu. Jde o ekvivalent přidat odkaz na projekt v sadě Visual Studio. `Include` Atribut určuje cestu odkazované sestavení.  
  
-   `Using` Element uvádí obory názvů, které chcete získat přístup. To se podobá `Using` příkaz v jazyce Visual C#. `Namespace` Atribut určuje obor názvů, které chcete zahrnout.  
  
 `Reference` a `Using` prvky jsou jazykově nezávislého. Vložené úlohy může být napsán v některém z podporovaných jazyků .NET CodeDom, například jazyka Visual Basic nebo Visual C#.  
  
> [!NOTE]
>  Elementů obsažených `Task` element jsou specifické pro úlohy vytváření, v takovém případě objektu pro vytváření úloh kódu.  
  
### <a name="code-element"></a>Element Code  
 Poslední podřízený element se objeví v rámci `Task` elementu je `Code` elementu. `Code` Obsahuje element, nebo vyhledá kód, který chcete být zkompilovány do úlohy. Umístit do `Code` element závisí na tom, jak chcete zapsat úlohu.  
  
 `Language` Atribut určuje jazyk, ve kterém je zadán kód. Přípustné hodnoty jsou `cs` pro jazyk C#, `vb` jazyka Visual Basic.  
  
 `Type` Atribut určuje typ kód, který se nachází v `Code` elementu.  
  
-   Pokud hodnota `Type` je `Class`, pak se `Code` element obsahuje kód pro třídu, která pochází z <xref:Microsoft.Build.Framework.ITask> rozhraní.  
  
-   Pokud hodnota `Type` je `Method`, kód definuje přepsání `Execute` metodu <xref:Microsoft.Build.Framework.ITask> rozhraní.  
  
-   Pokud hodnota `Type` je `Fragment`, kód definuje obsah `Execute` metoda, ale není podpis nebo `return` příkaz.  
  
 Samotný kód se obvykle zobrazují mezi `<![CDATA[` značky a `]]>` značky. Protože kód je v oddílu CDATA, nemusíte starat o uvozovací znaky vyhrazené znaky, například "\<" nebo ">".  
  
 Alternativně můžete použít `Source` atribut `Code` element k určení umístění souboru, který obsahuje kód pro úlohu. Kód zdrojového souboru musí být typu, která je zadána `Type` atribut. Pokud `Source` atribut je k dispozici, výchozí hodnota `Type` je `Class`. Pokud `Source` nejsou k dispozici, výchozí hodnota je `Fragment`.  
  
> [!NOTE]
>  Při definování třída úlohy ve zdrojovém souboru, název třídy, musíte souhlasit s `TaskName` atribut odpovídající [usingtask –](../msbuild/usingtask-element-msbuild.md) elementu.  
  
## <a name="hello-world"></a>Hello World  
 Zde je robustnější vložené úlohy s RoslynCodeTaskFactory. Zobrazí úlohu HelloWorld "Hello, world!" v zařízení výchozí protokolování chyb, který je obvykle systémové konzoly nebo sady Visual Studio **výstup** okno. `Reference` Element v příkladu je zahrnutý jenom pro obrázek.  
  
```xml  
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- This simple inline task displays "Hello, world!" -->  
  <UsingTask  
    TaskName="HelloWorld"  
    TaskFactory="RoslynCodeTaskFactory"  
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
  
 Může úloha HelloWorld uložení v souboru, který je pojmenován HelloWorld.targets a pak ho následujícím způsobem vyvolat z projektu.  
  
```xml  
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <Import Project="HelloWorld.targets" />  
  <Target Name="Hello">  
    <HelloWorld />  
  </Target>  
</Project>  
```  
  
## <a name="input-and-output-parameters"></a>Vstupní a výstupní parametry  
 Parametry úlohy vložené jsou podřízených elementů `ParameterGroup` elementu. Název elementu, který ji definuje přebírá každý parametr. Následující kód definuje parametr `Text`.  
  
```xml  
<ParameterGroup>  
    <Text />  
</ParameterGroup>  
```  
  
 Parametry může mít jeden nebo více těchto atributů:  
  
-   `Required` je volitelný atribut, který je `false` ve výchozím nastavení. Pokud `true`, pak parametr je povinná a musí být zadána hodnota před voláním úlohu.  
  
-   `ParameterType` je volitelný atribut, který je `System.String` ve výchozím nastavení. Může být nastaven na žádný plně kvalifikovaný typ, který je určitá položka nebo hodnotu, která může být převeden do a z řetězce pomocí System.Convert.ChangeType. (Jinými slovy, žádný typ, který se dá předat do a z externí úkolů.)  
  
-   `Output` je volitelný atribut, který je `false` ve výchozím nastavení. Pokud `true`, pak parametr musí být zadána hodnota před návratem od Metoda Execute.  
  
Například  
  
```xml  
<ParameterGroup>  
    <Expression Required="true" />  
    <Files ParameterType="Microsoft.Build.Framework.ITaskItem[]" Required="true" />  
    <Tally ParameterType="System.Int32" Output="true" />  
</ParameterGroup>  
```  
  
definuje tyto tři parametry:  
  
-   `Expression` je povinný vstupní parametr typu System.String.  
  
-   `Files` je požadovaná položka vstupní parametr seznamu.  
  
-   `Tally` je výstupní parametr typu System.Int32.  
  
 Pokud `Code` má element `Type` atribut `Fragment` nebo `Method`, pak vlastnosti se vytvářejí automaticky pro všechny parametry. Vlastnosti, jinak hodnota musí být explicitně deklarován ve zdrojovém kódu úloh a musí přesně shodovat jejich definicemi parametrů.  
  
## <a name="example"></a>Příklad  
 Následující vložené úlohy protokolů některé zprávy a vrátí řetězec.  
  
```xml  
<Project xmlns='http://schemas.microsoft.com/developer/msbuild/2003' ToolsVersion="15.0">  
  
    <UsingTask TaskName="MySample"
               TaskFactory="RoslynCodeTaskFactory"
               AssemblyFile="$(MSBuildBinPath)\Microsoft.Build.Tasks.Core.dll">
        <ParameterGroup>
            <Parameter1 ParameterType="System.String" Required="true" />
            <Parameter2 ParameterType="System.String" />
            <Parameter3 ParameterType="System.String" Output="true" />
        </ParameterGroup>
        <Task>
            <Using Namespace="System" />
            <Code Type="Fragment" Language="C#">
              <![CDATA[
              Log.LogMessage(MessageImportance.High, "Hello from an inline task created by Roslyn!");
              Log.LogMessageFromText($"Parameter1: '{Parameter1}'", MessageImportance.High);
              Log.LogMessageFromText($"Parameter2: '{Parameter2}'", MessageImportance.High);
              Parameter3 = "A value from the Roslyn CodeTaskFactory";
            ]]>
            </Code>
        </Task>
    </UsingTask>
  
    <Target Name="Demo">  
      <MySample Parameter1="A value for parameter 1" Parameter2="A value for parameter 2">
          <Output TaskParameter="Parameter3" PropertyName="NewProperty" />
      </MySample>

      <Message Text="NewProperty: '$(NewProperty)'" />
    </Target>  
</Project>  
```  

 Tyto vložené úlohy můžete kombinovat cesty a získat název souboru.  
  
```xml  
<Project xmlns='http://schemas.microsoft.com/developer/msbuild/2003' ToolsVersion="15.0">  
  
    <UsingTask TaskName="PathCombine"
               TaskFactory="RoslynCodeTaskFactory"
               AssemblyFile="$(MSBuildBinPath)\Microsoft.Build.Tasks.Core.dll">
        <ParameterGroup>
            <Paths ParameterType="System.String[]" Required="true" />
            <Combined ParameterType="System.String" Output="true" />
        </ParameterGroup>
        <Task>
            <Using Namespace="System" />
            <Code Type="Fragment" Language="C#">
            <![CDATA[
            Combined = Path.Combine(Paths);
            ]]>
            </Code>
        </Task>
    </UsingTask>

    <UsingTask TaskName="PathGetFileName"
             TaskFactory="RoslynCodeTaskFactory"
             AssemblyFile="$(MSBuildBinPath)\Microsoft.Build.Tasks.Core.dll">
        <ParameterGroup>
            <Path ParameterType="System.String" Required="true" />
            <FileName ParameterType="System.String" Output="true" />
        </ParameterGroup>
        <Task>
            <Using Namespace="System" />
            <Code Type="Fragment" Language="C#">
            <![CDATA[
            FileName = System.IO.Path.GetFileName(Path);
            ]]>
            </Code>
        </Task>
    </UsingTask>
  
    <Target Name="Demo">  
        <PathCombine Paths="$(Temp);MyFolder;$([System.Guid]::NewGuid()).txt">
            <Output TaskParameter="Combined" PropertyName="MyCombinedPaths" />
        </PathCombine>

        <Message Text="Combined Paths: '$(MyCombinedPaths)'" />

        <PathGetFileName Path="$(MyCombinedPaths)">
            <Output TaskParameter="FileName" PropertyName="MyFileName" />
        </PathGetFileName>

        <Message Text="File name: '$(MyFileName)'" />
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Návod: Vytvoření vložené úlohy](../msbuild/walkthrough-creating-an-inline-task.md)
