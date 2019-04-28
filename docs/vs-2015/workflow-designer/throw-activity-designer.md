---
title: Návrhář aktivity throw | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Throw.UI
ms.assetid: 5e97c947-be39-4a1f-af04-000e2e09528a
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: db909618971eeab2d92506d1c29b06290aa9263b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62976619"
---
# <a name="throw-activity-designer"></a>Návrhář aktivity Throw
**Throw** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Throw> aktivity.  
  
## <a name="the-throw-activity"></a>Aktivity Throw  
 <xref:System.Activities.Statements.Throw> Aktivita vyvolá výjimku.  
  
### <a name="using-the-throw-activity-designer"></a>Pomocí Návrhář aktivity Throw  
 **Throw** návrháře aktivit najdete v **zpracování chyb** kategorii **nástrojů**, který přistupuje po kliknutí **nástrojů**karty na levé straně [!INCLUDE[wfd2](../includes/wfd2-md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **Throw** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface všude, kde aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Throw> aktivity s výchozím **DisplayName** o vyvolání výjimky. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v záhlaví **Throw** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností. <xref:System.Activities.Statements.Throw.Exception%2A> Vlastnost musí upravit v mřížce vlastností.  
  
### <a name="the-throw-properties"></a>Vyvolání vlastnosti  
 Následující tabulka ukazuje <xref:System.Activities.Statements.Throw> vlastnosti a popisuje, jak se používají v návrháři.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje volitelný popisný název <xref:System.Activities.Statements.Throw> aktivity. Výchozí hodnota je vyvolání výjimky.|  
|<xref:System.Activities.Statements.Throw.Exception%2A>|Pravda|Výjimka, která má být vyvolána. Tato výjimka musí být odvozen od <xref:System.Exception>. Pokud chcete nastavit výjimky, zadejte výraz jazyka Visual Basic v mřížce vlastností.|  
  
## <a name="see-also"></a>Viz také  
 [Kolekce](../workflow-designer/collection-activity-designers.md)   
 [Znovu vyvolejte](../workflow-designer/rethrow-activity-designer.md)   
 [Návrhář aktivity throw](../workflow-designer/throw-activity-designer.md)   
 [TryCatch](../workflow-designer/trycatch-activity-designer.md)