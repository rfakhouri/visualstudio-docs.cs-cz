---
title: Doporučené postupy nástroje MSBuild | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
helpviewer_keywords:
- best practices, MSBuild
- MSBuild, best practices
ms.assetid: 90ef8693-e921-410a-a377-fe4d13f58c48
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6973e905a0587ffdc7cbd0a401e03f933fc60a3a
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59662210"
---
# <a name="msbuild-best-practices"></a>Doporučené postupy nástroje MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Doporučujeme následující osvědčené postupy pro psaní skriptů nástroje MSBuild:  
  
-   Výchozí hodnoty vlastností jsou nejlépe odstraníte pomocí `Condition` atribut a ne pomocí deklarace vlastnost, jejíž výchozí hodnota se dá přepsat v příkazovém řádku. Například použít  
  
     `<MyProperty Condition="$(MyProperty)" == ''>`  
  
     `MyDefaultValue`  
  
     `</MyProperty>`  
  
-   Při výběru položek, vyhněte se zástupné znaky. Místo toho zadejte soubory explicitně. To usnadňuje sledování chyb, které mohou nastat při přidání nebo odstranění souborů.  
  
## <a name="see-also"></a>Viz také  
 [Rozšířené koncepty](../msbuild/msbuild-advanced-concepts.md)
