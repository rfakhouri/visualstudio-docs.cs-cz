---
title: "Referenční dokumentace schématu souboru projektu nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, file schema
ms.assetid: d9a68146-1f43-4621-ac78-2c8c3f400936
caps.latest.revision: 
author: kempb
ms.author: kempb
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b4f21f1f70a468bd22876dad04226dba5deb4c50
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="msbuild-project-file-schema-reference"></a>Referenční dokumentace schématu souboru projektu nástroje MSBuild
Poskytuje tabulku všech [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] schématu XML elementů pomocí jejich dostupné atributy a podřízené elementy.  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] soubory projektu používá dáte pokyn, aby modul sestavení co a jak ji od sestavit sestavení. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]soubory projektu jsou soubory formátu XML, které dodržovat [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] schématu XML. Tato část popisuje soubor definice (.xsd) schéma XML pro [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].  
  
## <a name="msbuild-xml-schema-elements"></a>Prvky schématu XML nástroje MSBuild  
 V následující tabulce jsou uvedeny všechny [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] prvků schématu XML spolu s jejich podřízené elementy a atributy.  
  
|Prvek|Podřízené elementy|Atributy|  
|-------------|--------------------|----------------|  
|[Choose – element (MSBuild)](../msbuild/choose-element-msbuild.md)|v opačném případě<br /><br /> Kdy|--|  
|[Import – element (MSBuild)](../msbuild/import-element-msbuild.md)|--|Podmínka<br /><br /> Projekt|  
|[ImportGroup – element](../msbuild/importgroup-element.md)|Import|Podmínka|  
|[Item – element (MSBuild)](../msbuild/item-element-msbuild.md)|*ItemMetaData*|Podmínka<br /><br /> Vyloučení<br /><br /> Zařadit členy<br /><br /> Odebrat|  
|[ItemDefinitionGroup – element (MSBuild)](../msbuild/itemdefinitiongroup-element-msbuild.md)|*Položka*|Podmínka|  
|[ItemGroup – element (MSBuild)](../msbuild/itemgroup-element-msbuild.md)|*Položka*|Podmínka|  
|[ItemMetadata – element (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)|*Položka*|Podmínka|  
|[OnError – element (MSBuild)](../msbuild/onerror-element-msbuild.md)|--|Podmínka<br /><br /> ExecuteTargets|  
|[Otherwise – element (MSBuild)](../msbuild/otherwise-element-msbuild.md)|Zvolte<br /><br /> ItemGroup<br /><br /> PropertyGroup|--|  
|[Output – element (MSBuild)](../msbuild/output-element-msbuild.md)|--|Podmínka<br /><br /> ItemName<br /><br /> PropertyName<br /><br /> TaskParameter|  
|[Parameter – element](../msbuild/parameter-element.md)|--|Výstup<br /><br /> ParameterType<br /><br /> Požadováno|  
|[ParameterGroup – element](../msbuild/parametergroup-element.md)|*Parameter*|--|  
|[Project – element (MSBuild)](../msbuild/project-element-msbuild.md)|Zvolte<br /><br /> Import<br /><br /> ItemGroup<br /><br /> ProjectExtensions<br /><br /> PropertyGroup<br /><br /> cíl<br /><br /> Usingtask –|Defaulttargets –<br /><br /> InitialTargets<br /><br /> Atribut ToolsVersion<br /><br /> TreatAsLocalProperty<br /><br /> atribut xmlns|  
|[ProjectExtensions – element (MSBuild)](../msbuild/projectextensions-element-msbuild.md)|--|--|  
|[Property – element (MSBuild)](../msbuild/property-element-msbuild.md)|--|Podmínka|  
|[PropertyGroup – element (MSBuild)](../msbuild/propertygroup-element-msbuild.md)|*Vlastnost*|Podmínka|  
|[Element Sdk (MSBuild)](../msbuild/sdk-element-msbuild.md)|--|Název<br /><br /> Version|  
|[Target – element (MSBuild)](../msbuild/target-element-msbuild.md)|OnError<br /><br /> *Úloha*|AfterTargets<br /><br /> BeforeTargets<br /><br /> Podmínka<br /><br /> DependsOnTargets<br /><br /> Vstupy<br /><br /> KeepDuplicateOutputs<br /><br /> Název<br /><br /> Výstupy<br /><br /> Vrací|  
|[Task – element (MSBuild)](../msbuild/task-element-msbuild.md)|Výstup|Podmínka<br /><br /> ContinueOnError –<br /><br /> *Parameter*|  
|[TaskBody – element (MSBuild)](../msbuild/taskbody-element-msbuild.md)|*Data*|Vyhodnocení|  
|[UsingTask – element (MSBuild)](../msbuild/usingtask-element-msbuild.md)|ParameterGroup<br /><br /> TaskBody|AssemblyFile<br /><br /> AssemblyName<br /><br /> Podmínka<br /><br /> TaskFactory<br /><br /> TaskName|  
|[When – element (MSBuild)](../msbuild/when-element-msbuild.md)|Zvolte<br /><br /> ItemGroup<br /><br /> PropertyGroup|Podmínka|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Podmínky](../msbuild/msbuild-conditions.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)  
 [MSBuild](../msbuild/msbuild.md)
