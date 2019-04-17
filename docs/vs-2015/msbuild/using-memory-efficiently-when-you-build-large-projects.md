---
title: Efektivní využívání paměti při sestavování rozsáhlých projektů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- memory use (MSBuild)
- msbuild, efficient memory use building large trees
- caching (MSBuild)
ms.assetid: 853a21ed-69f7-4817-af00-57f73e2c74b5
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 28d9f3d43faa53731b101dfdf58fe1e68a0920c5
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59655696"
---
# <a name="using-memory-efficiently-when-you-build-large-projects"></a>Efektivní využívání paměti při sestavování rozsáhlých projektů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Velké projekty často obsahovat mnoho dílčích projektů a další závislosti, a ty můžou spotřebovat velké množství systémové paměti v okamžiku sestavení. Když je snížení dostupné systémové paměti, může také snížit výkon systému. Starší verze [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] projekty zůstala v paměti nebo ve verzi 3.5 projekty byly odebrány, ale zachovali výsledků sestavení v mezipaměti pro pozdější načtení.  
  
 Verze 4.0 zpracovává správy paměti automaticky, nebudou muset použít vlastnosti, jako je ukládání projektů `UnloadProjectsOnCompletion` a `UseResultsCache`.  
  
## <a name="see-also"></a>Viz také  
 [Paralelní sestavování více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)
