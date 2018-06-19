---
title: 'Postupy: použití Návrhář schématu XML s XML – literály'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: d11803e7-f81a-41a2-a145-ba494a45cc93
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 589bfa54a0ba1a7efb2964cf5b74446ca9ffe10d
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2018
ms.locfileid: "34548197"
---
# <a name="how-to-use-the-xml-schema-designer-with-xml-literals"></a>Postupy: použití Návrhář schématu XML s XML – literály

Toto téma popisuje postup zobrazení schéma spojené s XML literál v projektu jazyka Visual Basic.

## <a name="to-create-a-new-visual-basic-console-application-project"></a>Chcete-li vytvořit nový projekt konzolové aplikace v jazyce Visual Basic

1.  Spuštění sady Visual Studio.

2.  Z **soubor** nabídce vyberte možnost **nový**a potom vyberte **projektu**. **Nový projekt** zobrazí se dialogové okno. Pro **typy projektů**, vyberte **jiné jazyky** a pak vyberte **jazyka Visual Basic**. Pro **šablony**, vyberte konzolové aplikace. Pak zadejte `XMLLiterals` v **název** pole a umístění projektu v **umístění** pole. Click **OK**.

     Vytvoření nového projektu. Projekt XMLLiterals obsahuje jeden zdrojový soubor jazyka Visual Basic, *Module1.vb*.

## <a name="to-add-an-existing-xsd-file-to-the-project"></a>Chcete-li přidat existující soubor XSD do projektu

1.  Nový textový soubor otevřete v poznámkovém bloku. Zkopírujte schématu XML ukázkový kód z [zakoupit pořadí schématu](../xml-tools/sample-xsd-file-simple-schema.md) a vložte jej do souboru.

2.  Uložte soubor v některém umístění s názvem *PurchaseOrderSchema.xsd*.

3.  V Průzkumníku řešení klikněte pravým tlačítkem na název projektu, vyberte **přidat**a potom vyberte **existující položka**. **AddExisting položky** zobrazí se dialogové okno. Vyhledejte *PurchaseOrderSchema.xsd* souboru, vyberte ho a pak klikněte na tlačítko **přidat**.

     Projekt XMLLiterals teď obsahuje dva soubory: *Module1.vb* a *PurchaseOrderSchema.xsd*.

## <a name="to-add-visual-basic-code-with-an-xml-literal-based-on-the-xsd-file-included-in-the-project"></a>Chcete-li přidat kód jazyka Visual Basic s XML literálu, založené na souboru XSD zahrnutý v projektu

1.  Nahraďte kód v *Module1.vb* soubor s následujícím kódem:

   ```vb
   Imports <xmlns:ns="http://tempuri.org/PurchaseOrderSchema.xsd">

   Module Module1
       Sub Main()

           Dim XMLLiteral = <ns:PurchaseOrder OrderDate="1900-01-01">
                                <ns:ShipTo country="US">
                                    <ns:name>name1</ns:name>
                                    <ns:street>street1</ns:street>
                                    <ns:city>city1</ns:city>
                                    <ns:state>state1</ns:state>
                                    <ns:zip>1</ns:zip>
                                </ns:ShipTo>
                                <ns:BillTo country="US">
                                    <ns:name>name1</ns:name>
                                    <ns:street>street1</ns:street>
                                    <ns:city>city1</ns:city>
                                    <ns:state>state1</ns:state>
                                    <ns:zip>1</ns:zip>
                                </ns:BillTo>
                            </ns:PurchaseOrder>

       End Sub
   End Module
   ```

2.  Klikněte pravým tlačítkem na libovolný uzel XML ve literál XML nebo importu obor názvů XML a vyberte **zobrazit v Průzkumníku schématu**.

     **Explorer schématu XML** se zobrazí node souběžně s soubor jazyka Visual Basic, který má literál XML, které jsou přidružené k sadě schématu XML.