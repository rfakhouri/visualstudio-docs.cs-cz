---
title: 'CA2130: Konstanty kritické pro zabezpečení musejí být transparentní | Dokumentace Microsoftu'
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
- CA2130
ms.assetid: 344c7f7b-9130-4675-ae7f-9fa260cc9789
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: a0423b8b2d6d3add6be4646863f4e7d8d3d25a89
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629329"
---
# <a name="ca2130-security-critical-constants-should-be-transparent"></a>CA2130: Konstanty kritické pro zabezpečení musejí být transparentní
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2130: konstanty kritické pro zabezpečení musejí být transparentní](https://docs.microsoft.com/visualstudio/code-quality/ca2130-security-critical-constants-should-be-transparent).  
  
TypeName | ConstantsShouldBeTransparent |  
| ID kontroly | CA2130 |  
| Kategorie | Microsoft.Security|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Konstanty pole nebo na člena výčtu je označeno <xref:System.Security.SecurityCriticalAttribute>.  
  
## <a name="rule-description"></a>Popis pravidla  
 Pro konstantní hodnoty není vynucována transparentnost, protože kompilátory vkládají konstantní hodnoty do kódu, aby za běhu programu nebylo zapotřebí žádné vyhledávání. Konstantní pole by měla být transparentní z pohledu zabezpečení, aby kontroloři kódu nepředpokládali, že transparentní kód nemůže ke konstantě přistoupit.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, odeberte atribut SecurityCritical z pole nebo hodnoty.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 V následujících příkladech, hodnota výčtu `EnumWithCriticalValues.CriticalEnumValue` a konstanty `CriticalConstant` vyvolat toto upozornění. Chcete-li opravit problémy, odeberte [`SecurityCritical`] atribut, aby se daly zabezpečení transparentní.  
  
 [!code-csharp[FxCop.Security.CA2130.ConstantsShouldBeTransparent#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2130.constantsshouldbetransparent/cs/ca2130 - constantsshouldbetransparent.cs#1)]



