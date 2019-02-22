---
title: Vytvoření přidružení mezi entitami | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.BDC.Association_Dialog
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
ms.openlocfilehash: c285b699487bd761447e5fbdf6ccd77987a8c0a8
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56597501"
---
# <a name="create-an-association-between-entities"></a>Vytvoření přidružení mezi entitami
  Je možné definovat vztahy mezi entitami v modelu obchodní Data připojení (BDC) tak, že vytvoříte přidružení. Visual Studio generuje metody, které poskytují příjemci modelu s informacemi o každé přidružení. Tyto metody mohou být spotřebovány webových částí služby SharePoint, seznamy nebo vlastní aplikace pro zobrazení relací mezi daty v uživatelském rozhraní (UI).

## <a name="create-an-association"></a>Vytvoření přidružení
 Vytvoření přidružení výběrem **přidružení** ovládací prvek v sadě Visual Studio **nástrojů**, vyberete první entitu (označované jako zdrojová entita) a potom kliknete druhou entitu (volá se Cílová entita). Můžete definovat podrobnosti přidružení v **Editor asociace**. Další informace najdete v tématu [jak: Vytvoření přidružení mezi entitami](../sharepoint/how-to-create-an-association-between-entities.md).

## <a name="association-methods"></a>Metody přidružení
 Aplikací, jako jsou webové části služby SharePoint obchodní data využívat přidružení při volání metody ve třídě služby entity. Metody pro třídu služby entity můžete přidat tak, že je vyberete **Editor asociace**.

 Ve výchozím nastavení **Editor asociace** přidá metodu přidružení navigace na zdrojové a cílové entity. Metodu přidružení navigace ve zdrojové entitě umožňuje příjemci k načtení seznamu cílové entity. Metodu přidružení navigace v cílové entity umožňuje uživatelům načítat zdrojové entity, která má vztah k Cílová entita.

 U každého z těchto metod vrací odpovídající informace je nutné přidat kód. Můžete také přidat další typy metod pro podporu pokročilejší scénáře. Další informace o každé z těchto metod najdete v tématu [podporované operace](http://go.microsoft.com/fwlink/?LinkId=169286).

## <a name="types-of-associations"></a>Typy přidružení
 Dva druhy přidružení můžete vytvořit v Návrháři služby BDC: přidružení cizího na základě klíčů a cizích bez klíčů přidružení.

### <a name="foreign-key-based-association"></a>Přidružení cizího na základě klíčů
 Přidružení cizího klíče na základě vytvoříte týkající se identifikátor ve zdrojové entitě na typ popisovače, které jsou definovány v cílové entity. Tento vztah umožňuje uživatelům modelu poskytovat Vylepšené uživatelské rozhraní pro své uživatele. Například na formulář v Outlooku, který umožňuje uživateli vytvořit prodejní objednávky zákazníků můžete zobrazit v rozevíracím seznamu; nebo seznam prodejních objednávek v Sharepointu, který umožňuje uživatelům a otevřete stránku profil pro zákazníka.

 K vytvoření přidružení cizího klíče na základě, týkají identifikátory a popisovače typů, které sdílejí stejný název a typ. Můžete například vytvořit cizí klíč na základě přidružení mezi `Contact` entity a `SalesOrder` entity. `SalesOrder` Vrátí entity `ContactID` popisovač typu jako součást návratový parametr metody Finder a Specific Finder. Joinkind obou popisovače typu **Editor asociace**. K vytvoření relace cizího klíče na základě mezi `Contact` entity a `SalesOrder` entity, zvolte `ContactID` identifikátor vedle každého z těchto polí.

 Přidejte kód do metody přidružení Navigátor zdrojové entity, který vrátí kolekce z cílové entity. Následující příklad vrátí prodejních objednávek kontaktu.

 [!code-csharp[SP_BDC#7](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#7)]
 [!code-vb[SP_BDC#7](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#7)]

 Přidejte kód do metody přidružení Navigátor cílové entity, která vrací zdrojové entity. Následující příklad vrátí kontakt, který se vztahuje na prodejní objednávku.

 [!code-csharp[SP_BDC#8](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/salesorderservice.cs#8)]
 [!code-vb[SP_BDC#8](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/salesorderservice.vb#8)]

### <a name="foreign-keyless-association"></a>Přidružení cizího bez kódu
 Přidružení můžete vytvořit bez mapování identifikátorů na typ popisovače pole. Vytvořte tento druh přiřazení zdrojová entita nemá přímý vztah se Cílová entita. Například `SalesOrderDetail` tabulka neobsahuje cizí klíč, který se mapuje na primární klíč v `Contact` tabulky.

 Pokud chcete zobrazit informace v `SalesOrderDetail` tabulku, která má vztah k `Contact`, můžete vytvořit přidružení cizího bez klíčů mezi `Contact` entity a `SalesOrderDetail` entity.

 V metodě přidružení navigace `Contact` entity vrácené `SalesOrderDetail` entity spojování tabulek nebo volání uložené procedury.

 Následující příklad vrátí podrobnosti o všech prodejních objednávek podle spojování tabulek.

 [!code-csharp[SP_BDC#9](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#9)]
 [!code-vb[SP_BDC#9](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#9)]

 V metodě přidružení navigace `SalesOrderDetail` entity, vrátí související `Contact`. Následující příklad ukazuje to.

 [!code-csharp[SP_BDC#10](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/salesorderdetailservice.cs#10)]
 [!code-vb[SP_BDC#10](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/salesorderdetailservice.vb#10)]

## <a name="see-also"></a>Viz také:
- [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)
- [Postupy: Vytvoření přidružení mezi entitami](../sharepoint/how-to-create-an-association-between-entities.md)
