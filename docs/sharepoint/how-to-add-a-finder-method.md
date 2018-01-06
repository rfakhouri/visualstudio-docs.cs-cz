---
title: "Postupy: přidání vyhledávací metody | Microsoft Docs"
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
- BDC [SharePoint development in Visual Studio], get entities
- Business Data Connectivity service [SharePoint development in Visual Studio], return entities
- BDC [SharePoint development in Visual Studio], return entities
- Business Data Connectivity service [SharePoint development in Visual Studio], Finder method
- Business Data Connectivity service [SharePoint development in Visual Studio], get entities
- BDC [SharePoint development in Visual Studio], Finder method
ms.assetid: 5de2cae3-d1f7-4a68-aac0-458967aca692
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: b7594c650c1492b16e784ec649de6e66d1e6ec33
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-finder-method"></a>Postupy: Přidání vyhledávací metody
  Chcete-li služba připojení obchodních dat k zobrazení seznamu entit ve webové části nebo seznam, musíte vytvořit *vyhledávací* metoda. Vyhledávací metody je speciální metoda, která vrátí kolekci instancí entit. Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
### <a name="to-create-a-finder-method"></a>Chcete-li vytvořit vyhledávací metody  
  
1.  V Návrháři BDC zvolíte entity.  
  
     Další informace najdete v tématu [postupy: Přidání Entity do modelu](../sharepoint/how-to-add-an-entity-to-a-model.md).  
  
2.  Na řádku nabídek zvolte **zobrazení**, **ostatní okna**, **podrobnosti o metodě BDC**.  
  
     **Podrobnosti o metodě BDC** otevře se okno. Další informace o **podrobnosti o metodě BDC** okně najdete v části [přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md).  
  
3.  V **přidejte metodu** vyberte **vytvořit vyhledávací metody**.  
  
     Visual Studio přidá metody, návratový parametr a popisovačem typu.  
  
4.  Popisovač typu nakonfigurujte jako popisovač typ kolekce entit. Další informace o tom, jak vytvořit popisovač typ kolekce entit najdete v tématu [postupy: definování deskriptoru typu pro parametr](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).  
  
    > [!NOTE]  
    >  Nemusíte tento krok proveďte, pokud jste přidali specifické vyhledávací metody k entitě. Visual Studio použije popisovač typu, který jste definovali ve specifické vyhledávací metody.  
  
5.  V **Průzkumníku řešení**, otevřete nabídku zástupce služby kódu souboru, který byl vygenerován pro entitu a potom zvolte **kód zobrazení**. Další informace o souboru kódu služby najdete v tématu [vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
6.  Přidávání kódu do vyhledávací metody. Tento kód provede následující:  
  
    -   Načte data z datového zdroje.  
  
    -   Vrátí seznam entit služby BDC.  
  
     Následující příklad vrátí kolekci `Contact` entity pomocí dat z ukázkovou databázi AdventureWorks pro SQL Server.  
  
    > [!NOTE]  
    >  Nahraďte hodnotu `ServerName` pole s názvem serveru.  
  
     [!code-csharp[SP_BDC#2](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#2)]
     [!code-vb[SP_BDC#2](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#2)]  
  
## <a name="see-also"></a>Viz také  
 [Přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md)   
 [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Postupy: Přidání specifické vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Postupy: přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md)   
 [Postupy: přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md)   
 [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)   
 [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Postupy: Definování instance metody](../sharepoint/how-to-define-a-method-instance.md)  
  
  