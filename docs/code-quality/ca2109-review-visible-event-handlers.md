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
ms.openlocfilehash: de5ab1fac368f1da1ceea39df19b198a22d999c1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62808286"
---
# <a name="ca2109-review-visible-event-handlers"></a>CA2109: Zkontrolujte viditelné obslužné rutiny událostí

|||
|-|-|
|TypeName|ReviewVisibleEventHandlers|
|CheckId|CA2109|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Byla zjištěna veřejná nebo chráněná metoda zpracování událostí.

## <a name="rule-description"></a>Popis pravidla
 Externě viditelná metoda zpracování událostí představuje problém zabezpečení, která vyžaduje kontrolu.

Nezveřejňujte metody zpracování událostí, pokud není nezbytně nutné. Obslužné rutiny události, delegát typu, který vyvolá metodu vystavené lze přidat na libovolnou událost shodují signatury obslužné rutiny a události. Události může potenciálně navýšit tak, že veškerý kód a jsou často vydané kódem vysoce důvěryhodných systému v odpovědi s uživatelskými akcemi, jako je kliknutí na tlačítko. Přidání kontrolu zabezpečení metody zpracování událostí nebrání kód obslužné rutiny události, která volá metodu registrace.

 Požadavek nelze spolehlivě chránit metoda vyvolá obslužnou rutinu události. Pomoc se požadavky na zabezpečení chránit kódu z nedůvěryhodných volajících prozkoumáním volající v zásobníku volání. Kód, který přidá obslužnou rutinu události pro událost se nutně nenachází v zásobníku volání při spuštění metody obslužné rutiny události. Proto zásobník volání může mít pouze vysoce důvěryhodné volající při vyvolání metody obslužné rutiny události. To způsobí, že požadavky metodu obslužné rutiny události úspěšné. Požadované oprávnění může být také, uplatněna při vyvolání metody. Z těchto důvodů riziko není opravit porušení tohoto pravidla lze pouze použit k vyhodnocení po kontrole metody zpracování událostí. Při kontrole kódu, zvažte následující skutečnosti:

- Obslužnou rutinu události provádět žádné operace, které jsou nebezpečné nebo zneužitelné, jako je například potvrzující oprávnění nebo potlačení oprávnění nespravovaného kódu?

- Co jsou bezpečnostní hrozby na a z vašeho kódu, protože může probíhat kdykoli bez pouze vysoce důvěryhodné volající v zásobníku?

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zkontrolujte metodu a vyhodnoťte následující:

- Budete moct nastavit metodu zpracování událostí neveřejné?

- Můžete přesunout všechny funkce nebezpečné mimo obslužnou rutinu události?

- Pokud je zavedena požadavku zabezpečení, můžete to provést jiným způsobem?

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačení upozornění tohoto pravidla až po přezkoumání pečlivé ověření zabezpečení, abyste měli jistotu, že váš kód nepředstavuje bezpečnostní hrozbu.

## <a name="example"></a>Příklad
 Následující kód ukazuje metodu zpracování událostí, které mohou být zneužity škodlivý kód.

 [!code-csharp[FxCop.Security.EventSecLib#1](../code-quality/codesnippet/CSharp/ca2109-review-visible-event-handlers_1.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName>
- <xref:System.EventArgs?displayProperty=fullName>