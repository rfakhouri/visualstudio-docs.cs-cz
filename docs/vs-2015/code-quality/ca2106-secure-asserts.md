---
title: 'CA2106: Zabezpečte nepodmíněné výrazy | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2106
- SecureAsserts
helpviewer_keywords:
- CA2106
- SecureAsserts
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 1fb1968c6e2750f658f39f009c97fbab133cccab
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65687399"
---
# <a name="ca2106-secure-asserts"></a>CA2106: Zabezpečte kontrolní příkazy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|SecureAsserts|
|CheckId|CA2106|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Metoda uplatňuje oprávnění a na volajícím nejsou vykonány žádné kontroly zabezpečení.

## <a name="rule-description"></a>Popis pravidla
 Uplatnění oprávnění zabezpečení bez provedení jakékoliv kontroly zabezpečení může zanechat ve vašem kódu zneužitelné slabé stránky zabezpečení. Procházení zásobníku zabezpečení zastaví, když je uplatněna oprávnění zabezpečení. Pokud uplatňujete oprávnění bez provedení jakékoli kontroly volajícího, volající mohl nepřímo spustit kód pomocí oprávnění. Nepodmíněné výrazy bez kontroly zabezpečení jsou přípustné, pouze pokud jste si jisti, že kontrolní výraz nelze použít škodlivých způsobem. Assert je neškodný, pokud kód, který voláte je neškodný, nebo uživatelé nemůžou projít libovolné informace pro kód, který voláte.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, přidejte do metody nebo její deklarující typ požadavku zabezpečení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění tohoto pravidla až po přezkoumání pečlivé ověření zabezpečení.

## <a name="see-also"></a>Viz také
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName> [Pokyny pro zabezpečené kódování](https://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)
