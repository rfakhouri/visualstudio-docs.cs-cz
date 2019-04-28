---
title: Ověření dokumentu XML v editoru XML
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: abb353bd-6c4a-4978-b03b-a8c245bbfb55
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 59b8ed5c74d998b47ff4a187b420695eab5be035
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62807713"
---
# <a name="xml-document-validation"></a>Ověření dokumentu XML

XML editor ověří syntaxi XML 1.0 a také provádí ověření dat při psaní. V editoru můžete ověřit pomocí definice typu dokumentu (DTD) nebo schéma. Červené podtržení vlnovkou zvýrazněte všechny chyby ve správném formátu XML 1.0. Modré podtržení vlnovkou Zobrazit sémantické chyby podle specifikace DTD nebo schématu ověřování. Každá chyba má přidružený záznam v seznamu chyb. Když pozastavíte ukazatel myši nad podtržení vlnovkou můžete také zobrazit chybová zpráva.

 Při ověřování se používají schémata se nacházejí to provede spárováním odpovídajících `targetNamespace` kompilované schématu s xmlns deklarací elementu. Zkompilovaných schémat jsou načteny z jednoho z následujících umístění, uvedeny v pořadí podle priority:

- Od zadaný v názvu souboru **schémata** pole dokumentu **vlastnosti** okna.

- Vložené schéma nebo DTD.

- Externí specifikaci DTD nebo `xsd:schemaLocation` a `xsd:noNamespaceSchemaLocation` atribut

- "X-schema" XDR schématu obor názvů služby identifikátoru URI.

Schémata můžete také najít v následujících umístěních další schéma obsahuje prázdný cílový obor názvů:

- Jiné okno editoru obsahující schéma.

- Schéma v aktuálním řešení.

- Schéma z adresáře mezipaměti schématu.

## <a name="xslt-files"></a>Soubory XSLT
 Při úpravách souboru XSLT *xslt.xsd* soubor umístěný v mezipaměti schématu se používá k ověření. Chyby ověřování se zobrazí jako modré podtržení vlnovkou. Chyby kompilátoru XSLT se zobrazují jako červené podtržení vlnovkou.

## <a name="xml-schema-xsd-files"></a>Soubory XML (XSD) schématu
 Při úpravách souboru schématu XML *xsdschema.xsd* soubor umístěný v mezipaměti schématu se používá k ověření. Chyby ověřování se zobrazí jako modré podtržení vlnovkou. Chyby při kompilaci jsou také zobrazeny červenou vlnovkou.

## <a name="see-also"></a>Viz také:

- [XML editor](../xml-tools/xml-editor.md)