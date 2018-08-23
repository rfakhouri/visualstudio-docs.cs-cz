---
title: Použití řídicích sekvencí v textových šablonách | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, escape sequences
ms.assetid: 36fff542-2f42-460f-a2d5-03fc76817f3b
caps.latest.revision: 31
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 24e2629001d7c426193059175eab64ea0ab8dacf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666385"
---
# <a name="using-escape-sequences-in-text-templates"></a>Použití řídicích sekvencí v textových šablonách
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [pomocí řídicí sekvencí v textových šablonách](https://docs.microsoft.com/visualstudio/modeling/using-escape-sequences-in-text-templates).  
  
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



