---
title: 'CA2132: Výchozí konstruktory nesmějí být kritické jako výchozí konstruktory základního typu | Dokumentace Microsoftu'
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
- CA2132
ms.assetid: e758afa1-8bde-442a-8a0a-bd1ea7b0ce4d
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 165e745d40e5a8a488a3f35bc1ad8b066b0ae523
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672728"
---
# <a name="ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors"></a>CA2132: Výchozí konstruktory nesmějí být méně kritické než výchozí konstruktory základního typu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2132: výchozí konstruktory nesmějí být kritické jako výchozí konstruktory základního typu](https://docs.microsoft.com/visualstudio/code-quality/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors).  
  
TypeName | DefaultConstructorsMustHaveConsistentTransparency |  
| ID kontroly | CA2132 |  
| Kategorie | Microsoft.Security|  
| Zásadní změna | Zásadní |  
  
> [!NOTE]
>  Toto upozornění se použije pouze na kód, který je spuštěn CoreCLR (verze CLR, který je specifický pro Silverlight webových aplikací).  
  
## <a name="cause"></a>příčina  
 Atribut transparentnosti výchozího konstruktoru odvozené třídy není tak kritický jako transparentnosti základní třídy.  
  
## <a name="rule-description"></a>Popis pravidla  
 Typy a členy, které mají <xref:System.Security.SecurityCriticalAttribute> nelze použít kódem aplikace Silverlight. Typy a členy kritické z hlediska zabezpečení lze použít pouze prostřednictvím důvěryhodného kódu v knihovně tříd rozhraní .NET Framework aplikace Silverlight. Protože veřejné nebo chráněné konstrukce v odvozené třídě musí mít stejnou nebo větší transparentnost než jejich základní třída, nelze třídu v aplikaci odvodit z třídy označené jako SecurityCritical.  
  
 Pro CoreCLR kód platformy Pokud základní typ nemá veřejný nebo chráněný neprůhledné výchozí konstruktor. potom odvozený typ musí dodržovat pravidla dědičnosti výchozí konstruktor. Odvozený typ musí také mít výchozí konstruktor a tento konstruktor musí být dlouhý aspoň jako kritické výchozí konstruktor třídy základního typu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li vyřešit porušení zásady, odeberte typ nebo není odvozen od neprůhledných typ zabezpečení.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění tohoto pravidla. Porušení tohoto pravidla kódem aplikace, bude výsledkem CoreCLR odmítá načíst typ s <xref:System.TypeLoadException>.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Security.CA2132.DefaultConstructorsMustHaveConsistentTransparency#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2132.defaultconstructorsmusthaveconsistenttransparency/cs/ca2132 - defaultconstructorsmusthaveconsistenttransparency.cs#1)]  
  
### <a name="comments"></a>Komentáře



