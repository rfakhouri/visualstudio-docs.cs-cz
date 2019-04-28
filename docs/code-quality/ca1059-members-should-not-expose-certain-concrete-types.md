---
title: 'CA1059: Členy by neměly zveřejňovat určité konkrétní typy'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1059
- MembersShouldNotExposeCertainConcreteTypes
helpviewer_keywords:
- MembersShouldNotExposeCertainConcreteTypes
- CA1059
ms.assetid: 59f61f52-8d6c-49cb-aefb-191910523a3c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2ea06de685d5e73f55e3fa8921d6785bc222da87
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62788621"
---
# <a name="ca1059-members-should-not-expose-certain-concrete-types"></a>CA1059: Členy by neměly zveřejňovat určité konkrétní typy

|||
|-|-|
|TypeName|MembersShouldNotExposeCertainConcreteTypes|
|CheckId|CA1059|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Externě viditelného členu je některé konkrétní typ nebo zpřístupňuje určité konkrétní typy prostřednictvím jednoho z jeho parametry nebo návratovou hodnotu. Toto pravidlo v současné době sestavy vystavení následující konkrétní typy:

- Typ odvozený od <xref:System.Xml.XmlNode?displayProperty=fullName>.

## <a name="rule-description"></a>Popis pravidla
 Konkrétní typ je typ, který je zcela implementován, a lze tudíž vytvořit jeho instanci. Chcete-li umožnit široké využití členu, nahraďte konkrétní typ navrhovaného rozhraní. To umožňuje členu, který chcete přijmout libovolný typ, který implementuje rozhraní, nebo použít, kde se očekává typ, který implementuje rozhraní.

 Následující tabulka uvádí cílové konkrétní typy a jejich navrhované nahrazení.

|Konkrétní typ|Nahrazení|
|-------------------|-----------------|
|<xref:System.Xml.XPath.XPathDocument>|<xref:System.Xml.XPath.IXPathNavigable?displayProperty=fullName>.<br /><br /> Pomocí rozhraní odděluje obě části člena z konkrétní implementaci zdroj dat XML.|

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte konkrétní typ na navrhovaného rozhraní.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné k potlačení zprávy z tohoto pravidla, pokud konkrétní funkce poskytované službou konkrétní typ je povinný.

## <a name="related-rules"></a>Související pravidla
 [CA1011: Zvažte předání základních typů jako parametrů](../code-quality/ca1011-consider-passing-base-types-as-parameters.md)