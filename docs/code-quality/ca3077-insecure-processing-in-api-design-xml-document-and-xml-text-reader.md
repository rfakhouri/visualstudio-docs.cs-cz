---
title: 'CA3077: Nezabezpečené zpracování v návrhu rozhraní API, dokumentu XML a čtečku textu XML'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: 7f33771b-f3c8-4c02-bef6-f581b623c303
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 21c7d4fcf2ec1e16a225879b7feceef2a61a8161
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31918009"
---
# <a name="ca3077-insecure-processing-in-api-design-xml-document-and-xml-text-reader"></a>CA3077: Nezabezpečené zpracování v návrhu rozhraní API, dokumentu XML a čtečku textu XML
|||
|-|-|
|TypeName|InsecureDTDProcessingInAPIDesign|
|CheckId|CA3077|
|Kategorie|Microsoft.Security|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Při navrhování rozhraní API odvozená od třídou XMLDocument nastavenou na a XMLTextReader, mělo pamatovat <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A>.  Pomocí nezabezpečené instancí DTDProcessing při odkazování na externí entity zdroje řešení nebo nastavení nezabezpečené hodnot v souboru XML může způsobit zpřístupnění informací.

## <a name="rule-description"></a>Popis pravidla
 A *dokumentu typ definice (DTD)* je jedním ze dvou způsobů analyzátor jazyka XML můžete určit platnost dokumentu, podle definice [World Wide Web Consortium (W3C) Extensible Markup Language (XML) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/). Toto pravidlo bude hledat vlastnosti a instance, kde je nedůvěryhodné data přijatá varování před vývojáře o potenciální [zpřístupnění informací](/dotnet/framework/wcf/feature-details/information-disclosure) hrozeb, které mohou vést k [útok na dostupnost služby (DoS)](/dotnet/framework/wcf/feature-details/denial-of-service) útoky. Toto pravidlo aktivuje, když:

-   <xref:System.Xml.XmlDocument> nebo <xref:System.Xml.XmlTextReader> třídy použít výchozí překladač hodnoty pro zpracování souboru DTD protokolu.

-   Žádný konstruktor je definována pro dokument XML nebo XmlTextReader odvozených tříd nebo žádná zabezpečené hodnota se používá pro <xref:System.Xml.XmlResolver>.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

-   Catch – a zpracovat všechny výjimky XmlTextReader správně, aby se zabránilo cesta zpřístupnění informací.

-   Použití <xref:System.Xml.XmlSecureResolver>místo objekt XmlResolver omezit přístup XmlTextReader prostředky.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pokud si nejste jisti, že vstup se označuje jako z důvěryhodného zdroje, není potlačit pravidlo z toto upozornění.

## <a name="pseudo-code-examples"></a>Příklady pseudo kódu

### <a name="violation"></a>Porušení

```csharp
using System;
using System.Xml;

namespace TestNamespace
{
    class TestClass : XmlDocument
    {
        public TestClass () {} // warn
    }

    class TestClass2 : XmlTextReader
    {
        public TestClass2() // warn
        {
        }
    }
}
```

### <a name="solution"></a>Řešení

```csharp
using System;
using System.Xml;

namespace TestNamespace
{
    class TestClass : XmlDocument
    {
        public TestClass ()
        {
            XmlResolver = null;
        }
    }

    class TestClass2 : XmlTextReader
    {
        public TestClass2()
        {
               XmlResolver = null;
        }
    }
}
```