---
title: "Postupy: Přidat novou položku do projektu Workflow | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 5c6180ca-af10-4513-b0cb-7d478fd84eab
caps.latest.revision: "14"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: f748ce8ad7469d88ad2b50eb1704a8b979c1c636
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-add-a-new-item-to-a-workflow-project"></a>Postupy: Přidání nové položky do projektu pracovního postupu
Po vytvoření projektu workflow, můžete přidat aktivit pracovního postupu, návrháře a jiných známým rozhraním [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] položek do projektu.  
  
 Následující tabulka uvádí [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] položky, které můžete přidat do projektu pracovního postupu.  
  
|Název|Popis|  
|----------|-----------------|  
|Aktivita|Aktivity k musí se skládat z jiné aktivity. Výběrem této položky přidá ke stejnému souboru XAML do projektu, jak lze získat při výběru **knihovna aktivit** šablonu pro nový projekt. [!INCLUDE[crabout](../test/includes/crabout_md.md)]v tomto postupu najdete v části [postupy: vytvoření knihovna aktivit](../workflow-designer/how-to-create-an-activity-library.md).|  
|Návrhář aktivity|Návrhář přizpůsobit prostředí návrhu aktivity. Stejné soubory, které výběrem této položky přidáte do projektu, jak lze získat při výběru **knihovny návrháře aktivit** šablonu pro nový projekt. [!INCLUDE[crabout](../test/includes/crabout_md.md)]v tomto postupu najdete v části [postupy: vytvoření knihovny návrháře aktivit](../workflow-designer/how-to-create-an-activity-designer-library.md).|  
|Kód aktivity|Aktivita, jejíž logiky provádění napsané v kódu. Soubor zdrojového kódu se pomocí přepsání <xref:System.Activities.CodeActivity.Execute%2A> metoda byl již vygenerován za vás.|  
|Pracovní postup služby WCF|A [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] služby vytvořené pomocí aktivity pracovního postupu. Stejné soubory, které výběrem této položky přidáte do projektu, jak lze získat při výběru **aplikace služby pracovního postupu WCF** šablonu pro nový projekt. [!INCLUDE[crabout](../test/includes/crabout_md.md)]v tomto postupu najdete v části [postupy: vytvoření aplikace služby pracovního postupu WCF](../workflow-designer/how-to-create-a-wcf-workflow-service-application.md).|  
  
### <a name="to-add-a-new-item-to-a-workflow-project"></a>Chcete-li přidat novou položku do projektu pracovního postupu  
  
1.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku...** .  
  
     **Přidat novou položku** otevře se dialogové okno.  
  
2.  V **nainstalovaných šablonách** podokně, vyberte **pracovního postupu** skupiny.  
  
3.  Vyberte jeden ze čtyř položky. V předchozí tabulce jsou uvedeny možnosti, které jsou k dispozici.  
  
4.  Zadejte vhodný název pro položku v **název** pole v dolní části dialogových oken.  
  
5.  Klikněte na tlačítko **přidat** přidat položku do aktuálního projektu pracovního postupu.  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření projektu pracovního postupu](../workflow-designer/creating-a-workflow-project.md)