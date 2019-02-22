---
title: 'Postupy: Vytvoření přidružení mezi entitami | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- AssociationGroupTool
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], create an assocation
- Business Data Connectivity service [SharePoint development in Visual Studio], associations between entities
- BDC [SharePoint development in Visual Studio], associations between entities
- Business Data Connectivity service [SharePoint development in Visual Studio], create an assocation
- Business Data Connectivity service [SharePoint development in Visual Studio], associate external content types
- Business Data Connectivity service [SharePoint development in Visual Studio], relate entities
- BDC [SharePoint development in Visual Studio], relate entities
- BDC [SharePoint development in Visual Studio], associate external content types
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 5d8558745de7539350bde4f00673c99d23cd1def
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56645118"
---
# <a name="how-to-create-an-association-between-entities"></a>Postupy: Vytvoření přidružení mezi entitami
  Je možné definovat vztahy mezi entitami v modelu obchodní Data připojení (BDC) tak, že vytvoříte přidružení. Visual Studio generuje metody, které poskytují příjemci modelu s informacemi o každé přidružení. Tyto metody mohou být spotřebovány webových částí služby SharePoint, seznamy nebo vlastní aplikace pro zobrazení relací mezi daty v uživatelském rozhraní (UI).

 Dva druhy přidružení můžete vytvořit v Návrháři služby BDC: přidružení cizího na základě klíčů a cizích bez klíčů přidružení. Další informace najdete v tématu [vytvoření přidružení mezi entitami](../sharepoint/creating-an-association-between-entities.md).

### <a name="to-create-an-association-between-entities"></a>Vytvoření přidružení mezi entitami

1.  Na **služby Připojení obchodních dat** karty **nástrojů**, zvolte **přidružení** položky.

2.  V Návrháři služby BDC zvolte zdrojové entity a klikněte na tlačítko Cílová entita.

     **Editor asociace** se zobrazí.

3.  Pokud chcete vytvořit přidružení cizího klíče na základě, vyberte **je přidružení cizího klíče** zaškrtávací políčko.

    1.  V **ID zdroje** sloupec **identifikátor mapování** tabulky, zvolte identifikátor vedle každé odpovídající popisovač typu, který se zobrazí **pole** sloupce.

         Například v **ID zdroje** sloupci vyberte `ContactID` vedle `ReadList.salesOrderList.SalesOrderList.SalesOrder.ContactID` popisovač typu a `ReadItem.salesOrder.SalesOrder.ContactID` popisovačem typu.

4.  Pokud chcete vytvořit přidružení cizího bez klíčů, zrušte zaškrtnutí políčka **je přidružení cizího klíče** zaškrtávací políčko.

5.  Zvolte **OK** tlačítko.

6.  V Návrháři služby BDC zobrazí se řádek, který představuje přidružení mezi entitou zdrojové a cílové entity.

     Visual Studio přidá metodu přidružení Navigátor třídu služby cílové entity a třídu služby zdrojové entity. Další informace o přidružení navigační metody, naleznete v tématu [podporované operace](http://go.microsoft.com/fwlink/?LinkId=169286).

7.  Metoda přidružení Navigátor zdrojové entitě přidejte kód, který vrátí kolekce z cílové entity.

8.  Metoda přidružení Navigátor Cílová entita přidejte kód, který vrátí související zdrojové entity.

     Příklady metod Navigátor přidružení, najdete v článku [vytvoření přidružení mezi entitami](../sharepoint/creating-an-association-between-entities.md).

## <a name="see-also"></a>Viz také:
- [Vytvoření přidružení mezi entitami](../sharepoint/creating-an-association-between-entities.md)
- [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)
- [Postupy: Přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)
- [Postupy: Přidání konkrétní vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)
- [Postupy: Přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md)
- [Postupy: Přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md)
- [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)
- [Přehled nástroje pro navrhování modelů služby BDC](../sharepoint/bdc-model-design-tools-overview.md)
- [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [Postupy: Definování instance metody](../sharepoint/how-to-define-a-method-instance.md)
- [Postupy: Definování deskriptoru typu pro parametr](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)
- [Návod: Vytvoření externího seznamu ve službě SharePoint s použitím obchodních dat](../sharepoint/walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data.md)
