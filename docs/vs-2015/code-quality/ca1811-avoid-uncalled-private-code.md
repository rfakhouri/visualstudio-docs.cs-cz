---
title: 'CA1811: Vyhněte se nevolanému místnímu kódu | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- AvoidUncalledPrivateCode
- CA1811
helpviewer_keywords:
- CA1811
- AvoidUncalledPrivateCode
ms.assetid: aadbba74-7821-475f-8980-34d17c0a0a8b
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2f08d3fe31d6a314de9bc64441add64246f8e256
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902586"
---
# <a name="ca1811-avoid-uncalled-private-code"></a>CA1811: Vyhněte se nevolanému místnímu kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1811: Vyhněte se nevolanému místnímu kódu](https://docs.microsoft.com/visualstudio/code-quality/ca1811-avoid-uncalled-private-code).

|||
|-|-|
|TypeName|AvoidUncalledPrivateCode|
|CheckId|CA1811|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Privátní nebo interní člen (na úrovni sestavení) nemá v sestavení volající, není vyvolán modulem common language runtime a není vyvolán delegátem. Toto pravidlo nekontroluje následující členy:

-   Explicitní členy.

-   Statické konstruktory.

-   Serializační konstruktory.

-   Metody označené <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> nebo <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>.

-   Členy, které jsou přepsání.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo můžete sestavu falešně pozitivních výsledků, pokud dojde k vstupních bodů, které nejsou aktuálně identifikovaný logice pravidla. Kompilátor může také, vygenerujte noncallable kód do sestavení.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, noncallable kód odeberte, nebo přidejte kód, který je volá.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla.

## <a name="related-rules"></a>Související pravidla
 [CA1812: Vyhněte se nevytvořeným instancím vnitřních tříd](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801: Revize nepoužitých parametrů](../code-quality/ca1801-review-unused-parameters.md)

 [CA1804: Odeberte nepoužívané místní hodnoty](../code-quality/ca1804-remove-unused-locals.md)



