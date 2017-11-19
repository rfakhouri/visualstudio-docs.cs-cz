---
title: "Použití řídicích sekvencí v textových šablon | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, escape sequences
ms.assetid: 36fff542-2f42-460f-a2d5-03fc76817f3b
caps.latest.revision: "29"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: fdf062c9b33dd4a160f54bba83991a3cdda7f0d1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="using-escape-sequences-in-text-templates"></a>Použití řídicích sekvencí v textových šablonách
Můžete použít řídicích sekvencí v textových šablonách mají vygenerovat značky text šablony a (v C# pouze kód) řídicí řídicí znaky a znaky uvozovek.  
  
 Pokud chcete vytisknout otevření a zavření značky pro blok kódu standardního výstupního souboru, vyhnuli značek následujícím způsobem:  
  
```  
\<# ... \#>  
```  
  
 Můžete provést stejný s jiné text šablony směrnice a kód bloku značky.  
  
 Obsahuje-li bloku řetězce používá k uvození textové šablony značky, pak můžete použít následující řídicí sekvence:  
  
-   Pokud je před značku text šablony sudý počet řídicí (\\) znaků šablony analyzátor bude zahrnovat polovinu řídicí znaky a obsahovat pořadí jako značku text šablony. Například, pokud existují čtyři řídicí znaky v textové šablony, budou existovat dvě "\\" znaků v generovaném souboru.  
  
-   Pokud text šablony značky předchází lichý počet řídicí (\\) znaky, šablony analyzátor bude obsahovat polovinu "\\" znaků plus samotné značky (\<# nebo #>). Značky se nepovažuje za značku text šablony.  
  
-   Pokud řídicí (\\) znak zobrazí kdekoliv jinde v libovolném pořadí, než kde je řídicí sekvence řídicí znak nebo uvozovky (v jazyku C# pouze), znak, který bude výstup přímo.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: generování šablon ze šablon pomocí řídicích sekvencí](../modeling/how-to-generate-templates-from-templates-by-using-escape-sequences.md)