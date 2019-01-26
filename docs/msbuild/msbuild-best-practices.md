---
title: Doporučené postupy nástroje MSBuild | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- best practices, MSBuild
- MSBuild, best practices
ms.assetid: 90ef8693-e921-410a-a377-fe4d13f58c48
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 622d7b087e94d21f86691b88c3af4891aa533e9a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55013207"
---
# <a name="msbuild-best-practices"></a>Doporučené postupy nástroje MSBuild
Doporučujeme následující osvědčené postupy pro psaní skriptů nástroje MSBuild:  
  
-   Výchozí hodnoty vlastností jsou nejlépe odstraníte pomocí `Condition` atribut a ne pomocí deklarace vlastnost, jejíž výchozí hodnota se dá přepsat v příkazovém řádku. Například použít  
  
```xml
<MyProperty Condition="'$(MyProperty)' == ''">
   MyDefaultValue
</MyProperty>
```
  
-   Při výběru položek, vyhněte se zástupné znaky. Místo toho zadejte soubory explicitně. To usnadňuje sledování chyb, které mohou nastat při přidání nebo odstranění souborů.  
  
## <a name="see-also"></a>Viz také:  
 [Rozšířené koncepty](../msbuild/msbuild-advanced-concepts.md)
