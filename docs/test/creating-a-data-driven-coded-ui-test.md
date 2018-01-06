---
title: "Vytvoření datově řízeného programového testu uživatelského rozhraní | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: coded UI tests, data-driven
ms.assetid: 5838f02d-001f-49ce-adce-c9ea1afaec2f
caps.latest.revision: "56"
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: cb7e1e231cda62f5312be7dd1058667e5b9ae363
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-data-driven-coded-ui-test"></a>Vytvoření datově řízeného programového testu UI
K testování různých podmínkách, můžete spustit testy vícekrát s jiným parametrem hodnotami. Datově řízeného programového uživatelského rozhraní jsou testy pohodlný způsob, jak to udělat. Můžete definovat hodnoty parametrů ve zdroji dat a každý řádek ve zdroji dat je iterace programového testu uživatelského rozhraní. Celkový výsledek testu budou založeny na výsledek pro všechny iterace. Například pokud se jeden testovací iterace nezdaří, celkový výsledek testu je selhání.  
  
 **Požadavky**  
  
-   Visual Studio Enterprise  
  
## <a name="create-a-data-driven-coded-ui-test"></a>Vytvoření datové programového testu uživatelského rozhraní  
 Tato ukázka vytvoří programového testu uživatelského rozhraní, která běží na Windows kalkulačky aplikace. Ho společně sečte dvě čísla a kontrolní výrazy používá k ověření, zda je správný součet. Dále jsou kontrolní výraz a hodnoty parametrů pro dva čísla programového stane řízené daty a uložené v souboru hodnot oddělených čárkami (.csv).  
  
#### <a name="step-1---create-a-coded-ui-test"></a>Krok 1 – Vytvoření programového testu UI  
  
1.  Vytvořte projekt.  
  
     ![Vytvoření projektu programových testů uživatelského rozhraní](../test/media/cuit_datadriven_.png "CUIT_dataDriven_")  
  
2.  Zvolte záznam akce.  
  
     ![Akce, které zaznamenáte](../test/media/cuit_datadriven_generatecodedialog.png "CUIT_dataDriven_GenerateCodeDialog")  
  
3.  Otevřete aplikaci kalkulačky a spusťte záznam test.  
  
     ![Záznam akcí](../test/media/cuit_datadriven_cuitbuilder.png "CUIT_dataDriven_CUITBuilder")  
  
4.  Přidat 1 a 2, pozastavit záznam a vygenerovat zkušební metody. Hodnoty tento uživatelský vstup jsme později budete nahraďte hodnotami z datového souboru.  
  
     ![Metoda test Genetate](../test/media/cuit_datadriven_cuitbuildergencode.png "CUIT_dataDriven_CUITBuilderGenCode")  
  
     Zavřete Tvůrce testu. Metoda je přidat do testu:  
  
    ```csharp  
    [TestMethod]  
    public void CodedUITestMethod1()  
    {  
        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.  
        this.UIMap.AddNumbers();  
  
    }  
    ```  
  
5.  Použití `AddNumbers()` metodu k ověření, že test běží. Umístěte kurzor do výše uvedená metoda test, otevřete kontextu nabídku a vyberte **spuštění testů**. (Klávesové zkratky: Ctrl + R, T).  
  
     Výsledek testu, který ukazuje Pokud test předán nebo se nezdařilo se zobrazí v okně Průzkumníka testů. Otevřete okno Průzkumníka testů z **TEST** nabídce zvolte **Windows** a potom zvolte **Průzkumníka testů**.  
  
6.  Protože zdroj dat lze také hodnoty parametrů assertion – které jsou používány test ověření očekávaných hodnot – přidejme kontrolní výrazy k ověření, zda je správný součet dvou čísel. Umístěte kurzor do výše uvedená metoda test, otevřete kontextu nabídku a vyberte **generovat kód pro programové testování uživatelského rozhraní**a potom **použití programových Tvůrce uživatelského rozhraní Test**.  
  
     Mapy ovládacího prvku text kalkulačky, který zobrazuje součet.  
  
     ![Map – ovládací prvek text uživatelského rozhraní](../test/media/cuit_datadriven_addassertion.png "CUIT_dataDriven_AddAssertion")  
  
7.  Přidáte kontrolní výraz, který ověří, zda hodnota součtu je správný. Vyberte **ZobrazenýText** vlastnost, která má hodnotu **3** a potom zvolte **přidat kontrolní**. Použití **AreEqual** komparátoru a ověřte, zda je hodnota porovnání **3**.  
  
     ![Nakonfigurujte kontrolní výraz](../test/media/cuit_datadriven_builderaddassertion2.png "CUIT_dataDriven_BuilderAddAssertion2")  
  
8.  Po dokončení konfigurace kontrolní výraz, generování kódu z Tvůrce znovu. Tím se vytvoří nová metoda pro ověření.  
  
     ![Generate – metoda assertion](../test/media/cuit_datadriven_assertiongencode.png "CUIT_dataDriven_AssertionGenCode")  
  
     Protože `ValidateSum` metoda ověří výsledky `AddNumbers` metoda, přesunout ho k dolnímu okraji bloku kódu.  
  
    ```csharp  
    public void CodedUITestMethod1()  
    {  
  
        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.  
        this.UIMap.AddNumbers();  
        this.UIMap.ValidateSum();  
  
    }  
    ```  
  
9. Ověřte, že test běží pomocí `ValidateSum()` metoda. Umístěte kurzor do výše uvedená metoda test, otevřete kontextu nabídku a vyberte **spuštění testů**. (Klávesové zkratky: Ctrl + R, T).  
  
     V tomto okamžiku všechny hodnoty parametrů jsou definovány v své metody jako konstanty. V dalším kroku vytvoříme datové sady, aby naše testovací řízené daty.  
  
#### <a name="step-2---create-a-data-set"></a>Krok 2 – Vytvoření datové sady  
  
1.  Přidejte do textového souboru do dataDrivenSample projektu s názvem `data.csv`.  
  
     ![Přidejte do projektu soubor hodnota hodnotami oddělenými čárkami](../test/media/cuit_datadriven_addcsvfile.png "CUIT_dataDriven_AddCSVFile")  
  
2.  Naplnění souboru .csv s následujícími údaji:  
  
    |Num1|Num2|Součet|  
    |----------|----------|---------|  
    |3|4|7|  
    |5|6|11|  
    |6|8|14|  
  
     Po přidání data, soubor by měl vypadat takto:  
  
     ![Naplnění. Soubor CSV s daty](../test/media/cuit_datadriven_adddatatocsvfile.png "CUIT_dataDriven_AddDataToCSVFile")  
  
3.  Je důležité k uložení souboru .csv pomocí správné kódování. Na **soubor** nabídce zvolte **rozšířené možnosti ukládání** a zvolte **Unicode (UTF-8 bez podpisu) - Codepage 65001** jako kódování.  
  
4.  Soubor CSV musí zkopírovat do výstupního adresáře, nebo nelze spustit test. Použití okna Vlastnosti a zkopírujte ho.  
  
     ![Nasazení. Soubor CSV](../test/media/cuit_datadriven_deploycsvfile.png "CUIT_dataDriven_DeployCSVFile")  
  
     Teď, když máme sadu dat vytvořili, můžeme vazbu dat na test.  
  
#### <a name="step-3---add-data-source-binding"></a>Krok 3 – Přidání datového zdroje vazby  
  
1.  Svázat zdroj dat, přidejte `DataSource` atribut do existujícího `[TestMethod]` atribut, který je hned nad metodu test.  
  
    ```  
    [DataSource("Microsoft.VisualStudio.TestTools.DataSource.CSV", "|DataDirectory|\\data.csv", "data#csv", DataAccessMethod.Sequential), DeploymentItem("data.csv"), TestMethod]  
    public void CodedUITestMethod1()  
    {  
  
        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.  
        this.UIMap.AddNumbers();  
        this.UIMap.ValidateSum();  
  
    }  
  
    ```  
  
     Zdroj dat je nyní k dispozici pro použití v této metodě test.  
  
    > [!TIP]
    >  V tématu [ukázky atribut zdroje dat](#CreateDataDrivenCUIT_QA_DataSourceAttributes) ve funkci QA část ukázky použití jiné typy zdrojů dat, jako je například XML, SQL Express a Excel.  
  
2.  Spuštění testu.  
  
     Všimněte si, že test běží prostřednictvím tři iterací. To je proto tří řádků dat obsahuje zdroj dat, která byla vázána. Však bude také zjistíte, že test stále používá hodnoty parametru konstantní a je přidání 1 + 2 s součet hodnot 3 pokaždé, když.  
  
     V dalším kroku nakonfigurujeme testu chcete hodnoty použít v datovém souboru zdroje.  
  
#### <a name="step-4---use-the-data-in-the-coded-ui-test"></a>Krok 4 – používat data při programového testu uživatelského rozhraní  
  
1.  Přidat `using Microsoft.VisualStudio.TestTools.UITesting.WinControls` na začátek souboru CodedUITest.cs:  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text.RegularExpressions;  
    using System.Windows.Input;  
    using System.Windows.Forms;  
    using System.Drawing;  
    using Microsoft.VisualStudio.TestTools.UITesting;  
    using Microsoft.VisualStudio.TestTools.UnitTesting;  
    using Microsoft.VisualStudio.TestTools.UITest.Extension;  
    using Keyboard = Microsoft.VisualStudio.TestTools.UITesting.Keyboard;  
    using Microsoft.VisualStudio.TestTools.UITesting.WinControls;  
    ```  
  
2.  Přidat `TestContext.DataRow[]` v `CodedUITestMethod1()` metodu, která bude ze zdroje dat použít hodnoty. Hodnoty zdroje dat přepsat konstanty přiřadit do zdroje UIMap ovládacích prvků pomocí ovládacích prvků `SearchProperties`:  
  
    ```  
    public void CodedUITestMethod1()  
    {  
  
        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.  
        this.UIMap.UICalculatorWindow.UIItemWindow.UIItem1Button.SearchProperties[WinButton.PropertyNames.Name] = TestContext.DataRow["Num1"].ToString();this.UIMap.UICalculatorWindow.UIItemWindow21.UIItem2Button.SearchProperties[WinButton.PropertyNames.Name] = TestContext.DataRow["Num2"].ToString();  
        this.UIMap.AddNumbers();  
        this.UIMap.ValidateSumExpectedValues.UIItem2TextDisplayText = TestContext.DataRow["Sum"].ToString();  
        this.UIMap.ValidateSum();  
  
    }  
    ```  
  
     Vlastnosti, které hledání do kódu data, a pokuste se zjistit pomocí editoru programových testů uživatelského rozhraní.  
  
    -   Otevřete soubor UIMap.uitest.  
  
         ![Otevřete editoru programových testů UI](../test/media/cuit_datadriven_opentesteditor.png "CUIT_dataDriven_OpenTestEditor")  
  
    -   Vyberte akci uživatelského rozhraní a sledovat odpovídající mapování ovládacích prvků uživatelského rozhraní. Všimněte si, jak mapování odpovídá kódu, například `this.UIMap.UICalculatorWindow.UIItemWindow.UIItem1Button`.  
  
         ![Pomocí editoru programových testů uživatelského rozhraní, abyste kódu](../test/media/cuit_datadriven_testeditor.png "CUIT_dataDriven_TestEditor")  
  
    -   V okně vlastností otevřete **vlastností vyhledávání**. Vlastností vyhledávání **název** co je se s nimi manipulovat, v kódu pomocí zdroje dat je hodnota. Například `SearchProperties` je právě přiřazován hodnoty z prvního sloupce každý řádek dat: `UIItem1Button.SearchProperties[WinButton.PropertyNames.Name] = TestContext.DataRow["Num1"].ToString();`. Pro tři iterací tento test se změní **název** hodnotu pro vlastnost vyhledávání 3, potom 5 a nakonec 6.  
  
         ![Pomocí vlastností vyhledávání v kódování pomoct](../test/media/cuit_datadriven_searchproperties.png "CUIT_dataDriven_SearchProperties")  
  
3.  Uložte řešení.  
  
#### <a name="step-5---run-the-data-driven-test"></a>Krok 5 – spuštění testu řízené daty  
  
1.  Ověřte, zda test nyní řízené daty tak, že znovu spustíte test.  
  
     Měli byste vidět testu, spuštění prostřednictvím tři iterací pomocí hodnot v souboru CSV. Ověření by měla fungovat tak dobře a test by měla zobrazovat jako předaný v Průzkumníku otestovat.  
  
 **Pokyny**  
  
 Další informace najdete v tématu [testování pro nastavené průběžné doručování s Visual Studio 2012 – kapitoly 2: testování částí: testování uvnitř](http://go.microsoft.com/fwlink/?LinkID=255188) a [testování pro nastavené průběžné doručování s Visual Studio 2012 – kapitoly 5: Automatizace systémových testů](http://go.microsoft.com/fwlink/?LinkID=255196)  
  
## <a name="q--a"></a>Dotazy a odpovědi  
  
###  <a name="CreateDataDrivenCUIT_QA_DataSourceAttributes"></a>Jaké jsou atributy zdroje dat pro jiné typy zdrojů dat, jako je například SQL Express nebo XML?  
 Řetězce zdrojů dat ukázka v následující tabulce můžete použít tak, že kopírování je do vašeho kódu a potřebná přizpůsobení.  
  
 **Typy zdrojů dat a atributy**  
  
-   SDÍLENÝ SVAZEK CLUSTERU  
  
     `[DataSource("Microsoft.VisualStudio.TestTools.DataSource.CSV", "|DataDirectory|\\data.csv", "data#csv", DataAccessMethod.Sequential), DeploymentItem("data.csv"), TestMethod]`  
  
-   Excel  
  
     `DataSource("System.Data.Odbc", "Dsn=ExcelFiles;Driver={Microsoft Excel Driver (*.xls)};dbq=|DataDirectory|\\Data.xls;defaultdir=.;driverid=790;maxbuffersize=2048;pagetimeout=5;readonly=true", "Sheet1$", DataAccessMethod.Sequential), DeploymentItem("Sheet1.xls"), TestMethod]`  
  
-   Testovacího případu v sadě Team Foundation Server  
  
     `[DataSource("Microsoft.VisualStudio.TestTools.DataSource.TestCase", "http://vlm13261329:8080/tfs/DefaultCollection;Agile", "30", DataAccessMethod.Sequential), TestMethod]`  
  
-   XML  
  
     `[DataSource("Microsoft.VisualStudio.TestTools.DataSource.XML", "|DataDirectory|\\data.xml", "Iterations", DataAccessMethod.Sequential), DeploymentItem("data.xml"), TestMethod]`  
  
-   SQL Express  
  
     `[DataSource("System.Data.SqlClient", "Data Source=.\\sqlexpress;Initial Catalog=tempdb;Integrated Security=True", "Data", DataAccessMethod.Sequential), TestMethod]`  
  
### <a name="q-can-i-use-data-driven-tests-on-my-windows-phone-app"></a>Otázka: je možné použít datové testy na mé aplikace Windows Phone?  
 **Odpověď:** Ano. Řízené daty testy programového uživatelského rozhraní pro Windows Phone jsou definovány pomocí atributu DataRow na testovací metoda. V následujícím příkladu, x a y pomocí hodnoty 1 a 2 pro první iterace a -1 -2 pro druhý iterace testu.  
  
```  
[DataRow(1, 2, DisplayName = "Add positive numbers")]  
[DataRow(-1, -2, DisplayName = "Add negative numbers")]  
[TestMethod]  
public void DataDrivingDemo_MyTestMethod(int x, int y)  
  
```  
  
 Další informace najdete v tématu [řízené daty pomocí programových testů uživatelského rozhraní pro aplikace z Windows Phone](../test/test-windows-phone-8-1-apps-with-coded-ui-tests.md#TestingPhoneAppsCodedUI_DataDriven).  
  
### <a name="q-why-cant-i-modify-the-code-in-the-uimapdesigner-file"></a>Otázka: Proč nelze změnit kód v souboru UIMap.Designer?  
 **Odpověď:** změny kódu provedené v souboru UIMapDesigner.cs budou přepsány pokaždé, když generování kódu pomocí zdroje UIMap - Tvůrce programového testu uživatelského rozhraní. V této ukázce a ve většině případů můžete provést změny kódu potřebnými k povolení testu budou používat zdroj dat k souboru zdrojového kódu testu (CodedUITest1.cs).  
  
 Pokud je třeba změnit zaznamenanou metodu, musíte ji zkopírovat do souboru UIMap.cs a přejmenovat ji. Soubor UIMap.cs lze použít k přepsání metod a vlastností v souboru UIMapDesigner.cs. Je třeba odebrat odkaz na původní metodu v kódovaném souboru UITest.cs a nahradit ji názvem přejmenované metody.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap>   
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>   
 [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)   
 [Vytváření programové testy uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate)   
 [Osvědčené postupy pro programové testy uživatelského rozhraní](../test/best-practices-for-coded-ui-tests.md)   
 [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
