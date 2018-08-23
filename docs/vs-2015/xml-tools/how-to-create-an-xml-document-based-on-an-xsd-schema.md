---
title: 'Postupy: vytvoření dokumentu XML na základě schématu XSD | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 193b195f-e918-4c79-a1a1-8096a1433bde
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7ce870506097c820d5a6a8e981ffd63d64257780
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627662"
---
# <a name="how-to-create-an-xml-document-based-on-an-xsd-schema"></a>Postupy: vytvoření dokumentu XML na základě schématu XSD
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: vytvoření dokumentu XML založené na schématu XSD](https://docs.microsoft.com/visualstudio/xml-tools/how-to-create-an-xml-document-based-on-an-xsd-schema).  
  
  
**Generovat ukázkové XML** funkce generuje ukázkový soubor XML na základě souboru schématu XML (XSD).  
  
 Tuto možnost můžete použít v následujících scénářích:  
  
-   Abyste pochopili použití různých konstrukcí ve schématu.  
  
-   Potvrďte, že schéma co dělá jeho účelem je provádět.  
  
 **Generovat ukázkové XML** funkce je dostupná pouze na globální prvky a vyžaduje platnou sadu schémat XML.  
  
 Tato funkce generuje obvykle platný dokumentů XML. Nicméně pokud schéma obsahuje jeden nebo více z následujících akcí, ukázka nemusí být platné:  
  
-   `xs:key`, `xs:keyref`, A `xs:unique` omezení identity.  
  
-   `xs:pattern` omezující vlastnosti.  
  
-   Výčty `xs:QName` typu.  
  
-   `xs:ENTITY`, `xs:ENTITIES`, a `xs:NOTATION` typy.  
  
 Všimněte si také, že `xs:base64Binary` obsah se bude generovat jenom v případě, že dojde k vyčíslení ve schématu pro daný typ.  
  
### <a name="to-generate-an-xml-instance-document-based-on-the-xsd-file"></a>Generovat dokument XML instance na základě souboru XSD  
  
1.  Postupujte podle kroků v [postupy: vytvoření a úprava souboru schématu XSD](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).  
  
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



