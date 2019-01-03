---
title: 'CA1009: Deklarujte správně obslužné rutiny událostí'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1009
- DeclareEventHandlersCorrectly
helpviewer_keywords:
- CA1009
- DeclareEventHandlersCorrectly
ms.assetid: ab65c471-1449-49d2-9896-7b9af74284b4
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: b56f93a1ea4afbe3c9fd590df937fe56a155b044
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53987651"
---
# <a name="ca1009-declare-event-handlers-correctly"></a>CA1009: Deklarujte správně obslužné rutiny událostí

|||
|-|-|
|TypeName|DeclareEventHandlersCorrectly|
|CheckId|CA1009|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Delegát, který zpracovává událost veřejná nebo chráněná nemá správný podpis, návratový typ nebo názvy parametrů.

## <a name="rule-description"></a>Popis pravidla
 Metody zpracování událostí přebírají dva parametry. První je typu <xref:System.Object?displayProperty=fullName> a je pojmenován "sender". Je jím objekt, který vyvolal událost. Druhý parametr je typu <xref:System.EventArgs?displayProperty=fullName> a je pojmenován "e". Představuje data přidružená k události. Například pokud se vyvolá událost pokaždé, když je soubor otevřen, data událostí obvykle obsahuje název souboru.

 Obslužné rutiny události by neměly vracet hodnotu. V jazyce C# programovací jazyk, je toto označeno návratovým typem `void`. Obslužné rutiny události můžete vyvolat několik metod v několika objektů. Pokud metody se může vrátit hodnotu, by tomu bylo více vrácených hodnot pro každou jednotlivou událost a bude k dispozici pouze hodnotu poslední metodu, která byla vyvolána.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, opravte podpis, návratový typ nebo názvy parametrů delegáta. Podrobnosti najdete v tématu v následujícím příkladu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje delegáta, který je vhodný pro zpracování událostí. Metody, které mohou být vyvolány touto obslužnou rutinou události v souladu s podpisu, který je zadán v pokyny návrhu. `AlarmEventHandler` je název typu delegáta. `AlarmEventArgs` je odvozena ze základní třídy pro data události <xref:System.EventArgs>, a obsahuje budíku data události.

 [!code-cpp[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/CPP/ca1009-declare-event-handlers-correctly_1.cpp)]
 [!code-csharp[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/CSharp/ca1009-declare-event-handlers-correctly_1.cs)]
 [!code-vb[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/VisualBasic/ca1009-declare-event-handlers-correctly_1.vb)]

## <a name="related-rules"></a>Související pravidla
 [CA2109: Zkontrolujte viditelných obslužných rutin událostí](../code-quality/ca2109-review-visible-event-handlers.md)

## <a name="see-also"></a>Viz také:

- <xref:System.EventArgs?displayProperty=fullName>
- <xref:System.Object?displayProperty=fullName>
- [Zpracování a generování událostí](/dotnet/standard/events/index)