---
title: "Postupy: Zobrazit chyby doplňku uživatelského rozhraní | Microsoft Docs"
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
helpviewer_keywords:
- add-ins [Office development in Visual Studio], user interface errors
- errors [Office development in Visual Studio], user interface errors
- user interfaces [Office development in Visual Studio], errors
- application-level add-ins [Office development in Visual Studio], user interface errors
ms.assetid: aa82cc04-e616-4501-940c-79d11fb393cc
caps.latest.revision: "27"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 35247fed0577d410db86b6d3bd436586784f240a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-show-add-in-user-interface-errors"></a>Postupy: Zobrazení chyb uživatelského rozhraní doplňku
  Ve výchozím nastavení je-li doplňku VSTO pokusí manipulovat s Microsoft Office uživatelské rozhraní (UI) a selže, zobrazí žádná chybová zpráva. Můžete ale nakonfigurovat aplikace Microsoft Office pro zobrazení zprávy pro chyby, které se vztahují k uživatelského rozhraní. Pokud chcete zjistit, proč vlastní pás karet nezobrazí, můžete použít tyto zprávy nebo proč se zobrazí pásu karet, ale žádné ovládací prvky se zobrazí.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-show-vsto-add-in-user-interface-errors"></a>Chcete-li zobrazit chyby rozhraní doplňku VSTO uživatele  
  
1.  Spusťte aplikaci.  
  
2.  Klikněte **souboru** kartě.  
  
3.  Klikněte na tlačítko **možnosti**.  
  
4.  V podokně kategorie, klikněte na **Upřesnit**.  
  
5.  V podokně podrobností vyberte **doplňku VSTO zobrazit chyby uživatelského rozhraní**a potom klikněte na **OK**.  
  
    > [!NOTE]  
    >  Pro aplikaci Outlook **doplňku VSTO zobrazit chyby uživatelského rozhraní** zaškrtávací políčko se nachází v **vývojáře** části podokna podrobností. U ostatních aplikací na zaškrtávací políčko se nachází v **Obecné** části podokna podrobností.  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Přehled podokna akcí](../vsto/actions-pane-overview.md)  
  
  