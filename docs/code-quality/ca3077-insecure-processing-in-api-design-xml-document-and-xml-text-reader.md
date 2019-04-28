---
title: 'CA3077: Nezabezpečené zpracování v návrhu rozhraní API, dokumentu XML a čtečce textu XML'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 7f33771b-f3c8-4c02-bef6-f581b623c303
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dd3b17ad3449bebcab57344355f7cc7687ea6b19
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541074"
---
# <a name="ca3077-insecure-processing-in-api-design-xml-document-and-xml-text-reader"></a>CA3077: Nezabezpečené zpracování v návrhu rozhraní API, dokumentu XML a čtečce textu XML

|||
|-|-|
|TypeName|InsecureDTDProcessingInAPIDesign|
|CheckId|CA3077|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina
 Při navrhování rozhraní API odvozený od XMLDocument a XMLTextReader, mějte na paměti z <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A>.  Použití nezabezpečené DTDProcessing instancí, při odkazování na řešení externí entity zdroje nebo nastavení nezabezpečené hodnot v souboru XML může způsobit zpřístupnění informací.

## <a name="rule-description"></a>Popis pravidla
 A *dokumentu typ definice (DTD)* je jedním ze dvou způsobů analyzátor jazyka XML můžete určit platnosti dokumentu, podle definice [World Wide Web Consortium (W3C) značky XML (Extensible Language) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/). Toto pravidlo vyhledá vlastnosti a instance, kde je nedůvěryhodná data přijat upozornit vývojáře o potenciál [informacím](/dotnet/framework/wcf/feature-details/information-disclosure) hrozeb, které mohou vést k [útok na dostupnost služby (DoS)](/dotnet/framework/wcf/feature-details/denial-of-service) útoky. Toto pravidlo aktivuje, když:

- <xref:System.Xml.XmlDocument> nebo <xref:System.Xml.XmlTextReader> třídy použijte výchozí překladač hodnoty pro zpracování deklarace DTD.

- Žádný konstruktor je definován pro dokument XML nebo odvozené třídy XmlTextReader nebo bez zabezpečeného hodnota se používá pro <xref:System.Xml.XmlResolver>.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

- Zachytit a zpracovat všechny výjimky XmlTextReader správně, aby se zabránilo zpřístupnění informací cestu.

- Použití <xref:System.Xml.XmlSecureResolver>místo objekt XmlResolver omezit prostředky XmlTextReader přístup.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pokud si nejste jisti, že vstup je znám jako z důvěryhodného zdroje, nepotlačujte pravidlo z tohoto upozornění.

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