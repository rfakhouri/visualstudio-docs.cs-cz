---
title: Efektivní využívání paměti při sestavování rozsáhlých projektů | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- memory use (MSBuild)
- msbuild, efficient memory use building large trees
- caching (MSBuild)
ms.assetid: 853a21ed-69f7-4817-af00-57f73e2c74b5
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d2cb204fcfb5a96fe9833571895513dfda4449b8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669491"
---
# <a name="using-memory-efficiently-when-you-build-large-projects"></a>Efektivní využívání paměti při sestavování rozsáhlých projektů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [pomocí paměti efektivně když je sestavení velké projekty](https://docs.microsoft.com/visualstudio/msbuild/using-memory-efficiently-when-you-build-large-projects).  
  
  
Velké projekty často obsahovat mnoho dílčích projektů a další závislosti, a ty můžou spotřebovat velké množství systémové paměti v okamžiku sestavení. Když je snížení dostupné systémové paměti, může také snížit výkon systému. Starší verze [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] projekty zůstala v paměti nebo ve verzi 3.5 projekty byly odebrány, ale zachovali výsledků sestavení v mezipaměti pro pozdější načtení.  
  
 Verze 4.0 zpracovává správy paměti automaticky, nebudou muset použít vlastnosti, jako je ukládání projektů `UnloadProjectsOnCompletion` a `UseResultsCache`.  
  
## <a name="see-also"></a>Viz také  
 [Sestavování více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)



