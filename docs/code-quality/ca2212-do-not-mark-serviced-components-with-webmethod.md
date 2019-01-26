---
title: 'CA2212: Neoznačujte obsluhované komponenty pomocí WebMethod'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
helpviewer_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
ms.assetid: 774bc55d-e588-48ee-8f38-c228580feca2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 774aa1372244c8ef397d5c2ff312e21b4e589b24
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55006805"
---
# <a name="ca2212-do-not-mark-serviced-components-with-webmethod"></a>CA2212: Neoznačujte obsluhované komponenty pomocí WebMethod

|||
|-|-|
|TypeName|DoNotMarkServicedComponentsWithWebMethod|
|CheckId|CA2212|
|Kategorie|Microsoft.Usage|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Metoda v typu, která dědí z <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName> je označené <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>.

## <a name="rule-description"></a>Popis pravidla

<xref:System.Web.Services.WebMethodAttribute> platí pro metody v rámci webové služby XML, které byly vytvořeny pomocí technologie ASP.NET; Díky metodu volat z klientů vzdáleného webového. Metody a třídy musí být veřejné a provádění ve webové aplikaci ASP.NET. <xref:System.EnterpriseServices.ServicedComponent> typy jsou hostované aplikace COM + a využívat služby COM +. <xref:System.Web.Services.WebMethodAttribute> neplatí pro <xref:System.EnterpriseServices.ServicedComponent> typy, protože nejsou určeny pro stejné scénáře. Konkrétně přidání atributu <xref:System.EnterpriseServices.ServicedComponent> – metoda neprovede metoda volatelná aplikacemi od klientů vzdálené webové. Protože <xref:System.Web.Services.WebMethodAttribute> a <xref:System.EnterpriseServices.ServicedComponent> metody mají konfliktní chování a budou požadavky na kontext a tok transakcí, chování metody v některých případech nesprávné.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, odeberte atribut z <xref:System.EnterpriseServices.ServicedComponent> metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo. Nejsou žádné scénáře, kde kombinaci těchto prvků je správná.

## <a name="see-also"></a>Viz také:

- <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName>
- <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>