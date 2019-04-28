---
title: Návrhář aktivity WriteLine | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.WriteLine.UI
ms.assetid: 1b5f29a8-b7fd-477e-949e-2f689cae3c96
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 591ecf53e04eaff115d45e1358f385a009ab29f5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62855228"
---
# <a name="writeline-activity-designer"></a>Návrhář aktivity WriteLine
**WriteLine** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.WriteLine> aktivity.  
  
## <a name="the-writeline-activity"></a>Aktivity WriteLine  
 <xref:System.Activities.Statements.WriteLine> Aktivita zapíše text do zadaného <xref:System.IO.TextWriter> objektu. Pokud ne <xref:System.IO.TextWriter> není zadána, <xref:System.Activities.Statements.WriteLine> zapíše text do konzoly.  
  
### <a name="using-the-writeline-activity-designer"></a>Návrhář aktivity WriteLine pomocí  
 **WriteLine** návrháře aktivit najdete v **primitiv** kategorii **nástrojů**, který přistupuje po kliknutí **nástrojů**karty [!INCLUDE[wfd2](../includes/wfd2-md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **WriteLine** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface všude, kde aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.WriteLine> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> WriteLine. <xref:System.Activities.Activity.DisplayName%2A> Můžete upravovat v záhlaví **WriteLine** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.  
  
### <a name="the-writeline-properties"></a>Vlastnosti WriteLine  
 Následující tabulka ukazuje <xref:System.Activities.Statements.WriteLine> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravit v mřížce vlastností a některé z nich bylo možné upravovat ve [!INCLUDE[wfd2](../includes/wfd2-md.md)]návrhové ploše.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.WriteLine> aktivity. Výchozí hodnota je WriteLine. I když <xref:System.Activities.Activity.DisplayName%2A> není bezpodmínečně nutné, je osvědčeným postupem použít jeden.|  
|<xref:System.Activities.Statements.WriteLine.Text%2A>|False|Text pro zápis. Chcete-li nastavena vlastnost, zadejte výraz jazyka Visual Basic v **Text** pole na **WriteLine** aktivity návrháře nebo v mřížce vlastností.|  
|<xref:System.Activities.Statements.WriteLine.TextWriter%2A>|False|<xref:System.IO.TextWriter> Ke kterému <xref:System.Activities.Statements.WriteLine> zapíše <xref:System.Activities.Statements.WriteLine.Text%2A>. Výchozí hodnota je konzola.|  
  
## <a name="see-also"></a>Viz také  
 [Primitiv](../workflow-designer/primitives-activity-designers.md)   
 [přiřazení](../workflow-designer/assign-activity-designer.md)   
 [zpoždění](../workflow-designer/delay-activity-designer.md)   
 [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)