---
title: Dialogové okno pro výběr adresy URL (vývoj pro SharePoint v sadě Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.VWD.URLPicker
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, URL picker
- SharePoint development in Visual Studio, designer
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e7820723c88fd76639fa47e5c97ad179a208fc18
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120163"
---
# <a name="url-picker-dialog-box-sharepoint-development-in-visual-studio"></a>Dialogové okno pro výběr adresy URL (vývoj pro SharePoint v sadě Visual Studio)
  V dialogovém okně pro výběr adresy URL můžete soubory, jako jsou hlavní stránkovací soubory nebo soubory obrázků, které jsou umístěné ve vašem projektu nebo na místním serveru, na kterém běží SharePoint.  
  
 Toto dialogové okno se zobrazí, když máte možnost vybrat soubor, který chcete nastavit vlastnost. Toto dialogové okno můžete otevřít tak, že zvolíte tlačítko se třemi tečkami (![ASP.NET – Návrhář mobilních řešení elipsy](../sharepoint/media/mwellipsis.gif "ASP.NET – Návrhář mobilních řešení elipsy")) vedle různé vlastnosti v **vlastnosti** okno. Tlačítko se třemi tečkami se rovněž zobrazuje jako IntelliSense výzvy při přiřazení hodnoty k určité atributy v **zdroj** zobrazení návrháře.  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 **Složky projektu**  
 Zobrazí seznam složek definované v projektu nebo na místním serveru, na kterém běží SharePoint. Zvolte tlačítko se rozšíření pro zobrazení podsložky.  
  
 Rozbalte **projektu** uzel pro výběr souborů ve vašem projektu. Než se objeví jako volitelný v dialogovém okně, soubory v projektu musí splňovat následující kritéria:  
  
-   Soubor musí být součástí mapované složky.  
  
-   Soubor musí být přidán do balíčku řešení.  
  
-   Soubor nebyl nalezen v jiném projektu.  
  
 Pokud chcete odkazovat na soubory, které tato kritéria nesplňují, budete muset ručně zadejte cestu k souboru.  
  
 Rozbalte **Server** uzel a vyberte soubory, které jsou umístěné na místním serveru, na kterém běží SharePoint. Než se objeví jako volitelný v dialogovém okně, tyto soubory musí splňovat následující kritéria:  
  
-   Soubor se musí nacházet v jednom z následujících mapované složky: **bitové kopie**, **rozložení**, nebo **ControlTemplates**.  
  
-   Soubor nebyl nalezen v databázi obsahu služby SharePoint.  
  
 Pokud chcete odkazovat na soubory, které tato kritéria nesplňují, budete muset ručně zadejte cestu k souboru.  
  
 **Obsah složky**  
 Zobrazí seznam souborů ve vybrané složce. Vyberte soubor a potom vyberte **OK** tlačítko a zavřete dialogové okno Výběr poslat proces, který je volán.  
  
 **Soubory typu**  
 Umožňuje vybrat ze seznamu souborů, které jsou vhodné pro úlohy, kterou provádíte.  
  
## <a name="see-also"></a>Viz také:
 [Vytváření stránek aplikací pro službu SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [Vytvoření webové části pro službu SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [Vytváření opakovaně použitelných ovládacích prvků pro webové části nebo stránky aplikací](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)   
  
