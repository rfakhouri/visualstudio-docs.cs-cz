---
title: Přidat nové zdroje dat
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.datasource.datasourcefieldspicker
helpviewer_keywords:
- data [Visual Studio], data sources
- data sources
ms.assetid: ed28c625-bb89-4037-bfde-cfa435d182a2
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 1c7df62a0801534f8a23f7b5cde984c75742406a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="add-new-data-sources"></a>Přidat nové zdroje dat
V rámci .NET data nástroje v sadě Visual Studio termín *zdroj dat* odkazují na objekty .NET, které se připojují k úložišti dat a zpřístupnit data pro aplikace .NET. Návrháři Visual Studio můžete využívat výstup zdroje dat pro generování často používaný kód, který váže data do formulářů, když jste přetažení databázové objekty z **zdroje dat** okno. Tento typ zdroje dat může být:

-   Třída ve model Entity Framework, který je přidružen nějaký druh databáze.

-   Datovou sadu, která souvisí s nějaký druh databáze.

-   Třída, která představuje síťové služby, například datové služby Windows Communication Foundation (WCF) nebo službu REST.

-   Třída zastupující služby SharePoint.

-   Třída nebo kolekce ve vašem řešení.

> [!NOTE]
>  Pokud nepoužíváte funkce vazby dat, datové sady, rozhraní Entity Framework, technologie LINQ to SQL, WCF nebo SharePoint, koncept "zdroj dat" neplatí. Stačí připojit přímo k databázi pomocí objektů SQLCommand a komunikovat přímo s databází.

 Vytvářet a upravovat zdroje dat pomocí **Průvodce konfigurací zdroje dat** v aplikaci Windows Forms nebo Windows Presentation Foundation. Rozhraní Entity Framework, nejprve vytvořit třídy entity, a poté spusťte Průvodce výběrem **projektu** > **přidat nový zdroj dat** (podrobněji popsané v dále v tomto článku).

 ![Průvodce konfigurací zdroje dat](../data-tools/media/data-source-configuration-wizard.png "Průvodce konfigurací zdroje dat")

 Po vytvoření zdroje dat, zobrazí se v **zdroje dat** okno nástroje (Shift + Alt + D nebo **zobrazení** > **ostatní okna**  >  **Zdroj dat**). Můžete přetáhnout zdroje dat z **zdroje dat** okna do formuláře návrhové ploše nebo ovládací prvek. To způsobí, že má být vygenerován často používaný kód – kódu, který zobrazuje data, která pochází v úložišti dat pro uživatele. Následující obrázek ukazuje datovou sadu, která byla vyřazena na formuláři Windows. Pokud jste vybrali F5 na aplikaci, by se data z databáze v ovládacích prvků formuláře.

 ![Zdroj dat přetáhněte operaci](../data-tools/media/raddata-data-source-drag-operation.png "raddata zdroj dat přetáhněte operace")

## <a name="data-source-for-a-database-or-a-database-file"></a>Zdroj dat pro databáze nebo souboru databáze

### <a name="dataset"></a>Datová sada
 Chcete-li vytvořit datovou sadu jako zdroj dat, spusťte **Průvodce konfigurací zdroje dat** (**projektu** > **přidat nový zdroj dat**) a vyberte  **Databáze** typ zdroje dat. Postupujte podle pokynů k určení připojení k nové nebo existující databázi nebo soubor databáze.

### <a name="entity-classes"></a>Třídy entity
 Chcete-li vytvořit model Entity Framework jako zdroj dat, nejprve spustit **Entity Data Model Wizard** k vytváření tříd entity (**projektu** > **přidat novou položku**  >  **Model ADO.NET Entity Data Model**).

 ![Nová položka projektu modelu Entity Framework](../data-tools/media/raddata-new-entity-framework-model-project-item.png "položka projektu modelu raddata nové Entity Framework")

 Zvolte metodu, pomocí kterého chcete generovat model.

 ![Entity Data Model průvodce](../data-tools/media/raddata-entity-data-model-wizard.png "raddata Průvodce Model dat Entity")

 Přidáte jako zdroj dat modelu. Zobrazí třídy, které byly vygenerovány v **Průvodce konfigurací zdroje dat** při výběru **objekty** kategorie.

 ![Průvodce konfigurací zdroje dat s tříd entit](../data-tools/media/raddata-data-source-configuration-wizard-with-entity-classes.png "raddata Průvodce konfigurací zdroje dat s tříd entit")

## <a name="data-source-for-a-service"></a>Zdroj dat pro služby
 Chcete-li vytvořit zdroj dat ze služby, spusťte **Průvodce konfigurací zdroje dat** a zvolte **služby** typ zdroje dat. Toto je pouze zástupce **přidat odkaz na službu** dialogové okno, které můžete otevřít také kliknutím pravým tlačítkem myši na projekt v **Průzkumníku řešení** a výběrem **přidat odkaz na službu** .

 Když vytvoříte zdroj dat ze služby, Visual Studio přidá odkaz na službu do projektu. Visual Studio vytvoří také proxy objekty, které odpovídají objekty, které vrátí službu. Například služby, která vrací datové sady je vyjádřené v projektu datovou sadu; Služba, která vrátí určitý typ je reprezentována ve vašem projektu jako typ vrátí.

 Můžete vytvořit zdroj dat z následujících typů služeb:

-   Služby WCF Data Services. Další informace najdete v tématu [přehled](/dotnet/framework/data/wcf/wcf-data-services-overview).

-   Služby WCF. Další informace najdete v tématu [služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md).

-   Webové služby.

    > [!NOTE]
    >  Položky, které se zobrazují v **zdroje dat** okna jsou závislé na data, která službu vrátí. Některé služby nemusí poskytuje dostatek informací **Průvodce konfigurací zdroje dat** vytvořit vazbu objekty. Například pokud služba vrátí netypové datové sady, bude se neobjeví žádné položky v **zdroje dat** okno při dokončení průvodce. Je to proto netypové datové sady neposkytují schématu, a proto Průvodce nemá dostatek informací pro vytvoření zdroje dat.

## <a name="data-source-for-an-object"></a>Zdroj dat pro objekt
 Můžete vytvořit zdroj dat z libovolného objektu, který vystavuje jeden nebo více veřejné vlastnosti spuštěním **Průvodce konfigurací zdroje dat** a potom vyberete **objekt** typ zdroje dat. Všechny veřejné vlastnosti objektu se zobrazí v **zdroje dat** okno.   Pokud používáte rozhraní Entity Framework a vygenerování modelu, je to, kde najít tříd entit, které budou zdroje dat pro vaši aplikaci.

 Na **vyberte datových objektů** rozbalte uzly ve stromovém zobrazení objekty, které chcete vytvořit vazbu na. Zobrazení stromu obsahuje uzly pro svůj projekt a pro sestavení a další projekty, které se odkazuje projektu.

 Pokud chcete vytvořit vazbu na objekt v sestavení nebo projekt, který se nenachází ve stromovém zobrazení, klikněte na tlačítko **přidat odkaz na** a použít **dialogové okno Přidat odkaz na** se přidat odkaz na sestavení nebo projektu. Po přidání odkaz na sestavení nebo projektu se přidá do stromové struktury.

> [!NOTE]
>  Musíte vytvořit projekt, který obsahuje vaše objekty objekty se v zobrazení stromu.

> [!NOTE]
>  Pro podporu přetažení myší datové vazby, které implementují objekty <xref:System.ComponentModel.ITypedList> nebo <xref:System.ComponentModel.IListSource> rozhraní musí mít výchozí konstruktor. Jinak Visual Studio nelze doložit objekt zdroje dat a zobrazí chybu, když přetáhněte ji na plochu návrháře.

## <a name="data-source-for-a-sharepoint-list"></a>Zdroj dat pro seznam serveru SharePoint
 Zdroj dat ze seznamu serveru SharePoint můžete vytvořit spuštěním **Průvodce konfigurací zdroje dat** a výběrem **SharePoint** typ zdroje dat. SharePoint zpřístupní data prostřednictvím [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)], takže vytvoření zdroje dat SharePoint je stejný jako vytváření zdroje dat ze služby. Výběr **SharePoint** položky v **Průvodce konfigurací zdroje dat** otevře **přidat odkaz na službu** dialogové okno, kde můžete připojit ke službě data služby SharePoint Tím přejdete na serveru SharePoint.  To vyžaduje SharePoint SDK.

## <a name="see-also"></a>Viz také

- [Visual Studio Data Tools for .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)