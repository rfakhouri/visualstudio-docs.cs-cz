---
title: "Postupy: Přidání a odebrání závislostí funkce | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MICROSOFT.VISUALSTUDIO.SHAREPOINT.DESIGNERS.CUSTOMDEPENDENCYWINDOW
- VS.SHAREPOINTTOOLS.RAD.FEATUREDESIGNERDEPENDENCY
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, features
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 6e74ac8cef88319a54df0c08cd91fb2654d390cb
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-and-remove-feature-dependencies"></a>Postupy: Přidání a odebrání závislostí funkce
  Vaše funkce služby SharePoint může záviset na jiných funkcí pro funkce nebo data. V těchto případech můžete tyto další funkce označit jako závislosti pro vaše funkci. Tímto způsobem serveru SharePoint zajišťuje, že závislé součásti jsou aktivované předtím, než je zapnuta.  
  
## <a name="adding-dependencies"></a>Přidání závislostí  
 Můžete přidat další funkce ve vašem řešení jako závislosti. Tímto způsobem zajistit instalace a aktivovat dříve, než je nainstalována součást pro vaše požadované funkce.  
  
#### <a name="to-add-a-dependency-on-a-feature-in-the-solution"></a>Chcete-li přidat závislost na funkci v řešení  
  
1.  Otevřete návrháře funkce, rozbalte **závislostí aktivace funkce** uzel a potom zvolte **přidat** tlačítko.  
  
2.  V **přidat závislosti aktivace funkce** dialogovém okně vyberte **Přidat závislost na funkce v řešení** možnost tlačítko, vyberte název funkce, která chcete přidat jako závislost a potom Vyberte **přidat** tlačítko.  
  
     Při výběru klávesu Ctrl a vybrat několik témat můžete přidat více než jedna z funkcí.  
  
## <a name="adding-custom-dependencies"></a>Přidání vlastní závislosti  
 Funkce, které jsou už nasazené na serveru služby SharePoint můžete přidat jako závislost. Tímto způsobem proces aktivace SharePoint zkontroluje, ujistěte se, že všechny závislé součásti jsou aktivované předtím, než je nainstalována součást pro vaše.  
  
#### <a name="to-add-a-dependency-by-the-feature-id"></a>Chcete-li přidat závislost podle ID funkce  
  
1.  Otevřete návrháře funkce, rozbalte **závislostí aktivace funkce** uzel a potom zvolte **přidat** tlačítko.  
  
2.  V **přidat závislosti aktivace funkce** dialogovém okně vyberte **přidejte vlastní závislost** tlačítko.  
  
3.  V **ID funkce** text zadejte identifikátor GUID pro funkce, které chcete označit jako závislost k aktivaci a potom vyberte **přidat** tlačítko.  
  
## <a name="editing-custom-dependencies"></a>Úpravy vlastní závislosti  
 Můžete upravit vlastní závislosti, které jste přidali dříve. Závislé součásti, které jsou v řešení můžete pouze odebrat, ale ne upravovat.  
  
#### <a name="to-change-a-dependency-on-a-feature-in-the-solution"></a>Chcete-li změnit závislost na funkci v řešení  
  
1.  Otevřete návrháře funkce a potom rozbalte **závislostí aktivace funkce** uzlu.  
  
2.  Zvolte název funkce, kterou chcete upravit a potom vyberte **upravit** tlačítko.  
  
3.  V **upravit vlastní funkce aktivace závislost** dialogové okno, změňte název, ID funkce nebo popis a potom zvolte **odeslání** tlačítko.  
  
## <a name="removing-dependencies"></a>Odebrání závislostí  
  
#### <a name="to-remove-a-dependency-on-a-feature-in-the-solution"></a>Chcete-li odebrat závislost na funkci v řešení  
  
1.  V Návrháři funkci Rozbalit **závislostí aktivace funkce** uzlu, vyberte název funkce, kterou chcete odebrat a potom vyberte **odebrat** tlačítko.  
  
## <a name="see-also"></a>Viz také  
 [Vytváření funkcí služby SharePoint](../sharepoint/creating-sharepoint-features.md)   
 [Postupy: přizpůsobení funkce služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [Postupy: Přidání a odebrání položek z funkcí služby SharePoint](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)  
  
  