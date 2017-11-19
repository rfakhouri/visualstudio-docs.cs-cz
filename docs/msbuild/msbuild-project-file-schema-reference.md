---
title: "Referenční dokumentace schématu souboru projektu nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords: MSBuild, file schema
ms.assetid: d9a68146-1f43-4621-ac78-2c8c3f400936
caps.latest.revision: "19"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: a88962b87466a2345ac8dafa642d457a6fee5be0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-project-file-schema-reference"></a>Referenční dokumentace schématu souboru projektu nástroje MSBuild
Poskytuje tabulku všech [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] schématu XML elementů pomocí jejich dostupné atributy a podřízené elementy.  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]soubory projektu používá dáte pokyn, aby modul sestavení co a jak ji od sestavit sestavení. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]soubory projektu jsou soubory formátu XML, které dodržovat [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] schématu XML. Tato část popisuje soubor definice (.xsd) schéma XML pro [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].  
  
## <a name="msbuild-xml-schema-elements"></a>Prvky schématu XML nástroje MSBuild  
 V následující tabulce jsou uvedeny všechny [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] prvků schématu XML spolu s jejich podřízené elementy a atributy.  
  
|Prvek|Podřízené elementy|Atributy|  
|-------------|--------------------|----------------|  
|[Choose – prvek (MSBuild)](../msbuild/choose-element-msbuild.md)|v opačném případě<br /><br /> Kdy|--|  
|[Import – Element (MSBuild)](../msbuild/import-element-msbuild.md)|--|Podmínka<br /><br /> Project|  
|[ImportGroup – Element](../msbuild/importgroup-element.md)|Import|Podmínka|  
|[Item – Element (MSBuild)](../msbuild/item-element-msbuild.md)|*Itemmetadata –*|Podmínka<br /><br /> Vyloučení<br /><br /> Zařadit členy<br /><br /> Odebrat|  
|[ItemDefinitionGroup – Element (MSBuild)](../msbuild/itemdefinitiongroup-element-msbuild.md)|*Položka*|Podmínka|  
|[ItemGroup – Element (MSBuild)](../msbuild/itemgroup-element-msbuild.md)|*Položka*|Podmínka|  
|[Itemmetadata – Element (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)|*Položka*|Podmínka|  
|[OnError – Element (MSBuild)](../msbuild/onerror-element-msbuild.md)|--|Podmínka<br /><br /> ExecuteTargets|  
|[Otherwise – Element (MSBuild)](../msbuild/otherwise-element-msbuild.md)|Zvolte<br /><br /> ItemGroup<br /><br /> PropertyGroup –|--|  
|[Output – Element (MSBuild)](../msbuild/output-element-msbuild.md)|--|Podmínka<br /><br /> Název položky<br /><br /> PropertyName<br /><br /> Parametr úkolu|  
|[Parameter – Element](../msbuild/parameter-element.md)|--|Výstup<br /><br /> ParameterType<br /><br /> Požadováno|  
|[ParameterGroup – Element](../msbuild/parametergroup-element.md)|*Parametr*|--|  
|[Project – Element (MSBuild)](../msbuild/project-element-msbuild.md)|Zvolte<br /><br /> Import<br /><br /> ItemGroup<br /><br /> ProjectExtensions<br /><br /> PropertyGroup –<br /><br /> cíl<br /><br /> Usingtask –|Defaulttargets –<br /><br /> InitialTargets<br /><br /> Atribut ToolsVersion<br /><br /> TreatAsLocalProperty<br /><br /> atribut xmlns|  
|[ProjectExtensions – Element (MSBuild)](../msbuild/projectextensions-element-msbuild.md)|--|--|  
|[Property – Element (MSBuild)](../msbuild/property-element-msbuild.md)|--|Podmínka|  
|[PropertyGroup – Element (MSBuild)](../msbuild/propertygroup-element-msbuild.md)|*Vlastnost*|Podmínka|  
|[Target – Element (MSBuild)](../msbuild/target-element-msbuild.md)|OnError<br /><br /> *Úloha*|AfterTargets<br /><br /> BeforeTargets<br /><br /> Podmínka<br /><br /> DependsOnTargets<br /><br /> Vstupy<br /><br /> KeepDuplicateOutputs<br /><br /> Název<br /><br /> Výstupy<br /><br /> Vrací|  
|[Task – Element (MSBuild)](../msbuild/task-element-msbuild.md)|Výstup|Podmínka<br /><br /> ContinueOnError –<br /><br /> *Parametr*|  
|[Taskbody – Element (MSBuild)](../msbuild/taskbody-element-msbuild.md)|*Data*|Vyhodnocení|  
|[Usingtask – Element (MSBuild)](../msbuild/usingtask-element-msbuild.md)|ParameterGroup<br /><br /> Taskbody –|AssemblyFile<br /><br /> AssemblyName<br /><br /> Podmínka<br /><br /> TaskFactory<br /><br /> Název úlohy|  
|[Když – Element (MSBuild)](../msbuild/when-element-msbuild.md)|Zvolte<br /><br /> ItemGroup<br /><br /> PropertyGroup –|Podmínka|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Podmínky](../msbuild/msbuild-conditions.md)   
 [MSBuild – Reference](../msbuild/msbuild-reference.md)  
 [Nástroje MSBuild](../msbuild/msbuild.md)