---
title: 'Postupy: Přidání parametru do metody | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], adding a method to a parameter
- Business Data Connectivity service [SharePoint development in Visual Studio], parameter
- BDC [SharePoint development in Visual Studio], adding a method to a parameter
- BDC [SharePoint development in Visual Studio], parameter
- Business Data Connectivity service [SharePoint development in Visual Studio], method parameters
- BDC [SharePoint development in Visual Studio], method parameters
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a5b76e49285a629234557a973f6d4b45703f1cfd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62967231"
---
# <a name="how-to-add-a-parameter-to-a-method"></a>Postupy: Přidání parametru k metodě
  Parametr použijte k předávání informací do metody nebo který vrací informace z metody. Všechny metody musí mít aspoň jeden parametr. Další informace o tom, jak navrhnout parametr pro podporu typ metody, kterou chcete vytvořit, naleznete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).

 Při přidání parametru k metodě Visual Studio přidá prvek parametru do XML souboru modelu ve vašem projektu. Další informace o atributech elementu Parameter najdete v tématu [parametr](http://go.microsoft.com/fwlink/?LinkId=169284).

### <a name="to-add-a-parameter-to-a-method"></a>Přidání parametru do metody

1. Přidejte metodu k entitě.

2. V panelu nabídky zvolte **zobrazení** > **ostatní Windows** > **podrobnosti metody služby BDC**.

     **Podrobnosti metody služby BDC** otevře se okno. Další informace najdete v tématu [přehled nástroje pro navrhování modelů služby BDC](../sharepoint/bdc-model-design-tools-overview.md).

3. V **podrobnosti metody služby BDC** okna, rozbalte uzel metodu a poté rozbalte **parametry** uzlu.

4. V **přidat parametr** klikněte na položku **vytvořit parametr**.

     Nový parametr se zobrazí pod **parametry** uzlu.

5. V panelu nabídky zvolte **zobrazení** > **okno vlastností**.

6. V **vlastnosti** okno, nastaveno **název** vlastnost na libovolný název, který dává smysl. Pokud metoda vrátí zákazníků, můžete například pojmenovat metodu **GetCustomers**.

7. V **podrobnosti metody služby BDC** okno, otevřete seznam, který se zobrazí pro směr parametru a klikněte na tlačítko **v**, **InOut**, **si**, nebo **vrátit**.

     Další informace o směr zvolit typ metody, kterou vytváříte, naleznete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).

8. Změnit typ popisovače parametru. Další informace najdete v tématu [jak: Definování deskriptoru typu pro parametr](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).

## <a name="see-also"></a>Viz také:
- [Přehled nástroje pro navrhování modelů služby BDC](../sharepoint/bdc-model-design-tools-overview.md)
- [Postupy: Přidání entity do modelu](../sharepoint/how-to-add-an-entity-to-a-model.md)
- [Postupy: Definování deskriptoru typu pro parametr](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)
- [Postupy: Definování instance metody](../sharepoint/how-to-define-a-method-instance.md)
- [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)
