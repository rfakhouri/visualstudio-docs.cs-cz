---
title: "Postupy: Přidání aktualizační metody | Microsoft Docs"
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
- BDC [SharePoint development in Visual Studio], updating data
- BDC [SharePoint development in Visual Studio], Updater
- Business Data Connectivity service [SharePoint development in Visual Studio], updating data
- Business Data Connectivity service [SharePoint development in Visual Studio], Updater
- Business Data Connectivity service [SharePoint development in Visual Studio], updating entity instances
- BDC [SharePoint development in Visual Studio], updating entity instances
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 506d22358493d7b38a6cdfac6cee9efd97435943
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-an-updater-method"></a>Postupy: Přidání aktualizační metody
  Můžete povolit uživatelům aktualizovat obchodní data v externí seznam serveru SharePoint tak, že vytvoříte *aktualizační* metoda. Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
### <a name="to-create-an-updater-method"></a>Chcete-li vytvořit aktualizační metody  
  
1.  V Návrháři BDC zvolíte entity.  
  
2.  Na řádku nabídek zvolte **zobrazení**, **ostatní okna**, **podrobnosti o metodě BDC**.  
  
     Otevře se okno Podrobnosti o metodě BDC. Další informace o tomto okně najdete v tématu [přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md).  
  
3.  V **přidejte metodu** vyberte **vytvořit aktualizační metody**.  
  
     Visual Studio přidá následující prvky modelu. Tyto prvky se zobrazí v okně BDC podrobnosti o metodě.  
  
    -   Metoda, která je s názvem **aktualizace**.  
  
    -   Vstupního parametru pro metodu.  
  
    -   Popisovač typu pro parametr. Ve výchozím nastavení, Visual Studio použije popisovač typu entity, který jste definovali pro vyhledávací metody (například: Obraťte se na).  
  
    -   Instance metody pro metodu.  
  
     Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
    > [!NOTE]  
    >  Pokud identifikátor typ entity představuje pole v databázové tabulky, který je generován automaticky, nastavte **před aktualizační pole** vlastnost **True**.  
  
4.  V **Průzkumníku řešení**, otevřete nabídku zástupce služby kódu souboru, který byl vygenerován pro entitu a potom zvolte **kód zobrazení**.  
  
     Otevření souboru kódu služby entity v editoru kódu. Další informace týkající se tohoto souboru najdete v tématu [vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
5.  Přidejte kód k metodě aktualizace, aktualizace dat. Následující příklad aktualizuje informace získáte v ukázkové databázi AdventureWorks pro SQL Server.  
  
    > [!NOTE]  
    >  Nahraďte hodnotu `ServerName` pole s názvem serveru.  
  
     [!code-csharp[SP_BDC#5](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#5)]
     [!code-vb[SP_BDC#5](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#5)]  
  
## <a name="see-also"></a>Viz také  
 [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Postupy: přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)   
 [Postupy: Přidání specifické vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Postupy: přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md)   
 [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)   
 [Postupy: přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md)   
 [Přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md)   
 [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Postupy: Definování instance metody](../sharepoint/how-to-define-a-method-instance.md)  
  
  