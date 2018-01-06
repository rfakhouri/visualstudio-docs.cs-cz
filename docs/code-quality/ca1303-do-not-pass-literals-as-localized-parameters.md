---
title: "CA1303: Nepředávejte literály jako lokalizované parametry | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Do not pass literals as localized parameters
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
helpviewer_keywords:
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
ms.assetid: 904d284e-76d0-4b8f-a4df-0094de8d7aac
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 361155e9d46e4f71ddc61775f56105cedb5d18b9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1303-do-not-pass-literals-as-localized-parameters"></a>CA1303: Nepředávejte literály jako lokalizované parametry
|||  
|-|-|  
|TypeName|DoNotPassLiteralsAsLocalizedParameters|  
|CheckId|CA1303|  
|Kategorie|Microsoft.Globalization|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Metoda předá řetězec literálu jako parametr konstruktoru nebo metodu v [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] třídy knihovny a že by měl být řetězec lokalizovatelný.  
  
 Toto upozornění se vyvolá, když řetězcový literál je předán jako hodnotu parametru nebo vlastnost a platí jeden nebo více následujících případech:  
  
-   <xref:System.ComponentModel.LocalizableAttribute> Atribut parametru nebo vlastnosti je nastaven na hodnotu true.  
  
-   Název parametru nebo vlastnost obsahuje "Text", "Zpráva" nebo "Titulek".  
  
-   Název parametru řetězce, který je předaný metodě Console.Write nebo Console.WriteLine je "value" nebo "format".  
  
## <a name="rule-description"></a>Popis pravidla  
 Textové literály, které jsou součástí zdrojového kódu se obtížně lokalizaci.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li porušení toto pravidlo, nahraďte řetězcový literál řetězcem načíst prostřednictvím instance <xref:System.Resources.ResourceManager> třídy.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, pokud nebude možné lokalizovat knihovny kódu, nebo pokud řetězec není vystavený koncovému uživateli nebo vývojáři pomocí knihovny kódu.  
  
 Uživatele můžete eliminovat šumu proti metody, které by neměly být předány lokalizovaných řetězců přejmenováním parametr nebo vlastnost s názvem nebo označením tyto položky jako podmíněného.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metodu, která vyvolá výjimku, pokud některý z jeho dva argumenty jsou mimo rozsah. První argument konstruktoru výjimka je předán řetězcový literál, který je v rozporu toto pravidlo. Pro druhý argument, je předaná konstruktoru správně řetězec načteny prostřednictvím <xref:System.Resources.ResourceManager>.  
  
 [!code-cpp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CPP/ca1303-do-not-pass-literals-as-localized-parameters_1.cpp)]
 [!code-vb[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/VisualBasic/ca1303-do-not-pass-literals-as-localized-parameters_1.vb)]
 [!code-csharp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CSharp/ca1303-do-not-pass-literals-as-localized-parameters_1.cs)]  
  
## <a name="see-also"></a>Viz také  
 [Prostředky v desktopových aplikacích](/dotnet/framework/resources/index)