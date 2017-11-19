---
title: "CA1806: Neignorujte výsledky metody | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1806
- DoNotIgnoreMethodResults
helpviewer_keywords:
- CA1806
- DoNotIgnoreMethodResults
ms.assetid: fd805687-0817-481e-804e-b62cfb3b1076
caps.latest.revision: "27"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 58da9a40f8cbbf8a506feb35dcba8a8e9f405899
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1806-do-not-ignore-method-results"></a>CA1806: Neignorujte výsledky metody
|||  
|-|-|  
|TypeName|DoNotIgnoreMethodResults|  
|CheckId|CA1806|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Existuje několik možných důvodů pro toto upozornění:  
  
-   Nový objekt, který vytvoří, ale nikdy použity.  
  
-   Je volána metoda, která vytvoří a vrátí nového řetězce a nový řetězec se nikdy nepoužívá.  
  
-   COM nebo P/Invoke metodu, která vrátí kód HRESULT nebo chyba, který se nikdy nepoužívá. Popis pravidla  
  
 Vytvoření objektu nepotřebné a přidružené uvolňování nepoužívané objektu snížit výkon.  
  
 Řetězce jsou neměnné a metod, jako je String.ToUpper – vrátí novou instanci třídy řetězec místo úpravy instanci řetězec v volání metody.  
  
 Ignoruje kód HRESULT nebo chyba, může dojít k neočekávanému chování v chybové stavy nebo podmínky nedostatku prostředků.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Pokud metoda A vytvoří novou instanci objektu B, který se nikdy nepoužívá, instance předat jako argument na jinou metodu nebo instanci přiřadit proměnné. Pokud vytvoření objektu je zbytečné, odeberte ní- nebo -  
  
 Pokud metoda A volá metodu B, ale nepoužívá novou instanci řetězec, který vrátí metoda B. Instance předat jako argument na jinou metodu, přiřadit instanci proměnné. Nebo odeberte volání, pokud je zbytečné.  
  
 -nebo-  
  
 Pokud metoda A volá metodu B, ale ne pomocí HRESULT nebo kód chyby, který vrátí metoda. Výsledek použít v příkazu podmíněného, přiřadit výsledek proměnné nebo předat jako argument na jinou metodu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Pokud v rámci vytváření objektu slouží některé účelu není potlačení upozornění od tohoto pravidla.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje třídu, která je výsledkem volání String.Trim ignoruje.  
  
 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_1.cs)]
 [!code-vb[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/VisualBasic/ca1806-do-not-ignore-method-results_1.vb)]
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_1.cpp)]  
  
## <a name="example"></a>Příklad  
 Následující příklad opravy předchozí porušení přiřazením výsledek String.Trim zpět na proměnnou, kterou byla volána na.  
  
 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_2.cs)]
 [!code-vb[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/VisualBasic/ca1806-do-not-ignore-method-results_2.vb)]
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_2.cpp)]  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metodu, která nepoužívá objekt, který vytvoří.  
  
> [!NOTE]
>  Tato porušení nelze reprodukovat v jazyce Visual Basic.  

 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults5#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_3.cpp)]
 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults5#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_3.cs)]   
  
## <a name="example"></a>Příklad  
 Následující příklad opravy předchozí porušení odebráním nepotřebných vytvoření objektu.  

 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults6#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_4.cs)]
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults6#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_4.cpp)] 

<!-- Examples don't exist for the below... -->
<!--
## Example  
 The following example shows a method that ignores the error code that the native method GetShortPathName returns.  
  
## Example  
 The following example fixes the previous violation by checking the error code and throwing an exception when the call fails.  
-->