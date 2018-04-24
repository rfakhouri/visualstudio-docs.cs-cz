---
title: 'CA1811: Vyhněte se nevolanému místnímu kódu'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidUncalledPrivateCode
- CA1811
helpviewer_keywords:
- CA1811
- AvoidUncalledPrivateCode
ms.assetid: aadbba74-7821-475f-8980-34d17c0a0a8b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d7f31b27740b286065221838e733d99e94b3307d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1811-avoid-uncalled-private-code"></a>CA1811: Vyhněte se nevolanému místnímu kódu
|||
|-|-|
|TypeName|AvoidUncalledPrivateCode|
|CheckId|CA1811|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Člen soukromý nebo interní (sestavení úrovni) nemá volající v sestavení, není vyvolané modul common language runtime a není vyvolané delegáta. Toto pravidlo není zaškrtnuta možnost následující členy:

-   Explicitní rozhraní členy.

-   Statické konstruktory.

-   Serializační konstruktory.

-   Metody označené jako <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> nebo <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>.

-   Členy, kteří jsou přepsání.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo může hlásit, že falešně pozitivních, pokud dojde k vstupní body, které nejsou aktuálně identifikovaný logice pravidla. Kompilátor také může vysílat noncallable kódu do sestavení.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, odeberte kód noncallable nebo přidejte kód, který volá ho.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné upozornění toto pravidlo potlačit.

## <a name="related-rules"></a>Související pravidla
 [CA1812: Vyhněte se nevytvořeným instancím vnitřních tříd](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801: Revize nepoužitých parametrů](../code-quality/ca1801-review-unused-parameters.md)

 [CA1804: Odeberte nepoužívané místní hodnoty](../code-quality/ca1804-remove-unused-locals.md)