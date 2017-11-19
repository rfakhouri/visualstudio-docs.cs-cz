---
title: "CA3077: Nezabezpečené zpracování v návrhu rozhraní API, dokumentu XML a čtečku textu XML | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f33771b-f3c8-4c02-bef6-f581b623c303
caps.latest.revision: "7"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6944b49626771317f1643f7ae521b0db43c2200c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca3077-insecure-processing-in-api-design-xml-document-and-xml-text-reader"></a>CA3077: Nezabezpečené zpracování v návrhu rozhraní API, dokumentu XML a čtečku textu XML
|||  
|-|-|  
|TypeName|InsecureDTDProcessingInAPIDesign|  
|CheckId|CA3077|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Při navrhování rozhraní API odvozená od třídou XMLDocument nastavenou na a XMLTextReader, mělo pamatovat <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A>.  Pomocí nezabezpečené instancí DTDProcessing při odkazování na externí entity zdroje řešení nebo nastavení nezabezpečené hodnot v souboru XML může způsobit zpřístupnění informací.  
  
## <a name="rule-description"></a>Popis pravidla  
 A [dokumentu typ definice (DTD)](https://msdn.microsoft.com/en-us/library/aa468547.aspx) je jedním ze dvou způsobů analyzátor jazyka XML můžete určit platnost dokumentu, podle definice [World Wide Web Consortium (W3C) Extensible Markup Language (XML) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/). Toto pravidlo bude hledat vlastnosti a instance, kde je nedůvěryhodné data přijatá varování před vývojáře o potenciální [zpřístupnění informací](/dotnet/framework/wcf/feature-details/information-disclosure) hrozeb, které mohou vést k [útok na dostupnost služby (DoS)](/dotnet/framework/wcf/feature-details/denial-of-service) útoky. Toto pravidlo aktivuje, když:  
  
-   <xref:System.Xml.XmlDocument>nebo <xref:System.Xml.XmlTextReader> třídy použít výchozí překladač hodnoty pro zpracování souboru DTD protokolu.  
  
-   Žádný konstruktor je definována pro dokument XML nebo XmlTextReader odvozených tříd nebo žádná zabezpečené hodnota se používá pro <xref:System.Xml.XmlResolver>.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
  
-   Catch – a zpracovat všechny výjimky XmlTextReader správně, aby se zabránilo cesta zpřístupnění informací.  
  
-   Použití <xref:System.Xml.XmlSecureResolver>místo objekt XmlResolver omezit přístup XmlTextReader prostředky.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Pokud si nejste jisti, že vstup se označuje jako z důvěryhodného zdroje, není potlačit pravidlo z toto upozornění.  
  
## <a name="pseudo-code-examples"></a>Příklady pseudo kódu  
  
### <a name="violation"></a>Porušení  
  
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