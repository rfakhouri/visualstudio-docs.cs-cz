---
title: "CA1009: Deklarujte správně obslužné rutiny událostí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1009
- DeclareEventHandlersCorrectly
helpviewer_keywords:
- CA1009
- DeclareEventHandlersCorrectly
ms.assetid: ab65c471-1449-49d2-9896-7b9af74284b4
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8e72f10ef44c784af98628f4b0c1ed3b72814977
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1009-declare-event-handlers-correctly"></a>CA1009: Deklarujte správně obslužné rutiny událostí
|||  
|-|-|  
|TypeName|DeclareEventHandlersCorrectly|  
|CheckId|CA1009|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Delegát, který zpracovává událost veřejných nebo chráněného nemá správný podpis, vrátí typ, nebo názvy parametrů.  
  
## <a name="rule-description"></a>Popis pravidla  
 Metody zpracování událostí přebírají dva parametry. První je typu <xref:System.Object?displayProperty=fullName> a má název 'odesílatele'. Je jím objekt, který vyvolal událost. Druhý parametr není typu <xref:System.EventArgs?displayProperty=fullName> a má název "e". Představuje data přidružená k události. Například pokud událost se vyvolá při každém otevření souboru, data události obvykle obsahuje název souboru.  
  
 Metody obslužné rutiny události nesmí vrátit hodnotu. V jazyka C# programovací jazyk, je dána návratový typ `void`. Obslužné rutiny události můžete vyvolat několika metod ve více objektů. Pokud bylo povoleno metody vrátit hodnotu, by tomu bylo více vrácených hodnot pro všechny události a pouze hodnota poslední metodu, která byla vyvolána by být k dispozici.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, opravte podpis, návratový typ nebo názvy parametrů delegáta. Podrobnosti najdete v tématu v následujícím příkladu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje delegáta, který je vhodný pro zpracování událostí. Metody, které můžete vyvolat této obslužné rutiny události v souladu s podpisu, který je uveden v pokynů pro návrh. `AlarmEventHandler`je název typu delegáta. `AlarmEventArgs`je odvozen od základní třídu pro data události <xref:System.EventArgs>, a blokování poplašný data události.  
  
 [!code-cpp[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/CPP/ca1009-declare-event-handlers-correctly_1.cpp)]
 [!code-csharp[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/CSharp/ca1009-declare-event-handlers-correctly_1.cs)]
 [!code-vb[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/VisualBasic/ca1009-declare-event-handlers-correctly_1.vb)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2109: Revize viditelných obslužných rutin událostí](../code-quality/ca2109-review-visible-event-handlers.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.EventArgs?displayProperty=fullName>   
 <xref:System.Object?displayProperty=fullName>   
 [Zpracování a generování událostí](/dotnet/standard/events/index)  