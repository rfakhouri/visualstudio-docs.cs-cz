---
title: 'CA1052: Statické typy vlastníků by měly být zapečetěné'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- StaticHolderTypesShouldBeSealed
- CA1052
helpviewer_keywords:
- CA1052
- StaticHolderTypesShouldBeSealed
ms.assetid: 51a3165d-781e-4a55-aa0d-ea25fee7d4f2
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 46a8c9a4e22c7a54a4b2b68f95bb2b81f3a0888e
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57870383"
---
# <a name="ca1052-static-holder-types-should-be-sealed"></a>CA1052: Statické typy vlastníků by měly být zapečetěné

|||
|-|-|
|TypeName|StaticHolderTypesShouldBeSealed|
|CheckId|CA1052|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Neabstraktního typu obsahuje pouze statické členy a není deklarován [zapečetěné](/dotnet/csharp/language-reference/keywords/sealed) ([NotInheritable](/dotnet/visual-basic/language-reference/modifiers/notinheritable)) modifikátor.

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné typy, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

CA1052 pravidlo předpokládá, že typ, který obsahuje pouze statické členy nespouští zděděno, protože typ neposkytuje všechny funkce, která může být přepsána v odvozeném typu. Typ, který není určena k dědit by měly být označené `sealed` nebo `NotInheritable` modifikátor zakázat jeho použití jako základního typu. Toto pravidlo se neaktivuje pro abstraktní třídy.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, označte typ jako `sealed` nebo `NotInheritable`. Pokud cílíte rozhraní .NET Framework 2.0 nebo novější, je lepším řešením pro označení typu jako `static` nebo `Shared`. Tímto způsobem není nutné deklarovat soukromý konstruktor třídy zabránit vytváří.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Potlačit upozornění tohoto pravidla pouze v případě, že typ je navržen tak, aby se dědila. Chybí `sealed` nebo `NotInheritable` modifikátor naznačuje, že je užitečné jako základní typ typu.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```
dotnet_code_quality.ca1052.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (návrh). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="example-of-a-violation"></a>Příkladem porušení

Následující příklad ukazuje typ, který porušuje pravidla:

[!code-csharp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_1.cs)]
[!code-vb[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/VisualBasic/ca1052-static-holder-types-should-be-sealed_1.vb)]
[!code-cpp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CPP/ca1052-static-holder-types-should-be-sealed_1.cpp)]

## <a name="fix-with-the-static-modifier"></a>Oprava s statickém modifikátoru

Následující příklad ukazuje, jak opravit porušení tohoto pravidla typu s označením `static` modifikátor v C#:

[!code-csharp[FxCop.Design.StaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_2.cs)]

## <a name="related-rules"></a>Související pravidla

- [CA1053: Statický vlastník typů by neměly mít konstruktory](../code-quality/ca1053-static-holder-types-should-not-have-constructors.md)