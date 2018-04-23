---
title: 'CA1412: Označte rozhraní ComSource jako IDispatch'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkComSourceInterfacesAsIDispatch
- CA1412
helpviewer_keywords:
- CA1412
- MarkComSourceInterfacesAsIDispatch
ms.assetid: 131a7563-0410-443c-a8f5-52104250cfb4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5e4c446f1838120afd1dbcdf21ce9710982d38c0
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1412-mark-comsource-interfaces-as-idispatch"></a>CA1412: Označte rozhraní ComSource jako IDispatch
|||
|-|-|
|TypeName|MarkComSourceInterfacesAsIDispatch|
|CheckId|CA1412|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Typ je označené jako <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> alespoň jednu zadanou rozhraní a atribut není označen atributem <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> atribut nastaven na `InterfaceIsDispatch` hodnotu.

## <a name="rule-description"></a>Popis pravidla
 <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> slouží k identifikaci událostí rozhraní, která zveřejňuje třídu klientům modelu COM (Component Object). Tato rozhraní musí být zveřejněné jako `InterfaceIsIDispatch` umožníte klientům Visual Basic 6 COM příjem oznámení o události. Ve výchozím nastavení, pokud rozhraní není označen atributem <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> atribut je zpřístupněná jako duální rozhraní.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, přidat nebo upravit <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> atributů tak, aby jeho hodnota je nastavena na InterfaceIsIDispatch pro všechna rozhraní, které jsou určené s <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> atribut.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje třídu, kde jednomu z rozhraní porušuje pravidlo.

 [!code-csharp[FxCop.Interoperability.MarkIDispatch#1](../code-quality/codesnippet/CSharp/ca1412-mark-comsource-interfaces-as-idispatch_1.cs)]
 [!code-vb[FxCop.Interoperability.MarkIDispatch#1](../code-quality/codesnippet/VisualBasic/ca1412-mark-comsource-interfaces-as-idispatch_1.vb)]

## <a name="related-rules"></a>Související pravidla
 [CA1408: Nepoužívejte AutoDual ClassInterfaceType](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)

## <a name="see-also"></a>Viz také
 [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)