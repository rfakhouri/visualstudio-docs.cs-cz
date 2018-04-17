---
title: Doporučené postupy nástroje MSBuild | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- best practices, MSBuild
- MSBuild, best practices
ms.assetid: 90ef8693-e921-410a-a377-fe4d13f58c48
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 98d85a336a1741f6495959249fe605332d85aac2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="msbuild-best-practices"></a>Doporučené postupy nástroje MSBuild
Doporučujeme následující osvědčené postupy pro psaní skriptů MSBuild:  
  
-   Výchozí hodnoty vlastností jsou nejlépe vyřeší pomocí `Condition` atributů a ne pomocí deklarace vlastnosti, jejíž výchozí hodnota je možné přepsat na příkazovém řádku. Operátor  
  
     `<MyProperty Condition="'$(MyProperty)' == ''">`  
  
     `MyDefaultValue`  
  
     `</MyProperty>`  
  
-   Při výběru položek, vyhněte se zástupné znaky. Místo toho explicitně zadejte soubory. To usnadňuje sledování chyb, které mohou nastat při přidání nebo odstranění souborů.  
  
## <a name="see-also"></a>Viz také  
 [Rozšířené koncepty](../msbuild/msbuild-advanced-concepts.md)
