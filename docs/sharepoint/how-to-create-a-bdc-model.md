---
title: 'Postupy: Vytvoření modelu služby BDC | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], creating a model
- Business Data Connectivity service [SharePoint development in Visual Studio], creating a model
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d82678df0da5932dd33c08a6e3066462df204f6e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56596500"
---
# <a name="how-to-create-a-bdc-model"></a>Postupy: Vytvoření modelu služby BDC
  Obchodní Data připojení (BDC) model můžete vytvořit pomocí šablony pro tento druh položky a následným přidáním modelu do jakéhokoli projektu SharePoint. Další informace najdete v tématu [vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md). Další informace o tom, jak návrhu modelu naleznete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).

### <a name="to-create-a-bdc-project"></a>Vytvoření projektu BDC

1.  V panelu nabídky zvolte **souboru** > **nový** > **projektu**.

    > [!NOTE]
    >  Pokud vaše rozhraní IDE nastaveno pro použití vývojového nastavení jazyka Visual Basic, zvolte **souboru** > **nový projekt**.

     **Nový projekt** zobrazí se dialogové okno.

2.  V části **jazyka Visual Basic** nebo **Visual C#** , zvolte **Office/SharePoint**, **řešení služby SharePoint**.

3.  V **šablony** podokně, vyberte **SharePoint 2013 – prázdný projekt** položku a klikněte na tlačítko **OK** tlačítko.

     **Průvodce přizpůsobením SharePoint** otevře.

4.  Na **zadejte web a úroveň zabezpečení pro ladění** stránky, zadejte adresu URL webu služby SharePoint v místním počítači, zvolte **nasadit jako řešení farmy** přepínač a klikněte na tlačítko **Dokončit** tlačítko.

     Bude testovat model na webu služby SharePoint, který jste zadali.

    > [!IMPORTANT]
    >  Vzhledem k tomu, že modely služby BDC podporují pouze řešení farmy je nutné nasadit projekt jako řešení farmy.

     Je vytvořen prázdný projekt SharePoint.

5.  V panelu nabídky zvolte **projektu** > **přidat novou položku**.

6.  V **přidat novou položku** dialogového okna zvolte **Office/SharePoint** uzlu.

7.  V seznamu šablon služby SharePoint, zvolte **Model Připojení obchodních dat (pouze řešení farmy)**.

8.  V **název** pole, zadejte název pro model služby BDC a klikněte na tlačítko **přidat** tlačítko.

     A **Model Připojení obchodních dat** přidání položky do projektu. Ve výchozím nastavení se model zobrazen v Návrháři služby BDC. Další informace najdete v tématu [vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md).

## <a name="see-also"></a>Viz také:
- [Vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md)
- [Postupy: Přidání stávajícího souboru modelu služby BDC do projektu služby SharePoint](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)
- [Postupy: Určení lokalizovaných názvů, vlastností a oprávnění pomocí zdrojového souboru](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)
- [Postupy: Zahrnutí vlastního sestavení ve funkci BDC](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)
- [Integrace obchodních dat do služby SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)
