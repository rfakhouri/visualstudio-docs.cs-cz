---
title: "Efektivní využívání paměti při sestavování rozsáhlých projektů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- memory use (MSBuild)
- msbuild, efficient memory use building large trees
- caching (MSBuild)
ms.assetid: 853a21ed-69f7-4817-af00-57f73e2c74b5
caps.latest.revision: "11"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1e78afd0f76839d170f12cf4315610c183899fff
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="using-memory-efficiently-when-you-build-large-projects"></a>Efektivní využívání paměti při sestavování rozsáhlých projektů
Rozsáhlých projektů často obsahovat mnoho dílčích projektů a další závislosti, a tyto může využívat velké množství paměti systému v čase vytvoření buildu. Když dojde k omezení dostupné systémové paměti, může také snížit výkon systému. Starší verze [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekty zůstává v paměti nebo ve verze 3.5, projekty, které byly odebrány, však uchované výsledky sestavení v mezipaměti pro pozdější načtení.  
  
 Verze 4.0 zpracovává tato správa paměti automaticky, ukládání projekty z museli pomocí vlastnosti, jako například `UnloadProjectsOnCompletion` a `UseResultsCache`.  
  
## <a name="see-also"></a>Viz také  
 [Sestavování více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)