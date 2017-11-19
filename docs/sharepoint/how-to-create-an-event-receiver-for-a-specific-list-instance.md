---
title: "Postupy: vytvoření přijímače událostí pro specifickou instanci seznamu | Microsoft Docs"
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
helpviewer_keywords:
- SharePoint development in Visual Studio, event receivers
- event receivers [SharePoint development in Visual Studio]
ms.assetid: 4b4b3564-161a-4327-8963-50896c084ac2
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3db5af044b1e3eb25e68c96a42335082fd3523f1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-an-event-receiver-for-a-specific-list-instance"></a>Postupy: Vytvoření přijímače událostí pro specifickou instanci seznamu
  Přijímač událostí instanci seznamu odpoví na události, které nastaly v žádné instanci definice seznamu. I když příjemce šablony události neumožňuje zaměření na specifickou instanci seznamu, můžete upravit přijímače událostí, které budou platit pro definice seznamu reakce na události v specifickou instanci seznamu.  
  
 Pro specifickou instanci seznamu, v Elements.xml pro příjemce událostí nahradit `ListTemplateId` s `ListUrl` a přidejte adresu URL instance seznamu.  
  
## <a name="creating-a-list-instance-event-receiver"></a>Vytvoření příjemce událostí instanci seznamu  
 Následující kroky ukazují, jak upravit přijímač událostí položky seznamu odpovídal pouze na události, které nastaly v instanci vlastní seznam oznámení.  
  
#### <a name="to-modify-an-event-receiver-to-respond-to-a-specific-list-instance"></a>Chcete-li upravit přijímače událostí reagovat na specifickou instanci seznamu  
  
1.  V prohlížeči otevřete web služby SharePoint.  
  
2.  V navigačním podokně **uvádí** odkaz.  
  
3.  V **veškerý obsah webu** vyberte **vytvořit** odkaz.  
  
4.  V **vytvořit** dialogovém okně vyberte **oznámení** typem, název oznámení **TestAnnouncements**a potom vyberte **vytvořit**tlačítko.  
  
5.  V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], vytvoření projektu příjemce událostí.  
  
6.  V **jaký typ příjemce událostí chcete?** vyberte **události položky seznamu**.  
  
    > [!NOTE]  
    >  Můžete také vybrat jakýkoli jiný druh příjemce událostí, které rozsahy, například k definici seznamu **seznam e-mailu události** nebo **seznamu pracovního postupu události**.  
  
7.  V **co položka by měl být zdroj události?** vyberte **oznámení**.  
  
8.  V **zpracovávat následující události** seznamu, vyberte **přidat položku** zaškrtněte políčko a potom vyberte **Dokončit** tlačítko.  
  
9. V **Průzkumníku**, v části EventReceiver1, otevřete Elements.xml.  
  
     Příjemce událostí aktuálně odkazuje definice seznamu oznámení pomocí následující řádek:  
  
    ```  
    <Receivers ListTemplateId="104">  
    ```  
  
     Změňte tento řádek následujícím textem:  
  
    ```  
    <Receivers ListUrl="Lists/TestAnnouncements">  
    ```  
  
     To přesměruje příjemce událostí odpovídal pouze na události, které nastaly v novém **TestAnnouncements** seznam oznámení, kterou jste právě vytvořili. Můžete změnit `ListURL` atribut tak, aby odkazovaly na jakoukoli instanci seznamu serveru SharePoint.  
  
10. Otevřete soubor kódu pro příjemce událostí a umístí zarážka v metodě ItemAdding.  
  
11. Zvolte klávesy F5 sestavení a spuštění řešení.  
  
12. Ve službě SharePoint, vyberte **TestAnnouncements** odkaz v navigačním podokně.  
  
13. Vyberte **přidat nové oznámení** odkaz.  
  
14. Zadejte název oznámení a potom vyberte **Uložit** tlačítko.  
  
     Všimněte si, že zarážce je dosáhl při přidání nové položky do seznamu vlastní oznámení.  
  
15. Zvolte klávesy F5 Obnovit.  
  
16. V navigačním podokně, vyberte **uvádí** propojit a potom zvolte **oznámení** odkaz.  
  
17. Přidáte nové oznámení.  
  
     Všimněte si, že příjemce událostí na nové oznámení neaktivuje vzhledem k tomu, že příjemce je nakonfigurován, aby odpovídal pouze na události v seznamu instanci vlastní oznámení **TestAnnouncements**.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření přijímače událostí](../sharepoint/how-to-create-an-event-receiver.md)   
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
  