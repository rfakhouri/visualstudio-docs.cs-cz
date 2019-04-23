---
title: 'Postupy: Přidat novou položku do projektu pracovního postupu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
ms.assetid: 5c6180ca-af10-4513-b0cb-7d478fd84eab
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ecc310896f7b938025d42e06ac5ef0ec8bac3d35
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60063621"
---
# <a name="how-to-add-a-new-item-to-a-workflow-project"></a>Postupy: Přidání nové položky do projektu pracovního postupu
Po vytvoření projektu pracovního postupu můžete přidat aktivit pracovního postupu, návrháře a další známé [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] položky do projektu.  
  
 Následující tabulce jsou uvedeny [!INCLUDE[wf](../includes/wf-md.md)] položky, které přidáte do projektu pracovního postupu.  
  
|Název|Popis|  
|----------|-----------------|  
|Aktivita|Aktivitu se skládá z jiné aktivity. Výběrem této položky přidá stejný soubor XAML do projektu, jak lze získat při výběru **knihovny aktivit** šablonu pro nový projekt. [!INCLUDE[crabout](../includes/crabout-md.md)] v tomto postupu najdete v článku [jak: Vytvoření knihovny aktivit](../workflow-designer/how-to-create-an-activity-library.md).|  
|Návrhář aktivity|Návrhář pro přizpůsobení prostředí doby návrhu aktivity. Stejné soubory, které vyberete tuto položku přidá do projektu, jak lze získat při výběru **knihovny návrháře aktivit** šablonu pro nový projekt. [!INCLUDE[crabout](../includes/crabout-md.md)] v tomto postupu najdete v článku [jak: Vytvoření knihovny návrhářů aktivit](../workflow-designer/how-to-create-an-activity-designer-library.md).|  
|Aktivita s kódem|Aktivita s logikou provádění zapsanou v kódu. Soubor zdrojového kódu pomocí přepsání <xref:System.Activities.CodeActivity.Execute%2A> metoda byl již vygenerován za vás.|  
|Služba pracovního postupu WCF|A [!INCLUDE[indigo2](../includes/indigo2-md.md)] služby vytvořené pomocí aktivit pracovního postupu. Stejné soubory, které vyberete tuto položku přidá do projektu, jak lze získat při výběru **aplikace služeb pracovního postupu WCF** šablonu pro nový projekt. [!INCLUDE[crabout](../includes/crabout-md.md)] v tomto postupu najdete v článku [jak: Vytvoření aplikace služeb pracovního postupu WCF](../workflow-designer/how-to-create-a-wcf-workflow-service-application.md).|  
  
### <a name="to-add-a-new-item-to-a-workflow-project"></a>Chcete-li přidat novou položku do projektu pracovního postupu  
  
1. Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku...** .  
  
     **Přidat novou položku** zobrazí se dialogové okno.  
  
2. V **nainstalované šablony** vyberte **pracovního postupu** skupiny.  
  
3. Vyberte jednu z čtyři položky. V předchozí tabulce jsou uvedeny možnosti, které jsou k dispozici.  
  
4. Zadejte vhodný název pro položku v **název** políčko v dolní části dialogového okna.  
  
5. Klikněte na tlačítko **přidat** přidat položku do aktuálního projektu pracovního postupu.  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření projektu pracovního postupu](../workflow-designer/creating-a-workflow-project.md)