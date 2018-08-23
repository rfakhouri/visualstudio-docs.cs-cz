---
title: Ověření dokumentu XML | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: abb353bd-6c4a-4978-b03b-a8c245bbfb55
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 990aceabc2fa5fa38ea6902eec9de39da7cb9eff
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669639"
---
# <a name="xml-document-validation"></a>Ověření dokumentu XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [ověření dokumentu XML](https://docs.microsoft.com/visualstudio/xml-tools/xml-document-validation).  
  
  
XML Editor ověří syntaxi XML 1.0 a také provádí ověření dat při psaní. V editoru můžete ověřit pomocí definice typu dokumentu (DTD) nebo schéma. Červené podtržení vlnovkou zvýrazněte všechny chyby ve správném formátu XML 1.0. Modré podtržení vlnovkou Zobrazit sémantické chyby podle specifikace DTD nebo schématu ověřování. Každá chyba má přidružený záznam v seznamu chyb. Když pozastavíte ukazatel myši nad podtržení vlnovkou můžete také zobrazit chybová zpráva.  
  
 Při ověřování se používají schémata se nacházejí to provede spárováním odpovídajících `targetNamespace` kompilované schématu s xmlns deklarací elementu. Zkompilovaných schémat jsou načteny z jednoho z následujících umístění, uvedeny v pořadí podle priority:  
  
-   Od zadaný v názvu souboru **schémata** pole v okně Vlastnosti dokumentu.  
  
-   Vložené schéma nebo DTD.  
  
-   Externí specifikaci DTD nebo `xsd:schemaLocation` a `xsd:noNamespaceSchemaLocation` atribut  
  
-   "X-schema" XDR schématu obor názvů služby identifikátoru URI.  
  
 Schémata můžete také najít v následujících umístěních další schéma obsahuje prázdný cílový obor názvů:  
  
-   Jiné okno editoru obsahující schéma.  
  
-   Schéma v aktuálním řešení.  
  
-   Schéma z adresáře mezipaměti schématu.  
  
## <a name="xslt-files"></a>Soubory XSLT  
 Pokud upravujete soubor XSLT, xslt.xsd soubor umístěný v mezipaměti schématu se používá pro ověření. Chyby ověřování se zobrazí jako modré podtržení vlnovkou. Chyby kompilátoru XSLT se zobrazují jako červené podtržení vlnovkou.  
  
## <a name="xml-schema-xsd-files"></a>Soubory XML (XSD) schématu  
 Při úpravách souboru schématu XML, xsdschema.xsd soubor umístěný v mezipaměti schématu se používá pro ověření. Chyby ověřování se zobrazí jako modré podtržení vlnovkou. Chyby při kompilaci jsou také zobrazeny červenou vlnovkou.  
  
## <a name="see-also"></a>Viz také  
 [Editor XML](../xml-tools/xml-editor.md)



