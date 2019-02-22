---
title: Dialogové okno pro výběr adresy URL (vývoj pro SharePoint v sadě Visual Studio) | Dokumentace společnosti Microsoft
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.VWD.URLPicker
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, URL picker
- SharePoint development in Visual Studio, designer
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8d8f193e50053b5cdf0b89cf41b09471c513ee9d
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56635173"
---
# <a name="url-picker-dialog-box-sharepoint-development-in-visual-studio"></a>Dialogové okno pro výběr adresy URL (vývoj pro SharePoint v sadě Visual Studio)
  V dialogovém okně pro výběr adresy URL můžete soubory, jako jsou soubory stránky předlohy nebo obrazových souborů, které se nacházejí v projektu nebo na místním serveru, na kterém běží SharePoint.

 Toto dialogové okno se zobrazí, když máte možnost vybrat soubor k nastavení vlastnosti. Toto dialogové okno můžete otevřít kliknutím tlačítko se třemi tečkami (![ASP.NET – Návrhář mobilních řešení Elipsa](../sharepoint/media/mwellipsis.gif "elipsa ASP.NET – Návrhář mobilních řešení")) vedle různé vlastnosti v **vlastnosti** okna. Tlačítko se třemi tečkami se rovněž zobrazuje jako IntelliSense výzvy při přiřazení hodnoty k určité atributy v **zdroj** zobrazení návrháře.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 **Projekt složky** zobrazí seznam složek definované v projektu nebo na místním serveru, na kterém běží SharePoint. Klikněte na tlačítko rozšíření zobrazíte podsložky.

 Rozbalte **projektu** uzel k výběru souborů ve vašem projektu. Zobrazit jako volitelných v dialogovém okně, soubory v projektu musí splňovat následující kritéria:

- Soubor musí být součástí mapované složky.

- Soubor musí být přidán do balíčku řešení.

- Soubor nemůže být umístěné v jiném projektu.

  Pokud chcete odkazovat na soubory, které nesplňují tato kritéria, je nutné zadat cestu k souboru ručně.

  Rozbalte **Server** uzel a vyberte soubory, které jsou umístěné na místním serveru, na kterém běží SharePoint. Zobrazit jako volitelných v dialogovém okně, tyto soubory musí splňovat následující kritéria:

- Soubor se musí nacházet v jednom z následujících mapované složky: **Obrázky**, **rozložení**, nebo **ControlTemplates**.

- Soubor nemůže být umístěné v databázi obsahu služby SharePoint.

  Pokud chcete odkazovat na soubory, které nesplňují tato kritéria, je nutné zadat cestu k souboru ručně.

  **Obsah složky** zobrazí seznam souborů ve vybrané složce. Zvolte soubor a klikněte na tlačítko **OK** tlačítka zavřete dialogové okno a odeslat výběr do procesu, která ji zavolala.

  **Soubory typu** umožňuje vybrat ze seznamu souborů, které jsou vhodné pro úlohy, kterou provádíte.

## <a name="see-also"></a>Viz také:
- [Vytváření stránek aplikací pro SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md)
- [Vytvoření webové části pro SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)
- [Vytvoření opakovaně použitelné ovládací prvky webové části nebo stránky aplikace](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)
