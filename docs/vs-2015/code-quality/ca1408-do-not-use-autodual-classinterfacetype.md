---
title: 'CA1408: Nepoužívejte AutoDual ClassInterfaceType | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotUseAutoDualClassInterfaceType
- CA1408
helpviewer_keywords:
- CA1408
- DoNotUseAutoDualClassInterfaceType
ms.assetid: 60ca5e02-3c51-42dd-942b-4f950eecfa0f
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 88d23ee703b482813ad0a5401e9dea7adf9a063c
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65705711"
---
# <a name="ca1408-do-not-use-autodual-classinterfacetype"></a>CA1408: Nepoužívejte typ AutoDual ClassInterface
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotUseAutoDualClassInterfaceType|
|CheckId|CA1408|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Viditelného typu modelu COM (Component Object) je označena <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> atribut nastaven `AutoDual` hodnotu <xref:System.Runtime.InteropServices.ClassInterfaceType>.

## <a name="rule-description"></a>Popis pravidla
 Typy, které používají duální rozhraní, umožňují klientům navázat se na určité rozložení rozhraní. Změny v budoucí verzi rozložení typu nebo jakéhokoli základního typu přeruší klienty modulu COM, kteří jsou navázáni na toto rozhraní. Ve výchozím nastavení pokud <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> atribut není zadán, slouží pouze pro odeslání rozhraní.

 Pokud není označen jinak, jsou viditelné modelu COM; všechny veřejné neobecné typy všechny neveřejné a obecné typy nejsou viditelná modelu COM.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte hodnotu <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> atribut `None` hodnotu <xref:System.Runtime.InteropServices.ClassInterfaceType> a explicitně definují rozhraní.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění tohoto pravidla, pokud je jisté, že nedojde ke změně rozložení typu a jeho základních typů. v budoucí verzi.

## <a name="example"></a>Příklad
 Následující příklad ukazuje třídu, která porušuje pravidla a opakované deklaraci třídy, která se použijte explicitní rozhraní.

 [!code-csharp[FxCop.Interoperability.AutoDual#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.AutoDual/cs/FxCop.Interoperability.AutoDual.cs#1)]
 [!code-vb[FxCop.Interoperability.AutoDual#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.AutoDual/vb/FxCop.Interoperability.AutoDual.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1403: Typy automatického rozložení by neměly být viditelné modelu COM](../code-quality/ca1403-auto-layout-types-should-not-be-com-visible.md)

 [CA1412: Označte rozhraní ComSource jako IDispatch](../code-quality/ca1412-mark-comsource-interfaces-as-idispatch.md)

## <a name="see-also"></a>Viz také
 [Představení rozhraní třídy](https://msdn.microsoft.com/733c0dd2-12e5-46e6-8de1-39d5b25df024) [kvalifikace typů .NET pro spolupráci](https://msdn.microsoft.com/library/4b8afb52-fb8d-4e65-b47c-fd82956a3cdd) [spolupráce pomocí nespravovaného kódu](https://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)
