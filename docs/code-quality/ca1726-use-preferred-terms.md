---
title: "CA1726: Použijte upřednostňované výrazy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UsePreferredTerms
- CA1726
helpviewer_keywords: UsePreferredTerms
ms.assetid: 642b2acd-3a33-4d1f-b0a7-67073ae73be2
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2ae02d0eb136d45bc2b8af7dde5f897765493050
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1726-use-preferred-terms"></a>CA1726: Použijte upřednostňované výrazy
|||  
|-|-|  
|TypeName|UsePreferredTerms|  
|CheckId|CA1726|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Pozastavení - při aktivováno u sestavení<br /><br /> Bez ukončování - při vyvolání na parametry typu|  
  
## <a name="cause"></a>příčina  
 Název externě viditelného identifikátoru zahrnuje výraz, pro který existuje alternativní upřednostňovaný výraz. Alternativně název zahrnuje termín příznak nebo příznaků.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo analyzuje identifikátor do tokenů. Každý jeden token a každé souvislý kombinaci duální tokenu se porovná s podmínkami, které jsou integrované do pravidla a v části zastaralé všechny vlastní slovník. V následující tabulce jsou uvedeny podmínky, které jsou součástí pravidlo a jejich upřednostňované alternativy.  
  
|Zastaralé termín|Upřednostňovaný termín|  
|-------------------|--------------------|  
|nejsou|AreNot|  
|Zrušena|Zrušeno|  
|Nemůžete|Nelze|  
|ComPlus|EnterpriseServices|  
|Couldnt|CouldNot|  
|Didnt|DidNot|  
|Doesnt|Neobsahuje|  
|Dont|DoNot|  
|Příznak nebo příznaky|Neexistuje žádný termín nahrazení. Nepoužívejte.|  
|kdyby|HadNot|  
|Nebyl|HasNot|  
|nebyly|HaveNot|  
|Indexy|Indexy|  
|není|IsNot|  
|Přihlášení|Přihlášení|  
|Odhlášení|Odhlášení|  
|Shouldnt|ShouldNot|  
|Sign-on|Přihlášení|  
|Odhlásit se|Odhlášení|  
|Wasnt|WasNot|  
|nebyly|WereNot|  
|Nefunguje|WillNot|  
|Wouldnt|WouldNot|  
|Nelze zapisovat|Zápis|  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, nahraďte výraz upřednostňovaný alternativní termín.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačíte upozornění na toto pravidlo pouze v případě, že název identifikátoru je úmyslné a se zabývá pouze původní termín místo Upřednostňovaný termín.  
  
## <a name="related-rules"></a>Související pravidla  
 [Upozornění na pojmenování](../code-quality/naming-warnings.md)