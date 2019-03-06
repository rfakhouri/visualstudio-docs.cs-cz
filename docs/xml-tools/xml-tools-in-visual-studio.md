---
title: XML editor a Návrhář schémat
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a8854aee047fa961c4f0973397cfc2fe6ac6e6ad
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57526565"
---
# <a name="xml-tools-in-visual-studio"></a>Nástroje XML v sadě Visual Studio

*Kód XML (Extensible Language)* je značkovací jazyk, který poskytuje formátu pro popis data. Rozděluje data XML a jeho prezentaci pomocí přidružené šablony stylů, jako je šablona stylů XSL (Extensible Language) a šablony stylů CSS (CSS). Visual Studio obsahuje nástroje a funkce, které usnadňují práci s XML, XSLT a XML schémat.

## <a name="xml-editor"></a>XML editor

[Editoru XML](xml-editor.md) slouží k úpravám dokumentů XML. Poskytuje úplnou syntaxi XML kontrole, ověření schématu při psaní, barevného kódování a technologie IntelliSense. Pokud je k dispozici definici typu schématu nebo dokumentu, se používá technologie IntelliSense do seznamu povolených elementů a atributů.

Další funkce zahrnují:

- Podpora fragmentů kódu XML, včetně generované schématu fragmentů kódu

- Zdokumentujte sbalování tak, aby elementy můžete rozbalení a sbalení

- Možnost provedení transformace XSLT a zobrazit výsledky jako text, XML nebo HTML

- Možnost generování schémat schématu XML definice jazyk (XSD) z instance dokumentu XML

- Podpora pro úpravy šablon stylů XSLT, včetně podporu technologie IntelliSense

- Průzkumník schémat XML

## <a name="xml-schema-designer"></a>Návrhář schématu XML

[Návrhář schémat XML](xml-schema-designer.md) je integrovaná s Visual Studio a editor souborů XML umožňují pracovat s schémat jazyk (XSD) definice schématu XML.

## <a name="xslt-debugging"></a>Ladění XSLT

Visual Studio podporuje [ladění šablon stylů XSLT](../xml-tools/debugging-xslt.md). Pomocí ladicího programu, můžete nastavit body přerušení v šabloně stylů XSLT, krokování s vnořením do šablony stylů XSLT z kódu a tak dále.

> [!NOTE]
> Ladicí program XSLT je dostupná pouze v edici Enterprise systému Visual Studio.

## <a name="see-also"></a>Viz také:

- <xref:System.Xml?displayProperty=fullName>
- [Transformace XSLT](/dotnet/standard/data/xml/xslt-transformations)
- [Zpracování dat XML pomocí modelu dat XPath](/dotnet/standard/data/xml/process-xml-data-using-the-xpath-data-model)
- [Model DOM (Document Object Model) dokumentu XML](/dotnet/standard/data/xml/xml-document-object-model-dom)
- [Model objektu schématu (SOM) XML](/dotnet/standard/data/xml/xml-schema-object-model-som)