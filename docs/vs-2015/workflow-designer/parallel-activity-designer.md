---
title: Návrhář aktivity Parallel | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Parallel.UI
ms.assetid: 0306dc3b-075a-4091-ac3a-96486fbabed5
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 627a99fec632871b815904abd798c0e4bbfd6505
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54791849"
---
# <a name="parallel-activity-designer"></a>Návrhář aktivity Parallel
<xref:System.Activities.Statements.Parallel> Aktivity souběžně spustí sadu podřízených aktivit.  
  
## <a name="the-parallel-activity"></a>Paralelní aktivita  
 <xref:System.Activities.Statements.Parallel> Aktivity ukládá v jeho podřízených aktivit <xref:System.Activities.Statements.Parallel.Branches%2A> kolekce. Použití <xref:System.Activities.Statements.Parallel> aktivity místo <xref:System.Activities.Statements.Sequence> aktivitu, pokud některé z podřízených aktivit může přejít nečinnosti.  
  
 <xref:System.Activities.Statements.Parallel> Má aktivita <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> vlastnost, která obsahuje uživatelem zadaný [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] výrazu. <xref:System.Activities.Statements.Parallel> Aktivita vyhodnotí tuto vlastnost po dokončení každé větve. Pokud je vyhodnocen jako **True**, pak bude <xref:System.Activities.Statements.Parallel> dokončení aktivity bez provedení další větve. Pokud <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> nevyhodnocuje na **True**, pak bude <xref:System.Activities.Statements.Parallel> aktivity se dokončí po dokončení všech jeho podřízených aktivit.  
  
### <a name="using-the-parallel-activity-designer"></a>Pomocí návrháře paralelní aktivity  
 **Paralelní** návrháře aktivit najdete v **tok řízení** kategorii **nástrojů**, který přistupuje po kliknutí **nástrojů**karty na levé straně [!INCLUDE[wfd2](../includes/wfd2-md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **Paralelní** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface všude, kde návrháři aktivit jsou obvykle umístěny, například v rámci služby **Pořadí** návrháře aktivit. Po vyřazení do [!INCLUDE[wfd2](../includes/wfd2-md.md)], vytváří <xref:System.Activities.Statements.Parallel> aktivitu, která ve výchozím nastavení obsahuje <xref:System.Activities.Activity.DisplayName%2A> z **paralelní**  
  
 Přidat aktivitu <xref:System.Activities.Statements.Parallel.Branches%2A> kolekce paralelní aktivity, přetáhněte některé další Návrhář aktivity z **nástrojů** a umístěte ho na trojúhelník uvnitř **paralelní** návrháře aktivit. Trojúhelníků paždíku aktivity obsažené v větve. Opakováním tohoto postupu lze přidat další aktivity. Aktivity mohou přeuspořádány přetahováním je v rámci **paralelní** návrháře aktivit.  
  
### <a name="parallel-activity-properties-in-the-workflow-designer"></a>Vlastnosti paralelních aktivit v Návrháři postupu provádění  
 V následující tabulce jsou uvedeny vlastnosti paralelních aktivit a popisuje, jak se používají v návrháři.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje popisný Zobrazovaný název návrháře aktivit v záhlaví. Výchozí hodnota je **paralelní**. Hodnota může volitelně můžete upravit v **vlastnosti** mřížky nebo přímo v hlavičce návrháře aktivit.|  
|<xref:System.Activities.Statements.Parallel.Branches%2A>|Pravda|Obsahuje kolekci podřízené aktivity, který se spustí.|  
|<xref:System.Activities.Statements.Parallel.CompletionCondition%2A>|False|Vyhodnocení po dokončení větev. Pokud je vyhodnocen jako **True**, pak naplánované čekající větví, se zruší. Pokud tato vlastnost není nastavená nebo se vyhodnotí jako **False**, dokončení aktivity po dokončení všech jeho podřízených aktivit. Výchozí hodnota je **null**.|  
  
## <a name="see-also"></a>Viz také  
 [Pořadí](../workflow-designer/sequence-activity-designer.md)   
 [ParallelForEach\<T>](../workflow-designer/parallelforeach-t-activity-designer.md)   
 [Tok řízení](../workflow-designer/control-flow-activity-designers.md)