---
title: "Postupy: Přidání specifické vyhledávací metody | Microsoft Docs"
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
- Business Data Connectivity service [SharePoint development in Visual Studio], Specific Finder
- BDC [SharePoint development in Visual Studio], return an entity
- BDC [SharePoint development in Visual Studio], get an entity
- Business Data Connectivity service [SharePoint development in Visual Studio], return an entity
- BDC [SharePoint development in Visual Studio], Specific Finder
- Business Data Connectivity service [SharePoint development in Visual Studio], get an entity
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6bf2c422efd005c8121ee49fed6dbc7329708b90
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-a-specific-finder-method"></a>Postupy: Přidání specifické vyhledávací metody
  Můžete se vrátit do jedné entity instance tak, že vytvoříte *specifická metoda Finder* metoda. Business Data Connectivity (BDC) služby provede metodu specifická metoda Finder, když uživatel vybere entity v obchodní data webové části nebo externí seznam. Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
### <a name="to-create-a-specific-finder-method"></a>Chcete-li vytvořit specifické vyhledávací metody  
  
1.  V Návrháři BDC zvolíte entity.  
  
     Informace o tom, jak přidat entitu do návrháře BDC v sadě Visual Studio najdete v tématu [postupy: Přidání Entity do modelu](../sharepoint/how-to-add-an-entity-to-a-model.md).  
  
2.  Na řádku nabídek zvolte **zobrazení**, **ostatní okna**, **podrobnosti o metodě BDC**.  
  
     **Podrobnosti o metodě BDC** otevře se okno. Další informace o tomto okně najdete v tématu [přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md).  
  
3.  V **přidejte metodu** vyberte **vytvořit specifické vyhledávací metody**.  
  
     Visual Studio přidá následující prvky modelu. Tyto prvky se zobrazovat **podrobnosti o metodě BDC** okno.  
  
    -   Metoda.  
  
    -   Vstupního parametru pro metodu.  
  
    -   Návratový parametr metody.  
  
    -   Popisovač typu pro jednotlivé parametry.  
  
    -   Instance metody pro metodu.  
  
     Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
4.  Otevřete Visual Studio **vlastnosti** okno.  
  
5.  Nakonfigurujte deskriptoru typu pro návratový parametr jako popisovač typu entity. Informace o tom, jak vytvořit popisovač typu entity najdete v tématu [postupy: definování deskriptoru typu pro parametr](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).  
  
    > [!NOTE]  
    >  Nemusíte tento krok proveďte, pokud jste přidali vyhledávací metody k entitě. Visual Studio použije popisovač typu, který jste definovali ve vyhledávací metody.  
  
    > [!NOTE]  
    >  Pokud pole identifikátor typu entity představuje pole v databázové tabulky, který se automaticky vygeneroval, nastavte **jen pro čtení** vlastnost identifikátor pole, které chcete **True**.  
  
6.  V **podrobnosti o metodě** okně vyberte instanci metoda metody.  
  
7.  V **vlastnosti – okno**, nastavte **vrátí název parametru** vlastnost na název návratový parametr metody. Další informace o vlastnosti instance metoda najdete v tématu [MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282).  
  
8.  V **Průzkumníku řešení**, otevřete nabídku zástupce služby kódu souboru, který byl vygenerován pro entitu a potom zvolte **kód zobrazení**.  
  
     Otevření souboru kódu služby entity v editoru kódu. Další informace o souboru kódu služby entity najdete v tématu [vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
9. Přidávání kódu do specifické vyhledávací metody. Tento kód provede následující:  
  
    -   Načte záznam ze zdroje dat.  
  
    -   Vrátí entity služby BDC.  
  
     Následující příklad vrátí kontakt z ukázkovou databázi AdventureWorks pro SQL Server.  
  
    > [!NOTE]  
    >  Nahraďte hodnotu `ServerName` pole s názvem serveru.  
  
     [!code-csharp[SP_BDC#3](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#3)]
     [!code-vb[SP_BDC#3](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#3)]  
  
## <a name="see-also"></a>Viz také  
 [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Postupy: přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)   
 [Postupy: přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md)   
 [Postupy: přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md)   
 [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)   
 [Přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md)   
 [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Postupy: Definování instance metody](../sharepoint/how-to-define-a-method-instance.md)  
  
  