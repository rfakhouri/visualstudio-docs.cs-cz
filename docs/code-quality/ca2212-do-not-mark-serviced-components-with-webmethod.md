---
title: 'CA2212: Neoznačujte obsluhované součásti pomocí WebMethod | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
helpviewer_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
ms.assetid: 774bc55d-e588-48ee-8f38-c228580feca2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ca33b1dfeafa3894b3ad82fd42a04d8310d2bd50
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2212-do-not-mark-serviced-components-with-webmethod"></a>CA2212: Neoznačujte obsluhované součásti pomocí WebMethod
|||  
|-|-|  
|TypeName|DoNotMarkServicedComponentsWithWebMethod|  
|CheckId|CA2212|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Metoda v typ, který dědí z <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName> označena <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Popis pravidla  
 <xref:System.Web.Services.WebMethodAttribute> platí pro metody v rámci webové služby XML, které byly vytvořeny pomocí ASP.NET; Umožňuje metodu možné volat ze vzdálených klientů Web. Metoda a třída musí být veřejné a provádění ve webové aplikaci ASP.NET. <xref:System.EnterpriseServices.ServicedComponent> typy jsou hostované aplikací modelu COM + a použitím služby COM +. <xref:System.Web.Services.WebMethodAttribute> neplatí pro <xref:System.EnterpriseServices.ServicedComponent> typy, protože nejsou určeny pro stejné scénáře. Konkrétně přidání atribut, který se <xref:System.EnterpriseServices.ServicedComponent> metoda neposkytuje metodu s ze vzdálených klientů Web. Protože <xref:System.Web.Services.WebMethodAttribute> a <xref:System.EnterpriseServices.ServicedComponent> metoda mají konfliktní chování a požadavky kontextu a toku transakcí, chování metody jsou nesprávná v některých scénářích.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, odeberte atribut z <xref:System.EnterpriseServices.ServicedComponent> metoda.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Neexistují žádné scénářích, kdy spojení těchto prvků správné.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName>   
 <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>