---
title: 'CA1408: Nepoužívejte AutoDual ClassInterfaceType'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotUseAutoDualClassInterfaceType
- CA1408
helpviewer_keywords:
- CA1408
- DoNotUseAutoDualClassInterfaceType
ms.assetid: 60ca5e02-3c51-42dd-942b-4f950eecfa0f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0f324eee1ae71f063ddd19d5a7f3d82af6f45c00
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31897010"
---
# <a name="ca1408-do-not-use-autodual-classinterfacetype"></a>CA1408: Nepoužívejte AutoDual ClassInterfaceType
|||
|-|-|
|TypeName|DoNotUseAutoDualClassInterfaceType|
|CheckId|CA1408|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Je označené jako viditelného typu modelu COM (Component Object) <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> atribut nastaven `AutoDual` hodnotu <xref:System.Runtime.InteropServices.ClassInterfaceType>.

## <a name="rule-description"></a>Popis pravidla
 Typy, které používají duální rozhraní, umožňují klientům navázat se na určité rozložení rozhraní. Změny v budoucí verzi rozložení typu nebo jakéhokoli základního typu přeruší klienty modulu COM, kteří jsou navázáni na toto rozhraní. Ve výchozím nastavení pokud <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> atribut není určena, bude použita pouze pro odeslání rozhraní.

 V opačném případě označena, všechny veřejné neobecné typy jsou viditelné pro COM; všechny neveřejní a obecné typy jsou neviditelná modelu COM.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, změňte hodnotu <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> atribut `None` hodnotu <xref:System.Runtime.InteropServices.ClassInterfaceType> a explicitně definovat rozhraní.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pokud je jisté, že nedojde ke změně rozložení typu a jeho základní typy v budoucí verzi není potlačení upozornění od tohoto pravidla.

## <a name="example"></a>Příklad
 Následující příklad ukazuje třídu, která porušuje pravidlo a opakované deklaraci třídy explicitní rozhraní použít.

 [!code-csharp[FxCop.Interoperability.AutoDual#1](../code-quality/codesnippet/CSharp/ca1408-do-not-use-autodual-classinterfacetype_1.cs)]
 [!code-vb[FxCop.Interoperability.AutoDual#1](../code-quality/codesnippet/VisualBasic/ca1408-do-not-use-autodual-classinterfacetype_1.vb)]

## <a name="related-rules"></a>Související pravidla
 [CA1403: Typy automatického rozložení by neměly být viditelné modelu COM](../code-quality/ca1403-auto-layout-types-should-not-be-com-visible.md)

 [CA1412: Označte rozhraní ComSource jako IDispatch](../code-quality/ca1412-mark-comsource-interfaces-as-idispatch.md)

## <a name="see-also"></a>Viz také
 [Kvalifikace typů .NET pro spolupráci](/dotnet/framework/interop/qualifying-net-types-for-interoperation) [spolupráce pomocí nespravovaného kódu](/dotnet/framework/interop/index)