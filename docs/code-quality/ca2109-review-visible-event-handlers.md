---
title: 'CA2109: Zkontrolujte viditelné obslužné rutiny událostí'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2109
- ReviewVisibleEventHandlers
helpviewer_keywords:
- ReviewVisibleEventHandlers
- CA2109
ms.assetid: 8f8fa0ee-e94e-400e-b516-24d8727725d7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ee5b1d92a6c7a813eea6efb409d3c2a22f68547c
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921131"
---
# <a name="ca2109-review-visible-event-handlers"></a>CA2109: Zkontrolujte viditelné obslužné rutiny událostí

|||
|-|-|
|TypeName|ReviewVisibleEventHandlers|
|CheckId|CA2109|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Byla zjištěna veřejná nebo chráněná metoda zpracování událostí.

## <a name="rule-description"></a>Popis pravidla
Externě viditelná metoda zpracování událostí představuje problémy se zabezpečením, které vyžadují kontrolu.

Nezveřejňujte metody zpracování událostí, pokud není nezbytně nutné. Obslužná rutina události, typ delegáta, který vyvolá vystavenou metodu, lze přidat k jakékoli události, pokud se shodují signatury obslužné rutiny a události. Události mohou být vyvolány jakýmkoli kódem a často jsou vyvolány vysoce důvěryhodným systémovým kódem v reakci na akce uživatele, jako je například kliknutí na tlačítko. Přidání kontroly zabezpečení do metody zpracování události nebrání kódu v registraci obslužné rutiny události, která vyvolá metodu.

Poptávka nemůže spolehlivě chránit metodu vyvolanou obslužnou rutinou události. Požadavky na zabezpečení pomůžou chránit kód před nedůvěryhodnými volajícími prozkoumáním volajících v zásobníku volání. Kód, který přidá obslužnou rutinu události do události, není nutně přítomen v zásobníku volání při spuštění metod obslužné rutiny události. Proto zásobník volání může mít pouze vysoce důvěryhodné volající, když je vyvolána metoda obslužné rutiny události. To způsobí, že požadavky provedené metodou obslužné rutiny události budou úspěšné. Vyžádané oprávnění může také být při vyvolání metody uplatněno. Z těchto důvodů může být riziko, že není nutné opravit porušení tohoto pravidla, posouzeno pouze po kontrole metody zpracování událostí. Při revizi kódu Vezměte v úvahu následující problémy:

- Provádí vaše obslužná rutina události nějaké operace, které jsou nebezpečné nebo zneužitelné, jako je například vyhodnocení oprávnění nebo potlačení oprávnění nespravovaného kódu?

- Jaké jsou bezpečnostní hrozby a z vašeho kódu, protože může běžet kdykoli a s pouze vysoce důvěryhodnými volajícími v zásobníku?

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, Projděte si metodu a vyhodnoťte následující:

- Je možné provést neveřejnou metodu zpracování událostí?

- Je možné přesunout ze všech nebezpečných funkcí z obslužné rutiny události?

- Pokud je zajištěna žádost o zabezpečení, je možné ji provést nějakým jiným způsobem?

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Potlačí upozornění od tohoto pravidla až po pečlivém přezkoumání zabezpečení, abyste se ujistili, že váš kód nepředstavuje bezpečnostní riziko.

## <a name="example"></a>Příklad
Následující kód ukazuje metodu zpracování událostí, která může být zneužita škodlivým kódem.

[!code-csharp[FxCop.Security.EventSecLib#1](../code-quality/codesnippet/CSharp/ca2109-review-visible-event-handlers_1.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName>
- <xref:System.EventArgs?displayProperty=fullName>