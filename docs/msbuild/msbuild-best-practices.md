---
title: "Doporučené postupy nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- best practices, MSBuild
- MSBuild, best practices
ms.assetid: 90ef8693-e921-410a-a377-fe4d13f58c48
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3c2a1e55c9a43a8e94ed577fc8de135d76e12da5
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
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
