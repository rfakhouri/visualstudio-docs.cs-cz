---
title: 'CA1822: Označte členy jako statické'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MarkMembersAsStatic
- CA1822
helpviewer_keywords:
- MarkMembersAsStatic
- CA1822
ms.assetid: 743f0af7-41d1-4852-8d97-af0688b31118
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8f25b74949c734921c313ae2cf00a2d217029e52
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921390"
---
# <a name="ca1822-mark-members-as-static"></a>CA1822: Označte členy jako statické

|||
|-|-|
|TypeName|MarkMembersAsStatic|
|CheckId|CA1822|
|Kategorie|Microsoft. Performance|
|Narušující změna|Bez přerušení – Pokud člen není viditelný mimo sestavení, bez ohledu na změnu, kterou provedete. Bez přerušení – Pokud pouze změníte člena na člen instance pomocí `this` klíčového slova.<br /><br /> Přerušení – Pokud změníte člena z instance členu na statický člen a je viditelný mimo sestavení.|

## <a name="cause"></a>příčina
Člen, který nemá přístup k datům instance, není označený jako static (Shared [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]in).

## <a name="rule-description"></a>Popis pravidla
Členové, kteří nemají přístup k instanci dat nebo metodám instance volání může být označený jako statické (sdílené v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]). Po označení metod jako statických bude kompilátor generovat těmto členům nevirtuální místa volání. Vygenerování nevirtuálních lokalit volání zabrání v běhu kontrolu za běhu pro každé volání, které zajistí, že aktuální ukazatel na objekt je jiný než null. To může dosáhnout měřitelného nárůstu výkonu pro kód citlivý na výkon. V některých případech představuje selhání přístupu k aktuální instanci objektu problém se správností.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Označte člen jako statický (nebo sdílený v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) nebo použijte ' this '/' já ' v těle metody, pokud je to vhodné.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Z tohoto pravidla je bezpečné potlačit upozornění pro dříve dodaný kód, pro který by došlo k zásadní změně této opravy.

## <a name="related-rules"></a>Související pravidla
[CA1811: Vyhněte se nevolanému privátnímu kódu](../code-quality/ca1811-avoid-uncalled-private-code.md)

[CA1812: Vyhněte se nevytváření instancí vnitřních tříd](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

[CA1804: Odebrat nepoužívané místní hodnoty](../code-quality/ca1804-remove-unused-locals.md)