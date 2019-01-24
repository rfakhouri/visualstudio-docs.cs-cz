---
title: Použití řídicích sekvencí v textových šablonách | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, escape sequences
ms.assetid: 36fff542-2f42-460f-a2d5-03fc76817f3b
caps.latest.revision: 31
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: aecd53f9321108d429c732cc8b802ee5dfc8a99c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54758416"
---
# <a name="using-escape-sequences-in-text-templates"></a>Použití řídicích sekvencí v textových šablonách
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete použít řídicích sekvencí v textových šablonách mají vygenerovat značky textové šablony a (v jazyce C# jenom kód) řídicí řídicí znaky a uvozovky.  
  
 Otevření a zavření značky pro blok kódu standardní do výstupního souboru vytisknete řídicí značky následujícím způsobem:  
  
```  
\<# ... \#>  
```  
  
 Můžete provést stejným způsobem pracovat s další textové šablony směrnice a kód bloku značky.  
  
 Pokud obsahuje blok textu řetězce používá k uvození textové šablony značky, může použít řídicí sekvence, které následující:  
  
-   Pokud je sudý počet řídicí předchází značku textové šablony (\\) znaky šablony analyzátor bude obsahovat polovinu řídicí znaky a obsahovat sekvenci jako značku textové šablony. Například, pokud existují čtyři řídicích znaků v textové šabloně, bude existovat dva "\\" znaků v generovaném souboru.  
  
-   Pokud je značka šablony textu předchází lichý počet řídicí (\\) znaků, analyzátor šablona bude obsahovat polovinu "\\" znaků plus vlastní značku (\<# nebo #>). Značka se nepovažuje za značkou template text.  
  
-   Pokud se řídicí sekvence (\\) kdekoli jinde v libovolném pořadí, než ve kterém se řídicí sekvence řídicího znaku nebo uvozovky (v jazyce C# pouze) se objeví znak, znak, který bude výstup přímo.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Generování šablon ze šablon pomocí řídicích sekvencí](../modeling/how-to-generate-templates-from-templates-by-using-escape-sequences.md)
