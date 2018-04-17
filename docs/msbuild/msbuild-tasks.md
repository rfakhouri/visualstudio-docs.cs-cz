---
title: Úlohy nástroje MSBuild | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- tasks
- MSBuild, tasks
ms.assetid: 5d3cc4a7-e5db-4f73-b707-8b6882fddcf8
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e1d95b4ba7b271fad528d3e70494d3aafb077aca
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="msbuild-tasks"></a>Úlohy nástroje MSBuild
Platformy sestavení musí být schopné provést libovolného počtu akcí během procesu vytváření. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] používá *úlohy* k provedení těchto akcí. Úkol je jednotka spustitelný kód, který se používá [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] k provádění operací atomic sestavení.  
  
## <a name="task-logic"></a>Úloha logiky  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Formát souboru XML projektu nelze provést plně sestavení operací na svůj vlastní, takže logiku úloh, musí být implementována mimo souboru projektu.  
  
 Logika spuštění úlohy je implementovaný jako třídy rozhraní .NET, která implementuje <xref:Microsoft.Build.Framework.ITask> rozhraní, která je definována v <xref:Microsoft.Build.Framework> oboru názvů.  
  
 Třída úlohy definuje vstupní a výstupní parametry k dispozici také úlohy v souboru projektu. Všechny veřejné nastavit nestatické neabstraktní vlastnosti vystavené třída úlohy je přístupná v souboru projektu umístěním odpovídající atribut se stejným názvem na [úloh](../msbuild/task-element-msbuild.md) elementu.  
  
 Můžete napsat vlastní úlohy vytvářením spravované třídy, která implementuje <xref:Microsoft.Build.Framework.ITask> rozhraní. Další informace najdete v tématu [zápis úloh](../msbuild/task-writing.md).  
  
## <a name="executing-a-task-from-a-project-file"></a>Provádění úlohy ze souboru projektu  
 Před provedením úlohy v souboru projektu, je nutné nejprve mapovat typu v sestavení, které implementuje úlohu, aby název úlohy s [usingtask –](../msbuild/usingtask-element-msbuild.md) elementu. To umožní [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] věděli, kde má být vyhledán logiky provádění úkolu, pokud ho najde v souboru projektu.  
  
 Chcete-li spustit úlohu v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu, vytvořte prvek s názvem úkolu jako podřízenou `Target` elementu. Pokud úloha přijímá parametry, ty jsou předány jako atributy elementu.  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] položky seznamů a vlastnosti lze použít jako parametry. Například následující kód volání `MakeDir` úkolů a nastaví hodnotu `Directories` vlastnost `MakeDir` objekt rovná hodnotě `BuildDir` vlastnost deklarované v předchozím příkladu.  
  
```xml  
<Target Name="MakeBuildDirectory">  
    <MakeDir  
        Directories="$(BuildDir)" />  
</Target>  
```  
  
 Úlohy můžete se taky vrátit informace do souboru projektu, který mohou být uloženy ve položky nebo vlastnosti pro pozdější použití. Například následující kód volání `Copy` úlohy a ukládá informace od `CopiedFiles` výstup vlastnost `SuccessfullyCopiedFiles` seznamu položek.  
  
```xml  
<Target Name="CopyFiles">  
    <Copy  
        SourceFiles="@(MySourceFiles)"  
        DestinationFolder="@(MyDestFolder)">  
        <Output  
            TaskParameter="CopiedFiles"  
            ItemName="SuccessfullyCopiedFiles"/>  
     </Copy>  
</Target>  
```  
  
## <a name="included-tasks"></a>Zahrnuté úlohy  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] se dodává s mnoha úloh, jako [kopie](../msbuild/copy-task.md), který zkopíruje soubory, [makedir –](../msbuild/makedir-task.md), která vytvoří adresáře, a [Csc](../msbuild/csc-task.md), které zkompiluje [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] zdrojové soubory kódu. Úplný seznam dostupných úloh a informace o použití najdete v části [– Reference úlohy](../msbuild/msbuild-task-reference.md).  
  
## <a name="overridden-tasks"></a>Přepsané úlohy  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Vyhledá úlohy v několika umístěních. V souborech s příponou je první umístění. OverrideTasks uložené v adresáři pro rozhraní .NET Framework. Úlohy v těchto souborech přepsat další úlohy se stejnými názvy, včetně úloh v souboru projektu. Druhé umístění je v souborech s příponou. Úlohy v adresáři pro rozhraní .NET Framework. Pokud úloha nebyla nalezena v některém z těchto umístění, použije se úloha v souboru projektu.  
  
## <a name="see-also"></a>Viz také  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [Nástroje MSBuild](../msbuild/msbuild.md)   
 [Zápis úloh](../msbuild/task-writing.md)   
 [Vložené úlohy](../msbuild/msbuild-inline-tasks.md)