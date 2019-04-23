---
title: Připojení k datům v databázi aplikace Access (Windows Forms) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- databases, connecting to
- databases, Access
- data [Visual Studio], connecting
- connecting to data, from Access databases
- Access databases, connecting
ms.assetid: 4159e815-d430-4ad0-a234-e4125fcbef18
caps.latest.revision: 32
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 10b4efd574dd5829e4717b168dc4e565476e9b52
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60102948"
---
# <a name="connect-to-data-in-an-access-database-windows-forms"></a>Připojení k datům v databázi aplikace Access (Windows Forms)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pomocí sady Visual Studio se můžete připojit k databázi aplikace Access (soubor .mdf nebo soubor .accdb). Po definování připojení se data zobrazí v **zdroje dat** okna. Odtud můžete přetáhnout tabulky nebo zobrazení do formulářů.  
  
## <a name="prerequisites"></a>Požadavky  
 Pokud chcete použít tyto postupy, je třeba projekt aplikace Windows Forms a buď databázi aplikace Access (soubor .accdb) nebo databáze aplikace Access 2000-2003 (soubor .mdb). Postupujte podle kroků odpovídajících vašemu typu souboru.  
  
## <a name="creating-the-dataset-for-an-accdb-file"></a>Vytvoření datové sady pro soubor .accdb  
 Můžete připojit k databázím vytvořeným pomocí aplikace Access 2013, Office 365, Access 2010 nebo 2007 přístup pomocí následujícího postupu.  
  
#### <a name="to-create-the-dataset"></a>Vytvoření datové sady  
  
1. Otevřete aplikaci Windows Forms, ke kterému chcete připojit data.  
  
2. Na **zobrazení** nabídce vyberte možnost **ostatní Windows** > **zdroje dat**.  
  
     ![Zobrazení zdrojů dat Windows](../data-tools/media/viewdatasources.png "ViewDataSources")  
  
3. V **zdroje dat** okna, klikněte na tlačítko **přidat nový zdroj dat**.  
  
     ![Přidat nový zdroj dat](../data-tools/media/dataaddnewdatasource.png "dataAddNewDataSource")  
  
4. Vyberte **databáze** na **zvolte typ zdroje dat** stránce a pak vyberte **Další**.  
  
5. Vyberte **datovou sadu** na **vyberte databázový Model** stránce a pak vyberte **Další**.  
  
6. Na **vyberte datové připojení** stránce **nové připojení** konfigurace nové datové připojení.  
  
7. Změnit **zdroj dat** k **zprostředkovatele dat .NET Framework pro OLE DB**.  
  
     ![Změňte zprostředkovatele dat OLE DB](../data-tools/media/datachangedatasourceoledb.png "dataChangeDataSourceOLEDB")  
  
    > [!IMPORTANT]
    >  I když zdroj dat **soubor databáze Microsoft Access (OLE DB)** může jevit tou správnou volbou, použijete tento typ zdroje dat pouze pro soubory databáze .mdb.  
  
8. V **zprostředkovatele OLE DB**vyberte **Office 12.0 Access Database modulu zprostředkovatele Microsoft OLE DB**.  
  
     ![OLE DB poskytovatele Microsoft Office 12.0 Access](../data-tools/media/dataoledbprovideroffice12access.png "dataOLEDBProviderOffice12Access")  
  
9. V **serveru nebo název souboru**, zadejte cestu a název souboru .accdb, ke kterému chcete připojit a pak vyberte **OK**.  
  
    > [!NOTE]
    >  Pokud má soubor databáze uživatelské jméno a heslo, zadejte, je před výběrem **OK**.  
  
10. Vyberte **Další** na **vyberte datové připojení** stránky.  
  
11. Vyberte **Další** na **uložit připojovací řetězec do konfiguračního souboru aplikace** stránky.  
  
12. Rozbalte **tabulky** uzlu **zvolte vaše databázové objekty** stránky.  
  
13. Vyberte jakékoli tabulky a zobrazení v datové sadě a pak vyberte **Dokončit**.  
  
     Do projektu je přidána datová sada a tabulky a zobrazení se zobrazí **zdroje dat** okna.  
  
## <a name="creating-the-dataset-for-an-mdb-file"></a>Vytvoření datové sady pro soubor .mdb  
 Vytvořte datovou sadu spuštěním **Průvodce konfigurací zdroje dat**.  
  
#### <a name="to-create-the-dataset"></a>Vytvoření datové sady  
  
1. Otevřete aplikaci Windows Forms, ke kterému chcete připojit data.  
  
2. Na **zobrazení** nabídce vyberte možnost **ostatní Windows** > **zdroje dat**.  
  
     ![Zobrazení zdrojů dat Windows](../data-tools/media/viewdatasources.png "ViewDataSources")  
  
3. V **zdroje dat** okna, klikněte na tlačítko **přidat nový zdroj dat**.  
  
4. Vyberte **databáze** na **zvolte typ zdroje dat** stránce a pak vyberte **Další**.  
  
5. Vyberte **datovou sadu** na **vyberte databázový Model** stránce a pak vyberte **Další**.  
  
6. Na **vyberte datové připojení** stránce **nové připojení** konfigurace nové datové připojení.  
  
7. Pokud zdroj dat není **soubor databáze Microsoft Access (OLE DB)** vyberte **změnu** otevřít **změnit zdroj dat** dialogové okno a vyberte **Microsoft Přístup k souboru databáze**a pak vyberte **OK**.  
  
8. V **název souboru databáze**, zadejte cestu a název souboru .mdb, ke kterému chcete připojit a pak vyberte **OK**.  
  
     ![Přidat připojení souboru databáze aplikace Access](../data-tools/media/dataaddconnectionaccessmdb.png "dataAddConnectionAccessMDB")  
  
9. Vyberte **Další** na **vyberte datové připojení** stránky.  
  
10. Vyberte **Další** na **uložit připojovací řetězec do konfiguračního souboru aplikace** stránky.  
  
11. Rozbalte **tabulky** uzlu **zvolte vaše databázové objekty** stránky.  
  
12. Vyberte jakékoli tabulky a zobrazení v datové sadě a pak vyberte **Dokončit**.  
  
     Do projektu je přidána datová sada a tabulky a zobrazení se zobrazí **zdroje dat** okna.  
  
## <a name="security"></a>Zabezpečení  
 Ukládání citlivých informací (například hesla) může ovlivnit zabezpečení aplikace. Bezpečnější způsob, jak řídit přístup k databázi, je ověřování systému Windows (označované také jako integrované zabezpečení). Další informace najdete v tématu [chrání informace o připojení](http://msdn.microsoft.com/library/1471f580-bcd4-4046-bdaf-d2541ecda2f4).  
  
## <a name="next-steps"></a>Další kroky  
 Je teď dostupná v datové sadě, kterou jste právě vytvořili **zdroje dat** okna. Nyní můžete provést kteroukoli z následujících úloh:  
  
- Vyberte položky v **zdroje dat** okno a přetáhněte je na svůj formulář (naleznete v tématu [ovládací prvky vazby Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)).  
  
- Otevřete zdroj dat v návrháři datových sad můžete přidat nebo upravit objekty, které tvoří datové sady.  
  
- Přidejte logiku ověřování k <xref:System.Data.DataTable.ColumnChanging> nebo <xref:System.Data.DataTable.RowChanging> události tabulek dat v datové sadě (naleznete v tématu [ověření dat v datových sadách](../data-tools/validate-data-in-datasets.md)).  
  
## <a name="see-also"></a>Viz také

 [Příprava aplikace pro příjem dat](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [Ověřování dat](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [Návody k datům](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)