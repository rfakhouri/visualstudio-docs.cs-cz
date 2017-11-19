---
title: "Postupy: definování Instance metody | Microsoft Docs"
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
- Business Data Connectivity service [SharePoint development in Visual Studio], method instance
- BDC [SharePoint development in Visual Studio], method instance
- BDC [SharePoint development in Visual Studio], method
- Business Data Connectivity service [SharePoint development in Visual Studio], method
ms.assetid: f0c8a686-c0de-414e-8de9-f228f59d1eb3
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9316eaa48b11342891584e448f8bb67bdce6f682
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-define-a-method-instance"></a>Postupy: Definování instance metody
  Je nutné zadat alespoň jednu instanci metoda pro každou metodu v modelu.  
  
 Přidání instance metody pomocí **podrobnosti o metodě BDC** okno. Když přidáte instance metody, přidá aplikace Visual Studio `<MethodInstance>` element XML soubor modelu ve vašem projektu. Další informace o atributy `<MethodInstance>` elementu, najdete v části [MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282).  
  
### <a name="to-define-a-method-instance"></a>K definování instance metody  
  
1.  V **podrobnosti o metodě BDC** okno, rozbalte uzel metody a potom rozbalte **instance** uzlu.  
  
2.  V **přidat instanci metoda** vyberte **vytvořit instanci vyhledávací**.  
  
     Nové instance metody se zobrazí pod **instance** uzlu.  
  
3.  Na řádku nabídek zvolte **zobrazení**, zvolte **vlastnosti – okno**.  
  
4.  V **vlastnosti** nastavte vlastnosti instance metody. Další informace o jednotlivých vlastnostech najdete v tématu [MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282).  
  
## <a name="see-also"></a>Viz také  
 [Přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md)   
 [Postupy: Přidání Entity do modelu](../sharepoint/how-to-add-an-entity-to-a-model.md)   
 [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Postupy: definování deskriptoru typu parametru](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
  