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
ms.openlocfilehash: 6ad0bd131251259b375a4300807825205da2c6ea
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62931496"
---
# <a name="msbuild-best-practices"></a>Doporučené postupy nástroje MSBuild
Doporučujeme následující osvědčené postupy pro psaní skriptů nástroje MSBuild:

- Výchozí hodnoty vlastností jsou nejlépe odstraníte pomocí `Condition` atribut a ne pomocí deklarace vlastnost, jejíž výchozí hodnota se dá přepsat v příkazovém řádku. Například použít

```xml
<MyProperty Condition="'$(MyProperty)' == ''">
   MyDefaultValue
</MyProperty>
```

- Při výběru položek, vyhněte se zástupné znaky. Místo toho zadejte soubory explicitně. To usnadňuje sledování chyb, které mohou nastat při přidání nebo odstranění souborů.

## <a name="see-also"></a>Viz také:
- [Rozšířené koncepty](../msbuild/msbuild-advanced-concepts.md)
