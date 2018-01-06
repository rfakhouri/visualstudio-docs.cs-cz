---
title: "CA2211: Nekonstantní pole by neměly být viditelné | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2211
- NonConstantFieldsShouldNotBeVisible
helpviewer_keywords:
- NonConstantFieldsShouldNotBeVisible
- CA2211
ms.assetid: e1e42c40-0acd-4312-af29-70133739a304
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b31eb16fda818ab2eee001e0fe14c5f433f5fcd1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca2211-non-constant-fields-should-not-be-visible"></a>CA2211: Nekonstantní pole by nemělo být viditelné
|||  
|-|-|  
|TypeName|NonConstantFieldsShouldNotBeVisible|  
|CheckId|CA2211|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Veřejné nebo chráněného statických polí není konstantní ani je jen pro čtení.  
  
## <a name="rule-description"></a>Popis pravidla  
 Statická pole, která nejsou konstantami ani nejsou jen pro čtení, nejsou bezpečná pro přístup z více vláken. Přístup k toto pole je třeba pečlivě kontrolovat a vyžaduje pokročilé techniky programování pro synchronizaci přístup k objektu třídy. Protože jsou to obtížné dovednosti pro další informace a hlavní a testování takového objektu představuje vlastní výzvy, statická pole jsou k ukládání dat, který se nemění nejvhodnější. Toto pravidlo platí pro knihovny; aplikace by neměli zveřejňovat všechna pole.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, nastavit statické pole konstantní nebo jen pro čtení. Pokud to není možné změnit návrh typ, který má použít alternativní mechanismus jako je například vlastnost bezpečné pro přístup z více vláken, která spravuje přístup z více vláken bezpečný přístup k podkladové pole. Uvědomte si, že problémy, jako je spory uzamčení a blokování může ovlivnit výkon a chování knihovny.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, pokud vyvíjíte aplikaci a proto máte plnou kontrolu nad přístup k typ, který obsahuje statické pole. Knihovna návrháře nesmí potlačit upozornění na toto pravidlo; použití statických polí není konstantní. můžete nastavit pomocí knihovny těžko vývojářům používat správně.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který je v rozporu toto pravidlo.  
  
 [!code-vb[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/VisualBasic/ca2211-non-constant-fields-should-not-be-visible_1.vb)]
 [!code-csharp[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/CSharp/ca2211-non-constant-fields-should-not-be-visible_1.cs)]