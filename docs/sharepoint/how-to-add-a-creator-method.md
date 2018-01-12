---
title: "Postupy: přidání metody vytvoření | Microsoft Docs"
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
- BDC [SharePoint development in Visual Studio], Creator
- BDC [SharePoint development in Visual Studio], adding entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entity instances
- BDC [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], Creator
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 423992400abfb3f18c3f3d530be1d837c50948d6
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-a-creator-method"></a>Postupy: Přidání metody vytvoření
  Metody vytvoření přidává nová data do zdroje dat entity. Business Data Connectivity (BDC) služby volá tuto metodu, když uživatelé vybrat, **novou položku** na pásu karet seznamu, která je založená na modelu. Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
### <a name="to-add-a-creator-method"></a>Přidání metody vytvoření  
  
1.  V Návrháři BDC zvolíte entity.  
  
2.  Na řádku nabídek zvolte **zobrazení**, **ostatní okna**, **podrobnosti o metodě BDC**.  
  
     **Podrobnosti o metodě BDC** otevře se okno. Další informace o tomto okně najdete v tématu [přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md).  
  
3.  V **přidejte metodu** vyberte **vytvořit metody vytvoření**.  
  
     Visual Studio. přidá následující prvky modelu a tyto prvky se zobrazí ve **podrobnosti o metodě BDC** okno.  
  
    -   Metodu s názvem **vytvořit**.  
  
    -   Vstupního parametru pro metodu.  
  
    -   Návratový parametr metody.  
  
    -   Typ popisovače pro parametry.  
  
    -   Instance metody pro metodu.  
  
     Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
4.  V **Průzkumníku řešení**, otevřete nabídku zástupce služby kódu souboru, který byl vygenerován pro entitu a potom zvolte **kód zobrazení**.  
  
     Otevření souboru kódu služby entity v editoru kódu. Další informace o souboru kódu služby entity najdete v tématu [vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
5.  Přidejte kód do metody Creator, přidá data do zdroje dat. Následující příklad přidá kontakt pro ukázkovou databázi AdventureWorks pro SQL Server.  
  
    > [!NOTE]  
    >  Nahraďte hodnotu `ServerName` pole s názvem serveru.  
  
     [!code-csharp[SP_BDC#4](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#4)]
     [!code-vb[SP_BDC#4](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#4)]  
  
## <a name="see-also"></a>Viz také  
 [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Postupy: přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)   
 [Postupy: Přidání specifické vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Postupy: přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md)   
 [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)   
 [Přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md)   
 [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Postupy: Definování instance metody](../sharepoint/how-to-define-a-method-instance.md)  
  
  