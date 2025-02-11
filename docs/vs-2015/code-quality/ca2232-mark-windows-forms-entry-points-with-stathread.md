---
title: 'CA2232: Vstupní body označit Windows Forms pomocí STAThread | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkWindowsFormsEntryPointsWithStaThread
- CA2232
helpviewer_keywords:
- CA2232
- MarkWindowsFormsEntryPointsWithStaThread
ms.assetid: a3c95130-8e7f-4419-9fcd-b67d077e8efb
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6e8b7242fcd82db1a0cfb82cf6cd6df5a9f75084
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63435417"
---
# <a name="ca2232-mark-windows-forms-entry-points-with-stathread"></a>CA2232: Označte vstupní body modelu Windows Forms pomocí STAThread
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
> [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] projekty, které používají rozhraní Framework aplikace není nutné označit **hlavní** pomocí STAThread metoda. [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] Kompilátoru dělá automaticky.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, přidejte <xref:System.STAThreadAttribute> atribut pro vstupní bod. Pokud <xref:System.MTAThreadAttribute?displayProperty=fullName> je přítomen atribut, odeberte ji.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění tohoto pravidla, pokud vyvíjíte pro rozhraní .NET Compact Framework, pro kterou můžete bezpečně <xref:System.STAThreadAttribute> atribut je zbytečné a není podporována.

## <a name="example"></a>Příklad
 Následující příklady ukazují správné použití <xref:System.STAThreadAttribute>.

 [!code-csharp[FxCop.Usage.StaThread#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.StaThread/cs/FxCop.Usage.StaThread.cs#1)]
 [!code-vb[FxCop.Usage.StaThread#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.StaThread/vb/FxCop.Usage.StaThread.vb#1)]
