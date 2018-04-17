---
title: 'Postupy: použití Návrhář schématu XML s XML – literály | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: d11803e7-f81a-41a2-a145-ba494a45cc93
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 504b063ccbc9646755891fc0eea3647a5594b213
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-the-xml-schema-designer-with-xml-literals"></a>Postupy: použití Návrhář schématu XML s XML – literály
Toto téma popisuje postup zobrazení schéma spojené s XML literál v projektu jazyka Visual Basic.  
  
### <a name="to-create-a-new-visual-basic-console-application-project"></a>Chcete-li vytvořit nový projekt konzolové aplikace v jazyce Visual Basic  
  
1.  Spuštění sady Visual Studio.  
  
2.  Z **soubor** nabídce vyberte možnost **nový**a potom vyberte **projektu**. **Nový projekt** zobrazí se dialogové okno. Pro **typy projektů**, vyberte **jiné jazyky** a pak vyberte **jazyka Visual Basic**. Pro **šablony**, vyberte konzolové aplikace. Pak zadejte `XMLLiterals` v **název** pole a umístění projektu v **umístění** pole. Click **OK**.  
  
     Vytvoření nového projektu. Projekt XMLLiterals obsahuje jeden jazyka Visual Basic zdrojový soubor, Module1.vb.  
  
### <a name="to-add-an-existing-xsd-file-to-the-project"></a>Chcete-li přidat existující soubor XSD do projektu  
  
1.  Otevřete nový textový soubor v Notepad.Copy schématu XML ukázkový kód z [nákupu pořadí schématu](../xml-tools/sample-xsd-file-simple-schema.md) a vložte jej do souboru.  
  
2.  Uložte soubor v některém umístění s názvem PurchaseOrderSchema.xsd.  
  
3.  V Průzkumníku řešení klikněte pravým tlačítkem na název projektu, vyberte **přidat**a potom vyberte **existující položka...** . **AddExisting položky** zobrazí se dialogové okno. Vyhledejte soubor PurchaseOrderSchema.xsd, vyberte ho a pak klikněte na tlačítko **přidat**.  
  
     Projekt XMLLiterals teď obsahuje dva soubory: Module1.vb a PurchaseOrderSchema.xsd.  
  
### <a name="to-add-visual-basic-code-with-an-xml-literal-based-on-the-xsd-file-included-in-the-project"></a>Chcete-li přidat kód jazyka Visual Basic s XML literálu, založené na souboru XSD zahrnutý v projektu  
  
1.  Nahraďte kód v souboru Module1.vb následujícím kódem:  
  
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
  
     Průzkumník schématu XML se zobrazí node souběžně s soubor jazyka Visual Basic, který má XML literálu assotiated se schématem XML nastavit.