---
title: 'Postupy: přidání vyhledávací metody | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3c7233f344282b5ce5793f7b6733e5e657534023
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756977"
---
# <a name="how-to-add-a-finder-method"></a>Postupy: přidání vyhledávací metody
  Chcete-li povolit službu Business Data Connectivity (BDC) k zobrazení seznamu entit ve webové části nebo seznamu, je nutné vytvořit *vyhledávací* metoda. Vyhledávací metody je speciální metoda, která vrátí kolekci instancí entit. Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
### <a name="to-create-a-finder-method"></a>Chcete-li vytvořit vyhledávací metody  
  
1.  Na **BDC Návrhář**, zvolte entity.  
  
     Další informace najdete v tématu [postupy: Přidání entity do modelu](../sharepoint/how-to-add-an-entity-to-a-model.md).  
  
2.  Na řádku nabídek zvolte **zobrazení** > **ostatní okna** > **podrobnosti o metodě BDC**.  
  
     **Podrobnosti o metodě BDC** otevře se okno. Další informace o **podrobnosti o metodě BDC** okně najdete v části [návrhu modelu služby BDC nástroje Přehled](../sharepoint/bdc-model-design-tools-overview.md).  
  
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
  
## <a name="see-also"></a>Viz také:
 [Přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md)   
 [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Postupy: Přidání specifické vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Postupy: přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md)   
 [Postupy: přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md)   
 [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)   
 [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Postupy: definování instance metody](../sharepoint/how-to-define-a-method-instance.md)  
  
  
