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
ms.openlocfilehash: ca39cef1fb4f1bf1114673dd96a91a1ac8e105cc
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919879"
---
# <a name="ca3077-insecure-processing-in-api-design-xml-document-and-xml-text-reader"></a>CA3077: Nezabezpečené zpracování v návrhu rozhraní API, dokumentu XML a čtečce textu XML

|||
|-|-|
|TypeName|InsecureDTDProcessingInAPIDesign|
|CheckId|CA3077|
|Kategorie|Microsoft.Security|
|Narušující změna|Bez přerušení|

## <a name="cause"></a>příčina
Při navrhování rozhraní API odvozeného z XMLDocument a XMLTextReader si zavědomi <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A>.  Použití nezabezpečených instancí DTDProcessing při odkazování na zdroje externích entit nebo jejich překládání na nezabezpečené hodnoty v XML může vést k odhalení informací.

## <a name="rule-description"></a>Popis pravidla
*Definice typu dokumentu (DTD)* je jedním ze dvou způsobů, jak může analyzátor XML určit platnost dokumentu, jak je definováno v [konsorcium World Wide Web (W3C) jazyk XML (Extensible Markup Language) (XML) 1,0](http://www.w3.org/TR/2008/REC-xml-20081126/). Toto pravidlo vyhledává vlastnosti a instance, kde jsou přijímána nedůvěryhodná data, aby upozornila vývojáře na potenciální hrozby [zpřístupnění informací](/dotnet/framework/wcf/feature-details/information-disclosure) , což může vést k útokům DOS [(Denial of Service)](/dotnet/framework/wcf/feature-details/denial-of-service) . Toto pravidlo se aktivuje v těchto případech:

- <xref:System.Xml.XmlDocument>třídy <xref:System.Xml.XmlTextReader> nebo používají výchozí hodnoty překladače pro zpracování DTD.

- Pro odvozené třídy XmlDocument nebo XmlTextReader není definován žádný konstruktor nebo není použita žádná bezpečná hodnota pro <xref:System.Xml.XmlResolver>.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

- Zachyťte a zpracujte všechny výjimky XmlTextReader správně, aby nedocházelo k odhalení informací o cestách.

- Použijte <xref:System.Xml.XmlSecureResolver>místo objekt XmlResolver k omezení prostředků, ke kterým má přístup XmlTextReader přístup.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Pokud si nejste jistí, že je vstup z důvěryhodného zdroje známý, nedoporučujeme z tohoto upozornění pravidlo potlačit.

## <a name="pseudo-code-examples"></a>Příklady kódu pseudo

### <a name="violation"></a>Selhání

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