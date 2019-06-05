---
title: 'CA1403: Typy automatického rozložení by neměly být viditelné modelu COM'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AutoLayoutTypesShouldNotBeComVisible
- CA1403
helpviewer_keywords:
- CA1403
- AutoLayoutTypesShouldNotBeComVisible
ms.assetid: a7007714-f9b4-4730-94e0-67d3dc68991f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: ef7b693a881aaa1457004c84968ebc80936fc2b2
ms.sourcegitcommit: 5483e399f14fb01f528b3b194474778fd6f59fa6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2019
ms.locfileid: "66714844"
---
# <a name="ca1403-auto-layout-types-should-not-be-com-visible"></a>CA1403: Typy automatického rozložení by neměly být viditelné modelu COM

|||
|-|-|
|TypeName|AutoLayoutTypesShouldNotBeComVisible|
|CheckId|CA1403|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Typ hodnoty viditelné modelu COM (Component Object) je označena <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=fullName> atribut nastaven na <xref:System.Runtime.InteropServices.LayoutKind.Auto?displayProperty=fullName>.

## <a name="rule-description"></a>Popis pravidla

<xref:System.Runtime.InteropServices.LayoutKind> modul common language runtime spravuje typy rozložení. Mezi verzemi rozhraní .NET, který přeruší klienty modelu COM, které očekávají specifické rozložení můžete změnit rozložení těchto typů. Pokud <xref:System.Runtime.InteropServices.StructLayoutAttribute> atribut není zadán, C#, Visual Basic, a zadejte kompilátory C++ [hodnotu LayoutKind.Auto](<xref:System.Runtime.InteropServices.LayoutKind.Auto>) pro typy hodnot.

Pokud není označen jinak, všechny veřejné, neobecné typy jsou viditelné modelu COM, a všechny neveřejné a obecné typy nejsou viditelná modelu COM. Pokud chcete snížit počet falešně pozitivních výsledků, vyžaduje toto pravidlo viditelnost modelu COM typ, který má být explicitně uvedena. Musí být označené obsahující sestavení <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> nastavena na `false` a typ musí být označeny pomocí <xref:System.Runtime.InteropServices.ComVisibleAttribute> nastavena na `true`.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, změňte hodnotu <xref:System.Runtime.InteropServices.StructLayoutAttribute> atribut [LayoutKind.Explicit](<xref:System.Runtime.InteropServices.LayoutKind.Explicit>) nebo [LayoutKind.Sequential](<xref:System.Runtime.InteropServices.LayoutKind.Sequential>), nebo skrytí typu modelu COM.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad

Následující příklad ukazuje typ, který porušuje pravidla a typ, který splňuje pravidlo.

[!code-csharp[FxCop.Interoperability.AutoLayout#1](../code-quality/codesnippet/CSharp/ca1403-auto-layout-types-should-not-be-com-visible_1.cs)]
[!code-vb[FxCop.Interoperability.AutoLayout#1](../code-quality/codesnippet/VisualBasic/ca1403-auto-layout-types-should-not-be-com-visible_1.vb)]

## <a name="related-rules"></a>Související pravidla

[CA1408: Nepoužívejte AutoDual ClassInterfaceType](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)

## <a name="see-also"></a>Viz také:

- [Kvalifikovat typů .NET pro spolupráci](/dotnet/framework/interop/qualifying-net-types-for-interoperation)
- [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)