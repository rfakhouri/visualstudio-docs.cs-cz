---
title: 'Návod: Vytvoření vazby ovládacích prvků obsahu do vlastní části XML'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- PlainTextContentControl, binding to a custom XML part
- custom XML parts, binding to content controls
- content controls [Office development in Visual Studio], data binding
- data binding [Office development in Visual Studio], content controls
- DropDownListContentControl, binding items to a custom XML part
- DatePickerContentControl, binding to a custom XML part
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 71fc9f944ec8861503f5518eec9edf33170bf050
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34768089"
---
# <a name="walkthrough-bind-content-controls-to-custom-xml-parts"></a>Návod: Vytvoření vazby ovládacích prvků obsahu do vlastní části XML
  Tento návod ukazuje, jak vazby ovládacích prvků obsahu přizpůsobení na úrovni dokumentu ve Wordu na data XML, který je uložený v dokumentu.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Word umožňuje ukládat data XML s názvem *vlastní části XML*, v dokumentu. Zobrazení těchto dat můžete řídit pomocí vytvoření vazby ovládacích prvků obsahu elementům ve vlastní část XML. Příklad dokumentu v tomto návodu zobrazí informace o zaměstnancích, která je uložená v na vlastní část XML. Když otevřete dokument, zobrazí ovládací prvky obsahu hodnoty elementů XML. Veškeré změny, které provedete na text v ovládacích prvků obsahu se ukládají do vlastní část XML.  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Přidání ovládacích prvků obsahu do dokumentů aplikace Word v projektech na úrovni dokumentu v době návrhu.  
  
-   Vytvoření datového souboru XML a schéma XML, který definuje elementy pro vytvoření vazby na ovládací prvky obsahu.  
  
-   Schéma XML se připojuje k dokumentu v době návrhu.  
  
-   Přidání obsahu souboru XML na vlastní část XML v dokumentu za běhu.  
  
-   Vytvoření vazby ovládacích prvků obsahu na elementy ve vlastní část XML.  
  
-   Vytvoření vazby <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> do sady hodnot, které jsou definovány v schématu XML.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Aplikace Microsoft Word.  
  
## <a name="create-a-new-word-document-project"></a>Vytvoření nového projektu dokumentu aplikace Word  
 Vytvořte dokument aplikace Word, které použijete v návodu.  
  
### <a name="to-create-a-new-word-document-project"></a>K vytvoření nového projektu dokumentu aplikace Word  
  
1.  Vytvoření projektu dokumentu aplikace Word s názvem **EmployeeControls**. Vytvořte nový dokument pro řešení. Další informace najdete v tématu [postupy: vytvoření Office projekty v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Otevře nový dokument aplikace Word v návrháři a přidá **EmployeeControls** projektu do **Průzkumníku řešení**.  
  
## <a name="add-content-controls-to-the-document"></a>Přidání ovládacích prvků obsahu v dokumentu  
 Vytvořte tabulku, která obsahuje tři různé typy obsahu ovládacích prvků, které může uživatel zobrazit nebo upravit informace o zaměstnanec.  
  
### <a name="to-add-content-controls-to-the-document"></a>Přidání ovládacích prvků obsahu do dokumentu  
  
1.  Do Wordového dokumentu, který je hostován v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] designer a na pásu karet, vyberte **vložit** kartě.  
  
2.  V **tabulky** skupiny, vyberte **tabulky**a vložte tabulku se sloupci 2 a 3 řádky.  
  
3.  Zadejte text z prvního sloupce tak, aby je podobná následující sloupce:  
  
    ||  
    |-|  
    |**Jméno zaměstnance**|  
    |**Datum přijetí**|  
    |**Název**|  
  
4.  V druhém sloupci tabulky, zvolte první řádek (vedle **jméno zaměstnance**).  
  
5.  Na pásu karet, vyberte **vývojáře** kartě.  
  
    > [!NOTE]  
    >  Pokud **vývojáře** karta není viditelný, musíte ji nejdříve zobrazit. Další informace najdete v tématu [postupy: zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
6.  V **ovládací prvky** skupiny, vyberte **Text** tlačítko ![PlainTextContentControl](../vsto/media/plaintextcontrol.gif "PlainTextContentControl") přidat <xref:Microsoft.Office.Tools.Word.PlainTextContentControl>na první buňky.  
  
7.  V druhém sloupci tabulky, vyberte druhý řádek (vedle **datum přijetí**).  
  
8.  V **ovládací prvky** skupiny, vyberte **výběr data** tlačítko ![DatePickerContentControl](../vsto/media/datepicker.gif "DatePickerContentControl") přidat <xref:Microsoft.Office.Tools.Word.DatePickerContentControl> do druhé buňky.  
  
9. V druhém sloupci tabulky, vyberte třetí řádek (vedle **název**).  
  
10. V **ovládací prvky** skupiny, vyberte **rozevíracího seznamu** tlačítko ![DropDownListContentControl](../vsto/media/dropdownlist.gif "DropDownListContentControl") přidat <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> na poslední buňku.  
  
 Který označuje celý uživatelské rozhraní pro tento projekt. Pokud spustíte projekt teď můžete zadejte text v prvním řádku a vyberte datum ve druhém řádku. Dalším krokem je připojit data, která se má zobrazit v dokumentu v souboru XML.  
  
## <a name="create-the-xml-data-file"></a>Vytvoření datového souboru XML  
 Obvykle se získat data XML pro ukládání na vlastní část XML z externího zdroje, jako je například soubor nebo databázi. V tomto návodu vytvoříte soubor XML, který obsahuje data zaměstnanců, označeny prvky, které bude vytvoření vazby na ovládací prvky obsahu v dokumentu. Pokud chcete data zpřístupnit za běhu, vložte jako prostředek v sestavení přizpůsobení souboru XML.  
  
#### <a name="to-create-the-data-file"></a>K vytvoření datového souboru  
  
1.  Na **projektu** nabídce zvolte **přidat novou položku**.  
  
     **Přidat novou položku** zobrazí se dialogové okno.  
  
2.  V **šablony** podokně, vyberte **souboru XML**.  
  
3.  Název souboru **employees.xml**a potom zvolte **přidat** tlačítko.  
  
     **Employees.xml** soubor se otevře v editoru kódu.  
  
4.  Nahraďte obsah **employees.xml** soubor s tímto textem.  
  
    ```xml 
    <?xml version="1.0" encoding="utf-8" ?>  
    <employees xmlns="http://schemas.microsoft.com/vsto/samples">  
      <employee>  
        <name>Karina Leal</name>  
        <hireDate>1999-04-01</hireDate>  
        <title>Manager</title>  
      </employee>  
    </employees>  
    ```  
  
5.  V **Průzkumníku řešení**, vyberte **employees.xml** souboru.  
  
6.  V **vlastnosti** vyberte **akce sestavení** vlastnost a potom změňte hodnotu na **vložený prostředek**.  
  
     Tento krok vloží soubor XML jako prostředek v sestavení při sestavování projektu. To umožňuje přístup k obsahu souboru XML za běhu.  
  
## <a name="create-an-xml-schema"></a>Vytvořit schéma XML  
 Pokud chcete vytvořit vazbu ovládacího prvku obsahu do jednoho elementu v na vlastní část XML, nemáte použít schéma XML. Však vytvořit vazbu <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> do sady hodnot, je nutné vytvořit schéma XML, která ověřuje datový soubor XML, který jste vytvořili dříve. Možné hodnoty pro definuje schéma XML `title` elementu. Vytvoříte vazbu <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> do tohoto elementu. dále v tomto návodu.  
  
#### <a name="to-create-an-xml-schema"></a>Chcete-li vytvořit schéma XML  
  
1.  Na **projektu** nabídce zvolte **přidat novou položku**.  
  
     **Přidat novou položku** zobrazí se dialogové okno.  
  
2.  V **šablony** podokně, vyberte **schématu XML**.  
  
3.  Název schématu **employees.xsd** a zvolte **přidat** tlačítko.  
  
     Otevře se Návrhář schématu.  
  
4.  V **Průzkumníku řešení**, otevřete místní nabídku pro **employees.xsd**a potom zvolte **kód zobrazení**.  
  
5.  Nahraďte obsah **employees.xsd** soubor s následující schéma.  
  
    ```xml
    <?xml version="1.0" encoding="utf-8" ?>  
    <xs:schema xmlns="http://schemas.microsoft.com/vsto/samples"   
        targetNamespace="http://schemas.microsoft.com/vsto/samples"  
        xmlns:xs="http://www.w3.org/2001/XMLSchema"  
        elementFormDefault="qualified">  
      <xs:element name="employees" type="EmployeesType"></xs:element>  
      <xs:complexType name="EmployeesType">  
        <xs:all>  
          <xs:element name="employee" type="EmployeeType"/>  
        </xs:all>  
      </xs:complexType>  
      <xs:complexType name="EmployeeType">  
        <xs:sequence>  
          <xs:element name="name" type="xs:string" minOccurs="1" maxOccurs="1"/>  
          <xs:element name="hireDate" type="xs:date" minOccurs="1" maxOccurs="1"/>  
          <xs:element name="title" type="TitleType" minOccurs="1" maxOccurs="1"/>  
        </xs:sequence>  
      </xs:complexType>  
      <xs:simpleType name="TitleType">  
        <xs:restriction base="xs:string">  
          <xs:enumeration value ="Engineer"/>  
          <xs:enumeration value ="Designer"/>  
          <xs:enumeration value ="Manager"/>  
        </xs:restriction>  
      </xs:simpleType>  
    </xs:schema>  
    ```  
  
6.  Na **soubor** nabídky, klikněte na tlačítko **Uložit vše** uložte změny do **employees.xml** a **employees.xsd** soubory.  
  
## <a name="attach-the-xml-schema-to-the-document"></a>Přiřadit dokument schématu XML  
 Schéma XML musí připojit k dokumentu, který má-li vytvořit vazbu <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> na platné hodnoty `title` elementu.  
  
### <a name="to-attach-the-xml-schema-to-the-document-includeword15shortvstoincludesword-15-short-mdmd"></a>Pro připojení k dokument schématu XML ([!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)])  
  
1.  Aktivovat **EmployeeControls.docx** v návrháři.  
  
2.  Na pásu karet, vyberte **vývojáře** a pak klikněte na příkaz **doplňky** tlačítko.  
  
3.  V **šablony a doplňky** dialogovém okně vyberte **schématu XML** a pak klikněte na příkaz **přidat schéma** tlačítko.  
  
4.  Vyhledejte **employees.xsd** schématu jste vytvořili dříve, který je umístěný v adresáři projektu a zvolte **otevřete** tlačítko.  
  
5.  Vyberte **OK** v tlačítko **schéma – nastavení** dialogové okno.  
  
6.  Vyberte **OK** tlačítko zavřete **šablony a doplňky** dialogové okno.  
  
### <a name="to-attach-the-xml-schema-to-the-document-word-2010"></a>Připojit schématu XML v dokumentu (Word 2010)  
  
1.  Aktivovat **EmployeeControls.docx** v návrháři.  
  
2.  Na pásu karet, vyberte **vývojáře** kartě.  
  
3.  V **XML** skupiny, vyberte **schématu** tlačítko.  
  
4.  V **šablony a doplňky** dialogovém okně vyberte **schématu XML** a pak klikněte na příkaz **přidat schéma** tlačítko.  
  
5.  Vyhledejte **employees.xsd** schéma, které jste vytvořili dříve, který je umístěný v adresáři projektu a zvolte **otevřete** tlačítko.  
  
6.  Vyberte **OK** v tlačítko **schéma – nastavení** dialogové okno.  
  
7.  Vyberte **OK** tlačítko zavřete **šablony a doplňky** dialogové okno.  
  
     **Struktuře XML** otevře v podokně úloh.  
  
8.  Zavřít **struktuře XML** podokna úloh.  
  
## <a name="add-a-custom-xml-part-to-the-document"></a>Přidat na vlastní část XML do dokumentů  
 Před ovládací prvky obsahu můžete vázat na elementy v souboru XML, je nutné přidat nové vlastní část XML v dokumentu obsah souboru XML.  
  
### <a name="to-add-a-custom-xml-part-to-the-document"></a>Přidat na vlastní část XML do dokumentů  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **ThisDocument.cs** nebo **ThisDocument.vb**a potom zvolte **kód zobrazení**.  
  
2.  Přidejte následující deklarace k `ThisDocument` třídy. Tento kód deklaruje několik objektů, které budete používat pro přidání na vlastní část XML do dokumentu.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#1](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#1)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#1](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#1)]  
  
3.  Přidejte následující metodu do `ThisDocument` třídy. Tato metoda získá obsah datového souboru XML, který je vložený jako prostředek v sestavení a vrátí obsah jako řetězec v kódu XML.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#3](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#3)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#3](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#3)]  
  
4.  Přidejte následující metodu do `ThisDocument` třídy. `AddCustomXmlPart` Metoda vytvoří novou vlastní část XML, který obsahuje řetězec XML, který je předaný metodě.  
  
     Pokud chcete, aby vlastní část XML je vytvořen pouze jednou, metoda vytvoří vlastní kód XML část pouze v případě, že na vlastní část XML s odpovídajícím identifikátorem GUID již neexistuje v dokumentu. Tato metoda je volána, když poprvé uloží hodnotu <xref:Microsoft.Office.Core._CustomXMLPart.Id%2A> vlastnost, která má `employeeXMLPartID` řetězec. Hodnota `employeeXMLPartID` řetězec je jako trvalý v dokumentu, protože byla deklarována pomocí <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> atribut.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#4](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#4)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#4](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#4)]  
  
## <a name="bind-the-content-controls-to-elements-in-the-custom-xml-part"></a>Vytvoření vazby ovládacích prvků obsahu elementům ve vlastní část XML  
 Navázat každý ovládací prvek elementu v vlastní část XML pomocí **XMLMapping** vlastnost pro každý ovládací prvek.  
  
### <a name="to-bind-the-content-controls-to-elements-in-the-custom-xml-part"></a>K vytvoření vazby ovládacích prvků obsahu elementů ve vlastní část XML  
  
1.  Přidejte následující metodu do `ThisDocument` třídy. Tato metoda váže každý ovládací prvek elementu v vlastní část XML a nastaví formát zobrazení data <xref:Microsoft.Office.Tools.Word.DatePickerContentControl>.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#5](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#5)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#5](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#5)]  
  
## <a name="run-your-code-when-the-document-is-opened"></a>Spuštění kódu při otevření dokumentu  
 Vytvořte vlastní část XML a vytvořit vazbu vlastní ovládací prvky na data, po otevření dokumentu.  
  
### <a name="to-run-your-code-when-the-document-is-opened"></a>Ke spuštění kódu při otevření dokumentu  
  
1.  Přidejte následující kód, který `ThisDocument_Startup` metodu `ThisDocument` třídy. Tento kód získá řetězec XML z **employees.xml** souboru, přidá řetězec XML nové vlastní část XML v dokumentu a sváže ovládací prvky obsahu elementů ve vlastní část XML.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#2](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#2)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#2](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#2)]  
  
## <a name="test-the-project"></a>Testování projektu  
 Když otevřete dokument, ovládací prvky obsahu zobrazit data z elementů v vlastní část XML. Můžete kliknout na <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> vyberte jednu ze tří platné hodnoty pro `title` element, který jsou definovány v **employees.xsd** souboru. Pokud chcete upravit data v některém z ovládacích prvků obsahu, na nové hodnoty se ukládají do vlastní část XML v dokumentu.  
  
### <a name="to-test-the-content-controls"></a>K testování ovládací prvky obsahu  
  
1.  Stiskněte klávesu **F5** spustit projekt.  
  
2.  Ověřte, že v tabulce v dokumentu podobá v následující tabulce. Každý z řetězců v druhém sloupci se získávají z elementu v vlastní část XML v dokumentu.  
  
    |||  
    |-|-|  
    |**Jméno zaměstnance**|**Karina Leal**|  
    |**Datum přijetí**|**1. dubna 1999**|  
    |**Název**|**Správce**|  
  
3.  Zvolte buňky napravo **jméno zaměstnance** buňky a zadejte jiný název.  
  
4.  Zvolte buňky napravo **datum přijetí** buňky a vyberte jiné datum při výběru data.  
  
5.  Zvolte buňky napravo **název** buňky a vyberte novou položku z rozevíracího seznamu.  
  
6.  Uložte a zavřete dokument.  
  
7.  V Průzkumníku souborů, otevřete *\bin\Debug* složku v umístění projektu.  
  
8.  Otevřete místní nabídku pro **EmployeeControls.docx** a potom zvolte **přejmenovat**.  
  
9. Název souboru **EmployeeControls.docx.zip**.  
  
     **EmployeeControls.docx** uložení ve formátu Open XML. Tento dokument s přejmenováním *.zip* příponou názvu souboru můžete zkontrolovat obsah dokumentu. Další informace o Open XML, najdete v článku na technické [představení Office (2007) Open XML formáty souborů](http://msdn.microsoft.com/en-us/96018532-f62c-4da7-bbff-16b96a483fbf).  
  
10. Otevřete **EmployeeControls.docx.zip** souboru.  
  
11. Otevřete **customXml** složky.  
  
12. Otevřete místní nabídku pro **item2.xml** a potom zvolte **otevřete**.  
  
     Tento soubor obsahuje vlastní část XML, který jste přidali do dokumentu.  
  
13. Ověřte, zda `name`, `hireDate`, a `title` obsahovat elementy s novými hodnotami, které jste zadali do ovládacích prvků obsahu v dokumentu.  
  
14. Zavřít **item2.xml** souboru.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o tom, jak používat ovládací prvky obsahu z těchto témat:  
  
-   Všechny dostupné ovládací prvky obsahu použijte k vytvoření šablony. Další informace najdete v tématu [návod: vytvoření šablony s použitím ovládacích prvků obsahu](../vsto/walkthrough-creating-a-template-by-using-content-controls.md).  
  
-   Upravte data v vlastní části XML při zavření dokumentu. Ovládací prvky obsahu, které jsou vázány na elementy XML při příštím otevření dokumentu se zobrazí nová data.  
  
-   Použití ovládacích prvků obsahu s ochrana částí dokumentu. Další informace najdete v tématu [postupy: ochrana částí dokumentů pomocí ovládacích prvků obsahu](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md).  
  
## <a name="see-also"></a>Viz také:  
 [Automatizace aplikace Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [Ovládací prvky obsahu](../vsto/content-controls.md)   
 [Postupy: Přidání ovládacích prvků obsahu do dokumentů aplikace Word](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Postupy: ochrana částí dokumentů pomocí ovládacích prvků obsahu](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  