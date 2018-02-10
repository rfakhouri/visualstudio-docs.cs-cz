---
title: "Použití řídicích sekvencí v textových šablon | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- text templates, escape sequences
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: f6ab5346ed82aadea339bc8ee45ac4a3bfb72c65
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
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
 [Postupy: Generování šablon ze šablon pomocí řídicích sekvencí](../modeling/how-to-generate-templates-from-templates-by-using-escape-sequences.md)