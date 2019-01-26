---
title: 'CA2232: Označte vstupní body modelu Windows Forms pomocí STAThread'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 1ee37645d1cc20bfd83a18b9dbb7a001731702f1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55043671"
---
# <a name="ca2232-mark-windows-forms-entry-points-with-stathread"></a>CA2232: Označte vstupní body modelu Windows Forms pomocí STAThread

|||
|-|-|
|TypeName|MarkWindowsFormsEntryPointsWithStaThread|
|CheckId|CA2232|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina
 Sestavení se odkazuje <xref:System.Windows.Forms> obor názvů a jeho vstupního bodu není označen atributem <xref:System.STAThreadAttribute?displayProperty=fullName> atribut.

## <a name="rule-description"></a>Popis pravidla
 <xref:System.STAThreadAttribute> Označuje, že práce s vlákny modelu pro aplikace modelu COM je jednovláknový apartment. Tento atribut musí být přítomen u vstupního bodu jakékoliv aplikace, která používá model Windows Forms. Pokud je vynechán, nemusí součásti systému Windows pracovat správně. Pokud atribut není k dispozici, používá aplikace s více vlákny typu apartment modelu, který není podporován pro model Windows Forms.

> [!NOTE]
> [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projekty, které používají rozhraní Framework aplikace není nutné označit **hlavní** pomocí STAThread metoda. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] Kompilátoru dělá automaticky.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, přidejte <xref:System.STAThreadAttribute> atribut pro vstupní bod. Pokud <xref:System.MTAThreadAttribute?displayProperty=fullName> je přítomen atribut, odeberte ji.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění tohoto pravidla, pokud vyvíjíte pro rozhraní .NET Compact Framework, pro kterou můžete bezpečně <xref:System.STAThreadAttribute> atribut je zbytečné a není podporována.

## <a name="example"></a>Příklad
 Následující příklady ukazují správné použití <xref:System.STAThreadAttribute>:

 [!code-csharp[FxCop.Usage.StaThread#1](../code-quality/codesnippet/CSharp/ca2232-mark-windows-forms-entry-points-with-stathread_1.cs)]
 [!code-vb[FxCop.Usage.StaThread#1](../code-quality/codesnippet/VisualBasic/ca2232-mark-windows-forms-entry-points-with-stathread_1.vb)]