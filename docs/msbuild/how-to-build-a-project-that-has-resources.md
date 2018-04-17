---
title: 'Postupy: sestavení projektu, který má prostředky | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- resource files, compiling with MSBuild
- resources [Visual Studio], compiling with MSBuild
- projects [.NET Framework], building
- MSBuild, building a project with resources
ms.assetid: d07ac73f-2c2d-4e9a-812a-6dcb632bafe2
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1932a49af8d6a7ebd6a72ec42700bf51554990bd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
[MSBuild](../msbuild/msbuild.md)  
 [Generateresource – úloha](../msbuild/generateresource-task.md)   
 [CSC – úloha](../msbuild/csc-task.md)   
 [Resgen.exe (generátor zdrojových souborů)](/dotnet/framework/tools/resgen-exe-resource-file-generator)