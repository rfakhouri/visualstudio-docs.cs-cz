---
title: "Doporučené postupy nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- best practices, MSBuild
- MSBuild, best practices
ms.assetid: 90ef8693-e921-410a-a377-fe4d13f58c48
caps.latest.revision: "5"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9634fe1a0fa26d5180edc9312b925e6740bac216
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
