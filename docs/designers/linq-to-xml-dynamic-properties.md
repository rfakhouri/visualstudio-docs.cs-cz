---
title: Technologie LINQ to XML dynamické vlastnosti
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 0455f47c-4a68-4f2e-a3f8-dd1d85b99012
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f51995cf1e327691276f0adb417e1832dc936f3e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53823390"
---
# <a name="linq-to-xml-dynamic-properties"></a>Dynamické vlastnosti LINQ to XML

Tato část obsahuje referenční informace o dynamické vlastnosti LINQ to XML. Konkrétně tyto vlastnosti jsou vystaveny <xref:System.Xml.Linq.XAttribute> a <xref:System.Xml.Linq.XElement> třídy, které jsou v <xref:System.Xml.Linq> oboru názvů.

Jak je popsáno v tématu [datová vazba přehled WPF s LINQ to XML](../designers/wpf-data-binding-with-linq-to-xml-overview.md), dynamické vlastnosti je ekvivalentní standardní veřejné vlastnosti nebo metody ve stejné třídě. Tyto standardní členy by měl sloužit pro většinu účelů; dynamické vlastnosti jsou k dispozici speciálně pro funkci LINQ to XML scénáře datových vazeb. Další informace o standardní členové těchto tříd naleznete v tématu <xref:System.Xml.Linq.XAttribute> a <xref:System.Xml.Linq.XElement> referenčních témat.

S ohledem na jejich vyřešení hodnoty dynamických vlastností v této části spadají do dvou kategorií:

- Jednoduché ty, které jsou, jako `Value` vlastnosti v <xref:System.Xml.Linq.XAttribute> a <xref:System.Xml.Linq.XElement> třídy, které přeložit na jedinou hodnotu.

- Indexované hodnoty, například [prvky](../designers/elements-xelement-dynamic-property.md) a [následníky](../designers/descendants-xelement-dynamic-property.md) vlastnosti <xref:System.Xml.Linq.XElement>, který řešení do typu indexeru. Indexer typům přeložit na požadovanou hodnotu nebo kolekci musí být předán parametr rozbalený název k nim.

Dynamické vlastnosti, které vracejí indexovanou hodnotu typu <xref:System.Collections.Generic.IEnumerable%601> pomocí odloženého provedení. Další informace o odložené provedení, najdete v části [Úvod do dotazů LINQ (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries).

## <a name="reference"></a>Odkaz

- <xref:System.Xml.Linq>
- <xref:System.Xml.Linq.XElement?displayProperty=fullName>
- <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>

## <a name="see-also"></a>Viz také:

- [Datová vazba WPF s LINQ to XML](../designers/wpf-data-binding-with-linq-to-xml-overview.md)
- [Datová vazba WPF s LINQ XML – přehled](../designers/wpf-data-binding-with-linq-to-xml-overview.md)
- [Úvod do dotazů LINQ (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)
