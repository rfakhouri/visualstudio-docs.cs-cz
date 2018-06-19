---
title: 'CA2233: Operace by neměly přetéct'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- OperationsShouldNotOverflow
- CA2233
helpviewer_keywords:
- OperationsShouldNotOverflow
- CA2233
ms.assetid: 3a2b06ba-6d1b-4666-9eaf-e053ef47ffaa
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93d4fc872f14a63eeec446d8e6d1f9a2c7acf7ff
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31919302"
---
# <a name="ca2233-operations-should-not-overflow"></a>CA2233: Operace by neměly přetéct
|||
|-|-|
|TypeName|OperationsShouldNotOverflow|
|CheckId|CA2233|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Metoda provádí aritmetické operace a neověřuje operandy předem, aby zabránil přetečení.

## <a name="rule-description"></a>Popis pravidla
 Aritmetické operace nebude prováděna bez první ověření a ujistěte se, že výsledek operace není mimo rozsah možných hodnot pro typy dat zahrnutých operandy. V závislosti na kontextu spuštění a datové typy související se situací, aritmetického přetečení může mít za následek buď <xref:System.OverflowException?displayProperty=fullName> nebo zrušených nejvýznamnějších bits výsledku.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, ověřte operandy před provedením operace.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění na toto pravidlo, je-li možné hodnoty operandy nikdy způsobí přetečení aritmetické operace.

## <a name="example-of-a-violation"></a>Příkladem porušení

### <a name="description"></a>Popis
 Metoda v následujícím příkladu manipuluje celé číslo, které je v rozporu toto pravidlo. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] vyžaduje **odebrat** možnost přetečení celé číslo se zakáže tento postup provést.

### <a name="code"></a>Kód
 [!code-vb[FxCop.Usage.OperationOverflow#1](../code-quality/codesnippet/VisualBasic/ca2233-operations-should-not-overflow_1.vb)]
 [!code-csharp[FxCop.Usage.OperationOverflow#1](../code-quality/codesnippet/CSharp/ca2233-operations-should-not-overflow_1.cs)]

### <a name="comments"></a>Komentáře
 Pokud metoda v tomto příkladu je předán <xref:System.Int32.MinValue?displayProperty=fullName>, operace by podtečení. To způsobí, že nejvyšší bit výsledku budou zahozeny. Následující kód ukazuje, jak k tomu dochází.

 [C#]

```
public static void Main()
{
    int value = int.MinValue;    // int.MinValue is -2147483648
    value = Calculator.Decrement(value);
    Console.WriteLine(value);
}
```

 [VB]

```
Public Shared Sub Main()
    Dim value = Integer.MinValue    ' Integer.MinValue is -2147483648
    value = Calculator.Decrement(value)
    Console.WriteLine(value)
End Sub
```

### <a name="output"></a>Výstup

```
2147483647
```

## <a name="fix-with-input-parameter-validation"></a>Oprava se vstupní parametr ověření

### <a name="description"></a>Popis
 Následující příklad opravy předchozí porušení ověřením hodnota vstupu.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Usage.OperationOverflowFixed#1](../code-quality/codesnippet/CSharp/ca2233-operations-should-not-overflow_2.cs)]
 [!code-vb[FxCop.Usage.OperationOverflowFixed#1](../code-quality/codesnippet/VisualBasic/ca2233-operations-should-not-overflow_2.vb)]

## <a name="fix-with-a-checked-block"></a>Oprava se zaškrtnuté bloku

### <a name="description"></a>Popis
 Následující příklad opravy předchozí porušení podle zabalení operaci v zaškrtnuté bloku. Pokud operace způsobí přetečení, <xref:System.OverflowException?displayProperty=fullName> bude vyvolána.

 Všimněte si, že zaškrtnuté bloky nejsou podporovány v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)].

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Usage.OperationOverflowChecked#1](../code-quality/codesnippet/CSharp/ca2233-operations-should-not-overflow_3.cs)]

## <a name="turn-on-checked-arithmetic-overflowunderflow"></a>Zapnout zaškrtnuté aritmetického přetečení nebo podtečení
 Pokud zapnete zaškrtnuté aritmetického přetečení nebo podtečení v jazyce C#, je ekvivalentní zabalení každé operace celé číslo v zaškrtnuté bloku.

 **Chcete-li zaškrtnutí aritmetického přetečení nebo podtečení v jazyce C#**

1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a vyberte možnost **vlastnosti**.

2.  Vyberte **sestavení** a klikněte na **Upřesnit**.

3.  Vyberte **Kontrola aritmetického přetečení nebo podtečení** a klikněte na tlačítko **OK**.

## <a name="see-also"></a>Viz také
 <xref:System.OverflowException?displayProperty=fullName> [Operátory jazyka C#](/dotnet/csharp/language-reference/operators/index) [zaškrtnuto a nezaškrtnuto](/dotnet/csharp/language-reference/keywords/checked-and-unchecked)