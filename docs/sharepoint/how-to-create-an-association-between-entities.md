---
title: "Postupy: vytvoření přidružení mezi entitami | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AssociationGroupTool
dev_langs:
- VB
- CSharp
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
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 49b4d68a8d957462954c998d96e9309944cdb9f5
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-create-an-association-between-entities"></a>Postupy: Vytvoření přidružení mezi entitami
  Je možné definovat vztahy mezi entity v modelu Business Data Connectivity (BDC) tak, že vytvoříte přidružení. Visual Studio generuje metody, které poskytují informace o každé přidružení příjemci modelu. Tyto metody mohou být spotřebovávána webových částí služby SharePoint, seznamy nebo vlastních aplikací zobrazíte relace mezi daty v uživatelském rozhraní (UI).  
  
 Můžete vytvořit dva typy přidružení v Návrháři BDC: cizí klíč na základě přidružení a přidružení cizího bez kódu. Další informace najdete v tématu [vytváření přidružení mezi entitami](../sharepoint/creating-an-association-between-entities.md).  
  
### <a name="to-create-an-association-between-entities"></a>K vytvoření přidružení mezi entitami  
  
1.  Na **BusinessDataConnectivity** kartě **sada nástrojů**, vyberte **přidružení** položky.  
  
2.  Na návrháře BDC zvolte zdrojové entitě a potom vyberte Cílová entita.  
  
     **Přidružení Editor** se zobrazí.  
  
3.  Pokud chcete vytvořit přidružení cizího klíče na základě, vyberte **je přidružení cizího klíče** zaškrtávací políčko.  
  
    1.  V **ID zdroje** sloupec **identifikátor mapování** tabulky, zvolte identifikátor vedle jednotlivých odpovídající popisovač typu, který se zobrazí v **pole** sloupce.  
  
         Například v **ID zdroje** sloupce, vyberte `ContactID` vedle `ReadList.salesOrderList.SalesOrderList.SalesOrder.ContactID` deskriptor typů a `ReadItem.salesOrder.SalesOrder.ContactID` deskriptor typů.  
  
4.  Pokud chcete vytvořit to přidružení cizího bez kódu, zrušte **je přidružení cizího klíče** zaškrtávací políčko.  
  
5.  Vyberte **OK** tlačítko.  
  
6.  Řádek, který představuje přidružení zobrazí v Návrháři BDC se mezi zdrojové entitě a Cílová entita.  
  
     Visual Studio přidá metodu Navigátor přidružení k třídě služby cílové entity a třídu služby zdrojové entity. Další informace o přidružení navigační metody najdete v tématu [podporované operace](http://go.microsoft.com/fwlink/?LinkId=169286).  
  
7.  V metodě přidružení Navigátor zdrojové entity přidejte kód, který vrátí kolekce cílové entity.  
  
8.  V metodě přidružení Navigátor cílové entity přidejte kód, který vrátí související zdrojové entity.  
  
     Příklady metod přidružení Navigátor najdete v tématu [vytváření přidružení mezi entitami](../sharepoint/creating-an-association-between-entities.md).  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření přidružení mezi entitami](../sharepoint/creating-an-association-between-entities.md)   
 [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Postupy: přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)   
 [Postupy: Přidání specifické vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Postupy: přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md)   
 [Postupy: přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md)   
 [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)   
 [Přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md)   
 [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Postupy: definování Instance metody](../sharepoint/how-to-define-a-method-instance.md)   
 [Postupy: definování deskriptoru typu parametru](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [Návod: Vytvoření externího seznamu ve službě SharePoint s použitím obchodních dat](../sharepoint/walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data.md)  
  
  