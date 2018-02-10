---
title: "Efektivní využívání paměti při sestavování rozsáhlých projektů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- memory use (MSBuild)
- msbuild, efficient memory use building large trees
- caching (MSBuild)
ms.assetid: 853a21ed-69f7-4817-af00-57f73e2c74b5
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 203868b91778f977affc9c20c8dafa8a5fdf8f60
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="using-memory-efficiently-when-you-build-large-projects"></a>Efektivní využívání paměti při sestavování rozsáhlých projektů
Rozsáhlých projektů často obsahovat mnoho dílčích projektů a další závislosti, a tyto může využívat velké množství paměti systému v čase vytvoření buildu. Když dojde k omezení dostupné systémové paměti, může také snížit výkon systému. Starší verze [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekty zůstává v paměti nebo ve verze 3.5, projekty, které byly odebrány, však uchované výsledky sestavení v mezipaměti pro pozdější načtení.  
  
 Verze 4.0 zpracovává tato správa paměti automaticky, ukládání projekty z museli pomocí vlastnosti, jako například `UnloadProjectsOnCompletion` a `UseResultsCache`.  
  
## <a name="see-also"></a>Viz také  
 [Sestavování více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)