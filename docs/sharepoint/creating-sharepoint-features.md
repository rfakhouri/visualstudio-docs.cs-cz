---
title: Vytváření funkcí služby SharePoint | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, features
- features [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 55b1b3f2f243a6c4d35a4c1effbb4ca759abd9d9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53842879"
---
# <a name="create-sharepoint-features"></a>Vytvoření funkcí služby SharePoint
  Funkce služby SharePoint můžete použít k seskupení souvisejících položek projektu služby SharePoint pro snazší nasazení. Můžete vytvořit funkce, nastavit obory a označit jiné funkce jako závislosti pomocí funkce návrháře služby SharePoint. Návrhář také vygeneruje manifest, který je soubor XML, který popisuje každou funkci.  
  
## <a name="add-features-to-the-sharepoint-solution"></a>Přidání funkce do řešení služby SharePoint
 Funkce můžete přidat do řešení služby SharePoint pomocí Průzkumníka řešení nebo Průzkumníku balíčků. Můžete použít jednu z následujících metod přidáte funkci.  
  
-   V **Průzkumníka řešení**, otevřete místní nabídku pro **funkce**a klikněte na tlačítko **přidat funkci**.  
  
-   V **Průzkumník balení**, otevřete místní nabídku pro balíček a klikněte na tlačítko **přidat funkci**.  
  
## <a name="using-the-feature-designer"></a>Pomocí návrháře funkcí
 Řešení služby SharePoint mohou obsahovat jednu nebo více funkcí služby SharePoint, jsou seskupené v uzlu funkce v Průzkumníku řešení. Každá funkce má svůj vlastní **funkce návrháře** , můžete použít pro přizpůsobení vlastnosti funkce. Další informace najdete v tématu [jak: Přizpůsobení funkce služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-feature.md). K rozlišení funkce od sebe, můžete nakonfigurovat vlastnosti funkce, jako je například název, popis, verze a obor.  
  
### <a name="feature-designer-options"></a>Možnosti návrháře funkcí
 Po vytvoření funkce, můžete jej přizpůsobit návrháře funkcí.  
  
 Následující tabulka popisuje vlastnosti funkce, které jsou zobrazeny v Návrháři funkce.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|Název|Volitelné. Výchozí název funkce je nastavena na *SolutionName* *FeatureName*.|  
|Popis|Volitelné. Popis funkce Sharepointu.|  
|Rozsah|Povinný parametr. Pokud funkce je vytvořena pomocí **Průzkumníka řešení**, rozsah se nastaví na webu ve výchozím nastavení.<br /><br /> -Farmy: Aktivujte funkci pro celou serverovou farmu.<br /><br /> -Lokalita: Aktivujte funkci pro všechny weby v kolekci webů.<br /><br /> – Web: Aktivujte funkci pro konkrétní web.<br /><br /> -WebApplication: Aktivujte funkci pro všechny webové servery ve webové aplikaci.|  
|Položky v řešení|Všechny položky služby SharePoint, které mohou být přidány do funkce.|  
|Položky ve funkci|Položky Sharepointového projektu, které byly přidány k funkci.|  
  
## <a name="add-and-remove-sharepoint-project-items"></a>Přidání a odebrání položek projektu služby SharePoint
 Můžete vybrat položky Sharepointového projektu, které chcete přidat funkce služby SharePoint do nasazení. Použití **návrháře funkcí** k přidání a odebrání položek z funkcí a zobrazit manifest funkce. Další informace najdete v tématu [jak: Přidání a odebrání položek z funkcí služby SharePoint](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md).  
  
## <a name="add-feature-dependencies"></a>Přidat závislosti
 Manifest funkce můžete nakonfigurovat tak, aby SharePoint server aktivuje určité funkce předtím, než je zapnuta. Například pokud vaše funkce služby SharePoint závisí na jiné funkce pro funkce nebo data, SharePoint server nejprve zkusit některou z funkcí, které vaše funkce závisí na aktivovat. Další informace najdete v tématu [jak: Přidání a odebrání závislostí funkce](../sharepoint/how-to-add-and-remove-feature-dependencies.md).  
  
## <a name="see-also"></a>Viz také:
 [Postupy: Přizpůsobení funkce služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [Postupy: Přidání a odebrání položek z funkcí služby SharePoint](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)   
 [Postupy: Přidání a odebrání závislostí funkce](../sharepoint/how-to-add-and-remove-feature-dependencies.md)  
