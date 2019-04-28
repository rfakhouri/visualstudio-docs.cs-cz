---
title: Efektivní využívání paměti při sestavování rozsáhlých projektů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- memory use (MSBuild)
- msbuild, efficient memory use building large trees
- caching (MSBuild)
ms.assetid: 853a21ed-69f7-4817-af00-57f73e2c74b5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ab3be342f31e5df018c14f84d30febd38c31c401
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62786203"
---
# <a name="use-memory-efficiently-when-you-build-large-projects"></a>Efektivní použití paměti při sestavování rozsáhlých projektů
Velké projekty často obsahovat mnoho dílčích projektů a další závislosti, které můžou spotřebovat velké množství systémové paměti v okamžiku sestavení. Když je snížení dostupné systémové paměti, může také snížit výkon systému. Starší verze [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekty zůstala v paměti. Verze 3.5 odebrat staršími verzemi projektů, ale zachovají výsledků sestavení v mezipaměti pro pozdější načtení.

 Verze 4.0 zpracovává správy paměti automaticky, nebudou muset použít vlastnosti, jako je ukládání projektů `UnloadProjectsOnCompletion` a `UseResultsCache`.

### <a name="see-also"></a>Viz také:
- [Sestavování více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)