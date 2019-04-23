---
title: 'Postupy: Vytvoření přijímače událostí pro specifickou instanci seznamu | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, event receivers
- event receivers [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: deba5e493f58a99e672e362977406670e1eee0e1
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60094343"
---
# <a name="how-to-create-an-event-receiver-for-a-specific-list-instance"></a>Postupy: Vytvoření přijímače událostí pro specifickou instanci seznamu
  Příjemce událostí instance seznamu jsou reaguje na události, ke kterým dochází v žádné instanci definice seznamu. I když šablony příjemce události není povoleno zaměření na specifickou instanci seznamu, můžete upravit přijímače událostí, které působí na definici seznamu pro reakci na události v specifickou instanci seznamu.

 Cílit na specifickou instanci seznamu, v *Elements.xml* příjemce událostí, nahraďte `ListTemplateId` s `ListUrl` a přidejte adresu URL instance seznamu.

## <a name="create-a-list-instance-event-receiver"></a>Vytvoření příjemce události instance seznamu
 Následující kroky ukazují, jak upravit příjemce události položky seznamu pro reagovat jen na události, ke kterým dochází v případě vlastní seznam oznámení.

#### <a name="to-modify-an-event-receiver-to-respond-to-a-specific-list-instance"></a>Chcete-li změnit přijímače událostí na specifickou instanci seznamu

1. V prohlížeči otevřete web služby SharePoint.

2. V navigačním podokně **uvádí** odkaz.

3. V **veškerý obsah webu** zvolte **vytvořit** odkaz.

4. V **vytvořit** dialogového okna zvolte **oznámení** zadejte, zadejte název oznámení **TestAnnouncements**a klikněte na tlačítko **vytvořit**tlačítko.

5. V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], vytvoření projektu příjemce událostí.

6. V **jaký typ příjemce událostí požadujete?** klikněte na položku **události položky seznamu**.

    > [!NOTE]
    >  Můžete také vybrat jakýkoli jiný typ příjemce událostí, které obory, například s definicí seznamu **e-mailové události seznamu** nebo **události pracovního postupu seznamu**.

7. V **jaká položka by měla být zdroj událostí?** klikněte na položku **oznámení**.

8. V **zpracovávat následující události** seznamu, vyberte **přidání položky** zaškrtněte políčko a klikněte na tlačítko **Dokončit** tlačítko.

9. V **Průzkumníka řešení**, v části EventReceiver1, otevřete *Elements.xml*.

     Příjemce událostí, který aktuálně odkazuje definice seznamu oznámení s použitím následující řádek:

    ```xml
    <Receivers ListTemplateId="104">
    ```

     Změňte tento řádek následujícím textem:

    ```xml
    <Receivers ListUrl="Lists/TestAnnouncements">
    ```

     To přesměruje příjemce událostí, který odpovídá pouze na události, ke kterým dochází v novém **TestAnnouncements** seznam oznámení, který jste právě vytvořili. Můžete změnit `ListURL` atribut odkazovat na jakoukoli instanci seznamu na serveru SharePoint.

10. Otevřete soubor kódu pro příjemce událostí a přidejte zarážku v metodě ItemAdding.

11. Zvolte **F5** klíče pro sestavení a spuštění řešení.

12. Ve službě SharePoint, zvolte **TestAnnouncements** odkaz v navigačním podokně.

13. Zvolte **přidat nové oznámení** odkaz.

14. Zadejte název oznámení a klikněte na tlačítko **Uložit** tlačítko.

     Všimněte si, že je zarážka dosažena při přidání nové položky do seznamu vlastních oznámení.

15. Zvolte **F5** klíč obnovit.

16. V navigačním podokně, vyberte **uvádí** propojit a klikněte na tlačítko **oznámení** odkaz.

17. Přidáte nové oznámení.

     Všimněte si, že příjemce událostí, který se neaktivuje na nové oznámení vzhledem k tomu, že příjemce je nakonfigurován, aby odpovídal pouze na události v instanci seznamu vlastní oznámení **TestAnnouncements**.

## <a name="see-also"></a>Viz také:
- [Postupy: Vytvoření přijímače událostí](../sharepoint/how-to-create-an-event-receiver.md)
- [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)
