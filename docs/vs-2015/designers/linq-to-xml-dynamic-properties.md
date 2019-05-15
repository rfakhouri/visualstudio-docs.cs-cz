---
title: Technologie LINQ to XML dynamické vlastnosti | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 0455f47c-4a68-4f2e-a3f8-dd1d85b99012
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1aed85754eb1238528af9b5d74f2369b2548edc0
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65687175"
---
# <a name="linq-to-xml-dynamic-properties"></a>Technologie LINQ to XML dynamické vlastnosti
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato část obsahuje referenční informace o dynamické vlastnosti LINQ to XML. Konkrétně tyto vlastnosti jsou vystaveny <xref:System.Xml.Linq.XAttribute> a <xref:System.Xml.Linq.XElement> třídy, které jsou v <xref:System.Xml.Linq> oboru názvů.  
  
 Jak je popsáno v tématu [přehled o WPF datové vazby s LINQ to XML](../designers/wpf-data-binding-with-linq-to-xml-overview.md), dynamické vlastnosti je ekvivalentní standardní veřejné vlastnosti nebo metody ve stejné třídě. Tyto standardní členy by měl sloužit pro většinu účelů; dynamické vlastnosti jsou k dispozici speciálně pro funkci LINQ to XML scénáře datových vazeb. Další informace o standardní členové těchto tříd naleznete v tématu <xref:System.Xml.Linq.XAttribute> a <xref:System.Xml.Linq.XElement> referenčních témat.  
  
 S ohledem na jejich vyřešení hodnoty dynamických vlastností v této části spadají do dvou kategorií:  
  
- Jednoduché ty, které jsou, jako `Value` vlastnosti v <xref:System.Xml.Linq.XAttribute> a <xref:System.Xml.Linq.XElement> třídy, které přeložit na jedinou hodnotu.  
  
- Indexované hodnoty, například [prvky](../designers/elements-xelement-dynamic-property.md) a [následníky](../designers/descendants-xelement-dynamic-property.md) vlastnosti <xref:System.Xml.Linq.XElement>, který řešení do typu indexeru. Indexer typům přeložit na požadovanou hodnotu nebo kolekci musí být předán parametr rozbalený název k nim.  
  
  Dynamické vlastnosti, které vracejí indexovanou hodnotu typu <xref:System.Collections.Generic.IEnumerable%601> použít deffered spuštění. Další informace o odložené provedení, najdete v části [Úvod do dotazů LINQ (C#)](https://msdn.microsoft.com/library/37895c02-268c-41d5-be39-f7d936fa88a8).  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|Téma|Popis|  
|-----------|-----------------|  
|[Dynamické vlastnosti třídy XAttribute](../designers/xattribute-class-dynamic-properties.md)|Obsahuje podrobné informace o dynamických vlastností vystavovaných třídami <xref:System.Xml.Linq.XAttribute> třídy.|  
|[Dynamické vlastnosti třídy XElement](../designers/xelement-class-dynamic-properties.md)|Obsahuje podrobné informace o dynamických vlastností vystavovaných třídami <xref:System.Xml.Linq.XElement> třídy.|  
  
## <a name="reference"></a>Odkaz  
 <xref:System.Xml.Linq>  
  
 <xref:System.Xml.Linq.XElement?displayProperty=fullName>  
  
 <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>  
  
## <a name="see-also"></a>Viz také  
 [Datová vazba WPF s LINQ to XML](../designers/wpf-data-binding-with-linq-to-xml.md)   
 [Datová vazba WPF s LINQ to XML přehled](../designers/wpf-data-binding-with-linq-to-xml-overview.md)   
 [Úvod do dotazů LINQ (C#)](https://msdn.microsoft.com/library/37895c02-268c-41d5-be39-f7d936fa88a8)
