---
title: "Postupy: přidání metody odstranění | Microsoft Docs"
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
- BDC [SharePoint development in Visual Studio], deleting data
- Business Data Connectivity service [SharePoint development in Visual Studio], Deleter
- BDC [SharePoint development in Visual Studio], Deleter
- BDC [SharePoint development in Visual Studio], removing data
- BDC [SharePoint development in Visual Studio], deleting entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], deleting entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], deleting data
- Business Data Connectivity service [SharePoint development in Visual Studio], removing data
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 5e2ac47b315189dc2f0f7196db46aeb17ed08480
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-a-deleter-method"></a>Postupy: Přidání metody odstranění
  Můžete povolit koncový uživatel odstranit záznam dat z externího seznamu na web služby SharePoint přidáním *metoda odstranění* metoda do modelu. Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
### <a name="to-create-a-deleter-method"></a>Chcete-li vytvořit metody odstranění  
  
1.  V Návrháři BDC zvolíte entity.  
  
2.  Na řádku nabídek zvolte **zobrazení**, **ostatní okna**, **podrobnosti o metodě BDC**.  
  
     **Podrobnosti o metodě BDC** otevře se okno. Další informace o tomto okně najdete v tématu [přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md).  
  
3.  V **přidejte metodu** vyberte **vytvořit metody odstranění**.  
  
     Visual Studio přidá následující prvky modelu. Tyto prvky se zobrazovat **podrobnosti o metodě BDC** okno.  
  
    -   Metodu s názvem **odstranit**.  
  
    -   Vstupního parametru pro metodu.  
  
    -   Popisovač typu pro parametr.  
  
    -   Instance metody pro metodu.  
  
     Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
4.  V **Průzkumníku řešení**, otevřete nabídku zástupce služby kódu souboru, který byl vygenerován pro entitu a potom zvolte **kód zobrazení**.  
  
     Otevření souboru kódu služby entity v editoru kódu. Další informace o souboru kódu služby entity najdete v tématu [vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
5.  Přidáte kód do metody odstranění odstranit záznam. Následující příklad odstraní položku řádku z prodejní objednávky pomocí ukázkovou databázi AdventureWorks pro SQL Server.  
  
    > [!NOTE]  
    >  Metoda v tomto příkladu používá dva vstupní parametry.  
  
    > [!NOTE]  
    >  Nahraďte hodnotu `ServerName` pole s názvem serveru.  
  
     [!code-csharp[SP_BDC#6](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/salesorderdetailservice.cs#6)]
     [!code-vb[SP_BDC#6](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/salesorderdetailservice.vb#6)]  
  
## <a name="see-also"></a>Viz také  
 [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Postupy: přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)   
 [Postupy: Přidání specifické vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Postupy: přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md)   
 [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)   
 [Přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md)   
 [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Postupy: Definování instance metody](../sharepoint/how-to-define-a-method-instance.md)  
  
  