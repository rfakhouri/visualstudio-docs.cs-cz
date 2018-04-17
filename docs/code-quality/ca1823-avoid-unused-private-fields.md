---
title: 'CA1823: Vyhněte se nepoužitým privátním polím | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- AvoidUnusedPrivateFields
- CA1823
helpviewer_keywords:
- AvoidUnusedPrivateFields
- CA1823
ms.assetid: 614f94f6-0dc7-430f-8124-cb889a4a720f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fa8af282866cd871d2717031091215cb431e1ec0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1823-avoid-unused-private-fields"></a>CA1823: Vyhněte se nepoužitým privátním polím
|||  
|-|-|  
|TypeName|AvoidUnusedPrivateFields|  
|CheckId|CA1823|  
|Kategorie|Microsoft.Performance|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Toto pravidlo je hlášené soukromé pole ve vašem kódu existuje, ale není používán všechny cesty kódu.  
  
## <a name="rule-description"></a>Popis pravidla  
 Byla zjištěna soukromá pole, která v rámci sestavení zjevně nejsou přístupná.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, odeberte pole nebo přidejte kód, který používá je.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné upozornění toto pravidlo potlačit.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1812: Vyhněte se nevytvořeným instancím vnitřních tříd](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)  
  
 [CA1801: Revize nepoužitých parametrů](../code-quality/ca1801-review-unused-parameters.md)  
  
 [CA1804: Odeberte nepoužívané místní hodnoty](../code-quality/ca1804-remove-unused-locals.md)  
  
 [CA1811: Vyhněte se nevolanému místnímu kódu](../code-quality/ca1811-avoid-uncalled-private-code.md)