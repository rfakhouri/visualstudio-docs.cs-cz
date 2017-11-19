---
title: "CA2212: Neoznačujte obsluhované součásti pomocí WebMethod | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
helpviewer_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
ms.assetid: 774bc55d-e588-48ee-8f38-c228580feca2
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 44c29215301212a12c5652fbf1fe91af23db1082
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 <xref:System.Web.Services.WebMethodAttribute>platí pro metody v rámci webové služby XML, které byly vytvořeny pomocí ASP.NET; Umožňuje metodu možné volat ze vzdálených klientů Web. Metoda a třída musí být veřejné a provádění ve webové aplikaci ASP.NET. <xref:System.EnterpriseServices.ServicedComponent>typy jsou hostované aplikací modelu COM + a použitím služby COM +. <xref:System.Web.Services.WebMethodAttribute>neplatí pro <xref:System.EnterpriseServices.ServicedComponent> typy, protože nejsou určeny pro stejné scénáře. Konkrétně přidání atribut, který se <xref:System.EnterpriseServices.ServicedComponent> metoda neposkytuje metodu s ze vzdálených klientů Web. Protože <xref:System.Web.Services.WebMethodAttribute> a <xref:System.EnterpriseServices.ServicedComponent> metoda mají konfliktní chování a požadavky kontextu a toku transakcí, chování metody jsou nesprávná v některých scénářích.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, odeberte atribut z <xref:System.EnterpriseServices.ServicedComponent> metoda.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Neexistují žádné scénářích, kdy spojení těchto prvků správné.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName>   
 <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>