---
title: 'Postupy: Přidání zdrojového souboru | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- resource files [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, resource files
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3406e65ad96b93cd21890d61270c0ed989ad496c
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756568"
---
# <a name="how-to-add-a-resource-file"></a>Postupy: Přidání zdrojového souboru
  Příkazy pro přidání souborů prostředků je v místní nabídce uzlu řešení a funkce uzlů v Průzkumníku řešení. Další informace najdete v tématu [řešení služby SharePoint lokalizace](../sharepoint/localizing-sharepoint-solutions.md).  
  
### <a name="to-add-a-global-resource-file-to-a-sharepoint-solution"></a>Přidání souboru globálních prostředků do řešení služby SharePoint  
  
1.  V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], otevřete řešení služby SharePoint.  
  
2.  V **Průzkumníku řešení**, vyberte uzel projektu služby SharePoint a potom na řádku nabídek zvolte **projektu** > **přidat novou položku**.  
  
3.  V **přidat novou položku** dialogovém okně vyberte **globální souboru prostředků** šablony a potom zvolte **přidat** tlačítko.  
  
    > [!NOTE]  
    >  Šablony položek projektu globální souboru prostředků se zobrazí, pouze pokud je vybrána položka projektu služby SharePoint.  
  
4.  V **přidat prostředek** dialogovém okně vyberte jazykovou verzi pro soubor prostředků, jako je angličtina (Spojené státy).  
  
     Tento krok přidává globální soubor prostředků pro vaše řešení ve formátu, prostředků * x ***.*** jazyková verze ***.** resx, jako je třeba *Resource1.en-US.resx*.  
  
5.  Když **Editor prostředků** se otevře v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], přidat prostředky do souboru prostředků.  
  
### <a name="to-add-a-feature-resource-file-to-a-sharepoint-feature"></a>Přidání funkce zdrojového souboru do funkce služby SharePoint  
  
1.  Pokud řešení služby SharePoint již není otevřen v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], otevřete řešení.  
  
2.  V **Průzkumníku řešení**, otevřete místní nabídku pro název funkce v rámci **funkce** uzel a potom zvolte **přidat prostředek funkce**.  
  
     Tento krok přidává funkce ve formátu souboru prostředků * ResourceFileName ***.*** jazyková verze ***.** resx, jako je třeba *Feature1.en-US.resx*.  
  
3.  Když **Editor prostředků** se otevře v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], přidat prostředky do souboru prostředků.  
  
## <a name="see-also"></a>Viz také:
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
 
