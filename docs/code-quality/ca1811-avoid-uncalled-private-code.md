---
title: 'CA1811: Vyhněte se nevolanému místnímu kódu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
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
ms.openlocfilehash: 8d9015fe8b7384046b621cd11600528cd76a97c1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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