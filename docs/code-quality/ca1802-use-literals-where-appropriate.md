---
title: 'CA1802: Použijte literály, kde je to vhodné'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UseLiteralsWhereAppropriate
- CA1802
helpviewer_keywords:
- UseLiteralsWhereAppropriate
- CA1802
ms.assetid: 2515e4cd-9e61-486d-b067-58ba1a743ce4
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: f4dbafb4c6f7ad590244842ac3def0e26f8a14fd
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57872963"
---
# <a name="ca1802-use-literals-where-appropriate"></a>CA1802: Použijte literály, kde je to vhodné

|||
|-|-|
|TypeName|UseLiteralsWhereAppropriate|
|CheckId|CA1802|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina

Pole je deklarován `static` a `readonly` (`Shared` a `ReadOnly` v jazyce Visual Basic) a je inicializován s hodnotou, kterou lze vypočítat v době kompilace.

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné pole, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Hodnota `static readonly` pole je vypočítán za běhu při volání statického konstruktoru pro deklarujícího typu. Pokud `static readonly` pole je inicializováno při deklaraci a statický konstruktor není explicitně deklarované, kompilátor vydává statický konstruktor k inicializaci pole.

Hodnota `const` pole je vypočítána v době kompilace a uložená v metadatech, což zvyšuje výkon modulu runtime srovnání s `static readonly` pole.

Protože hodnotu přiřazenou cílovému poli je nelze vypočítat v době kompilace, změňte deklaraci do `const` pole tak, aby hodnota byla vypočítána v době kompilace místo za běhu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, nahraďte `static` a `readonly` modifikátory `const` modifikátor.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla nebo zakázat pravidlo, pokud výkon není žádný problém.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```
dotnet_code_quality.ca1802.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (výkon). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="example"></a>Příklad

Následující příklad ukazuje typ, `UseReadOnly`, který porušuje pravidla a typ, `UseConstant`, vyhovující pravidlo.

[!code-vb[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/VisualBasic/ca1802-use-literals-where-appropriate_1.vb)]
[!code-csharp[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/CSharp/ca1802-use-literals-where-appropriate_1.cs)]