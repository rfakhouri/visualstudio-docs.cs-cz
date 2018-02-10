---
title: "Úlohy nástroje MSBuild vložené | Microsoft Docs"
ms.custom: 
ms.date: 09/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, tasks
ms.assetid: e72e6506-4a11-4edf-ae8d-cfb5a3b9d8a0
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d0e6ac51448f014e9d37e5e1521c01f3dfc903b0
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="msbuild-inline-tasks"></a>Vložené úlohy nástroje MSBuild
Úlohy nástroje MSBuild obvykle vytváří kompilování třídu, která implementuje <xref:Microsoft.Build.Framework.ITask> rozhraní. Další informace najdete v tématu [úlohy](../msbuild/msbuild-tasks.md).  
  
 Od verze rozhraní .NET Framework verze 4, můžete vytvořit úlohy vložené v souboru projektu. Chcete-li vytvořit samostatné sestavení pro hostování úlohy nemáte. To usnadňuje ke sledování zdrojového kódu a snazší nasazování úlohu. Zdrojový kód je integrovaná do skriptu.  
  
## <a name="the-structure-of-an-inline-task"></a>Struktura vložené úlohy  
 Vložené úlohy je obsažený v [usingtask –](../msbuild/usingtask-element-msbuild.md) elementu. Vložené úlohy a `UsingTask` element, který jej obsahuje obvykle součástí souboru .targets a naimportovat do jiných souborů projektu podle potřeby. Zde je základní vložené úlohy. Všimněte si, že ho neprovede žádnou akci.  
  
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
  
 `UsingTask` Element v příkladu má tři atributy, které popisují úlohy a úkolů vložený objekt factory, který zkompiluje ho.  
  
-   `TaskName` Názvy atributů, úlohy, v takovém případě `DoNothing`.  
  
-   `TaskFactory` Třídu, která implementuje objektu pro vytváření úloh vložené názvy atributů.  
  
-   `AssemblyFile` Atribut poskytuje umístění objektu pro vytváření úloh vložené. Alternativně můžete použít `AssemblyName` atribut zadat plně kvalifikovaný název vloženého třídu objektů factory úloh, která se obvykle nachází v globální mezipaměti sestavení (GAC).  
  
 Zbývající prvků `DoNothing` úloh jsou prázdné a je určen k objasnění pořadí a struktura vložené úlohy. Robustnější příkladu je uvedené dále v tomto tématu.  
  
-   `ParameterGroup` Prvek je volitelný. -Li zadána, deklaruje parametry úlohy. Další informace o vstupní a výstupní parametry najdete v části "Vstupní a výstupní parametry" dál v tomto tématu.  
  
-   `Task` Element popisuje a obsahuje zdrojový kód úloh.  
  
-   `Reference` Element určuje odkazy na sestavení .NET, které používáte ve svém kódu. Jde o ekvivalent přidat odkaz na projekt v sadě Visual Studio. `Include` Atribut určuje cestu odkazované sestavení.  
  
-   `Using` Element uvádí obory názvů, které chcete získat přístup. To se podobá `Using` příkaz v jazyce Visual C#. `Namespace` Atribut určuje obor názvů, které chcete zahrnout.  
  
 `Reference`a `Using` prvky jsou jazykově nezávislého. Vložené úlohy může být napsán v některém z podporovaných jazyků .NET CodeDom, například jazyka Visual Basic nebo Visual C#.  
  
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
 Zde je robustnější vložené úlohy. Zobrazí úlohu HelloWorld "Hello, world!" v zařízení výchozí protokolování chyb, který je obvykle systémové konzoly nebo sady Visual Studio **výstup** okno. `Reference` Element v příkladu je zahrnutý jenom pro obrázek.  
  
```xml  
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- This simple inline task displays "Hello, world!" -->  
  <UsingTask  
    TaskName="HelloWorld"  
    TaskFactory="CodeTaskFactory"  
    AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.Core.dll" >  
    <ParameterGroup />  
    <Task>  
      <Reference Include="System.Xml.dll"/>  
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
  
-   `Required`je volitelný atribut, který je `false` ve výchozím nastavení. Pokud `true`, pak parametr je povinná a musí být zadána hodnota před voláním úlohu.  
  
-   `ParameterType`je volitelný atribut, který je `System.String` ve výchozím nastavení. Může být nastaven na žádný plně kvalifikovaný typ, který je určitá položka nebo hodnotu, která může být převeden do a z řetězce pomocí System.Convert.ChangeType. (Jinými slovy, žádný typ, který se dá předat do a z externí úkolů.)  
  
-   `Output`je volitelný atribut, který je `false` ve výchozím nastavení. Pokud `true`, pak parametr musí být zadána hodnota před návratem od Metoda Execute.  
  
 Například  
  
```xml  
<ParameterGroup>  
    <Expression Required="true" />  
      <Files ParameterType="Microsoft.Build.Framework.ITaskItem[]" Required="true" />  
    <Tally ParameterType="System.Int32" Output="true" />  
</ParameterGroup>  
```  
  
 definuje tyto tři parametry:  
  
-   `Expression`je povinný vstupní parametr typu System.String.  
  
-   `Files`je požadovaná položka vstupní parametr seznamu.  
  
-   `Tally`je výstupní parametr typu System.Int32.  
  
 Pokud `Code` má element `Type` atribut `Fragment` nebo `Method`, pak vlastnosti se vytvářejí automaticky pro všechny parametry. Vlastnosti, jinak hodnota musí být explicitně deklarován ve zdrojovém kódu úloh a musí přesně shodovat jejich definicemi parametrů.  
  
## <a name="example"></a>Příklad  
 Následující vložené úlohy nahradí všechny výskyty řetězce token v daný soubor s danou hodnotou.  
  
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
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Návod: Vytvoření vložené úlohy](../msbuild/walkthrough-creating-an-inline-task.md)