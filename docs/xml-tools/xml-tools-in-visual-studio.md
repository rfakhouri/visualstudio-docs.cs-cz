---
title: "Nástroje XML v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vb.xmldesigner
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
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3786e74f9913400e7a95d962c8512d2263d6ae39
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="xml-tools-in-visual-studio"></a>Nástroje XML v sadě Visual Studio
*Jazyk XML (Extensible Markup)* je značka jazyk, který poskytuje formát pro popisující data. To zajišťuje přesnější deklarace výsledků vyhledávání a užitečnější napříč různými platformami. Kromě toho XML umožňuje oddělení prezentace z data. Například ve formátu HTML je použití značek ke prohlížeč zobrazit data jako tučné a kurzíva; v XML použijete jenom k popisu dat, jako název města, teploty a barometrický tlak značky. V XML vytvoříte pomocí šablony stylů například šablony stylů XSL (Extensible Language) a kaskádových stylů (CSS) pro data k dispozici v prohlížeči. XML odděluje data od prezentaci a proces. To umožňuje zobrazit a zpracovat data, protože chcete, s použitím různých šablony stylů a aplikace.  
  
 XML je podmnožinou SGML, která je optimalizovaná pro doručení přes Web. Definuje ho World Wide Web Consortium (W3C). Tato standardizace zaručuje, že strukturovaných dat bude jednotné a nezávislé aplikací nebo dodavatele.  
  
 XML je základem mnoha funkcí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Následující téma seznam názvů nástroje a funkce související s XML, které jsou nabízena v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
 Další informace najdete v tématu [XML Developer Center](http://go.microsoft.com/fwlink/?LinkID=100176), který poskytuje nejnovější dokumentace, technické informace, soubory ke stažení, diskusní skupiny a další prostředky pro vývojáře XML.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Práce s daty XML](../xml-tools/working-with-xml-data.md)  
 Popisuje role XML ve způsobu, jakým se zpracují data v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 [Ladění XSLT](../xml-tools/debugging-xslt.md)  
 Obsahuje odkazy na témata týkající se používání ladicího programu sady Visual Studio k ladění XSLT.  
  
## <a name="reference"></a>Odkaz  
 [Microsoft.VisualStudio.XmlEditor](http://go.microsoft.com/fwlink/?LinkID=165699)  
 Zpřístupní [editoru XML](http://go.microsoft.com/fwlink/?LinkId=228249) strom prostřednictvím analýzy [System.Xml.Linq](http://go.microsoft.com/fwlink/?LinkId=228250) pro všechny dokumenty XML.  
  
 [Referenční dokumentace XML standardy](http://msdn.microsoft.com/en-us/79c78508-c9d0-423a-a00f-672e855de401)  
 Poskytuje informace o technologiích, XML, včetně XML, dokumentu typ definice (DTD), jazyk definice schématu XML (XSD) a XSLT.  
  
 <xref:System.Xml?displayProperty=fullName>  
 Popisuje třídy a další prvky, které tvoří <xref:System.Xml> obor názvů a poskytuje odkazy na podrobnější informace o každé položce.  
  
 <xref:System.Xml.Serialization?displayProperty=fullName>  
 Popisuje třídy a další prvky, které tvoří <xref:System.Xml.Serialization> obor názvů a poskytuje odkazy na podrobnější informace o jednotlivých položkách.  
  
## <a name="related-sections"></a>Související oddíly  
 [XML Document Object Model (DOM).](/dotnet/standard/data/xml/xml-document-object-model-dom)  
 Popisuje, jak <xref:System.Xml.XmlDocument> a její související třídy dodržovat W3C Document Object Model (základní) úroveň 1 a 2 úrovni oboru názvů podporu specifikace.  
  
 [Načítání kódu XML s XmlReader](http://msdn.microsoft.com/en-us/3029834c-a27e-4331-b7aa-711924062182)  
 Popisuje, jak <xref:System.Xml.XmlReader> poskytuje mapovaný, předat dál pouze, jen pro čtení přístup k datům XML přes datový proud XML.  
  
 [Psaní kódu XML pomocí funkce XmlWriter](http://msdn.microsoft.com/en-us/ea41f72c-e1d3-4e0a-ab0f-f0eb1c27ab86)  
 Popisuje, jak <xref:System.Xml.XmlWriter> poskytuje mapovaný, předávat jenom, způsob generování datové proudy XML a pomáhá vytvářet dokumenty XML, které jsou v souladu se standardem W3C.  
  
 [Transformace XSLT](/dotnet/standard/data/xml/xslt-transformations)  
 Popisuje, jak <xref:System.Xml.Xsl.XslCompiledTransform> třída implementuje doporučení XSLT 1.0.  
  
 [Zpracování kódu XML dat pomocí jazyka XPath datový Model](/dotnet/standard/data/xml/process-xml-data-using-the-xpath-data-model)  
 Popisuje, jak <xref:System.Xml.XPath.XPathNavigator> třída může zpracovat data XML uložené v <xref:System.Xml.XPath.XPathDocument> nebo <xref:System.Xml.XmlDocument> objektu. <xref:System.Xml.XPath.XPathNavigator> Třídy je založena na XQuery 1.0 a XPath 2.0 datový Model a slouží k přejděte a upravit XML data.  
  
 [Objektový Model schématu XML (SOM)](/dotnet/standard/data/xml/xml-schema-object-model-som)  
 Popisuje třídy používané pro vytváření a manipulace s nimi schémat XML, tím, že poskytuje <xref:System.Xml.Schema.XmlSchema> třídy se načíst a upravit schéma.