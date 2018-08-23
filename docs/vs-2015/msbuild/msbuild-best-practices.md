---
title: Doporučené postupy nástroje MSBuild | Dokumentace Microsoftu
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
- best practices, MSBuild
- MSBuild, best practices
ms.assetid: 90ef8693-e921-410a-a377-fe4d13f58c48
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: df388b4b5aeac30e5ee83e24dc08905507318f18
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674119"
---
# <a name="msbuild-best-practices"></a>Doporučené postupy nástroje MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [doporučené postupy nástroje MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-best-practices).  
  
  
Doporučujeme následující osvědčené postupy pro psaní skriptů nástroje MSBuild:  
  
-   Výchozí hodnoty vlastností jsou nejlépe odstraníte pomocí `Condition` atribut a ne pomocí deklarace vlastnost, jejíž výchozí hodnota se dá přepsat v příkazovém řádku. Například použít  
  
     `<MyProperty Condition="$(MyProperty)" == ''>`  
  
     `MyDefaultValue`  
  
     `</MyProperty>`  
  
-   Při výběru položek, vyhněte se zástupné znaky. Místo toho zadejte soubory explicitně. To usnadňuje sledování chyb, které mohou nastat při přidání nebo odstranění souborů.  
  
## <a name="see-also"></a>Viz také  
 [Rozšířené koncepty](../msbuild/msbuild-advanced-concepts.md)



