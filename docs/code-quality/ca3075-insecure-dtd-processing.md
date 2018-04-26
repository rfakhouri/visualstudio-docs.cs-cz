---
title: 'CA3075: Zpracování nezabezpečené DTD'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: 65798d66-7a30-4359-b064-61a8660c1eed
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 821a2a3f50f94808482d50a8e1e36feefb184173
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca3075-insecure-dtd-processing"></a>CA3075: Zpracování nezabezpečené DTD
|||
|-|-|
|TypeName|InsecureDTDProcessing|
|CheckId|CA3075|
|Kategorie|Microsoft.Security|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Pokud používáte nezabezpečené <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> instance nebo odkaz na externí entity zdroje, analyzátor může přijímat nedůvěryhodná pro vstup a prozrazeny citlivé informace útočníci.

## <a name="rule-description"></a>Popis pravidla
 A *dokumentu typ definice (DTD)* je jedním ze dvou způsobů analyzátor jazyka XML můžete určit platnost dokumentu, podle definice [World Wide Web Consortium (W3C) Extensible Markup Language (XML) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/). Toto pravidlo bude hledat vlastnosti a instance, kde je nedůvěryhodné data přijatá varování před vývojáře o potenciální [zpřístupnění informací](/dotnet/framework/wcf/feature-details/information-disclosure) hrozeb, které mohou vést k [útok na dostupnost služby (DoS)](/dotnet/framework/wcf/feature-details/denial-of-service) útoky. Toto pravidlo aktivuje, když:

-   Je zapnuta DtdProcessing <xref:System.Xml.XmlReader> instance, který se přeloží externí entity XML pomocí <xref:System.Xml.XmlUrlResolver>.

-   <xref:System.Xml.XmlNode.InnerXml%2A> Nastavena v souboru XML.

-   <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> je nastavena na analýzy.

-   Nedůvěryhodná vstup zpracována pomocí <xref:System.Xml.XmlResolver> místo <xref:System.Xml.XmlSecureResolver> .

-   Objekt XmlReader.<xref:System.Xml.XmlReader.Create%2A> Metoda je volána s nezabezpečené <xref:System.Xml.XmlReaderSettings> instance nebo žádné na všechny.

-   <xref:System.Xml.XmlReader> je vytvořen s nezabezpečené výchozí nastavení nebo hodnoty.

 V každé z těchto případech je výsledek stejný: obsah z buď systému nebo síťové sdílené složky souborů z počítače, kde je soubor XML zpracování zveřejní útočníkovi, které pak mohou být použity jako DoS vektoru.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

-   Catch – a zpracovat všechny výjimky XmlTextReader správně, aby se zabránilo cesta zpřístupnění informací.

-   Použití <xref:System.Xml.XmlSecureResolver> omezit prostředky, které XmlTextReader přístup.

-   Nepovolit <xref:System.Xml.XmlReader> otevřete všem externím prostředkům, a to nastavením <xref:System.Xml.XmlResolver> vlastnost **null**.

-   Ujistěte se, že <xref:System.Data.DataViewManager.DataViewSettingCollectionString%2A> vlastnost <xref:System.Data.DataViewManager> je přiřazen z důvěryhodného zdroje.

 Rozhraní .NET 3.5 a starší

-   Zakázat DTD zpracování, pokud chcete pracovat s nedůvěryhodných zdrojů nastavením <xref:System.Xml.XmlReaderSettings.ProhibitDtd%2A> vlastnost **true** .

-   Třídy XmlTextReader má požadavek dědičnosti úplný vztah důvěryhodnosti.

 Rozhraní .NET 4 a novější

-   Nedoporučujeme povolovat DtdProcessing, pokud pracujete s nedůvěryhodných zdrojů, a to nastavením <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A?displayProperty=nameWithType> vlastnost **zakázat** nebo **Ignorovat**.

-   Ujistěte se, že metoda Load() přijímá instanci XmlReader ve všech případech InnerXml.

> [!NOTE]
>  Toto pravidlo může vykazovat některé platná instancí XmlSecureResolver falešně pozitivních zjištění. Pracujeme na řešení tohoto problému tím mid 2016.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pokud si nejste jisti, že vstup se označuje jako z důvěryhodného zdroje, není potlačit pravidlo z toto upozornění.

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
    XmlTextReader reader = new XmlTextReader(sreader) { DtdProcessing = DtdProcessing.Prohibit };
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
            XmlTextReader reader = new XmlTextReader(stream) { DtdProcessing = DtdProcessing.Prohibit } ;
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
            XmlTextReader reader = new XmlTextReader(path) { DtdProcessing = DtdProcessing.Prohibit };
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
    public class TestClass
    {
        public void TestMethod(string path)
        {
            XmlReaderSettings settings = new XmlReaderSettings(){ DtdProcessing = DtdProcessing.Parse };
            XmlReader reader = XmlReader.Create(path, settings); // warn
        }
    }
}
```

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
            XmlReaderSettings settings = new XmlReaderSettings(){ DtdProcessing = DtdProcessing.Prohibit };
            XmlReader reader = XmlReader.Create(path, settings);
        }
    }
}
```