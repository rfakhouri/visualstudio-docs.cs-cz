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
ms.openlocfilehash: e597b10913ad495193545ab304b3b324d8f66b41
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68181113"
---
# <a name="msbuild-best-practices"></a>Doporučené postupy nástroje MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Doporučujeme následující osvědčené postupy pro psaní skriptů nástroje MSBuild:  
  
- Výchozí hodnoty vlastností jsou nejlépe odstraníte pomocí `Condition` atribut a ne pomocí deklarace vlastnost, jejíž výchozí hodnota se dá přepsat v příkazovém řádku. Například použít  
  
     `<MyProperty Condition="$(MyProperty)" == ''>`  
  
     `MyDefaultValue`  
  
     `</MyProperty>`  
  
- Při výběru položek, vyhněte se zástupné znaky. Místo toho zadejte soubory explicitně. To usnadňuje sledování chyb, které mohou nastat při přidání nebo odstranění souborů.  
  
## <a name="see-also"></a>Viz také  
 [Rozšířené koncepty](../msbuild/msbuild-advanced-concepts.md)
