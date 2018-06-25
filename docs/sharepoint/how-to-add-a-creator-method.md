---
title: 'Postupy: přidání metody vytvoření | Microsoft Docs'
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
- BDC [SharePoint development in Visual Studio], Creator
- BDC [SharePoint development in Visual Studio], adding entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entity instances
- BDC [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], Creator
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 353d834ccd32376b53c875be356865711a4f89fd
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757232"
---
# <a name="how-to-add-a-creator-method"></a>Postupy: přidání metody vytvoření
  Metody vytvoření přidává nová data do zdroje dat entity. Business Data Connectivity (BDC) služby volá tuto metodu, když uživatelé vybrat, **nová položka** na tlačítko **pásu karet** seznamu, která je založená na modelu. Další informace najdete v tématu [návrhu modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
### <a name="to-add-a-creator-method"></a>Přidání metody vytvoření  
  
1.  Na **BDC Návrhář**, zvolte entity.  
  
2.  Na řádku nabídek zvolte **zobrazení** > **ostatní okna** >**podrobnosti o metodě BDC**.  
  
     **Podrobnosti o metodě BDC** otevře se okno. Další informace o tomto okně najdete v tématu [návrhu modelu služby BDC nástroje Přehled](../sharepoint/bdc-model-design-tools-overview.md).  
  
3.  V **přidejte metodu** vyberte **vytvořit metody vytvoření**.  
  
     Visual Studio. přidá následující prvky modelu a tyto prvky se zobrazí ve **podrobnosti o metodě BDC** okno.  
  
    -   Metodu s názvem **vytvořit**.  
  
    -   Vstupního parametru pro metodu.  
  
    -   Návratový parametr metody.  
  
    -   Typ popisovače pro parametry.  
  
    -   Instance metody pro metodu.  
  
     Další informace najdete v tématu [návrhu modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
4.  V **Průzkumníku řešení**, otevřete nabídku zástupce služby kódu souboru, který byl vygenerován pro entitu a potom zvolte **kód zobrazení**.  
  
     Otevření souboru kódu služby entity v editoru kódu. Další informace o souboru kódu služby entity najdete v tématu [vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
5.  Přidejte kód do metody Creator, přidá data do zdroje dat. Následující příklad přidá kontakt pro ukázkovou databázi AdventureWorks pro SQL Server.  
  
    > [!NOTE]  
    >  Nahraďte hodnotu `ServerName` pole s názvem serveru.  
  
     [!code-csharp[SP_BDC#4](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#4)]
     [!code-vb[SP_BDC#4](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#4)]  
  
## <a name="see-also"></a>Viz také:
 [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Postupy: přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)   
 [Postupy: Přidání specifické vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Postupy: přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md)   
 [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)   
 [Přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md)   
 [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Postupy: definování instance metody](../sharepoint/how-to-define-a-method-instance.md)  
  
  
