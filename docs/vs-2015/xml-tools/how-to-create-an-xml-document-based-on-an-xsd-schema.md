---
title: 'Postupy: Vytvoření dokumentu XML na základě schématu XSD | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 193b195f-e918-4c79-a1a1-8096a1433bde
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 70b42db031c200f16a9189c4d750c9011e739029
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59647568"
---
# <a name="how-to-create-an-xml-document-based-on-an-xsd-schema"></a>Postupy: Vytvoření dokumentu XML na základě schématu XSD
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**Generovat ukázkové XML** funkce generuje ukázkový soubor XML na základě souboru schématu XML (XSD).  
  
 Tuto možnost můžete použít v následujících scénářích:  
  
- Abyste pochopili použití různých konstrukcí ve schématu.  
  
- Potvrďte, že schéma co dělá jeho účelem je provádět.  
  
  **Generovat ukázkové XML** funkce je dostupná pouze na globální prvky a vyžaduje platnou sadu schémat XML.  
  
  Tato funkce generuje obvykle platný dokumentů XML. Nicméně pokud schéma obsahuje jeden nebo více z následujících akcí, ukázka nemusí být platné:  
  
- `xs:key`, `xs:keyref`, A `xs:unique` omezení identity.  
  
- `xs:pattern` omezující vlastnosti.  
  
- Výčty `xs:QName` typu.  
  
- `xs:ENTITY`, `xs:ENTITIES`, a `xs:NOTATION` typy.  
  
  Všimněte si také, že `xs:base64Binary` obsah se bude generovat jenom v případě, že dojde k vyčíslení ve schématu pro daný typ.  
  
### <a name="to-generate-an-xml-instance-document-based-on-the-xsd-file"></a>Generovat dokument XML instance na základě souboru XSD  
  
1.  Postupujte podle kroků v [jak: Vytvoření a úprava souboru schématu XSD](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).  
  
2.  V [Průzkumníka schémat XML](../xml-tools/xml-schema-explorer.md), klikněte pravým tlačítkem myši `PurchaseOrder` globální element. Vyberte **generovat ukázkový soubor XML**.  
  
     Když vyberete tuto možnost, soubor PurchaseOrder.xml s následujícím obsahem XML ukázky vygenerování a otevřít v editoru XML:  
  
    ```  
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
