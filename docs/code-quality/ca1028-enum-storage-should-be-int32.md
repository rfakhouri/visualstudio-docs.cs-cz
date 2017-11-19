---
title: "CA1028: Úložiště výčtu by měl být Int32 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1028
- EnumStorageShouldBeInt32
helpviewer_keywords:
- EnumStorageShouldBeInt32
- CA1028
ms.assetid: 87160825-9f39-4142-8d7f-a31fe7ac7b84
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bd0f74a322e136263b6445db2692380dfea2efa3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1028-enum-storage-should-be-int32"></a>CA1028: Úložiště výčtu by měl být Int32
|||  
|-|-|  
|TypeName|EnumStorageShouldBeInt32|  
|CheckId|CA1028|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Základní typ veřejný výčet není <xref:System.Int32?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Popis pravidla  
 Výčet je typ hodnoty, který definuje množinu souvisejících pojmenovaných konstant. Ve výchozím nastavení <xref:System.Int32?displayProperty=fullName> datový typ se používá k ukládání konstantní hodnotu. I když toto můžete změnit základní typ, není nutné nebo doporučené pro většinu scénářů. Všimněte si, že žádné významné výkonnější je dosaženo pomocí datový typ, který je menší než <xref:System.Int32>. Pokud nemůžete použít výchozí typ dat, měli byste použít jeden z System CLS (Common Language)-vyhovující integrální typy <xref:System.Byte>, <xref:System.Int16>, <xref:System.Int32>, nebo <xref:System.Int64> a ujistěte se, že všechny hodnoty výčtu může být reprezentován v Kompatibilní se specifikací CLS programovací jazyky.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, pokud k problémům s velikost nebo kompatibility, použijte <xref:System.Int32>. Pro situace, kdy <xref:System.Int32> není dostatečně velký pro uložení hodnot, použijte <xref:System.Int64>. Pokud zpětné kompatibility vyžaduje menší datový typ, použijte <xref:System.Byte> nebo <xref:System.Int16>.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačíte upozornění na toto pravidlo pouze v případě, že to vyžadují problémy zpětné kompatibility. V aplikacích nedodržení tohoto pravidla obvykle nezpůsobí potíže. V knihovnách, kdy je potřeba vzájemná funkční spolupráce jazyka, nedodržení tohoto pravidla může nepříznivě ovlivnit vaši uživatelé.  
  
## <a name="example-of-a-violation"></a>Příkladem porušení  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje dva výčty, které nepoužívají doporučené základní datový typ.  
  
### <a name="code"></a>Kód  
 [!code-vb[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_1.vb)]
 [!code-csharp[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_1.cs)]  
  
## <a name="example-of-how-to-fix"></a>Příklad, jak k opravě  
  
### <a name="description"></a>Popis  
 Následující příklad opravy předchozí porušení změnou základní datový typ pro <xref:System.Int32>.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_2.cs)]
 [!code-vb[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_2.vb)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1008: Výčty by měly mít nulovou hodnotu](../code-quality/ca1008-enums-should-have-zero-value.md)  
  
 [CA1027: Označte výčty pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
 [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
 [CA1700: Nepojmenovávejte hodnoty výčtu 'Reserved'](../code-quality/ca1700-do-not-name-enum-values-reserved.md)  
  
 [CA1712: Nezadávejte na hodnoty výčtu s názvem typu](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Byte?displayProperty=fullName>   
 <xref:System.Int16?displayProperty=fullName>   
 <xref:System.Int32?displayProperty=fullName>   
 <xref:System.Int64?displayProperty=fullName>