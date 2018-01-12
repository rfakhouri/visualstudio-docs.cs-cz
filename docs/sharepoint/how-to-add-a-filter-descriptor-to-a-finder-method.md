---
title: "Postupy: Přidání deskriptoru filtru do vyhledávací metody | Microsoft Docs"
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
- Business Data Connectivity service [SharePoint development in Visual Studio], filter descriptors
- Business Data Connectivity service [SharePoint development in Visual Studio], add a filter
- BDC [SharePoint development in Visual Studio], add a filter
- BDC [SharePoint development in Visual Studio], filter descriptors
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 06dcea1c8e6d8220461c201de443a26162a608e3
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-a-filter-descriptor-to-a-finder-method"></a>Postupy: Přidání deskriptoru filtru do vyhledávací metody
  Deskriptory filtrů povolení příjemcům modelu předat hodnoty metody před jejich provedení. Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
 Jeden běžný scénář je, že uživatele ve službě SharePoint chcete načíst instancí na externí typ obsahu, které odpovídají některé kritériím. Tento scénář může podporovat přidáním deskriptoru filtru do vyhledávací metody.  
  
### <a name="to-add-a-filter-descriptor-to-a-finder-method"></a>Přidání deskriptoru filtru do vyhledávací metody  
  
1.  V **podrobnosti o metodě BDC** okno, rozbalte uzel vyhledávací metody, rozbalte **parametry** uzel a poté přidejte vstupní parametr. Další informace najdete v tématu [postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md).  
  
2.  V **podrobnosti o metodě** okně zvolte popisovač typu parametru.  
  
3.  Na řádku nabídek zvolte **zobrazení**, **vlastnosti – okno**.  
  
4.  V **vlastnosti** nastavte **název typu** vlastnost, která má datový typ, který je vhodný pro filtr.  
  
     Například filtr může omezit počet prodeje objednávek vrácený metodou použít datu objednávky. Pro podporu tohoto filtru **název typu** vlastnost popisovač typu musí být nastavena na **System.DateTime**.  
  
5.  V **podrobnosti o metodě** okno, rozbalte **deskriptory filtrů** uzlu.  
  
6.  V **přidání deskriptoru filtru** vyberte **vytvořit deskriptoru filtru**.  
  
     Nový popisovač filtru se zobrazí pod **deskriptory filtrů** uzlu.  
  
7.  Na řádku nabídek zvolte **zobrazení**, **vlastnosti – okno**.  
  
8.  V **vlastnosti** okně zvolte **typ** vlastnost.  
  
9. V seznamu, který se zobrazí **typ** vlastnost, zvolte filtrování vzor, který chcete.  
  
     Například pokud chcete vytvořit filtr, který se používá datu objednávky omezit počet prodeje objednávek, vrátí se v vyhledávací metody, zvolte **porovnání**. Filtr porovnání zajistí, že vyhledávací metody vrátí pouze ty instance, které splňují určité podmínky. Další informace o jednotlivých filtrování vzor najdete v tématu [typy filtrů podporované aplikací BDC](http://go.microsoft.com/fwlink/?LinkId=169287).  
  
10. V **vlastnosti** okně zvolte **přidružené popisovače typu** vlastnost.  
  
11. V seznamu, který se zobrazí **přidružené popisovače typu** vlastnost, zvolte popisovač typu, který jste vytvořili dříve v tomto postupu. Vztahuje se filtr pro vstupní parametr vyhledávací metody.  
  
12. Přidávání kódu do vyhledávací metody, která vrací data. Vstupní parametr můžete použít jako podmínku vyberte dotazu.  
  
     Následující příklad vrátí prodeje objednávek datem zadaném pořadí.  
  
    > [!NOTE]  
    >  Nahraďte hodnotu `ServerName` pole s názvem serveru.  
  
     [!code-csharp[SP_BDC#11](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/salesorderservice.cs#11)]
     [!code-vb[SP_BDC#11](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/salesorderservice.vb#11)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)   
 [Postupy: Přidání specifické vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Postupy: definování deskriptoru typu parametru](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Integrace obchodních dat do služby SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  