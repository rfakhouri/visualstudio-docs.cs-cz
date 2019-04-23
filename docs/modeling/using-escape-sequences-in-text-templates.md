---
title: Použití řídicích sekvencí v textových šablonách
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, escape sequences
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9c88c9c8769051724855d292bfefb56f69cb8dee
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60053166"
---
# <a name="using-escape-sequences-in-text-templates"></a>Použití řídicích sekvencí v textových šablonách
Můžete použít řídicích sekvencí v textových šablonách mají vygenerovat značky textové šablony a (v jazyce C# jenom kód) řídicí řídicí znaky a uvozovky.

 Otevření a zavření značky pro blok kódu standardní do výstupního souboru vytisknete řídicí značky následujícím způsobem:

```
\<# ... \#>
```

 Můžete provést stejným způsobem pracovat s další textové šablony směrnice a kód bloku značky.

 Pokud obsahuje blok textu řetězce používá k uvození textové šablony značky, může použít řídicí sekvence, které následující:

- Pokud je sudý počet řídicí předchází značku textové šablony (\\) znaky šablony analyzátor bude obsahovat polovinu řídicí znaky a obsahovat sekvenci jako značku textové šablony. Například, pokud existují čtyři řídicích znaků v textové šabloně, bude existovat dva "\\" znaků v generovaném souboru.

- Pokud je značka šablony textu předchází lichý počet řídicí (\\) znaků, analyzátor šablona bude obsahovat polovinu "\\" znaků plus vlastní značku (\<# nebo #>). Značka se nepovažuje za značkou template text.

- Pokud se řídicí sekvence (\\) kdekoli jinde v libovolném pořadí, než ve kterém se řídicí sekvence řídicího znaku nebo uvozovky (v jazyce C# pouze) se objeví znak, znak, který bude výstup přímo.

## <a name="see-also"></a>Viz také

- [Postupy: Generování šablon ze šablon pomocí řídicích sekvencí](../modeling/how-to-generate-templates-from-templates-by-using-escape-sequences.md)