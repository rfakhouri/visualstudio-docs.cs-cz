---
title: Technologie LINQ to XML dynamické vlastnosti
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 0455f47c-4a68-4f2e-a3f8-dd1d85b99012
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 184204011a3862522be37f458839d5a1b56b7052
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="linq-to-xml-dynamic-properties"></a>Technologie LINQ to XML dynamické vlastnosti

Tato část obsahuje referenční informace o dynamických vlastností v technologii LINQ to XML. Konkrétně tyto vlastnosti jsou vystavené <xref:System.Xml.Linq.XAttribute> a <xref:System.Xml.Linq.XElement> třídy, které se nacházejí v <xref:System.Xml.Linq> oboru názvů.

Jak je popsáno v tématu [přehled z grafického subsystému WPF datové vazby s technologie LINQ to XML](../designers/wpf-data-binding-with-linq-to-xml-overview.md), každý dynamických vlastností je ekvivalentní standardní veřejné vlastnosti nebo metody ve stejné třídě. Tyto standardní členy se mají použít pro většinu účelů; dynamické vlastnosti jsou k dispozici speciálně pro technologie LINQ to XML scénáře datových vazeb. Další informace o standardní členy z těchto tříd naleznete v tématu <xref:System.Xml.Linq.XAttribute> a <xref:System.Xml.Linq.XElement> referenční témata.

Vzhledem k jejich vyřešení hodnoty dynamických vlastností v této části rozdělit do dvou kategorií:

- Jednoduché těch, jako `Value` vlastnosti v <xref:System.Xml.Linq.XAttribute> a <xref:System.Xml.Linq.XElement> třídy, které odkazují na jednu hodnotu.

- Indexované hodnoty, například [elementy](../designers/elements-xelement-dynamic-property.md) a [následníky](../designers/descendants-xelement-dynamic-property.md) vlastnosti <xref:System.Xml.Linq.XElement>, který přeložit na typ indexer. Pro typy indexer přeložit na požadovanou hodnotu nebo kolekci rozšířená název parametru musí být předán na ně.

Dynamické vlastnosti, které vracejí indexované hodnota typu <xref:System.Collections.Generic.IEnumerable%601> použít odložené provedení. Další informace o odložené provedení najdete v tématu [Úvod do dotazů LINQ (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries).

## <a name="reference"></a>Odkaz

- <xref:System.Xml.Linq>
- <xref:System.Xml.Linq.XElement?displayProperty=fullName>
- <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>

## <a name="see-also"></a>Viz také

- [Datová vazba WPF s LINQ to XML](../designers/wpf-data-binding-with-linq-to-xml-overview.md)
- [Přehled datové vazby WPF s LINQ to XML](../designers/wpf-data-binding-with-linq-to-xml-overview.md)
- [Úvod do dotazů LINQ (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)
