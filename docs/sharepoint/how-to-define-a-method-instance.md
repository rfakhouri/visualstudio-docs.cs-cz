---
title: 'Postupy: Definování Instance metody | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], method instance
- BDC [SharePoint development in Visual Studio], method instance
- BDC [SharePoint development in Visual Studio], method
- Business Data Connectivity service [SharePoint development in Visual Studio], method
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 318744ec1a1a9214ce0385fc56fb1c0cf340339b
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60068493"
---
# <a name="how-to-define-a-method-instance"></a>Postupy: Definování instance metody
  Je nutné zadat alespoň jednu instanci metody pro každou metodu ve vašem modelu.

 Přidat instanci metody pomocí **podrobnosti metody služby BDC** okna. Když chcete přidat instanci metody, Visual Studio přidá `<MethodInstance>` elementu XML souboru modelu ve vašem projektu. Další informace o atributech `<MethodInstance>` prvku, naleznete v tématu [třídu MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282).

### <a name="to-define-a-method-instance"></a>Definování instance metody

1. V **podrobnosti metody služby BDC** okna, rozbalte uzel metodu a poté rozbalte **instance** uzlu.

2. V **přidat instanci metody** klikněte na položku **vytvořit instanci Finder**.

     Nová instance metody se zobrazí pod **instance** uzlu.

3. V panelu nabídky zvolte **zobrazení** > **okno vlastností**.

4. V **vlastnosti** okno, nastavte vlastnosti metody instance. Další informace o jednotlivých vlastnostech najdete v tématu [třídu MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282).

## <a name="see-also"></a>Viz také:
- [Přehled nástroje pro navrhování modelů služby BDC](../sharepoint/bdc-model-design-tools-overview.md)
- [Postupy: Přidání entity do modelu](../sharepoint/how-to-add-an-entity-to-a-model.md)
- [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [Postupy: Definování deskriptoru typu pro parametr](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)
- [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)
