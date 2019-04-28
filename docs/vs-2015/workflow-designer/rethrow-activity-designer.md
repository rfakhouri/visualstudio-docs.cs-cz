---
title: Návrhář aktivity Rethrow | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Rethrow.UI
ms.assetid: 9cfa2eda-395f-4cf3-9154-83fadd4f7452
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8b023a42da1c862927606c4bec0215120a5e5a11
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62937754"
---
# <a name="rethrow-activity-designer"></a>Návrhář aktivity Rethrow
**Znovu vyvolejte** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Rethrow> aktivity.  
  
## <a name="the-rethrow-activity"></a>Aktivita Přegenerování  
 <xref:System.Activities.Statements.Rethrow> Aktivita vyvolá dříve vyvolané výjimky. Tato aktivita se dá použít jenom v <xref:System.Activities.Statements.Catch> obslužné rutiny v <xref:System.Activities.Statements.TryCatch> aktivity.  
  
### <a name="using-the-rethrow-activity-designer"></a>Návrhář aktivity ReThrow pomocí  
 **Znovu vyvolejte** návrháře aktivit najdete v **zpracování chyb** kategorii **nástrojů**, který přistupuje po kliknutí **nástrojů**karty na levé straně [!INCLUDE[wfd2](../includes/wfd2-md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **Znovu vyvolejte** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface všude, kde aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Rethrow> aktivity s výchozím **DisplayName** o vyvolání výjimky. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v záhlaví **znovu vyvolejte** Návrhář aktivity nebo **DisplayName** pole mřížku vlastností.  
  
### <a name="the-rethrow-properties"></a>Vlastnosti Rethrow  
 Následující tabulka ukazuje <xref:System.Activities.Statements.Rethrow> vlastnosti a popisuje, jak se používají v návrháři.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje volitelný popisný název <xref:System.Activities.Statements.Rethrow> aktivity. Výchozí hodnota je Přegenerování.|  
  
## <a name="see-also"></a>Viz také  
 [Kolekce](../workflow-designer/collection-activity-designers.md)   
 [vyvolání výjimky](../workflow-designer/throw-activity-designer.md)   
 [TryCatch](../workflow-designer/trycatch-activity-designer.md)