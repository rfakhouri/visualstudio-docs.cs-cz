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
ms.openlocfilehash: b214ff057125b2921ec853fbee004cbb7d41f9e0
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54792764"
---
# <a name="using-memory-efficiently-when-you-build-large-projects"></a>Efektivní využívání paměti při sestavování rozsáhlých projektů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Velké projekty často obsahovat mnoho dílčích projektů a další závislosti, a ty můžou spotřebovat velké množství systémové paměti v okamžiku sestavení. Když je snížení dostupné systémové paměti, může také snížit výkon systému. Starší verze [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] projekty zůstala v paměti nebo ve verzi 3.5 projekty byly odebrány, ale zachovali výsledků sestavení v mezipaměti pro pozdější načtení.  
  
 Verze 4.0 zpracovává správy paměti automaticky, nebudou muset použít vlastnosti, jako je ukládání projektů `UnloadProjectsOnCompletion` a `UseResultsCache`.  
  
## <a name="see-also"></a>Viz také  
 [Paralelní sestavování více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)
