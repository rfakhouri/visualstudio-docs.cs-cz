---
title: 'CA1059: Členové by neměli zveřejňovat určité konkrétní typy | Dokumentace Microsoftu'
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
- CA1059
- MembersShouldNotExposeCertainConcreteTypes
helpviewer_keywords:
- MembersShouldNotExposeCertainConcreteTypes
- CA1059
ms.assetid: 59f61f52-8d6c-49cb-aefb-191910523a3c
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 1c909595954b4f6c2ec193bcaf241bd2b1d8136e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683276"
---
# <a name="ca1059-members-should-not-expose-certain-concrete-types"></a>CA1059: Členové by neměli zveřejňovat určité konkrétní typy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1059: členové by neměli zveřejňovat určité konkrétní typy](https://docs.microsoft.com/visualstudio/code-quality/ca1059-members-should-not-expose-certain-concrete-types).  
  
TypeName | MembersShouldNotExposeCertainConcreteTypes |  
| ID kontroly | CA1059 |  
| Kategorie | Microsoft.Design|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Externě viditelného členu je některé konkrétní typ nebo zpřístupňuje určité konkrétní typy prostřednictvím jednoho z jeho parametry nebo návratovou hodnotu. Toto pravidlo v současné době sestavy vystavení následující konkrétní typy:  
  
-   Typ odvozený od <xref:System.Xml.XmlNode?displayProperty=fullName>.  
  
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



