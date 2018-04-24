---
title: 'Postupy: Vyčištění sestavení | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- Exec task [MSBuild]
- MSBuild, cleaning a build
- directories [.NET Framework], for output items
- output, removing items
ms.assetid: 999ba473-b0c4-45c7-930a-63ea7a510509
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 36e9af303b91cc0cdabc184f7ced329289eb7bd8
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-clean-a-build"></a>Postupy: Vyčištění sestavení
Při čištění sestavení se odstraní všechny zprostředkující a výstupní soubory, ponechat pouze soubory projektu a součást. Ze souborů projektu a součást nové instance třídy mezilehlých a výstupní soubory pak se dají vytvářet. Knihovny běžných úloh, které je k dispozici s [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] zahrnuje [Exec](../msbuild/exec-task.md) úlohu, která můžete použít ke spuštění příkazů systému. Další informace o knihovně úlohy najdete v tématu [– Reference úlohy](../msbuild/msbuild-task-reference.md).  
  
## <a name="creating-a-directory-for-output-items"></a>Vytváření adresářů pro výstupní položky  
 Ve výchozím nastavení je umístěn soubor .exe, který se vytvoří při sestavení projektu, ve stejném adresáři jako projektu a zdrojových souborech. Však se většinou, výstupní položky vytvořené v samostatném adresáři.  
  
#### <a name="to-create-a-directory-for-output-items"></a>K vytvoření adresáře pro výstupní položky  
  
1.  Použití `Property` element zadat umístění a název adresáře. Můžete například vytvořit adresář s názvem `BuiltApp` v adresáři, který obsahuje projektu a zdrojových souborech:  
  
     `<builtdir>BuiltApp</builtdir>`  
  
2.  Použití [makedir –](../msbuild/makedir-task.md) úloh vytvořit adresář, pokud adresář neexistuje. Příklad:  
  
     `<MakeDir Directories = "$(builtdir)"`  
  
     `Condition = "!Exists('$(builtdir)')" />`  
  
## <a name="removing-the-output-items"></a>Odebírání položek výstup  
 Před vytvořením nové instance třídy zprostředkující a výstupní soubory, může chcete vymazat všechny předchozí instance zprostředkující a výstupní soubory. Použití [removedir –](../msbuild/removedir-task.md) úloha odstranění adresáře a všechny soubory a adresáře, které obsahuje z disku.  
  
#### <a name="to-remove-a-directory-and-all-files-contained-in-the-directory"></a>Chcete-li odebrat adresář a všechny soubory obsažené v adresáři  
  
-   Použití `RemoveDir` na odebrat adresář úlohy. Příklad:  
  
     `<RemoveDir Directories="$(builtdir)" />`  
  
## <a name="example"></a>Příklad  
 Následující kód například projekt obsahuje nový cíl, `Clean`, která používá `RemoveDir` úloha odstranění adresáře a všechny soubory a adresáře, které obsahuje. Také v tomto příkladu `Compile` cíl vytvoří samostatné adresář pro výstupní položky, které jsou odstraněny při sestavení byla vyčištěna.  
  
 `Compile` je definován jako výchozí cíl a je proto použít automaticky Pokud zadáte jiný cíl nebo cíle. Použijte přepínač příkazového řádku **/target** k zadejte jiný cíl. Příklad:  
  
 `msbuild <file name>.proj /target:Clean`  
  
 **/Target** přepínač může být zkrátí tak, aby **/t** a můžete určit více než jeden cíl. Chcete-li například použít cíl `Clean` pak cíl `Compile`, typ:  
  
 `msbuild <file name>.proj /t:Clean;Compile`  
  
```xml  
<Project DefaultTargets = "Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <PropertyGroup>  
        <!-- Set the application name as a property -->  
        <name>HelloWorldCS</name>  
  
        <!-- Set the output folder as a property -->  
        <builtdir>BuiltApp</builtdir>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <!-- Specify the inputs by type and file name -->  
        <CSFile Include = "consolehwcs1.cs"/>  
    </ItemGroup>  
  
    <Target Name = "Compile">  
        <!-- Check whether an output folder exists and create  
        one if necessary -->  
        <MakeDir Directories = "$(builtdir)"   
            Condition = "!Exists('$(builtdir)')" />  
  
        <!-- Run the Visual C# compiler -->  
        <CSC Sources = "@(CSFile)"   
            OutputAssembly = "$(BuiltDir)\$(appname).exe">  
            <Output TaskParameter = "OutputAssembly"  
                ItemName = "EXEFile" />  
        </CSC>  
  
        <!-- Log the file name of the output file -->  
        <Message Text="The output file is @(EXEFile)"/>  
    </Target>  
  
    <Target Name = "Clean">  
        <RemoveDir Directories="$(builtdir)" />  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Exec – úloha](../msbuild/exec-task.md)   
 [Makedir – úloha](../msbuild/makedir-task.md)   
 [Removedir – úloha](../msbuild/removedir-task.md)   
 [CSC – úloha](../msbuild/csc-task.md)   
 [Cíle](../msbuild/msbuild-targets.md)