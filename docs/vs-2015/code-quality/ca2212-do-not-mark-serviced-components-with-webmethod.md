---
title: 'CA2212: Neoznačujte obsluhované součásti pomocí WebMethod | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
helpviewer_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
ms.assetid: 774bc55d-e588-48ee-8f38-c228580feca2
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 7a54d18d91075b187f126845d7e0278c5e4ad65b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668537"
---
# <a name="ca2212-do-not-mark-serviced-components-with-webmethod"></a>CA2212: Neoznačujte obsluhované součásti pomocí WebMethod
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2212: neoznačujte obsluhované součásti pomocí WebMethod](https://docs.microsoft.com/visualstudio/code-quality/ca2212-do-not-mark-serviced-components-with-webmethod).  
  
TypeName | DoNotMarkServicedComponentsWithWebMethod |  
| ID kontroly | CA2212 |  
| Kategorie | Microsoft.Usage|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Metoda v typu, která dědí z <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName> je označené <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Popis pravidla  
 <xref:System.Web.Services.WebMethodAttribute> platí pro metody v rámci webové služby XML, které byly vytvořeny pomocí technologie ASP.NET; Díky metodu volat ze vzdálených webových klientů. Metody a třídy musí být veřejné a provádění ve webové aplikaci ASP.NET. <xref:System.EnterpriseServices.ServicedComponent> typy jsou hostované aplikace COM + a využívat služby COM +. <xref:System.Web.Services.WebMethodAttribute> neplatí pro <xref:System.EnterpriseServices.ServicedComponent> typy, protože nejsou určeny pro stejné scénáře. Konkrétně, přidání atributu do <xref:System.EnterpriseServices.ServicedComponent> – metoda neprovede metodu volat ze vzdálených webových klientů. Protože <xref:System.Web.Services.WebMethodAttribute> a <xref:System.EnterpriseServices.ServicedComponent> metody mají konfliktní chování a budou požadavky na kontext a tok transakcí, chování metody v některých případech nesprávné.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, odeberte atribut z <xref:System.EnterpriseServices.ServicedComponent> metody.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Nejsou žádné scénáře, kde kombinaci těchto prvků je správná.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName>   
 <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>



