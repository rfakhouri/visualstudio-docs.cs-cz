---
title: "Použití více procesorů k sestavení projektů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple processors
- MSBuild, multiple processor systems
ms.assetid: 49fa36c9-8e14-44f5-8a2b-34146cf6807b
caps.latest.revision: "13"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c2879b753ecdf06779403b01bbeb0681448759fa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="using-multiple-processors-to-build-projects"></a>Použití více procesorů k sestavení projektů
Nástroj MSBuild může využívat výhod systémů s více procesory nebo procesorů s více jádry. Pro každý dostupný procesor je vytvořen samostatný proces sestavení. Pokud má systém například čtyři procesory, jsou vytvořeny čtyři procesy sestavení. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]Tyto sestavení současně zpracovávat, a proto celkové sníží čase vytvoření buildu. Paralelní sestavení však zavádí některé změny v tom, jak dochází k procesům sestavení. V tomto tématu jsou dané změny popsány.  
  
## <a name="project-to-project-references"></a>Odkazy typu projekt na projekt  
 Když [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] komunikaci odkaz na projekt projekt (P2P), zatímco ho používá paralelní sestavení pro sestavení projektu, sestavuje odkaz pouze jednou. Obsahují-li stejný P2P odkaz dva projekty, nedojde k opětovnému sestavení odkazu pro každý projekt. Místo toho se jádro sestavení vrátí na stejný P2P odkaz obou projektů, které na něm závisí. Budoucím požadavkům relace stejného cíle je poskytnut stejný P2P odkaz.  
  
## <a name="cycle-detection"></a>Zjišťování cyklů  
 Při zjišťování cyklu funguje stejně jako [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] nyní 2.0, který kromě [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] mohou zasílat zprávy o detekci cyklu v jinou dobu nebo v buildu.  
  
## <a name="errors-and-exceptions-during-parallel-builds"></a>Chyby a výjimky během paralelního sestavení  
 V paralelních sestaveních se mohou chyby a výjimky vyskytovat v odlišnou dobu, než jak je tomu u neparalelních sestavení. Nebo nedojde-li k sestavení projektu, sestavování jiného projektu pokračuje. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]neukončí žádné sestavení projektu, který je vytváření paralelně s ten, který se nezdařilo. Další projekty i nadále sestavení, dokud se úspěch nebo neúspěch. Pokud však bylo povoleno nastavení <xref:Microsoft.Build.Framework.IBuildEngine.ContinueOnError%2A>, nedojde k zastavení žádných sestavení dokonce ani při výskytu chyby.  
  
## <a name="visual-c-project-vcproj-and-solution-sln-files"></a>Soubory projektu (.vcproj) a řešení (.sln) Visual C++  
 Obě [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projekty (.vcproj) a soubory řešení (.sln) se dá předat do [úlohy nástroje MSBuild](../msbuild/msbuild-task.md). Pro [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projekty, se nazývá VCWrapperProject a pak interní [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] vytvoření projektu. Pro [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] řešení, je vytvořena SolutionWrapperProject a pak interní [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] vytvoření projektu. V obou případech je s výsledným projektem zacházeno stejně jako se všemi ostatními projekty nástroje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].  
  
## <a name="multi-process-execution"></a>Provádění ve více procesech  
 Téměř všechny činnosti týkající se sestavení vyžadují, aby aktuální adresář zůstal neměnný po celou dobu procesu sestavení, protože jen tak se zabrání chybám souvisejícím s umístěním. Z toho důvodu nelze projekty v rámci nástroje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] spouštět v různých vláknech, jelikož by to mohlo vést k vytvoření více adresářů.  
  
 Nástroj [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] se tomuto problému vyhýbá a při tom povoluje sestavení s více procesory pomocí „izolace procesů“. Pomocí izolace procesů může nástroj [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] vytvořit maximálně `n` procesů, kde `n` se rovná počtu procesorů, které jsou v systému k dispozici. Pokud například nástroj [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] sestaví řešení v systému, který má dva procesory, budou vytvořeny pouze dva procesy sestavení. Tyto procesy jsou znovu použity k sestavení všech projektů v řešení.  
  
## <a name="see-also"></a>Viz také  
 [Sestavování více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)