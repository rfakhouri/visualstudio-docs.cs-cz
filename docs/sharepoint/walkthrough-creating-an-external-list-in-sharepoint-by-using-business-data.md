---
title: "Návod: Vytvoření externího seznamu ve službě SharePoint s použitím obchodních dat | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], business data in a Web Part
- BDC [SharePoint development in Visual Studio], external list
- Business Data Connectivity service [SharePoint development in Visual Studio], business data in a SharePoint list
- BDC [SharePoint development in Visual Studio], business data in a SharePoint list
- BDC [SharePoint development in Visual Studio], business data in a Web Part
- BDC [SharePoint development in Visual Studio], entity backed list
- Business Data Connectivity service [SharePoint development in Visual Studio], entity backed list
- Business Data Connectivity service [SharePoint development in Visual Studio], external list
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 49c43e3add54b3ba3f584af6feda630a8d1ad526
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data"></a>Návod: Vytvoření externího seznamu ve službě SharePoint s použitím obchodních dat

Business Data Connectivity (BDC) služba umožňuje služby SharePoint k zobrazení obchodních dat ze serveru back-end aplikace, webové služby a databáze.

Tento návod ukazuje, jak pro vytvoření modelu služby BDC, který vrací informace o kontaktů v ukázkové databázi. Pak vytvoříte externího seznamu ve službě SharePoint pomocí tohoto modelu.

Tento návod znázorňuje následující úlohy:

- Vytvoření projektu.
- Přidání entity do modelu.
- Přidání vyhledávací metody.
- Přidání specifické vyhledávací metody.
- Testování projektu.

## <a name="prerequisites"></a>Požadavky

K dokončení tohoto návodu budete potřebovat následující komponenty:

- Podporované edice systému Windows a služby SharePoint. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).

- Přístup k ukázkové databázi AdventureWorks. Další informace o tom, jak nainstalovat databázi AdventureWorks najdete v tématu [ukázkové databáze systému SQL Server](http://go.microsoft.com/fwlink/?LinkID=117483).

## <a name="creating-a-project-that-contains-a-bdc-model"></a>Vytvoření projektu, který obsahuje model služby BDC

1. V řádku nabídek v sadě Visual Studio, vyberte **soubor**, **nový**, **projektu**.

     **Nový projekt** otevře se dialogové okno.

2. V části buď **Visual C#** nebo **jazyka Visual Basic**, rozbalte **SharePoint** uzel a potom vyberte **2010** položky.

3. V **šablony** podokně vyberte **projektu služby SharePoint 2010**, název projektu **AdventureWorksTest**a potom zvolte **OK** tlačítko .

     **Průvodce vlastním nastavením SharePoint** se zobrazí. V tomto průvodci můžete zadat web, který budete používat k ladění projektu a nastavení úrovně důvěryhodnosti řešení.

4. Vyberte **nasadit jako řešení farmy** tlačítko Možnosti můžete nastavit úroveň důvěryhodnosti.

5. Vyberte **Dokončit** tlačítko přijmout výchozí místní web služby SharePoint.

6. V **Průzkumníku**, vyberte uzel projektu služby SharePoint.

7. Na řádku nabídek zvolte **projektu**, **přidat novou položku**.

     **Přidat novou položku** otevře se dialogové okno.

8. V **šablony** podokně vyberte **modelu připojení obchodních dat (pouze řešení farmy)**, název projektu **AdventureWorksContacts**a potom zvolte **Přidat** tlačítko.

## <a name="adding-data-access-classes-to-the-project"></a>Přidání tříd pro přístup k datům do projektu

1. Na řádku nabídek zvolte **nástroje**, **připojit k databázi**.

     **Přidat připojení** otevře se dialogové okno.

2. Přidáte připojení k ukázkovou databázi AdventureWorks serveru SQL.

     Další informace najdete v tématu [přidat či upravit připojení (Microsoft SQL Server)](http://msdn.microsoft.com/fa400910-26c3-4df7-b9d1-115e688b4ea3).

3. V **Průzkumníku**, vyberte uzel projektu.

4. Na řádku nabídek zvolte **projektu**, **přidat novou položku**.

5. V **nainstalovaných šablonách** podokně, vyberte **Data** uzlu.

6. V **šablony** podokně vyberte **třídy LINQ to SQL**.

7. V **název** zadejte **AdventureWorks**a potom zvolte **přidat** tlačítko.

     Soubor DBML je přidán do projektu a otevře se Návrhář relací objektů (Návrhář relací objektů).

8. Na řádku nabídek zvolte **zobrazení**, **Průzkumníka serveru**.

9. V **Průzkumníka serveru**, rozbalte uzel, který představuje ukázkovou databázi AdventureWorks a potom rozbalte **tabulky** uzlu.

10. Přidat **kontakt (osoba)** tabulky do Návrhář relací objektů.

     Třídu entity se vytvoří a zobrazí se na návrhovou plochu. Třída entity má vlastnosti, které mapují na sloupce v tabulce Kontakt (uživatel).

## <a name="removing-the-default-entity-from-the-bdc-model"></a>Odebrání výchozí entity z modelu služby BDC

**Modelu připojení obchodních dat** projektu přidá výchozí entitu s názvem Entity1 do modelu. Odeberte tuto entitu. Později přidejte novou entitu. Počínaje prázdný model snižuje počet kroků potřebných k dokončení průvodce.

1. V **Průzkumníku řešení**, rozbalte **BdcModel1** uzel a pak otevřete soubor BdcModel1.bdcm.

2. Soubor modelu připojení obchodních dat se otevře v Návrháři BDC.

3. V návrháři, otevřete místní nabídku pro **Entity1**a potom zvolte **odstranit**.

4. V **Průzkumníku řešení**, otevřete místní nabídku pro Entity1.vb (v jazyce Visual Basic) nebo Entity1.cs (v jazyku C#) a potom zvolte **odstranit**.

5. Otevřete místní nabídku pro Entity1Service.vb (v jazyce Visual Basic) nebo Entity1Service.cs (v jazyku C#) a potom zvolte **odstranit**.

## <a name="adding-an-entity-to-the-model"></a>Přidání entity do modelu

Přidání entity do modelu. Můžete přidat entit ze sady Visual Studio **sada nástrojů** do BDC návrháře.

1. Na řádku nabídek zvolte **zobrazení**, **sada nástrojů**.

2. Na **BusinessDataConnectivity** kartě **sada nástrojů**, přidejte **Entity** do BDC návrháře.

     Nová entita, zobrazí se v designeru. Visual Studio přidá soubor, který je do projektu s názvem EntityService.vb (v jazyce Visual Basic) nebo EntityService.cs (v jazyku C#).

3. Na řádku nabídek zvolte **zobrazení**, **vlastnosti**, **okno**.

4. V **vlastnosti** nastavte **název** hodnotu vlastnosti na **kontaktujte**.

5. V designeru, otevřete místní nabídky pro entitu, zvolte **přidat**a potom zvolte **identifikátor**.

     Nový identifikátor se zobrazí u entity.

6. V **vlastnosti** okně změnit název identifikátor, který **KódKontaktu**.

7. V **název typu** vyberte **System.Int32**.

## <a name="adding-a-specific-finder-method"></a>Přidání konkrétní vyhledávací metody

Povolení služby BDC zobrazíte konkrétního kontaktu, je nutné přidat specifické vyhledávací metody. Služby BDC volá metodu specifická metoda Finder, když uživatel vybere položku v seznamu a potom vybere **položky zobrazení** na pásu karet.

Přidání specifické vyhledávací metody do entity Kontakt s použitím **podrobnosti o metodě BDC** okno. Pokud chcete vrátit konkrétní entitu, přidáte kód do metody.

1. V Návrháři BDC zvolte **kontaktujte** entity.

2. Na řádku nabídek zvolte **zobrazení**, **ostatní okna**, **podrobnosti o metodě BDC**.

     Otevře se okno Podrobnosti o metodě BDC.

3. V **přidejte metodu** vyberte **vytvořit specifické vyhledávací metody**.

     Visual Studio přidá následující prvky modelu. Tyto prvky se zobrazovat **podrobnosti o metodě BDC** okno.

    - Metoda s názvem ReadItem.

    - Vstupního parametru pro metodu.

    - Návratový parametr metody.

    - Popisovač typu pro jednotlivé parametry.

    - Instance metody pro metodu.

4. V **podrobnosti o metodě BDC** okně otevřete seznam, který se zobrazí pro **kontaktujte** deskriptor typů a potom vyberte **upravit**.

     **Průzkumník modelu BDC** otevře a poskytuje hierarchické zobrazení modelu.

5. V **vlastnosti** okně otevřete seznam vedle **TypeName** vlastnost, vyberte **aktuálního projektu** a pak klikněte na příkaz **kontaktujte**vlastnost.

6. V **Průzkumník modelu BDC**, otevřete v místní nabídce **kontaktujte**a potom zvolte **přidat popisovač typu**.

     Nový popisovač typu, který je pojmenován **TypeDescriptor1** se zobrazí v **Průzkumník modelu BDC**.

7. V **vlastnosti** nastavte **název** hodnotu vlastnosti na **KódKontaktu**.

8. Otevřete seznam vedle **TypeName** vlastnost a potom zvolte **Int32**.

9. Otevřete seznam vedle **identifikátor** vlastnost a potom zvolte **KódKontaktu**.

10. Zopakujte krok 6 k vytvoření popisovač typu pro každou z těchto polí.

    |Název|Název typu|
    |----------|---------------|
    |FirstName|System.String|
    |LastName|System.String|
    |Telefon|System.String|
    |EmailAddress|System.String|
    |EmailPromotion|System.Int32|
    |NameStyle|System.Boolean|
    |PasswordHash|System.String|
    |PasswordSalt|System.String|

11. V Návrháři BDC na **kontaktujte** entity, otevřete **ReadItem** metoda.

     Obraťte se na službu kód soubor se otevře v editoru kódu.

12. V `ContactService` třídy, nahraďte `ReadItem` metoda následujícím kódem. Tento kód provede následující:

    - Načte záznam z tabulky. Obraťte se na databáze AdventureWorks.

    - Vrátí entity kontakt do služby BDC.

    > [!NOTE]
    > Nahraďte hodnotu `ServerName` pole s názvem serveru.

     [!code-csharp[SP_BDC#3](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#3)]
     [!code-vb[SP_BDC#3](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#3)]

## <a name="adding-a-finder-method"></a>Přidání vyhledávací metody

Pokud chcete povolit službu BDC, kterou chcete zobrazit v seznamu kontaktů, je nutné přidat vyhledávací metody. Přidání vyhledávací metody do entity Kontakt s použitím **podrobnosti o metodě BDC** okno. Pokud chcete vrátit do služby BDC kolekci entit, přidáte kód do metody.

1. V Návrháři BDC zvolte **kontaktujte** entity.

2. V **podrobnosti o metodě BDC** okně sbalit **ReadItem** uzlu.

3. V **přidejte metodu** v rámci **ReadList** metoda, zvolte **vytvořit vyhledávací metody**.

     Visual Studio přidá metody, návratový parametr a popisovačem typu.

4. V Návrháři BDC na **kontaktujte** entity, otevřete **ReadList** metoda.

     Soubor kód pro službu kontakt se otevře v editoru kódu.

5. V `ContactService` třídy, nahraďte `ReadList` metoda následujícím kódem. Tento kód provede následující:

    - Načte data z tabulky kontaktů databázi AdventureWorks.

    - Vrátí seznam entit, obraťte se na služby BDC.

    > [!NOTE]
    > Nahraďte hodnotu `ServerName` pole s názvem serveru.

     [!code-csharp[SP_BDC#2](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#2)]
     [!code-vb[SP_BDC#2](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#2)]

## <a name="testing-the-project"></a>Testování projektu

Při spuštění projektu otevře web služby SharePoint a Visual Studio přidá modelu připojení obchodních dat služby. Vytvoření externího seznamu ve službě SharePoint, který odkazuje na entity Kontakt. V seznamu se zobrazí data pro kontakty v databázi AdventureWorks.

> [!NOTE]
> Možná budete muset změnit nastavení zabezpečení ve službě SharePoint, než můžete ladit, vaše řešení. Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).

1. Vyberte **F5** klíč.

     Otevře se stránka serveru SharePoint.

2. Na **Akce webu** nabídce zvolte **další možnosti** příkaz.

3. Na **vytvořit** vyberte **externí seznam** šablony a potom zvolte **vytvořit** tlačítko.

4. Název seznamu vlastní **kontakty**.

5. Klikněte na tlačítko Procházet vedle **externí obsah** pole.

6. V **výběr externích typů obsahu** dialogovém okně vyberte **AdventureWorksContacts.BdcModel1.Contact** položku a potom vyberte **vytvořit** tlačítko.

     SharePoint vytvoří externího seznamu, která obsahuje kontakty z ukázkovou databázi AdventureWorks.

7. Chcete-li otestovat specifické vyhledávací metody, zvolte v seznamu a obraťte se na.

8. Na pásu karet, vyberte **položky** a pak klikněte na příkaz **položky zobrazení** příkaz.

     Ve formuláři se zobrazují podrobnosti kontaktu, který jste si zvolili.

## <a name="next-steps"></a>Další kroky

Další informace o navrhování modelů služby BDC ve službě SharePoint z těchto témat:

- [Postupy: přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md).
- [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md).
- [Postupy: přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md).

## <a name="see-also"></a>Viz také

[Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)  
[Vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md)  
[Přehled nástrojů pro navrhování modelů služby BDC](../sharepoint/bdc-model-design-tools-overview.md)  
[Integrace obchodních dat do služby SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)
