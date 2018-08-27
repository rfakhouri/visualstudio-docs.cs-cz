---
title: 'CA2232: Označte Windows Forms vstupních bodů pomocí STAThread | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
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
ms.openlocfilehash: 9345009b889b3c382ce0030c34b547a8fd337e0e
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900776"
---
# <a name="ca2232-mark-windows-forms-entry-points-with-stathread"></a>CA2232: Označte vstupní bod modelu Windows Forms pomocí STAThread
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2232: vstupní body označit Windows Forms pomocí STAThread](https://docs.microsoft.com/visualstudio/code-quality/ca2232-mark-windows-forms-entry-points-with-stathread).

|||
|-|-|
|TypeName|MarkWindowsFormsEntryPointsWithStaThread|
|CheckId|CA2232|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina
 Sestavení se odkazuje <xref:System.Windows.Forms> obor názvů a jeho vstupního bodu není označen atributem <xref:System.STAThreadAttribute?displayProperty=fullName> atribut.

## <a name="rule-description"></a>Popis pravidla
 <xref:System.STAThreadAttribute> Označuje, že práce s vlákny modelu pro aplikace modelu COM je jednovláknový apartment. Tento atribut musí být přítomen u vstupního bodu jakékoliv aplikace, která používá model Windows Forms. Pokud je vynechán, nemusí součásti systému Windows pracovat správně. Pokud atribut není k dispozici, používá aplikace s více vlákny typu apartment modelu, který není podporován pro model Windows Forms.

> [!NOTE]
>  [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] projekty, které používají rozhraní Framework aplikace není nutné označit **hlavní** pomocí STAThread metoda. [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] Kompilátoru dělá automaticky.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, přidejte <xref:System.STAThreadAttribute> atribut pro vstupní bod. Pokud <xref:System.MTAThreadAttribute?displayProperty=fullName> je přítomen atribut, odeberte ji.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění tohoto pravidla, pokud vyvíjíte pro rozhraní .NET Compact Framework, pro kterou můžete bezpečně <xref:System.STAThreadAttribute> atribut je zbytečné a není podporována.

## <a name="example"></a>Příklad
 Následující příklady ukazují správné použití <xref:System.STAThreadAttribute>.

 [!code-csharp[FxCop.Usage.StaThread#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.StaThread/cs/FxCop.Usage.StaThread.cs#1)]
 [!code-vb[FxCop.Usage.StaThread#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.StaThread/vb/FxCop.Usage.StaThread.vb#1)]



