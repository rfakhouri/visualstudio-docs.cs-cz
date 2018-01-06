---
title: "Postupy: Přidání zdrojového souboru | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- resource files [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, resource files
ms.assetid: 2b4ac232-992e-4070-8e98-6f11eb88e1a8
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9ba7e2fa9b9e4991ac969347791b5231ee37bbd6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-resource-file"></a>Postupy: Přidání zdrojového souboru
  Příkazy pro přidání souborů prostředků je v místní nabídce uzlu řešení a funkce uzlů v Průzkumníku řešení. Další informace najdete v tématu [lokalizace řešení služby SharePoint](../sharepoint/localizing-sharepoint-solutions.md).  
  
### <a name="to-add-a-global-resource-file-to-a-sharepoint-solution"></a>Přidání souboru globálních prostředků do řešení služby SharePoint  
  
1.  V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], otevřete řešení služby SharePoint.  
  
2.  V **Průzkumníku řešení**, vyberte uzel projektu služby SharePoint a potom na řádku nabídek zvolte **projektu**, **přidat novou položku**.  
  
3.  V **přidat novou položku** dialogovém okně vyberte **globální souboru prostředků** šablony a potom zvolte **přidat** tlačítko.  
  
    > [!NOTE]  
    >  Šablony položek projektu globální souboru prostředků se zobrazí, pouze pokud je vybrána položka projektu služby SharePoint.  
  
4.  V **přidat prostředek** dialogovém okně vyberte jazykovou verzi pro soubor prostředků, jako je angličtina (Spojené státy).  
  
     Tento krok přidává globální soubor prostředků pro vaše řešení ve formátu, prostředků*x***.** *jazykovou verzi***.** resx, jako je například Resource1.en-US.resx.  
  
5.  Když **Editor prostředků** se otevře v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], přidat prostředky do souboru prostředků.  
  
### <a name="to-add-a-feature-resource-file-to-a-sharepoint-feature"></a>Přidání funkce zdrojového souboru do funkce služby SharePoint  
  
1.  Pokud řešení služby SharePoint již není otevřen v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], otevřete řešení.  
  
2.  V **Průzkumníku řešení**, otevřete místní nabídku pro název funkce v rámci **funkce** uzel a potom zvolte **přidat prostředek funkce**.  
  
     Tento krok přidává funkce ve formátu souboru prostředků *ResourceFileName***.** *jazykovou verzi***.** resx, jako je například Feature1.en-US.resx.  
  
3.  Když **Editor prostředků** se otevře v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], přidat prostředky do souboru prostředků.  
  
## <a name="see-also"></a>Viz také  
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
  