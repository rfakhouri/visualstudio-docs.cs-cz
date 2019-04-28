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
ms.openlocfilehash: c8d80c4e9a21c29ce7b34a3998e241b11713f355
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62545697"
---
# <a name="ca2106-secure-asserts"></a>CA2106: Zabezpečte kontrolní příkazy

|||
|-|-|
|TypeName|SecureAsserts|
|CheckId|CA2106|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Metoda uplatňuje oprávnění a provádí kontroly zabezpečení volajícího.

## <a name="rule-description"></a>Popis pravidla
 Uplatnění oprávnění zabezpečení bez provedení jakékoliv kontroly zabezpečení může zanechat ve vašem kódu zneužitelné slabé stránky zabezpečení. Procházení zásobníku zabezpečení zastaví, když je uplatněna oprávnění zabezpečení. Pokud uplatňujete oprávnění bez provedení jakékoli kontroly volajícího, volající mohl nepřímo spustit kód pomocí oprávnění. Nepodmíněné výrazy bez kontroly zabezpečení jsou přípustné, pokud si nejste jisti, že že kontrolní výraz nelze použít škodlivých způsobem. Pokud kód, který voláte je neškodný, nebo pokud uživatelé nemůžou projít libovolné informace pro kód, který voláte je neškodný assert.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, přidejte do metody nebo její deklarující typ požadavku zabezpečení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění tohoto pravidla až po přezkoumání pečlivé ověření zabezpečení.

## <a name="see-also"></a>Viz také:

- <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>
- [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)