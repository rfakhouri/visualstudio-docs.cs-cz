---
title: 'Postupy: Přidání deskriptoru filtru do vyhledávací metody | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], filter descriptors
- Business Data Connectivity service [SharePoint development in Visual Studio], add a filter
- BDC [SharePoint development in Visual Studio], add a filter
- BDC [SharePoint development in Visual Studio], filter descriptors
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: dc6492b52cb739c49bdba9f231ebcda313a66105
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60068662"
---
# <a name="how-to-add-a-filter-descriptor-to-a-finder-method"></a>Postupy: Přidání deskriptoru filtru do vyhledávací metody
  Deskriptory filtrů povolení příjemcům modelu předat hodnoty metody předtím, než se provedou. Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).

 Jeden běžný scénář je, že chcete získat instance externího typu obsahu, které odpovídají kritérií uživatelů v Sharepointu. Přidání deskriptoru filtru do vyhledávací metody můžete podpořit tento scénář.

### <a name="to-add-a-filter-descriptor-to-a-finder-method"></a>Přidání deskriptoru filtru do vyhledávací metody

1. V **podrobnosti metody služby BDC** okna, rozbalte uzel vyhledávací metody, rozbalte **parametry** uzel a pak přidejte vstupní parametr. Další informace najdete v tématu [jak: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md).

2. V **podrobnosti metody** okna, vyberte typ popisovače parametru.

3. V panelu nabídky zvolte **zobrazení** > **okno vlastností**.

4. V **vlastnosti** okno, nastaveno **název typu** vlastnost na datový typ, který je vhodný pro filtr.

     Například filtr použít data objednávky a omezit počet prodejních objednávek vrácený metodou. Pro podporu tohoto filtru, **název typu** musí být nastavena vlastnost popisovače typu **System.DateTime**.

5. V **podrobnosti metody** okna, rozbalte **deskriptory filtrů** uzlu.

6. V **přidání deskriptoru filtru** klikněte na položku **vytvořit popisovač filtru**.

     Nový popisovač filtru se zobrazí pod **deskriptory filtrů** uzlu.

7. V panelu nabídky zvolte **zobrazení** > **okno vlastností**.

8. V **vlastnosti** okna, vyberte **typ** vlastnost.

9. V seznamu, který se zobrazí pro **typ** vlastnost, zvolte možnost filtrování vzor, který chcete.

     Například chcete-li vytvořit filtr, který používá data objednávky a omezit počet prodejních objednávek vrácená do vyhledávací metody, zvolte **porovnání**. Filtr porovnávání zajistí, že vyhledávací metody vrátí pouze ty instance, které splňují určité podmínky. Další informace o jednotlivých filtrování vzor, naleznete v tématu [typy filtry podporované službou BDC](http://go.microsoft.com/fwlink/?LinkId=169287).

10. V **vlastnosti** okna, vyberte **přidružené popisovače typů** vlastnost.

11. V seznamu, který se zobrazí pro **přidružené popisovače typů** vlastnosti, vyberte typ popisovače, který jste vytvořili dříve v tomto postupu. To se týká filtr vstupní parametr metody Finder.

12. Přidejte kód do vyhledávací metody, která vrací data. Vstupní parametr můžete použít jako podmínku v dotazu select.

     Následující příklad vrátí prodejní objednávky, které mají datum zadané pořadí.

    > [!NOTE]
    >  Nahraďte hodnotu `ServerName` pole s názvem vašeho serveru.

     [!code-csharp[SP_BDC#11](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/salesorderservice.cs#11)]
     [!code-vb[SP_BDC#11](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/salesorderservice.vb#11)]

## <a name="see-also"></a>Viz také:
- [Postupy: Přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)
- [Postupy: Přidání konkrétní vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)
- [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [Postupy: Definování deskriptoru typu pro parametr](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)
- [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)
- [Integrace obchodních dat do služby SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)
