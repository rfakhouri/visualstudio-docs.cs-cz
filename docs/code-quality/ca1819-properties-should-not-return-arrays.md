---
title: 'CA1819: Vlastnosti by neměly vracet pole'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
helpviewer_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
ms.assetid: 85fcf312-57f8-438a-8b10-34441fe0bdeb
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 9fd738b0c16ede4f71c001036546c335d8ca7186
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547052"
---
# <a name="ca1819-properties-should-not-return-arrays"></a>CA1819: Vlastnosti by neměly vracet pole

|||
|-|-|
|TypeName|PropertiesShouldNotReturnArrays|
|CheckId|CA1819|
|Kategorie|Microsoft. Performance|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Vlastnost vrací pole.

Ve výchozím nastavení toto pravidlo vypadá pouze v externě viditelných vlastnostech a typech, ale je možné jej [nakonfigurovat](#configurability).

## <a name="rule-description"></a>Popis pravidla

Pole vrácená vlastnostmi nejsou chráněna proti zápisu, a to i v případě, že je vlastnost určena pouze pro čtení. Abyste pole ochránili před změnou, musí vlastnost vrátit kopii tohoto pole. Obvykle uživatelé nebudou rozumět negativním dopadům na výkon volání takové vlastnosti. Konkrétně můžou použít vlastnost jako indexovanou vlastnost.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, buď vlastnost nastavte jako metodu, nebo změňte vlastnost tak, aby vracela kolekci.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Můžete potlačit upozornění, která je vyvolána pro vlastnost atributu odvozeného od <xref:System.Attribute> třídy. Atributy můžou obsahovat vlastnosti, které vracejí pole, ale nemůžou obsahovat vlastnosti, které vracejí kolekce.

Můžete potlačit upozornění, pokud je vlastnost součástí třídy [přenos dat objektů (DTO)](/previous-versions/msp-n-p/ff649585(v=pandp.10)) .

V opačném případě potlačíte upozornění z tohoto pravidla.

## <a name="configurability"></a>Konfigurovatelnost

Pokud toto pravidlo spouštíte z [analyzátorů FxCop](install-fxcop-analyzers.md) (a ne pomocí starší verze analýzy), můžete nakonfigurovat, které části základu kódu mají spustit toto pravidlo, na základě jejich přístupnosti. Například chcete-li určit, že pravidlo by mělo běžet pouze proti neveřejnému povrchu rozhraní API, přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
dotnet_code_quality.ca1819.api_surface = private, internal
```

Tuto možnost můžete nakonfigurovat jenom pro toto pravidlo, pro všechna pravidla nebo pro všechna pravidla v této kategorii (výkon). Další informace najdete v tématu [Konfigurace analyzátorů FxCop](configure-fxcop-analyzers.md).

## <a name="example-violation"></a>Příklad porušení

Následující příklad ukazuje vlastnost, která porušuje toto pravidlo:

[!code-csharp[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_1.cs)]
[!code-vb[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_1.vb)]

Chcete-li opravit porušení tohoto pravidla, buď vlastnost nastavte jako metodu, nebo změňte vlastnost tak, aby vracela kolekci místo pole.

### <a name="change-the-property-to-a-method"></a>Změňte vlastnost na metodu.

Následující příklad opravuje porušení změnou vlastnosti na metodu:

[!code-vb[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_2.vb)]
[!code-csharp[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_2.cs)]

### <a name="change-the-property-to-return-a-collection"></a>Změňte vlastnost tak, aby vracela kolekci.

Následující příklad opravuje porušení změnou vlastnosti tak, aby vrátila <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>:

[!code-csharp[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_3.cs)]
[!code-vb[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_3.vb)]

## <a name="allow-users-to-modify-a-property"></a>Povolení úprav vlastnosti uživateli

Můžete chtít, aby příjemce třídy mohl upravovat vlastnost. Následující příklad ukazuje vlastnost pro čtení/zápis, která porušuje toto pravidlo:

[!code-csharp[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_4.cs)]
[!code-vb[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_4.vb)]

Následující příklad opravuje porušení změnou vlastnosti tak, aby vrátila <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>:

[!code-vb[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_5.vb)]
[!code-csharp[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_5.cs)]

## <a name="related-rules"></a>Související pravidla

- [CA1024: Použijte vlastnosti, kde je to vhodné](../code-quality/ca1024-use-properties-where-appropriate.md)