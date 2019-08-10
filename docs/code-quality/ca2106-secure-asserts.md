---
title: 'CA2106: Zabezpečte kontrolní příkazy'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2106
- SecureAsserts
helpviewer_keywords:
- CA2106
- SecureAsserts
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: df19d31abe88c6d12bafc933ba740badb832eb16
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921075"
---
# <a name="ca2106-secure-asserts"></a>CA2106: Zabezpečte kontrolní příkazy

|||
|-|-|
|TypeName|SecureAsserts|
|CheckId|CA2106|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Metoda uplatňuje oprávnění a neprovádí žádné kontroly zabezpečení volajícího.

## <a name="rule-description"></a>Popis pravidla
Uplatnění oprávnění zabezpečení bez provedení jakékoliv kontroly zabezpečení může zanechat ve vašem kódu zneužitelné slabé stránky zabezpečení. Pokud je uplatněno oprávnění zabezpečení, procházení zásobníku zabezpečení se zastaví. Pokud potvrdíte oprávnění bez provedení kontroly volajícího, volající by mohl nepřímo spustit kód pomocí vašich oprávnění. Výrazy bez kontroly zabezpečení jsou přípustné, pokud jste si jisti, že kontrolní výraz nelze použít škodlivým způsobem. Kontrolní výraz je neškodný, pokud je kód, který zavoláte, neškodný, nebo pokud uživatelé nemohou předat libovolné informace do kódu, který zavoláte.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, přidejte požadavek zabezpečení do metody nebo jejího deklarovaného typu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Potlačí upozornění od tohoto pravidla až po pečlivou kontrolu zabezpečení.

## <a name="see-also"></a>Viz také:

- <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>
- [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)