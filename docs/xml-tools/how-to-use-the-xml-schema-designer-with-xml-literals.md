---
title: 'Postupy: Používání Návrháře schémat XML s literály XML'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d11803e7-f81a-41a2-a145-ba494a45cc93
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: bb3daab1196e151a4fea57ae120b2ec280e2e23a
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "58070214"
---
# <a name="how-to-use-the-xml-schema-designer-with-xml-literals"></a>Postupy: Používání Návrháře schémat XML s literály XML

Toto téma popisuje postup zobrazení schématu přidružené k literálu v projektu jazyka Visual Basic XML.

## <a name="create-a-new-visual-basic-project"></a>Vytvoření nového projektu jazyka Visual Basic

1.  Otevřít Visual Studio.

2. Vytvořit nový jazyka Visual Basic **konzolovou aplikaci** projekt s názvem **XMLLiterals**.

     Nový projekt obsahuje jeden zdrojový soubor jazyka Visual Basic, *Module1.vb*.

## <a name="add-an-existing-xsd-file"></a>Přidání stávajícího souboru XSD

1.  Otevřete nový textový soubor v poznámkovém bloku. Zkopírujte ukázkový kód XML schéma z [nákupní pořadí schématu](../xml-tools/sample-xsd-file-simple-schema.md) a vložte ji do souboru.

2.  Uložte soubor do umístění s názvem *PurchaseOrderSchema.xsd*.

3.  V **Průzkumníka řešení**, klikněte pravým tlačítkem na název projektu, vyberte **přidat**a pak vyberte **existující položku**. **AddExisting položky** zobrazí se dialogové okno. Přejděte *PurchaseOrderSchema.xsd* souboru, vyberte ho a pak klikněte na tlačítko **přidat**.

     Projekt XMLLiterals teď obsahuje dva soubory: *Module1.vb* a *PurchaseOrderSchema.xsd*.

## <a name="add-code"></a>Přidejte kód

Přidání kódu jazyka Visual Basic s XML literál, na základě souboru XSD, které jsou součástí projektu:

1. Nahraďte kód v *Module1.vb* souboru následujícím kódem:

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

2. Klikněte pravým tlačítkem na libovolný uzel XML literál XML nebo import oboru názvů XML a vyberte **zobrazit v Průzkumníkovi schémat**.

   **Průzkumníka schémat XML** se zobrazí vedle souboru jazyka Visual Basic, který má literál XML, které jsou přidružené k sadě schémat XML.