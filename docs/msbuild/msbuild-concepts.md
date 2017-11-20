---
title: "Koncepty nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MSBuild, concepts
ms.assetid: 083b8ba3-e4ad-45af-bb5d-3bc81d406131
caps.latest.revision: "13"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 4395f4c82be689b1d573be44948e98711ba066c3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-concepts"></a>Koncepty nástroje MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]poskytuje základní schéma XML, které můžete použít k řízení, jak platformy sestavení sestavení softwaru. Pokud chcete zadat komponenty v sestavení a jak se má být sestaven, použijte tyto čtyři části MSBuild: vlastnosti, položky, úlohy a cíle.  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md)|Představuje vlastnosti a vlastnosti kolekce. Vlastnosti jsou páry klíč/hodnota, které můžete použít ke konfiguraci sestavení.|  
|[Položky](../msbuild/msbuild-items.md)|Popisuje obecné koncepty za [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru formátu a jak jsou navzájem propojené částí do jednoho.|  
|[Cíle](../msbuild/msbuild-targets.md)|Vysvětluje, jak povolit části procesu sestavení, která se má volat na příkazovém řádku a skupiny úlohy společně v určitém pořadí.|  
|[Úlohy](../msbuild/msbuild-tasks.md)|Ukazuje, jak vytvořit jednotku spustitelného kódu, který mohou využívat [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] k provádění operací atomic sestavení.|  
|[Porovnávání vlastností a položek](../msbuild/comparing-properties-and-items.md)|Porovná vlastnosti nástroje MSBuild a položky. Oba se používají k předávání informací do úlohy, vyhodnoťte podmínky a uložit hodnoty, které může být odkazováno v souboru projektu.|  
|[Speciální znaky nástroje MSBuild](../msbuild/msbuild-special-characters.md)|Vysvětluje, jak, abyste se vyhnuli některé znaků, který [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] rezervuje pro speciální použití v konkrétní kontexty.|  
|[Návod: Vytvoření souboru projektu MSBuild od začátku](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md)|Ukazuje, jak vytvořit základní projekt soubor postupně, pomocí pouze textový editor.|  
|[Návod: Použití nástroje MSBuild](../msbuild/walkthrough-using-msbuild.md)|Nabízí jako stavební bloky pro MSBuild a ukazuje, jak k zápisu, manipulaci a ladění projektů MSBuild bez zavření sadě Visual Studio integrované vývojové prostředí (IDE).|  
|[MSBuild – Reference](../msbuild/msbuild-reference.md)|Odkazy na dokumenty, které obsahují referenční informace.|  
|[Nástroje MSBuild](../msbuild/msbuild.md)|Obsahuje přehled schéma XML pro soubor projektu a ukazuje, jak se řídí procesy, které sestaví softwaru.|