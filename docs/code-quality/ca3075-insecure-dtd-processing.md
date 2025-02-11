---
title: 'CA3075: Zpracování nezabezpečené specifikace DTD'
ms.date: 03/18/2019
ms.topic: reference
ms.assetid: 65798d66-7a30-4359-b064-61a8660c1eed
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6de817e3aaecbdd1c89cc2174e91126ea39d99d7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541113"
---
# <a name="ca3075-insecure-dtd-processing"></a>CA3075: Zpracování nezabezpečené specifikace DTD

|||
|-|-|
|TypeName|InsecureDTDProcessing|
|CheckId|CA3075|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Pokud používáte nezabezpečené <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> instance nebo odkaz na externí entity zdroje, analyzátor může přijmout nedůvěryhodné vstupní tak zveřejnit citlivé informace, které útočníci.

## <a name="rule-description"></a>Popis pravidla

A *dokumentu typ definice (DTD)* je jedním ze dvou způsobů analyzátor jazyka XML můžete určit platnosti dokumentu, podle definice [World Wide Web Consortium (W3C) značky XML (Extensible Language) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/). Toto pravidlo vyhledá vlastnosti a instance, kde je nedůvěryhodná data přijat upozornit vývojáře o potenciál [informacím](/dotnet/framework/wcf/feature-details/information-disclosure) hrozby nebo [útok na dostupnost služby (DoS)](/dotnet/framework/wcf/feature-details/denial-of-service) útoky. Toto pravidlo aktivuje, když:

- Je zapnutá DtdProcessing <xref:System.Xml.XmlReader> instanci, která přeloží externí entity XML pomocí <xref:System.Xml.XmlUrlResolver>.

- <xref:System.Xml.XmlNode.InnerXml%2A> Nastavenou v souboru XML.

- <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> je nastavena na analýzy.

- Nedůvěryhodný vstup zpracována pomocí <xref:System.Xml.XmlResolver> místo <xref:System.Xml.XmlSecureResolver>.

- <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType> Metoda je volána s nezabezpečené <xref:System.Xml.XmlReaderSettings> instance nebo vůbec žádné instance.

- <xref:System.Xml.XmlReader> je vytvořen s nezabezpečené výchozí nastavení nebo hodnoty.

Ve všech těchto případech je výsledek stejný: obsah buď soubor systému nebo síťových sdílených složek z počítače, kde je zpracování souboru XML se zveřejní pro útočníka nebo zpracování DTD může sloužit jako vektor DoS.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

- Zachytit a zpracovat všechny výjimky XmlTextReader správně, aby se zabránilo zpřístupnění informací cestu.

- Použití <xref:System.Xml.XmlSecureResolver> omezit prostředky, ke kterým přístup XmlTextReader.

- Nejsou povoleny <xref:System.Xml.XmlReader> otevřete všem externím prostředkům tak, že nastavíte <xref:System.Xml.XmlResolver> vlastnost **null**.

- Ujistěte se, <xref:System.Data.DataViewManager.DataViewSettingCollectionString%2A?displayProperty=nameWithType> je vlastnosti přiřazen z důvěryhodného zdroje.

**Rozhraní .NET 3.5 a starší**

- Zakázat zpracování DTD, pokud pracujete se sekvenčním nedůvěryhodných zdrojů tak, že nastavíte <xref:System.Xml.XmlReaderSettings.ProhibitDtd%2A> vlastnost **true**.

- Pomocí třídy XmlTextReader má vyžádané dědičnosti úplný vztah důvěryhodnosti.

**Rozhraní .NET 4 a novější**

- Nedoporučujeme povolovat DtdProcessing, pokud pracujete s nedůvěryhodných zdrojů tak, že nastavíte <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A?displayProperty=nameWithType> vlastnost **zakázat** nebo **Ignorovat**.

- Zajistěte, aby metoda Load() XmlReader instance ve všech případech InnerXml.

> [!NOTE]
> Toto pravidlo může vykazovat některé platné instance XmlSecureResolver počet falešně pozitivních výsledků.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud si nejste jisti, že vstup je znám jako z důvěryhodného zdroje, nepotlačujte pravidlo z tohoto upozornění.

## <a name="pseudo-code-examples"></a>Příklady pseudo kódu

### <a name="violation"></a>Porušení

```csharp
using System.IO;
using System.Xml.Schema;

class TestClass
{
    public XmlSchema Test
    {
        get
        {
            var src = "";
            TextReader tr = new StreamReader(src);
            XmlSchema schema = XmlSchema.Read(tr, null); // warn
            return schema;
        }
    }
}
```

### <a name="solution"></a>Řešení

```csharp
using System.IO;
using System.Xml;
using System.Xml.Schema;

class TestClass
{
    public XmlSchema Test
    {
        get
        {
            var src = "";
            TextReader tr = new StreamReader(src);
            XmlTextReader reader = new XmlTextReader(tr) { DtdProcessing = DtdProcessing.Prohibit };
            XmlSchema schema = XmlSchema.Read(reader , null);
            return schema;
        }
    }
}
```

### <a name="violation"></a>Porušení

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public XmlReaderSettings settings = new XmlReaderSettings();
        public void TestMethod(string path)
        {
            var reader = XmlReader.Create(path, settings);  // warn
        }
    }
}
```

### <a name="solution"></a>Řešení

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public XmlReaderSettings settings = new XmlReaderSettings()
        {
            DtdProcessing = DtdProcessing.Prohibit
        };

        public void TestMethod(string path)
        {
            var reader = XmlReader.Create(path, settings);
        }
    }
}
```

### <a name="violations"></a>Porušení

```csharp
using System.Xml;

namespace TestNamespace
{
    public class DoNotUseSetInnerXml
    {
        public void TestMethod(string xml)
        {
            XmlDocument doc = new XmlDocument() { XmlResolver = null };
            doc.InnerXml = xml; // warn
        }
    }
}
```

```csharp
using System.Xml;

namespace TestNamespace
{
    public class DoNotUseLoadXml
    {
        public void TestMethod(string xml)
        {
            XmlDocument doc = new XmlDocument(){ XmlResolver = null };
            doc.LoadXml(xml); // warn
        }
    }
}
```

### <a name="solution"></a>Řešení

```csharp
using System.Xml;

public static void TestMethod(string xml)
{
    XmlDocument doc = new XmlDocument() { XmlResolver = null };
    System.IO.StringReader sreader = new System.IO.StringReader(xml);
    XmlReader reader = XmlReader.Create(sreader, new XmlReaderSettings() { XmlResolver = null });
    doc.Load(reader);
}
```

### <a name="violation"></a>Porušení

```csharp
using System.IO;
using System.Xml;
using System.Xml.Serialization;

namespace TestNamespace
{
    public class UseXmlReaderForDeserialize
    {
        public void TestMethod(Stream stream)
        {
            XmlSerializer serializer = new XmlSerializer(typeof(UseXmlReaderForDeserialize));
            serializer.Deserialize(stream); // warn
        }
    }
}
```

### <a name="solution"></a>Řešení

```csharp
using System.IO;
using System.Xml;
using System.Xml.Serialization;

namespace TestNamespace
{
    public class UseXmlReaderForDeserialize
    {
        public void TestMethod(Stream stream)
        {
            XmlSerializer serializer = new XmlSerializer(typeof(UseXmlReaderForDeserialize));
            XmlReader reader = XmlReader.Create(stream, new XmlReaderSettings() { XmlResolver = null });
            serializer.Deserialize(reader );
        }
    }
}
```

### <a name="violation"></a>Porušení

```csharp
using System.Xml;
using System.Xml.XPath;

namespace TestNamespace
{
    public class UseXmlReaderForXPathDocument
    {
        public void TestMethod(string path)
        {
            XPathDocument doc = new XPathDocument(path); // warn
        }
    }
}
```

### <a name="solution"></a>Řešení

```csharp
using System.Xml;
using System.Xml.XPath;

namespace TestNamespace
{
    public class UseXmlReaderForXPathDocument
    {
        public void TestMethod(string path)
        {
            XmlReader reader = XmlReader.Create(path, new XmlReaderSettings() { XmlResolver = null });
            XPathDocument doc = new XPathDocument(reader);
        }
    }
}
```

### <a name="violation"></a>Porušení

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        public XmlDocument doc = new XmlDocument() { XmlResolver = new XmlUrlResolver() };
    }
}
```

### <a name="solution"></a>Řešení

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        public XmlDocument doc = new XmlDocument() { XmlResolver = null }; // or set to a XmlSecureResolver instance
    }
}
```

### <a name="violations"></a>Porušení

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod()
        {
            var reader = XmlTextReader.Create(""doc.xml""); //warn
        }
    }
}
```

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public void TestMethod(string path)
        {
            try {
                XmlTextReader reader = new XmlTextReader(path); // warn
            }
            catch { throw ; }
            finally {}
        }
    }
}
```

### <a name="solution"></a>Řešení

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public void TestMethod(string path)
        {
            XmlReaderSettings settings = new XmlReaderSettings() { XmlResolver = null };
            XmlReader reader = XmlReader.Create(path, settings);
        }
    }
}
```
