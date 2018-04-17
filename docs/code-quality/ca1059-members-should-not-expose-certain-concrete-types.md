---
title: 'CA1059: Členové by neměli zveřejňovat určité konkrétní typy | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1059
- MembersShouldNotExposeCertainConcreteTypes
helpviewer_keywords:
- MembersShouldNotExposeCertainConcreteTypes
- CA1059
ms.assetid: 59f61f52-8d6c-49cb-aefb-191910523a3c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 78a5ab72d838cbac21208940bd43aec370777183
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1059-members-should-not-expose-certain-concrete-types"></a>CA1059: Členové by neměli zveřejňovat určité konkrétní typy
|||  
|-|-|  
|TypeName|MembersShouldNotExposeCertainConcreteTypes|  
|CheckId|CA1059|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Externě viditelné člen je určitý konkrétní typ nebo zpřístupní určité konkrétní typy prostřednictvím jednoho z jeho parametry nebo vrátit hodnotu. Toto pravidlo v současné době sestavy ohrožení následující konkrétní typy:  
  
-   Typ odvozený od <xref:System.Xml.XmlNode?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Popis pravidla  
 Konkrétní typ je typ, který je zcela implementován, a lze tudíž vytvořit jeho instanci. Povolit podnikové sféře často používají člena, nahraďte konkrétní typ rozhraní navržené. To umožňuje člen přijmout žádný typ, který implementuje rozhraní nebo použije, kde je očekávána typ, který implementuje rozhraní.  
  
 Následující tabulka uvádí cílové konkrétní typy a jejich navrhované nahrazení.  
  
|Konkrétní typ|Nahrazení|  
|-------------------|-----------------|  
|<xref:System.Xml.XPath.XPathDocument>|<xref:System.Xml.XPath.IXPathNavigable?displayProperty=fullName>.<br /><br /> Pomocí rozhraní oddělí člena z konkrétní implementace zdroje dat XML.|  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, změňte konkrétní typ rozhraní navržené.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné k potlačení zprávy z tohoto pravidla, pokud se vyžaduje konkrétní funkce poskytované službou konkrétní typ.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1011: Zvažte předání základních typů jako parametrů](../code-quality/ca1011-consider-passing-base-types-as-parameters.md)