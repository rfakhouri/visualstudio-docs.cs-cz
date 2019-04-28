---
title: 'CA1301: Vyhněte se duplicitním akcelerátorům'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1301
- AvoidDuplicateAccelerators
helpviewer_keywords:
- CA1301
- AvoidDuplicateAccelerators
ms.assetid: 20570a00-864b-459c-a1fa-a6e9db5f1001
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f82163b1c377df4c8c7fcbba07672312153dad9b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62797479"
---
# <a name="ca1301-avoid-duplicate-accelerators"></a>CA1301: Vyhněte se duplicitním akcelerátorům

|||
|-|-|
|TypeName|AvoidDuplicateAccelerators|
|CheckId|CA1301|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Typ rozšiřuje <xref:System.Windows.Forms.Control?displayProperty=fullName> a obsahuje dva nebo více nejvyšší úrovně ovládací prvky, které mají stejné přístupové klíče, které jsou uloženy do souboru prostředků.

## <a name="rule-description"></a>Popis pravidla

Přístupová klávesa neboli akcelerátor umožňuje klávesnici přístup k ovládacímu prvku s použitím **Alt** klíč. Když více ovládacích prvků mají stejný přístupový klíč, není chování přístupové klávesy dobře definované. Uživatel nemusí být možné získat přístup k odpovídající ovládací prvek pomocí přístupového klíče a ovládací prvek než ten, který je určený může být povolený.

Aktuální implementace tohoto pravidla ignoruje položky nabídky. Položky nabídky v podnabídce stejné ale by neměly mít identické přístupové klíče.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, definujte jedinečné přístupových klíčů pro všechny ovládací prvky.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje minimální formulář, který obsahuje dva ovládací prvky, které mají stejné přístupové klíče. Klíče jsou uložené v souboru prostředků, která není zobrazena. Jejich hodnoty se však zobrazí ve komentářem si `checkBox.Text` řádky. Chování duplicitním akcelerátorům se dají prozkoumat výměnou `checkBox.Text` řádky s jejich protějšky komentářem navýšení kapacity. Ale v takovém případě příklad nebude generovat upozornění z pravidla.

 [!code-csharp[FxCop.Globalization.AvoidDuplicateAccels#1](../code-quality/codesnippet/CSharp/ca1301-avoid-duplicate-accelerators_1.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.Resources.ResourceManager?displayProperty=fullName>
- [Prostředky v desktopových aplikacích](/dotnet/framework/resources/index)