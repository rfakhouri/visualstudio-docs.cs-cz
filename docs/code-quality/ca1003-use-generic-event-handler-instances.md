---
title: 'CA1003: Použijte instance obecných obslužných rutin události'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UseGenericEventHandlerInstances
- CA1003
helpviewer_keywords:
- CA1003
- UseGenericEventHandlerInstances
ms.assetid: 402101b6-555d-4cf7-b223-1d9fdfaaf1cd
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: f666dc71aaf9683d9a7c936cc4985e97146d9454
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842518"
---
# <a name="ca1003-use-generic-event-handler-instances"></a>CA1003: Použijte instance obecných obslužných rutin události

|||
|-|-|
|TypeName|UseGenericEventHandlerInstances|
|CheckId|CA1003|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Typ obsahuje delegát vracející hodnotu void a jehož předpis obsahuje dva parametry (první je objekt a druhý typ přiřaditelný do typu EventArgs) a .NET obsahující cíle sestavení.

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné typy, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Než .NET, chcete-li předat informace o vlastním obslužné rutiny události nového delegáta musí deklarovat, která je určena třída, která byla odvozena z <xref:System.EventArgs?displayProperty=fullName> třídy. To platí už v rozhraní .NET. Rozhraní .NET Framework zavedené <xref:System.EventHandler%601?displayProperty=fullName> delegáta, obecného delegáta, který umožňuje jakoukoli třídu, která je odvozena od <xref:System.EventArgs> se použije spolu s obslužnou rutinu události.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, odeberte delegáta a nahraďte jeho použití pomocí <xref:System.EventHandler%601?displayProperty=fullName> delegovat.

Pokud delegát je automaticky generované kompilátorem jazyka Visual Basic, změňte syntaxe deklarace události použití <xref:System.EventHandler%601?displayProperty=fullName> delegovat.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```ini
dotnet_code_quality.ca1003.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (návrh). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="example"></a>Příklad

Následující příklad ukazuje delegáta, který porušuje pravidla. Komentáře v jazyce Visual Basic příkladu popisují, jak upravte příklad tak, že splňují pravidla. Pro příklad jazyka C# následuje příklad, který ukazuje změny kódu.

[!code-vb[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/VisualBasic/ca1003-use-generic-event-handler-instances_1.vb)]
[!code-csharp[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_1.cs)]

Následující fragment kódu odstraní z předchozího příkladu, který splňuje pravidlo deklarace delegáta. Nahradí jeho použití v `ClassThatRaisesEvent` a `ClassThatHandlesEvent` metody pomocí <xref:System.EventHandler%601?displayProperty=fullName> delegovat.

[!code-csharp[FxCop.Design.GenericEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_2.cs)]

## <a name="related-rules"></a>Související pravidla

- [CA1005: Vyhněte se nadbytečným parametrům na obecných typech](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)
- [CA1010: Kolekce musí implementovat obecné rozhraní](../code-quality/ca1010-collections-should-implement-generic-interface.md)
- [CA1000: Nedeklarujte statické členy v obecných typech](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)
- [CA1002: Nezveřejňujte obecné seznamy](../code-quality/ca1002-do-not-expose-generic-lists.md)
- [CA1006: Nevnořujte obecné typy v signaturách členu](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)
- [CA1004: Obecné metody by měly poskytnout parametr typu](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)
- [CA1007: Použijte obecné typy, kde je to vhodné](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>Viz také:

- [Obecné typy](/dotnet/csharp/programming-guide/generics/index)