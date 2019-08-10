---
title: 'CA2211: Nekonstantní pole by neměla být viditelná'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2211
- NonConstantFieldsShouldNotBeVisible
helpviewer_keywords:
- NonConstantFieldsShouldNotBeVisible
- CA2211
ms.assetid: e1e42c40-0acd-4312-af29-70133739a304
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 77909627385a7aa2e41f87c23ec41dc8ac0e1a5e
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920361"
---
# <a name="ca2211-non-constant-fields-should-not-be-visible"></a>CA2211: Nekonstantní pole by neměla být viditelná

|||
|-|-|
|TypeName|NonConstantFieldsShouldNotBeVisible|
|CheckId|CA2211|
|Kategorie|Microsoft.Usage|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Veřejné nebo chráněné statické pole není konstantní ani jen pro čtení.

## <a name="rule-description"></a>Popis pravidla
Statická pole, která nejsou konstantami ani nejsou jen pro čtení, nejsou bezpečná pro přístup z více vláken. Přístup k takovému poli musí být pečlivě kontrolován a vyžaduje pokročilé programovací techniky pro synchronizaci přístupu k objektu třídy. Vzhledem k tomu, že se jedná o obtížné dovednosti při učení a hlavní a testování takového objektu představuje své vlastní výzvy, statická pole jsou nejvhodnější pro ukládání dat, která se nezmění. Toto pravidlo se vztahuje na knihovny; aplikace by neměly vystavovat žádná pole.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, nastavte konstantu statického pole nebo jen pro čtení. Pokud to není možné, změňte návrh typu tak, aby používal alternativní mechanismus, jako je například vlastnost bezpečná pro přístup z více vláken, která spravuje přístup s bezpečným přístupem k podkladovým polím. Je potřeba si uvědomit, že problémy, jako je například kolize zámků a zablokování, můžou ovlivnit výkon a chování knihovny.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Je bezpečné potlačit upozornění z tohoto pravidla, pokud vyvíjíte aplikaci, a proto máte plnou kontrolu nad přístupem k typu, který obsahuje statické pole. Návrháři knihovny by neměli potlačit upozornění z tohoto pravidla; použití nekonstantních statických polí může pro vývojáře ztížit používání knihovny.

## <a name="example"></a>Příklad
Následující příklad ukazuje typ, který je v rozporu s tímto pravidlem.

[!code-vb[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/VisualBasic/ca2211-non-constant-fields-should-not-be-visible_1.vb)]
[!code-csharp[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/CSharp/ca2211-non-constant-fields-should-not-be-visible_1.cs)]