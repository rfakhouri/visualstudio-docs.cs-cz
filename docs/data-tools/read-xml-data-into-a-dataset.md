---
title: Čtení dat XML do datové sady
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- reading XML
- data access [Visual Studio], XML data
- reading files, XML
- data [Visual Studio], reading from XML files
- reading data, XML files
- XML [Visual Studio], reading
- XML documents, reading
- datasets [Visual Basic], reading XML data
ms.assetid: fae72958-0893-47d6-b3dd-9d42418418e4
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: d54811f2fe46733d256a473c5fcb1c523a15a71e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="read-xml-data-into-a-dataset"></a>Čtení dat XML do datové sady
ADO.NET poskytuje jednoduché metody pro práci s daty XML. V tomto návodu vytvoříte aplikace Windows, která načte XML data do datové sady. Datová sada se následně zobrazí <xref:System.Windows.Forms.DataGridView> ovládacího prvku. Nakonec schématu XML na základě obsahu souboru XML se zobrazí v textovém poli.

 Tento názorný postup se skládá z pěti hlavních kroků:

1.  Vytvoření nového projektu

2.  Vytvoření souboru XML načte do datové sady

3.  Vytvoření uživatelského rozhraní

4.  Datová sada vytváření, čtení souboru XML a v zobrazení <xref:System.Windows.Forms.DataGridView> ovládací prvek

5.  Přidání kódu k zobrazení schématu XML podle v souboru XML <xref:System.Windows.Forms.TextBox> ovládací prvek

> [!NOTE]
>  Dialogová okna a příkazy nabídky, které vidíte, se může lišit od těch popsaných v nápovědě v závislosti na nastavení active nebo na edici, kterou používáte. Chcete-li změnit nastavení, na **nástroje** nabídce vyberte možnost **nastavení importu a exportu**. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).

## <a name="create-a-new-project"></a>Vytvoření nového projektu
 V tomto kroku vytvoříte projekt jazyka Visual Basic a Visual C#, který obsahuje tento návod.

#### <a name="to-create-the-new-windows-project"></a>Vytvoření nového projektu Windows

1. V sadě Visual Studio na **soubor** nabídce vyberte možnost **nový**, **projektu...** .

2. Rozbalte **Visual C#** nebo **jazyka Visual Basic** klikněte v levém podokně, pak vyberte **Windows Classic Desktop**.

3. V prostředním podokně, vyberte **aplikace pro Windows Forms** typ projektu.

4. Název projektu **ReadingXML**a potom zvolte **OK**.

     **ReadingXML** je vytvořen a přidán do projektu **Průzkumníku řešení**.

## <a name="generate-the-xml-file-to-be-read-into-the-dataset"></a>Generování souboru XML načte do datové sady
 Vzhledem k tomu, že Tento názorný postup se zaměřuje na čtení dat XML do datové sady, je k dispozici obsah souboru XML.

#### <a name="to-create-the-xml-file-that-will-be-read-into-the-dataset"></a>K vytvoření souboru XML, který bude načten do datové sady

1.  Na **projektu** nabídce vyberte možnost **přidat novou položku**.

2.  Vyberte **souboru XML**, název souboru `authors.xml`a potom vyberte **přidat**.

     Soubor XML načte do návrháře a je připravený pro úpravy.

3.  Vložte následující kód do editoru níže deklarace XML:

    ```xml
    <Authors_Table>
      <authors>
        <au_id>172-32-1176</au_id>
        <au_lname>White</au_lname>
        <au_fname>Johnson</au_fname>
        <phone>408 496-7223</phone>
        <address>10932 Bigge Rd.</address>
        <city>Menlo Park</city>
        <state>CA</state>
        <zip>94025</zip>
        <contract>true</contract>
      </authors>
      <authors>
        <au_id>213-46-8915</au_id>
        <au_lname>Green</au_lname>
        <au_fname>Margie</au_fname>
        <phone>415 986-7020</phone>
        <address>309 63rd St. #411</address>
        <city>Oakland</city>
        <state>CA</state>
        <zip>94618</zip>
        <contract>true</contract>
      </authors>
      <authors>
        <au_id>238-95-7766</au_id>
        <au_lname>Carson</au_lname>
        <au_fname>Cheryl</au_fname>
        <phone>415 548-7723</phone>
        <address>589 Darwin Ln.</address>
        <city>Berkeley</city>
        <state>CA</state>
        <zip>94705</zip>
        <contract>true</contract>
      </authors>
      <authors>
        <au_id>267-41-2394</au_id>
        <au_lname>Hunter</au_lname>
        <au_fname>Anne</au_fname>
        <phone>408 286-2428</phone>
        <address>22 Cleveland Av. #14</address>
        <city>San Jose</city>
        <state>CA</state>
        <zip>95128</zip>
        <contract>true</contract>
      </authors>
      <authors>
        <au_id>274-80-9391</au_id>
        <au_lname>Straight</au_lname>
        <au_fname>Dean</au_fname>
        <phone>415 834-2919</phone>
        <address>5420 College Av.</address>
        <city>Oakland</city>
        <state>CA</state>
        <zip>94609</zip>
        <contract>true</contract>
      </authors>
    </Authors_Table>
    ```

4.  Na **soubor** nabídce vyberte možnost **uložit authors.xml**.

## <a name="create-the-user-interface"></a>Vytvoření uživatelského rozhraní
 Uživatelské rozhraní pro tuto aplikaci se skládá z následujících akcí:

-   A <xref:System.Windows.Forms.DataGridView> ovládací prvek, který zobrazí obsah souboru XML jako data.

-   A <xref:System.Windows.Forms.TextBox> ovládací prvek, který zobrazí schéma XML pro soubor XML.

-   Dva <xref:System.Windows.Forms.Button> ovládací prvky.

    -   Jedno tlačítko načte soubor XML do datové sady a zobrazí se v <xref:System.Windows.Forms.DataGridView> ovládacího prvku.

    -   Druhé tlačítko extrahuje schéma z datové sady a prostřednictvím <xref:System.IO.StringWriter> zobrazí ho <xref:System.Windows.Forms.TextBox> ovládací prvek.

#### <a name="to-add-controls-to-the-form"></a>K přidávání ovládacích prvků formuláře

1.  Otevřete `Form1` v zobrazení návrhu.

2.  Z **sada nástrojů**, přetáhněte ovládací prvky na formuláři:

    -   Jeden <xref:System.Windows.Forms.DataGridView> ovládací prvek

    -   Jeden <xref:System.Windows.Forms.TextBox> ovládací prvek

    -   Dva <xref:System.Windows.Forms.Button> ovládací prvky

3.  Nastavte následující vlastnosti:

    |Ovládací prvek|Vlastnost|Nastavení|
    |-------------|--------------|-------------|
    |`TextBox1`|**Víceřádkového výrazu**|`true`|
    ||**Posuvníky**|**Svislý**|
    |`Button1`|**Jméno**|`ReadXmlButton`|
    ||**Text**|`Read XML`|
    |`Button2`|**Jméno**|`ShowSchemaButton`|
    ||**Text**|`Show Schema`|

## <a name="create-the-dataset-that-receives-the-xml-data"></a>Vytvořit datovou sadu, která přijímá XML data
 V tomto kroku vytvoříte novou datovou sadu s názvem `authors`. Další informace o datových sadách najdete v tématu [datové sady nástrojů v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md).

#### <a name="to-create-a-new-dataset-that-receives-the-xml-data"></a>Chcete-li vytvořit novou datovou sadu, která přijímá XML data

1.  V **Průzkumníku řešení**, vyberte zdrojový soubor pro **Form1**a pak vyberte **Návrhář zobrazení** tlačítko **Průzkumníku řešení** panel nástrojů.

2.  Z [sada nástrojů, karta Data](../ide/reference/toolbox-data-tab.md), přetáhněte ji **datovou sadu** na **Form1**.

3.  V **přidat datovou sadu** dialogové okno, vyberte **Netypové datové sady**a potom vyberte **OK**.

     **DataSet1** se přidá do komponent.

4.  V **vlastnosti** nastavte **název** a <xref:System.Data.DataSet.DataSetName%2A> vlastnosti`AuthorsDataSet`.

## <a name="create-the-event-handler-to-read-the-xml-file-into-the-dataset"></a>Vytvoření obslužné rutiny události pro čtení tohoto souboru XML do datové sady
 **XML pro čtení** tlačítko načte soubor XML do datové sady. Potom nastaví vlastnosti pro <xref:System.Windows.Forms.DataGridView> ovládací prvek, který vazby k datové sadě.

#### <a name="to-add-code-to-the-readxmlbuttonclick-event-handler"></a>Přidat kód obslužné rutiny události ReadXmlButton_Click

1.  V **Průzkumníku řešení**, vyberte **Form1**a pak vyberte **Návrhář zobrazení** tlačítko **Průzkumníku řešení** panelu nástrojů.

2.  Vyberte **XML pro čtení** tlačítko.

     **Editor kódu** otevře na `ReadXmlButton_Click` obslužné rutiny události.

3.  Zadejte následující kód do `ReadXmlButton_Click` obslužné rutiny události:

     [!code-csharp[VbRaddataFillingAndExecuting#2](../data-tools/codesnippet/CSharp/read-xml-data-into-a-dataset_1.cs)]
     [!code-vb[VbRaddataFillingAndExecuting#2](../data-tools/codesnippet/VisualBasic/read-xml-data-into-a-dataset_1.vb)]

4.  V `ReadXMLButton_Click` kód obslužné rutiny události, změny `filepath =` položku na správnou cestu.

## <a name="create-the-event-handler-to-display-the-schema-in-the-textbox"></a>Vytvoření obslužné rutiny události pro zobrazení schématu do textového pole
 **Zobrazit schématu** vytvoří tlačítko <xref:System.IO.StringWriter> objekt, který je vyplněn schéma a zobrazí se v <xref:System.Windows.Forms.TextBox>ovládacího prvku.

#### <a name="to-add-code-to-the-showschemabuttonclick-event-handler"></a>Přidat kód obslužné rutiny události ShowSchemaButton_Click

1.  V **Průzkumníku řešení**, vyberte **Form1**a pak vyberte **Návrhář zobrazení** tlačítko.

2.  Vyberte **zobrazit schématu** tlačítko.

     **Editor kódu** otevře na `ShowSchemaButton_Click` obslužné rutiny události.

3.  Zadejte následující kód do `ShowSchemaButton_Click` obslužné rutiny události.

     [!code-csharp[VbRaddataFillingAndExecuting#3](../data-tools/codesnippet/CSharp/read-xml-data-into-a-dataset_2.cs)]
     [!code-vb[VbRaddataFillingAndExecuting#3](../data-tools/codesnippet/VisualBasic/read-xml-data-into-a-dataset_2.vb)]

## <a name="test-the-form"></a>Testování formuláře
 Nyní můžete otestovat formuláře a ujistěte se, že se chová podle očekávání.

#### <a name="to-test-the-form"></a>Postup testování formuláře

1.  Vyberte **F5** ke spuštění aplikace.

2.  Vyberte **XML pro čtení** tlačítko.

     Ovládací prvek DataGridView zobrazí obsah souboru XML.

3.  Vyberte **zobrazit schématu** tlačítko.

     V textovém poli zobrazí schéma XML pro soubor XML.

## <a name="next-steps"></a>Další kroky
 Tento názorný postup se dozvíte, jaké základní informace o čtení souboru XML do datové sady, jakož i vytváření schématu na základě obsahu souboru XML. Zde jsou některé úlohy, které můžete využít, dále:

-   Úpravy dat v datové sadě a zápis zpátky formátu XML. Další informace naleznete v tématu <xref:System.Data.DataSet.WriteXml%2A>.

-   Úpravy dat v datové sadě a zapsat je do databáze. Další informace najdete v tématu [ukládání dat](../data-tools/saving-data.md).

## <a name="see-also"></a>Viz také

- [Přístup k datům v sadě Visual Studio](../data-tools/accessing-data-in-visual-studio.md)
- [Nástroje XML v sadě Visual Studio](../xml-tools/xml-tools-in-visual-studio.md)