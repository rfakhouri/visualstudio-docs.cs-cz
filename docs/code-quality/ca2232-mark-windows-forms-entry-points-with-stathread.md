---
title: 'CA2232: Označte vstupní bod modelu Windows Forms pomocí STAThread'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkWindowsFormsEntryPointsWithStaThread
- CA2232
helpviewer_keywords:
- CA2232
- MarkWindowsFormsEntryPointsWithStaThread
ms.assetid: a3c95130-8e7f-4419-9fcd-b67d077e8efb
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 043e1e6de12b3778022d27740793e7426f9eead2
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca2232-mark-windows-forms-entry-points-with-stathread"></a>CA2232: Označte vstupní bod modelu Windows Forms pomocí STAThread
|||
|-|-|
|TypeName|MarkWindowsFormsEntryPointsWithStaThread|
|CheckId|CA2232|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Sestavení odkazuje <xref:System.Windows.Forms> obor názvů a jeho vstupní bod není označen atributem <xref:System.STAThreadAttribute?displayProperty=fullName> atribut.

## <a name="rule-description"></a>Popis pravidla
 <xref:System.STAThreadAttribute> Označuje, že COM model pro aplikaci vláken je single-threaded apartment. Tento atribut musí být přítomen u vstupního bodu jakékoliv aplikace, která používá model Windows Forms. Pokud je vynechán, nemusí součásti systému Windows pracovat správně. Pokud atribut neexistuje, aplikace používá model více vláken typu apartment, což není podporováno pro Windows Forms.

> [!NOTE]
>  [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projekty, které používají rozhraní není nutné označit **hlavní** metoda pomocí STAThread. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] Kompilátoru dělá automaticky.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, přidejte <xref:System.STAThreadAttribute> atribut vstupní bod. Pokud <xref:System.MTAThreadAttribute?displayProperty=fullName> atribut je k dispozici, odeberte ji.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění na toto pravidlo, pokud vyvíjíte pro rozhraní .NET Compact Framework, pro kterou <xref:System.STAThreadAttribute> atribut je nepotřebné a není podporována.

## <a name="example"></a>Příklad
 Následující příklady ukazují správné použití <xref:System.STAThreadAttribute>.

 [!code-csharp[FxCop.Usage.StaThread#1](../code-quality/codesnippet/CSharp/ca2232-mark-windows-forms-entry-points-with-stathread_1.cs)]
 [!code-vb[FxCop.Usage.StaThread#1](../code-quality/codesnippet/VisualBasic/ca2232-mark-windows-forms-entry-points-with-stathread_1.vb)]