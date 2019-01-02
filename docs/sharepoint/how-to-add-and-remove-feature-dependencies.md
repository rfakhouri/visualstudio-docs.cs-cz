---
title: 'Postupy: Přidání a odebrání závislostí funkce | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- MICROSOFT.VISUALSTUDIO.SHAREPOINT.DESIGNERS.CUSTOMDEPENDENCYWINDOW
- VS.SHAREPOINTTOOLS.RAD.FEATUREDESIGNERDEPENDENCY
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, features
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 704973591b1bcdcb849e847e9c5e7cefc78f0202
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53924238"
---
# <a name="how-to-add-and-remove-feature-dependencies"></a>Postupy: Přidání a odebrání závislostí funkce
  Vaše funkce služby SharePoint může záviset na jiné funkce pro funkce nebo data. V těchto případech můžete tyto funkce označit jako závislosti pro vaši funkci. Tímto způsobem serveru SharePoint zajišťuje, že jsou závislé funkce aktivované předtím, než je zapnuta.  
  
## <a name="add-dependencies"></a>Přidat závislosti  
 Můžete přidat další funkce ve vašem řešení jako závislosti. Tímto způsobem zajistíte, že jsou nainstalované a aktivovat, než je nainstalována součást pro vaše požadované funkce.  
  
#### <a name="to-add-a-dependency-on-a-feature-in-the-solution"></a>Chcete-li přidat závislost na funkci v řešení
  
1.  Otevřete návrháře funkcí, rozbalte **závislosti aktivace funkce** uzel a klikněte na tlačítko **přidat** tlačítko.  
  
2.  V **přidat závislosti aktivace funkce** dialogového okna zvolte **Přidat závislost na funkcích v řešení** přepínač, zvolte název funkce, které chcete přidat jako závislost a pak Zvolte **přidat** tlačítko.  
  
     Můžete přidat více než jednu funkci výběrem více názvů při výběru **Ctrl** klíč.  
  
## <a name="addi-custom-dependencies"></a>Addi vlastní závislosti  
 Funkce, které jsou už nasazené na Sharepointovém serveru můžete přidat jako závislost. Tímto způsobem proces aktivace SharePoint zkontroluje, ujistěte se, že jsou všechny závislé funkce aktivované předtím, než je nainstalována součást pro vaše.  
  
#### <a name="to-add-a-dependency-by-the-feature-id"></a>Chcete-li přidat závislost podle ID funkce
  
1.  Otevřete návrháře funkcí, rozbalte **závislosti aktivace funkce** uzel a klikněte na tlačítko **přidat** tlačítko.  
  
2.  V **přidat závislosti aktivace funkce** dialogového okna zvolte **přidat vlastní závislost** přepínač.  
  
3.  V **ID funkce** textové pole, zadejte identifikátor GUID pro funkci, kterou chcete označit jako závislost aktivace a klikněte na tlačítko **přidat** tlačítko.  
  
## <a name="edit-custom-dependencies"></a>Upravit vlastní závislosti  
 Můžete upravit vlastní závislosti, které jste přidali dříve. Závislé součásti, které jsou v řešení můžete pouze odebrat, ale ne upravovat.  
  
#### <a name="to-change-a-dependency-on-a-feature-in-the-solution"></a>Chcete-li změnit závislosti na funkci v řešení
  
1.  Otevřít návrháře funkcí a potom rozbalte **závislosti aktivace funkce** uzlu.  
  
2.  Zvolte název funkce, kterou chcete upravit a klikněte na tlačítko **upravit** tlačítko.  
  
3.  V **Upravit závislost aktivace vlastní funkce** dialogovém okně změnit název, ID funkce nebo popis a klikněte na tlačítko **odeslat** tlačítko.  
  
## <a name="remove-dependencies"></a>Odebrat závislosti  
  
#### <a name="to-remove-a-dependency-on-a-feature-in-the-solution"></a>Chcete-li odebrat závislost na funkci v řešení
  
1.  V Návrháři funkci Rozbalit **závislosti aktivace funkce** uzlu, vyberte název funkce, které chcete odebrat a klikněte na tlačítko **odebrat** tlačítko.  
  
## <a name="see-also"></a>Viz také:
 [Vytvoření funkcí služby SharePoint](../sharepoint/creating-sharepoint-features.md)   
 [Postupy: Přizpůsobení funkce služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [Postupy: Přidání a odebrání položek z funkcí služby SharePoint](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)  
