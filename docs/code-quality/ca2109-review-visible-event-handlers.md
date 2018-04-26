---
title: 'CA2109: Revize viditelných obslužných rutin událostí'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 481f03cc9f1699a794c0f34159afd7faa6a50c3d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca2109-review-visible-event-handlers"></a>CA2109: Revize viditelných obslužných rutin událostí
|||
|-|-|
|TypeName|ReviewVisibleEventHandlers|
|CheckId|CA2109|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Byla zjištěna veřejná nebo chráněná metoda zpracování událostí.

## <a name="rule-description"></a>Popis pravidla
 Zpracování událostí metodu externě viditelné uvede problém zabezpečení, která vyžaduje kontrolu.

 Metody zpracování událostí by neměly být vystaveny, pokud to není nezbytně nutné. Obslužné rutiny události, typem delegáta, která volá metodu zveřejněné lze přidat na libovolnou událost tak dlouho, dokud obslužné rutiny a událostí podpisů shodují. Události lze zvýšit potenciálně žádný kód a jsou často vydané kódem vysoce důvěryhodných systému v odpovědi na akce uživatele, jako je například kliknutí na tlačítko. Přidání kontrolu zabezpečení pro metodu zpracování událostí nezabrání kód registraci obslužné rutiny události, která volá metodu.

 Požadavek nelze chránit spolehlivě metodu vyvolat obslužnou rutinu události. Zabezpečení vyžaduje nápovědy chránit kód z nedůvěryhodného volající prověřením volající v zásobníku volání. Kód, který přidá obslužnou rutinu události pro událost se nutně nenachází v zásobníku volání při spuštění metody obslužné rutiny události. Proto zásobníku volání může mít pouze vysoce důvěryhodné volající při vyvolání metody obslužné rutiny události. To způsobí, že požadavky provedené obslužná rutina události proběhla úspěšně. Požadované oprávnění také, může se uplatní při vyvolání metody. Z těchto důvodů může riziko není oprava porušení toto pravidlo hodnoceno pouze po zkontrolování metodu zpracování událostí. Při kontrole kódu, zvažte následující skutečnosti:

-   Vaší obslužné rutiny událostí provádět žádné operace, které jsou nebezpečné nebo využitelných, jako je například potvrzující oprávnění nebo potlačení oprávnění nespravovaného kódu?

-   Co jsou bezpečnostní hrozby do a z vašeho kódu, protože ho můžete spustit kdykoli bez pouze vysoce důvěryhodné volající v zásobníku?

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, metoda kontrola a vyhodnocení následující:

-   Můžete provádět metodu zpracování událostí neveřejný?

-   Můžete přesunout všechny nebezpečné funkce mimo obslužné rutiny události?

-   Pokud je požadavek zabezpečení zařízení, můžete to udělat jiným způsobem?

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačíte upozornění od tohoto pravidla až po kontrolu zabezpečení pozor, abyste měli jistotu, že kód není představovat ohrožení zabezpečení.

## <a name="example"></a>Příklad
 Následující kód ukazuje metodu zpracování událostí, která může došlo ke zneužití škodlivý kód.

 [!code-csharp[FxCop.Security.EventSecLib#1](../code-quality/codesnippet/CSharp/ca2109-review-visible-event-handlers_1.cs)]

## <a name="see-also"></a>Viz také
 <xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName><xref:System.EventArgs?displayProperty=fullName>
