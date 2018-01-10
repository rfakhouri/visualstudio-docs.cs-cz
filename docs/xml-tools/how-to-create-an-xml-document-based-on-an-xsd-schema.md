---
title: "Postupy: vytvoření dokumentu XML na základě schématu XSD | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 193b195f-e918-4c79-a1a1-8096a1433bde
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 63ce40fb765d3aab4cb91ebff8a3552f69d92586
ms.sourcegitcommit: 5f436413bbb1e8aa18231eb5af210e7595401aa6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2018
---
# <a name="how-to-create-an-xml-document-based-on-an-xsd-schema"></a>Postupy: vytvoření dokumentu XML na základě schématu XSD
**Generovat XML ukázka** funkce generuje ukázkový soubor XML založené na souboru schématu XML (XSD).  
  
 Tuto možnost můžete použít pro následující scénáře:  
  
-   Abyste pochopili použití různé konstrukce v schéma.  
  
-   Potvrďte, že schéma nemá co se má provést.  
  
**Generovat XML ukázka** funkce je dostupná pouze na globální elementy a vyžaduje platnou sadu schématu XML.  
  
Tato funkce se obvykle vygeneruje platný dokumentů XML. Ale pokud schéma obsahuje jeden nebo více z následujících, ukázky pravděpodobně není platný:  
  
-   `xs:key`, `xs:keyref`, A `xs:unique` omezení identity.  
  
-   `xs:pattern`omezující vlastnosti.  
  
-   Výčty `xs:QName` typu.  
  
-   `xs:ENTITY`, `xs:ENTITIES`, a `xs:NOTATION` typy.  
  
Rovněž Pamatujte, že `xs:base64Binary` pouze v případě, že dojde k výčty ve schématu pro tento typ se budou generovat obsah.  
  
### <a name="to-generate-an-xml-instance-document-based-on-the-xsd-file"></a>Pro generování dokumentu XML instance na základě souboru XSD  
  
1.  Postupujte podle kroků v [postupy: vytvoření a úprava souboru schématu XSD](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).  
  
2.  V [Explorer schématu XML](../xml-tools/xml-schema-explorer.md), klikněte pravým tlačítkem myši `PurchaseOrder` globálním elementem. Vyberte **generovat ukázka XML**.  
  
     Když vyberete tuto možnost, soubor PurchaseOrder.xml s následujícím obsahem XML Ukázka bude vygenerována a otevřít v editoru XML:  
  
    ```xml
    <?xml version="1.0" encoding="utf-8"?>  
    <PurchaseOrder OrderDate="1900-01-01" xmlns="http://tempuri.org/PurchaseOrderSchema.xsd">  
      <ShipTo country="US">  
        <name>name1</name>  
        <street>street1</street>  
        <city>city1</city>  
        <state>state1</state>  
        <zip>1</zip>  
      </ShipTo>  
      <ShipTo country="US">  
        <name>name2</name>  
        <street>street2</street>  
        <city>city2</city>  
        <state>state2</state>  
        <zip>-79228162514264337593543950335</zip>  
      </ShipTo>  
      <BillTo country="US">  
        <name>name1</name>  
        <street>street1</street>  
        <city>city1</city>  
        <state>state1</state>  
        <zip>1</zip>  
      </BillTo>  
    </PurchaseOrder>  
    ```
  
## <a name="see-also"></a>Viz také  
 [Práce s daty XML](../xml-tools/working-with-xml-data.md)