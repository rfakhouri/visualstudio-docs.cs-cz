---
title: "Postupy: sestavení projektu, který má prostředky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resource files, compiling with MSBuild
- resources [Visual Studio], compiling with MSBuild
- projects [.NET Framework], building
- MSBuild, building a project with resources
ms.assetid: d07ac73f-2c2d-4e9a-812a-6dcb632bafe2
caps.latest.revision: "14"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 42c447625093adb84f3db0c495efb7b0cfa2664e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-build-a-project-that-has-resources"></a>Postupy: Sestavení projektu, který má prostředky
Pokud vytváříte lokalizované verze projektu, musí být odděleny všechny prvky uživatelského rozhraní do zdrojových souborů pro různé jazyky. Pokud projekt používá pouze řetězce, můžete použít na soubory prostředků textových souborů. Soubory RESX můžete alternativně použít jako soubory prostředků.  
  
## <a name="compiling-resources-with-msbuild"></a>Kompilování prostředky pomocí nástroje MSBuild  
 Knihovny běžných úloh, které je k dispozici s [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] zahrnuje `GenerateResource` úlohu, která můžete použít pro kompilaci prostředky v soubory RESX a text. Tato úloha obsahuje `Sources` parametr k určení, který prostředek se soubory ke kompilaci a `OutputResources` parametr k určení názvů pro výstupní soubory prostředků. Další informace o `GenerateResource` úloh najdete v tématu [generateresource – úloha](../msbuild/generateresource-task.md).  
  
#### <a name="to-compile-resources-with-msbuild"></a>Kompilace prostředky pomocí nástroje MSBuild  
  
1.  Určit soubory projektu prostředků a předat je do `GenerateResource` buď jako položky seznamů, úloh, nebo jako názvů souborů.  
  
2.  Zadejte `OutputResources` parametr `GenerateResource` úkolu, který vám umožní nastavit názvy pro výstupní soubory prostředků.  
  
3.  Použití `Output` element úlohy k uložení hodnotu `OutputResources` parametr v položce.  
  
4.  Pomocí položky vytvořené z `Output` element jako vstup do jiná úloha.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje jak `Output` element určuje, že `OutputResources` atribut `GenerateResource` úloh bude obsahovat soubory kompilované prostředků `alpha.resources` a `beta.resources` a aby tyto dva soubory budou umístěny uvnitř `Resources` seznamu položek. Tím, že tyto soubory .resources určíte jako kolekce položek se stejným názvem, můžete snadno použít jako vstupy pro jiné úlohy, jako [Csc](../msbuild/csc-task.md) úloh.  
  
 Tato úloha je ekvivalentní k použití **/kompilovat** přepínač pro [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator):  
  
 `Resgen.exe /compile alpha.resx,alpha.resources /compile beta.txt,beta.resources`  
  
```xml  
<GenerateResource  
    Sources="alpha.resx; beta.txt"  
    OutputResources="alpha.resources; beta.resources">  
    <Output TaskParameter="OutputResources"  
        ItemName="Resources"/>  
</GenerateResource>  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad projektu obsahuje dvě úlohy: `GenerateResource` úlohy kompilace prostředky a `Csc` úloh zkompilovat soubory zdrojového kódu a soubory kompilované zdrojů. Soubory prostředků zkompilují `GenerateResource` úlohy jsou uloženy v `Resources` položky a předána `Csc` úloh.  
  
```xml  
<Project DefaultTargets = "Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <Target Name="Resources">  
        <GenerateResource  
            Sources="alpha.resx; beta.txt"  
            OutputResources="alpha.resources; beta.resources">  
            <Output TaskParameter="OutputResources"  
                ItemName="Resources"/>  
        </GenerateResource>  
    </Target>  
  
    <Target Name="Build" DependsOnTargets="Resources">  
        <Csc Sources="hello.cs"  
                Resources="@(Resources)"  
                OutputAssembly="hello.exe"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
[Nástroje MSBuild](../msbuild/msbuild.md)  
 [Generateresource – úloha](../msbuild/generateresource-task.md)   
 [CSC – úloha](../msbuild/csc-task.md)   
 [Resgen.exe (Generátor zdrojových souborů)](/dotnet/framework/tools/resgen-exe-resource-file-generator)