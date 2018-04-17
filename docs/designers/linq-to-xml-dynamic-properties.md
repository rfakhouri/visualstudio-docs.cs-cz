---
title: Technologie LINQ to XML dynamické vlastnosti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
ms.assetid: 0455f47c-4a68-4f2e-a3f8-dd1d85b99012
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d54a37b58f46d8c3d1de145cc623ac3138621da
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="linq-to-xml-dynamic-properties"></a>Technologie LINQ to XML dynamické vlastnosti
Tato část obsahuje referenční informace o dynamických vlastností v technologii LINQ to XML. Konkrétně tyto vlastnosti jsou vystavené <xref:System.Xml.Linq.XAttribute> a <xref:System.Xml.Linq.XElement> třídy, které se nacházejí v <xref:System.Xml.Linq> oboru názvů.  
  
 Jak je popsáno v tématu [přehled z grafického subsystému WPF datové vazby s technologie LINQ to XML](../designers/wpf-data-binding-with-linq-to-xml-overview.md), každý dynamických vlastností je ekvivalentní standardní veřejné vlastnosti nebo metody ve stejné třídě. Tyto standardní členy se mají použít pro většinu účelů; dynamické vlastnosti jsou k dispozici speciálně pro technologie LINQ to XML scénáře datových vazeb. Další informace o standardní členy z těchto tříd naleznete v tématu <xref:System.Xml.Linq.XAttribute> a <xref:System.Xml.Linq.XElement> referenční témata.  
  
 Vzhledem k jejich vyřešení hodnoty dynamických vlastností v této části rozdělit do dvou kategorií:  
  
-   Jednoduché těch, jako `Value` vlastnosti v <xref:System.Xml.Linq.XAttribute> a <xref:System.Xml.Linq.XElement> třídy, které odkazují na jednu hodnotu.  
  
-   Indexované hodnoty, například [elementy](../designers/elements-xelement-dynamic-property.md) a [následníky](../designers/descendants-xelement-dynamic-property.md) vlastnosti <xref:System.Xml.Linq.XElement>, který přeložit na typ indexer. Pro typy indexer přeložit na požadovanou hodnotu nebo kolekci rozšířená název parametru musí být předán na ně.  
  
 Dynamické vlastnosti, které vracejí indexované hodnota typu <xref:System.Collections.Generic.IEnumerable%601> použít deffered provádění. Další informace o odložené provedení najdete v tématu [Úvod do dotazů LINQ (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries).  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|Téma|Popis|  
|-----------|-----------------|  
|[Dynamické vlastnosti třídy XAttribute](../designers/xattribute-class-dynamic-properties.md)|Obsahuje podrobné informace o dynamické vlastnosti, které jsou zveřejněné <xref:System.Xml.Linq.XAttribute> třídy.|  
|[Dynamické vlastnosti třídy XElement](../designers/xelement-class-dynamic-properties.md)|Obsahuje podrobné informace o dynamické vlastnosti, které jsou zveřejněné <xref:System.Xml.Linq.XElement> třídy.|  
  
## <a name="reference"></a>Odkaz  
 <xref:System.Xml.Linq>  
  
 <xref:System.Xml.Linq.XElement?displayProperty=fullName>  
  
 <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>  
  
## <a name="see-also"></a>Viz také  
 [Datové vazby WPF s technologie LINQ to XML](../designers/wpf-data-binding-with-linq-to-xml.md)   
 [Datové vazby WPF s technologií LINQ to XML – přehled](../designers/wpf-data-binding-with-linq-to-xml-overview.md)   
 [Úvod do dotazů LINQ (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)