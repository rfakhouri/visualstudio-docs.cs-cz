---
title: "Vytvoření jednoduché datové aplikace pomocí ADO.NET | Microsoft Docs"
ms.custom: 
ms.date: 08/23/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: 2222841f-e443-4a3d-8c70-4506aa905193
caps.latest.revision: "42"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 05a0a339b413495aadfa397e5fec3b826f920026
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="create-a-simple-data-application-by-using-adonet"></a>Vytvoření jednoduché datové aplikace pomocí ADO.NET
Když vytvoříte aplikaci, která zpracovává data v databázi, můžete provádět základní úlohy, jako je například definování připojovací řetězce, vkládání dat a spuštění uložené procedury. Podle tohoto tématu zjistíte, jak používat databázi v aplikaci jednoduchou aplikaci "forms over data" Windows Forms pomocí Visual C# nebo Visual Basic a ADO.NET.  Všechny dat technologie .NET – včetně datové sady, technologie LINQ to SQL a Entity Framework – nakonec proveďte kroky, které jsou velmi podobné těm, které jsou uvedené v tomto článku.  
  
 Tento článek ukazuje jednoduchý způsob, jak získat data z databáze velmi rychlé způsobem. Pokud aplikace potřebuje ke změně dat nejsou v netriviálních způsoby a aktualizaci databáze, měli byste zvážit používající rozhraní Entity Framework a pomocí datové vazby ovládacích prvků uživatelského rozhraní na změny v základních datech automaticky synchronizovat.  
  
> [!IMPORTANT]
>  Pro zjednodušení kód neobsahuje výjimek produkční prostředí.  
  
 **V tomto tématu**  
  
-   [Nastavení ukázkové databáze](../data-tools/create-a-simple-data-application-by-using-adonet.md#BKMK_setupthesampledatabase)  
  
-   [Vytvoření formuláře a přidání ovládacích prvků](../data-tools/create-a-simple-data-application-by-using-adonet.md#BKMK_createtheformsandaddcontrols)  
  
-   [Připojovací řetězec uložit](../data-tools/create-a-simple-data-application-by-using-adonet.md#BKMK_storetheconnectionstring)   
  
-   [Napsání kódu pro formuláře](../data-tools/create-a-simple-data-application-by-using-adonet.md#BKMK_writethecodefortheforms)  
  
-   [Testování vaší aplikace](../data-tools/create-a-simple-data-application-by-using-adonet.md#BKMK_testyourapplication)  
  
## <a name="prerequisites"></a>Požadavky  
 Pokud chcete vytvořit aplikaci, budete potřebovat:  
  
-   Visual Studio Community Edition.  
  
-   SQL Server Express LocalDB. Pokud nemáte SQL serveru Express LocalDB, můžete ho nainstalovat [stránce pro stažení edice serveru SQL](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx).  

Toto téma předpokládá, že jste se seznámili s funkcemi základní prostředí Visual Studio IDE a můžete vytvořit aplikaci Windows Forms, přidat formuláře do projektu, put, tlačítek a jiných ovládacích prvků ve formulářích, nastavte vlastnosti ovládacích prvků a jednoduché události kódu. Pokud se tedy se tyto úlohy, doporučujeme provést [Začínáme s Visual C# a Visual Basic](../ide/getting-started-with-visual-csharp-and-visual-basic.md) tématu před spuštěním tohoto průvodce.  
  
##  <a name="BKMK_setupthesampledatabase"></a>Nastavení ukázkové databáze  
Vytvoření ukázkové databáze pomocí následujících kroků:  

1. V sadě Visual Studio, otevřete **Průzkumníka serveru** okno.  

2. Klikněte pravým tlačítkem na **datová připojení** a zvolte ** Vytvořit novou databázi SQL Server... ".  

3. V **název serveru** textové pole, zadejte **\mssqllocaldb (localdb)**.  

4. V **nový název databáze** textové pole, zadejte **prodej**, zvolte **OK**.  

     Prázdné **prodej** databáze je vytvořen a přidán do uzlu připojení dat v Průzkumníku serveru.  

5. Klikněte pravým tlačítkem na **prodej** datové připojení a vyberte **nový dotaz**.  

     Otevře se okno editoru dotazů.  

6. Kopírování [prodej Transact-SQL skriptu](https://github.com/MicrosoftDocs/visualstudio-docs/raw/master/docs/data-tools/samples/sales.sql) do schránky.  

7. Vložit do editoru dotazů skriptu T-SQL a potom vyberte **Execute** tlačítko.  

     Po krátkou dobu dotaz dokončí provádění a vytvoří se databázové objekty. Databáze obsahuje dvě tabulky: zákazníka a objednávky. Tyto tabulky původně neobsahují žádná data, ale můžete přidat dat při spuštění aplikace, které vytvoříte. Databáze také obsahuje čtyři jednoduché uložené procedury.   
  
##  <a name="BKMK_createtheformsandaddcontrols"></a>Vytvoření formuláře a přidání ovládacích prvků  
  
1.  Vytvořte projekt aplikace Windows Forms a pojmenujte ji SimpleDataApp.  
  
     Visual Studio vytvoří projekt a několik souborů, včetně prázdný formuláře Windows, který je pojmenován Form1.  
  
2.  Do projektu přidejte dva formuláře Windows tak, aby měl tři formulářů a pak jim poskytnout tyto názvy:  
  
    -   Navigace  
  
    -   Nový zákazník  
  
    -   FillOrCancel  
  
3.  Pro každý formulář přidejte do textových polí, tlačítek a jiných ovládacích prvků, které se zobrazují v následující ilustrace. Pro každý ovládací prvek nastavte vlastnosti, které jsou popsány v tabulce.  
  
    > [!NOTE]
    >  Skupinový rámeček a ovládací prvky popisek přidat přehlednost ale nejsou používány v kódu.  
  
 **Navigace formuláře**  
  
 ![Dialogové okno navigační](../data-tools/media/simpleappnav.png "SimpleAppNav")  
  
|Ovládací prvky pro daný formulář navigace|Vlastnosti|  
|--------------------------------------|----------------|  
|Tlačítko|Název = btnGoToAdd|  
|Tlačítko|Název = btnGoToFillOrCancel|  
|Tlačítko|Název = btnExit|  
  
 **Nový zákazník formuláře**  
  
 ![Přidání nového zákazníka a umístěte pořadí](../data-tools/media/simpleappnewcust.png "SimpleAppNewCust")  
  
|Ovládací prvky pro nový zákazník formulář|Vlastnosti|  
|---------------------------------------|----------------|  
|TextBox|Název = txtCustomerName|  
|TextBox|Název = txtCustomerID<br /><br /> Jen pro čtení = True|  
|Tlačítko|Název = btnCreateAccount|  
|NumericUpdown|Počet desetinných míst = 0<br /><br /> Maximální = 5000<br /><br /> Název = numOrderAmount|  
|DateTimePicker|Formát krátkého =<br /><br /> Název = dtpOrderDate|  
|Tlačítko|Název = btnPlaceOrder|  
|Tlačítko|Název = btnAddAnotherAccount|  
|Tlačítko|Název = btnAddFinish|  
  
 **FillOrCancel formuláře**  
  
 ![Zadejte nebo zrušit objednávky](../data-tools/media/simpleappcancelfill.png "SimpleAppCancelFill")  
  
|Ovládací prvky pro daný formulář FillOrCancel|Vlastnosti|  
|----------------------------------------|----------------|  
|TextBox|Název = txtOrderID|  
|Tlačítko|Název = btnFindByOrderID|  
|DateTimePicker|Formát krátkého =<br /><br /> Název = dtpFillDate|  
|DataGridView|Název = dgvCustomerOrders<br /><br /> Jen pro čtení = True<br /><br /> RowHeadersVisible = False|  
|Tlačítko|Název = btnCancelOrder|  
|Tlačítko|Název = btnFillOrder|  
|Tlačítko|Název = btnFinishUpdates|  
  
##  <a name="BKMK_storetheconnectionstring"></a>Připojovací řetězec uložit  
 Když se aplikace pokusí otevřít připojení k databázi, aplikace musí mít přístup k připojovací řetězec. Abyste se vyhnuli, zadáte řetězec ručně na každý formulář, řetězec uložit v souboru App.config ve vašem projektu a vytvoření metody, která vrátí řetězec, pokud metoda je volána z libovolného formuláře v aplikaci.  
  
 Kliknutím pravým tlačítkem na můžete najít připojovací řetězec **prodej** datové připojení v **Průzkumníka serveru** a výběr **vlastnosti**. Vyhledejte **ConnectionString** vlastnost a potom pomocí kombinace kláves Ctrl + A Ctrl + C vyberte a zkopírujte řetězec do schránky. 
  
1.  Pokud používáte C#, v **Průzkumníku řešení**, rozbalte **vlastnosti** uzlu v rámci projektu a pak otevřete **Settings.settings** souboru.  
    Pokud používáte v jazyce Visual Basic **Průzkumníku řešení**, klikněte na tlačítko **zobrazit všechny soubory**, rozbalte **Můj projekt** uzel a potom otevřete **Settings.settings** souboru.
  
2.  V **název** sloupce, zadejte `connString`.  
  
3.  V **typ** seznamu, vyberte **(připojovací řetězec)**.  
  
4.  V **oboru** seznamu, vyberte **aplikace**.    

5.  V **hodnotu** sloupec, zadejte připojovací řetězec (bez mimo uvozovek) a potom změny uložte.  
  
> [!NOTE]
>  V reálné aplikaci, měli byste uložit připojovací řetězec bezpečně, jak je popsáno v [připojovací řetězce a konfigurační soubory](/dotnet/framework/data/adonet/connection-strings-and-configuration-files).     
  
##  <a name="BKMK_writethecodefortheforms"></a>Napsání kódu pro formuláře  
 Tato část obsahuje stručný přehled jaké každý formulář. Nabízí taky kód, který definuje logiku při kliknutí na tlačítko ve formuláři.  
  
### <a name="navigation-form"></a>Navigace formuláře  

Navigace otevře při spuštění aplikace. **Přidat účet** tlačítko otevře nový zákazník formuláře. **Výplně nebo zrušit řadí** tlačítko otevře FillOrCancel formuláře. **Ukončení** tlačítko ukončení aplikace.  
  
#### <a name="make-the-navigation-form-the-startup-form"></a>Ujistěte se, navigace formuláři formulář spuštění.  
 Pokud používáte C#, v **Průzkumníku řešení**, otevřete Program.cs a potom změňte `Application.Run` řádek, který se toto:`Application.Run(new Navigation());`  
  
 Pokud používáte v jazyce Visual Basic **Průzkumníku řešení**, otevřete **vlastnosti** vyberte **aplikace** a pak vyberte  **SimpleDataApp.Navigation** v **formulář spuštění** seznamu.  
  
#### <a name="create-auto-generated-event-handlers"></a>Vytváření obslužných rutin automaticky generovaných událostí  
 Dvakrát klikněte na tři tlačítka na formuláři navigace k vytvoření metody obslužná rutina události prázdný. Dvakrát klikněte na tlačítka také přidá automaticky generovaný kód v souboru Návrhář kód, který umožňuje kliknutí na tlačítko pro vyvolání události.  
  
#### <a name="add-code-for-the-navigation-form-logic"></a>Přidejte kód pro formulář logiku navigace   
 Na stránce kód pro formulář navigační dokončení těla metody pro tlačítko tří obslužné rutiny události kliknutí jak je znázorněno v následujícím kódu.  
  
[!code-csharp[Navigation#1](../data-tools/codesnippet/CSharp/SimpleDataApp/Navigation.cs#1)]  
[!code-vb[Navigation#1](../data-tools/codesnippet/VisualBasic/SimpleDataApp/Navigation.vb#1)]   
  
### <a name="newcustomer-form"></a>Nový zákazník formuláře  
 Po zadání jméno zákazníka a pak vyberte **vytvořit účet** tlačítko Nový zákazník formuláře vytvoří účtu zákazníka a SQL Server vrací hodnotu IDENTITY jako nové ID zákazníka. Potom můžete umístit pořadí pro nový účet tak, že zadáte dobu a datu objednávky a výběr **odešlete objednávku** tlačítko.  
  
#### <a name="create-auto-generated-event-handlers"></a>Vytváření obslužných rutin automaticky generovaných událostí  
 Vytvořit prázdný klikněte na obslužné rutiny události pro každé tlačítko ve formuláři nový zákazník dvojím kliknutím na každý ze čtyř tlačítek. Dvakrát klikněte na tlačítka také přidá automaticky generovaný kód v souboru Návrhář kód, který umožňuje kliknutí na tlačítko pro vyvolání události.  
  
#### <a name="add-code-for-the-newcustomer-form-logic"></a>Přidejte kód pro logiku nový zákazník formuláře  
K dokončení logiku formuláře nový zákazník, postupujte takto.  

1. Přepněte ```System.Data.SqlClient``` oboru názvů do oboru tak, aby je nemuseli plně kvalifikaci názvy její členy.  

     ```csharp  
     using System.Data.SqlClient  
     ```  
     ```vb  
     Imports System.Data.SqlClient  
     ```  

2. Přidejte některé proměnné a pomocné metody pro třídu, jak je znázorněno v následujícím kódu.  

     [!code-csharp[NewCustomer#1](../data-tools/codesnippet/CSharp/SimpleDataApp/NewCustomer.cs#1)]  
     [!code-vb[NewCustomer#1](../data-tools/codesnippet/VisualBasic/SimpleDataApp/NewCustomer.vb#1)]  

3. Dokončení těla metody pro tlačítko čtyři obslužné rutiny události kliknutí jak je znázorněno v následujícím kódu.  

     [!code-csharp[NewCustomer#2](../data-tools/codesnippet/CSharp/SimpleDataApp/NewCustomer.cs#2)]  
     [!code-vb[NewCustomer#2](../data-tools/codesnippet/VisualBasic/SimpleDataApp/NewCustomer.vb#2)]  

### <a name="fillorcancel-form"></a>FillOrCancel formuláře  
 Formulář FillOrCancel spustí dotaz vrátí pořadí v případě zadejte ID pořadí a poté klikněte **najít pořadí** tlačítko. Vrácený řádek, který se zobrazí v mřížce dat jen pro čtení. Můžete označit pořadí jako zrušené (X), pokud jste vybrali **zrušit pořadí** tlačítko, nebo můžete označit pořadí jako vyplněný (F) Pokud jste vybrali **vyplnění pořadí** tlačítko. Pokud jste vybrali **najít pořadí** tlačítko znovu, se zobrazí aktualizovaná řádek.  
#### <a name="create-auto-generated-event-handlers"></a>Vytváření obslužných rutin automaticky generovaných událostí  
 Vytvořit prázdný obslužné rutiny události pro čtyři tlačítka na formuláři FillOrCancel kliknutí dvojitým kliknutím na tlačítka. Dvakrát klikněte na tlačítka také přidá automaticky generovaný kód v souboru Návrhář kód, který umožňuje kliknutí na tlačítko pro vyvolání události.  
  
#### <a name="add-code-for-the-fillorcancel-form-logic"></a>Přidejte kód pro logiku FillOrCancel formuláře  
K dokončení logice FillOrCancel formuláře, postupujte podle těchto kroků.  

1. Uveďte následující dva obory názvů do oboru, takže nemáte k plnému určení názvy jejich členové.  

     ```csharp  
     using System.Data.SqlClient;  
     using System.Text.RegularExpressions;  
     ```  
     ```vb  
     Imports System.Data.SqlClient  
     Imports System.Text.RegularExpressions  
     ```  

2. Přidejte proměnnou a pomocné metody do třídy, jak je znázorněno v následujícím kódu.  

     [!code-csharp[FillOrCancel#1](../data-tools/codesnippet/CSharp/SimpleDataApp/FillOrCancel.cs#1)]  
     [!code-vb[FillOrCancel#1](../data-tools/codesnippet/VisualBasic/SimpleDataApp/FillOrCancel.vb#1)]  

3. Dokončení těla metody pro tlačítko čtyři obslužné rutiny události kliknutí jak je znázorněno v následujícím kódu.  

     [!code-csharp[FillOrCancel#2](../data-tools/codesnippet/CSharp/SimpleDataApp/FillOrCancel.cs#2)]  
     [!code-vb[FillOrCancel#2](../data-tools/codesnippet/VisualBasic/SimpleDataApp/FillOrCancel.vb#2)]  

##  <a name="BKMK_testyourapplication"></a>Testování vaší aplikace  
Vyberte **F5** klíč pro vytvoření a testování vaší aplikace po code každou obslužnou rutinu události kliknutí a pak je po dokončení kódování.

## <a name="see-also"></a>Viz také
[Data nástroje sady Visual Studio pro .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)
