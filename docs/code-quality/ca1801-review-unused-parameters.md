---
title: "CA1801: Revize nepoužitých parametrů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AvoidUnusedParameters
- CA1801
- ReviewUnusedParameters
helpviewer_keywords:
- CA1801
- ReviewUnusedParameters
ms.assetid: 5d73545c-e153-4b7c-a7b2-be6bf5aca5be
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1bb8c38d1436ca687664f92bfe0ba6db1ccf68ea
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1801-review-unused-parameters"></a>CA1801: Revize nepoužitých parametrů
|||  
|-|-|  
|TypeName|ReviewUnusedParameters|  
|CheckId|CA1801|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez narušující – Pokud člen není zobrazen mimo sestavení, bez ohledu na změny, které provedete.<br /><br /> Bez narušující – Pokud změníte člen použití parametru v jeho textu.<br /><br /> Pozastavení – Pokud odeberte parametr a je viditelný mimo sestavení.|  
  
## <a name="cause"></a>příčina  
 Podpis metody obsahuje parametr, který není použit v těle metody. Toto pravidlo není zkontrolujte následující metody:  
  
-   Metody odkazuje delegáta.  
  
-   Metody použité jako obslužné rutiny událostí.  
  
-   Metody deklarovat s `abstract` (`MustOverride` v jazyce Visual Basic) modifikátor.  
  
-   Metody deklarovat s `virtual` (`Overridable` v jazyce Visual Basic) modifikátor.  
  
-   Metody deklarovat s `override` (`Overrides` v jazyce Visual Basic) modifikátor.  
  
-   Metody deklarovat s `extern` (`Declare` v jazyce Visual Basic) modifikátor.  
  
## <a name="rule-description"></a>Popis pravidla  
 Zkontrolujte parametry v nevirtuálních metody, které nejsou používány v těle metoda a ujistěte se, zda že existuje žádné správnost kolem selhání o přístup k nim. Nepoužité parametry vynakládá Údržba a výkon.  
  
 Někdy je porušení toto pravidlo může ukazovat na implementaci chyb v metodě. Například parametr by měl již byly použity v těle metoda. Potlačíte upozornění na toto pravidlo, pokud má parametr existovat z důvodu zpětné kompatibility.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, odeberte nepoužívané parametr (narušující změně) nebo použijte parametr v těle – metoda (pevné změnit).  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné pro potlačení upozornění od tohoto pravidla pro dříve dodané kód, pro které by bylo opravu narušující změně.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje dva způsoby. Jedna z metod porušuje pravidlo a jiné metody splňuje pravidlo.  
  
 [!code-csharp[FxCop.Usage.ReviewUnusedParameters#1](../code-quality/codesnippet/CSharp/ca1801-review-unused-parameters_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1811: Vyhněte se nevolanému místnímu kódu](../code-quality/ca1811-avoid-uncalled-private-code.md)  
  
 [CA1812: Vyhněte se nevytvořeným interní třídy](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)  
  
 [CA1804: Odeberte nepoužívané místní hodnoty](../code-quality/ca1804-remove-unused-locals.md)