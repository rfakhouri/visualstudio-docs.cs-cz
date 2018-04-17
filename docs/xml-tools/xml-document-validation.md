---
title: Ověření XML dokumentu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: abb353bd-6c4a-4978-b03b-a8c245bbfb55
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e226590b31a7b6b96755199bdb93cd95d438f08
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="xml-document-validation"></a>Ověření dokumentu XML
Editor souborů XML kontroluje syntaxe XML 1.0 a také provádí ověřování dat během psaní. Editor můžete ověřit pomocí definice typu dokumentu (DTD) nebo schéma. Červené podtržení vlnovkou zvýrazněte všechny chyby ve správném formátu XML 1.0. Modré podtržení vlnovkami Zobrazit sémantické chyby podle ověření DTD nebo schéma. Jednotlivé chyby má související záznam v seznamu chyb. Můžete také zobrazit chybová zpráva ponecháte myši nad vlnovkou.  
  
 Nebyly nalezeny schémata použít ověřování pomocí odpovídajících `targetNamespace` kompilované schématu s xmlns deklaraci elementu. Kompilované schémata jsou načteny z jednoho z následujících umístění, uvedené v pořadí podle priority:  
  
-   Z názvu souboru, který je zadaný v **schémata** pole v okně vlastností dokumentu.  
  
-   Vložené schéma nebo souboru DTD protokolu.  
  
-   Externí DTD nebo `xsd:schemaLocation` a `xsd:noNamespaceSchemaLocation` atribut  
  
-   "X-schema" XDR názvů schématu identifikátoru URI.  
  
Schémata možné také najít v následujících umístěních další schéma má prázdný cílový obor názvů:  
  
-   Další okno editor, který obsahuje schéma.  
  
-   Schéma v aktuálním řešení.  
  
-   Schéma z adresáře mezipaměti schématu.  
  
## <a name="xslt-files"></a>Soubory XSLT  
 Při úpravě soubor XSLT, xslt.xsd soubor nachází v mezipaměti schématu se používá pro ověření. Jako modré podtržení vlnovkami zobrazí chyby ověření. Chyby z kompilátoru XSLT se zobrazí jako červené podtržení vlnovkou.  
  
## <a name="xml-schema-xsd-files"></a>Soubory XML schématu (XSD)  
 Při úpravě souboru schématu XML, soubor xsdschema.xsd umístěný v mezipaměti schématu se používá pro ověření. Jako modré podtržení vlnovkami zobrazí chyby ověření. Red vlnovkou jsou také uvedené chyby kompilace.  
  
## <a name="see-also"></a>Viz také  
 [Editor XML](../xml-tools/xml-editor.md)