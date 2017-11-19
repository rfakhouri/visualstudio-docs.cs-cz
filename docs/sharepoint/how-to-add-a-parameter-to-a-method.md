---
title: "Postupy: Přidání parametru k metodě | Microsoft Docs"
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
- Business Data Connectivity service [SharePoint development in Visual Studio], adding a method to a parameter
- Business Data Connectivity service [SharePoint development in Visual Studio], parameter
- BDC [SharePoint development in Visual Studio], adding a method to a parameter
- BDC [SharePoint development in Visual Studio], parameter
- Business Data Connectivity service [SharePoint development in Visual Studio], method parameters
- BDC [SharePoint development in Visual Studio], method parameters
ms.assetid: c5b6fd32-bf85-4b2a-a01e-f9199f0fb26e
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 881eccae253fc07c13eead45ae9d14658f9adf46
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-parameter-to-a-method"></a>Postupy: Přidání parametru k metodě
  Použijte parametr k předání informací do metodu nebo k vrácení informací z metody. Všechny metody musí mít minimálně jeden parametr. Další informace o tom, jak navrhnout parametr pro podporu typ metody, které chcete vytvořit, naleznete v části [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
 Když přidáte parametr na metodu, Visual Studio přidá `<Parameter>` element XML soubor modelu ve vašem projektu. Další informace o atributy `<Parameter>` elementu, najdete v části [parametr](http://go.microsoft.com/fwlink/?LinkId=169284).  
  
### <a name="to-add-a-parameter-to-a-method"></a>Přidání parametru do metody  
  
1.  Přidání metody na entitu.  
  
2.  Na řádku nabídek zvolte **zobrazení**, **ostatní okna**, **podrobnosti o metodě BDC**.  
  
     **Podrobnosti o metodě BDC** otevře se okno. Další informace najdete v tématu [přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md).  
  
3.  V **podrobnosti o metodě BDC** okno, rozbalte uzel metody a potom rozbalte **parametry** uzlu.  
  
4.  V **přidat parametr** vyberte **vytvořit parametr**.  
  
     Nový parametr se zobrazí pod **parametry** uzlu.  
  
5.  Na řádku nabídek zvolte **zobrazení**, **vlastnosti – okno**.  
  
6.  V **vlastnosti** nastavte **název** vlastnost na libovolný název, který vám vyhovuje. Například pokud metoda vrátí zákazníků, můžete třeba pojmenovat metodu **GetCustomers**.  
  
7.  V **podrobnosti o metodě BDC** oken, otevřete seznam, který se zobrazí ve směru parametru a potom zvolte **v**, **InOut**, **Out**, nebo **vrátit**.  
  
     Další informace o směru zvolit typ metody, kterou vytváříte, najdete v části [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
8.  Upravte popisovač typu parametru. Další informace najdete v tématu [postupy: definování deskriptoru typu pro parametr](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).  
  
## <a name="see-also"></a>Viz také  
 [Přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md)   
 [Postupy: Přidání Entity do modelu](../sharepoint/how-to-add-an-entity-to-a-model.md)   
 [Postupy: definování deskriptoru typu parametru](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [Postupy: definování Instance metody](../sharepoint/how-to-define-a-method-instance.md)   
 [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
  