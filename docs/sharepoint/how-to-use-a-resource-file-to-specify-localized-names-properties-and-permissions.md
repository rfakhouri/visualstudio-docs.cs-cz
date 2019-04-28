---
title: 'Postupy: Určení lokalizovaných názvů, vlastností a oprávnění pomocí zdrojového souboru | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], localize strings
- BDC [SharePoint development in Visual Studio], localize strings
- BDC [SharePoint development in Visual Studio], resource file
- Business Data Connectivity service [SharePoint development in Visual Studio], resource strings
- BDC [SharePoint development in Visual Studio], properties
- Business Data Connectivity service [SharePoint development in Visual Studio], properties
- Business Data Connectivity service [SharePoint development in Visual Studio], resource file
- BDC [SharePoint development in Visual Studio], resource strings
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2be88a29d3e9e3da9d1963aa1226ffca0a0a2bbd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62813046"
---
# <a name="how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions"></a>Postupy: Určení lokalizovaných názvů, vlastností a oprávnění pomocí zdrojového souboru
  S použitím souboru prostředků, můžete zadat lokalizované názvy, definovat vlastnosti a použít oprávnění tor objekty, které jsou definovány v modelu služby Připojení obchodních dat (BDC). Zadat tyto informace, přidejte **prostředku připojení obchodních dat** položky do projektu, který obsahuje **Model Připojení obchodních dat** položky. Pak zadejte jména, vlastností a oprávnění pomocí úpravy souboru XML pro soubor prostředků.

### <a name="to-add-a-bdc-resource-file-to-a-sharepoint-project"></a>Chcete-li přidat soubor prostředků služby BDC do projektu SharePoint

1. V **Průzkumníka řešení**, rozbalte složku pro projekt služby SharePoint a pak zvolte složku, která obsahuje model služby BDC.

2. V panelu nabídky zvolte **projektu** > **přidat novou položku**.

3. Rozbalte **SharePoint** uzel a klikněte na tlačítko **2010** uzlu.

4. V **přidat novou položku** dialogového okna zvolte **položka zdroje připojení obchodních dat**.

5. V **název** pole, zadejte název souboru prostředků a klikněte na tlačítko **přidat** tlačítko.

     Soubor prostředků, který má příponu .bdcr je přidán do projektu a po otevření k úpravám.

6. Přidejte kód jazyka XML pro definování lokalizovaných názvů, vlastností a oprávnění, která má být použita modelu služby BDC.

     Informace o tom, jak definovat tyto prvky naleznete v tématu [modelu a souborů prostředků](http://go.microsoft.com/fwlink/?LinkID=169283).

## <a name="see-also"></a>Viz také:
- [Postupy: Přidání stávajícího souboru modelu služby BDC do projektu služby SharePoint](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)
- [Vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md)
- [Postupy: Vytvoření modelu služby BDC](../sharepoint/how-to-create-a-bdc-model.md)
- [Postupy: Zahrnutí vlastního sestavení ve funkci BDC](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)
- [Integrace obchodních dat do služby SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)
