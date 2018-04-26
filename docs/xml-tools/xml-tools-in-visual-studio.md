---
title: Nástroje XML v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
f1_keywords:
- vb.xmldesigner
helpviewer_keywords:
- XML [Visual Studio], resources
- Enterprise Templates, XML and
- discovery files, XML
- server controls, XML and
- Web server controls, XML
- XSL
- XML [Visual Studio], data sources
- XML schemas
- XML [Visual Studio], SGML relationship to
- CSS, style sheets for XML
- XML [Visual Studio], .NET Framework classes
- data [Visual Studio], XML
- classes [Visual Studio], XML
- style sheets, for XML
- Web services
- SGML, XML
- XML [Visual Studio]
- datasets [Visual Basic], XML Schemas
- XSD schemas
- XSL, style sheets
- XMLDataDocument class
ms.assetid: 1fd5de47-2d61-4180-9539-c2c4bf9ab768
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 279a0a73f24b2916e21293c854692ab40f444b4c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="xml-tools-in-visual-studio"></a>Nástroje XML v sadě Visual Studio

*Jazyk XML (Extensible Markup)* je značka jazyk, který poskytuje formát pro popisující data. To zajišťuje přesnější deklarace výsledků vyhledávání a užitečnější napříč různými platformami. Kromě toho XML umožňuje oddělení prezentace z data. Například ve formátu HTML je použití značek ke prohlížeč zobrazit data jako tučné a kurzíva; v XML použijete jenom k popisu dat, jako název města, teploty a barometrický tlak značky. V XML vytvoříte pomocí šablony stylů například šablony stylů XSL (Extensible Language) a kaskádových stylů (CSS) pro data k dispozici v prohlížeči. XML odděluje data od prezentaci a proces. To umožňuje zobrazit a zpracovat data, protože chcete, s použitím různých šablony stylů a aplikace.

XML je podmnožinou SGML, která je optimalizovaná pro doručení přes Web. Definuje ho World Wide Web Consortium (W3C). Tato standardizace zaručuje, že strukturovaných dat bude jednotné a nezávislé aplikací nebo dodavatele.

XML je základem mnoho funkcí sady Visual Studio a rozhraní .NET Framework. Následující téma seznam názvů nástroje a funkce související s XML, které jsou nabízena v sadě Visual Studio a rozhraní .NET Framework.

Další informace najdete v tématu <xref:System.Xml?displayProperty=fullName> dokumentaci.

## <a name="reference"></a>Odkaz

[Microsoft.VisualStudio.XmlEditor](http://go.microsoft.com/fwlink/?LinkID=165699) zpřístupní [editoru XML](http://go.microsoft.com/fwlink/?LinkId=228249) strom prostřednictvím analýzy [System.Xml.Linq](http://go.microsoft.com/fwlink/?LinkId=228250) pro všechny dokumenty XML.

[Referenční dokumentace XML standardy](http://msdn.microsoft.com/79c78508-c9d0-423a-a00f-672e855de401) poskytuje informace o technologiích, XML, včetně XML, dokumentu typ definice (DTD), jazyk definice schématu XML (XSD) a XSLT.

<xref:System.Xml?displayProperty=fullName> Popisuje třídy a další prvky, které tvoří <xref:System.Xml> obor názvů a poskytuje odkazy na podrobnější informace o každé položce.

<xref:System.Xml.Serialization?displayProperty=fullName> Popisuje třídy a další prvky, které tvoří <xref:System.Xml.Serialization> obor názvů a poskytuje odkazy na podrobnější informace o jednotlivých položkách.

## <a name="related-sections"></a>Související oddíly

[XML modelu DOM (Document Object)](/dotnet/standard/data/xml/xml-document-object-model-dom) popisuje jak <xref:System.Xml.XmlDocument> a její související třídy dodržovat W3C Document Object Model (základní) úroveň 1 a 2 úrovni oboru názvů podporu specifikace.

[Zpracování kódu XML dat s XmlReader a XmlWriter](https://msdn.microsoft.com/library/cc189001(v=vs.95).aspx)

[Transformace XSLT](/dotnet/standard/data/xml/xslt-transformations) popisuje jak <xref:System.Xml.Xsl.XslCompiledTransform> třída implementuje doporučení XSLT 1.0.

[Zpracování kódu XML dat pomocí datového modelu XPath](/dotnet/standard/data/xml/process-xml-data-using-the-xpath-data-model) popisuje jak <xref:System.Xml.XPath.XPathNavigator> třída může zpracovat data XML uložené v <xref:System.Xml.XPath.XPathDocument> nebo <xref:System.Xml.XmlDocument> objektu. <xref:System.Xml.XPath.XPathNavigator> Třídy je založena na XQuery 1.0 a XPath 2.0 datový Model a slouží k přejděte a upravit XML data.

[XML schéma objektu modelu (SOM)](/dotnet/standard/data/xml/xml-schema-object-model-som) popisuje třídy používané pro vytváření a manipulace s nimi schémat XML, tím, že poskytuje <xref:System.Xml.Schema.XmlSchema> třídy se načíst a upravit schéma.