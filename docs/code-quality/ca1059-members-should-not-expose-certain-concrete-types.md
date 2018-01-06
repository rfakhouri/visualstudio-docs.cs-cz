---
title: "CA1059: Členové by neměli zveřejňovat určité konkrétní typy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1059
- MembersShouldNotExposeCertainConcreteTypes
helpviewer_keywords:
- MembersShouldNotExposeCertainConcreteTypes
- CA1059
ms.assetid: 59f61f52-8d6c-49cb-aefb-191910523a3c
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: eae9070d76312fa4840f2cf8724a74a2cde4f7b2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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