---
title: 'CA2222: Nesnižujte viditelnost zděděného členu'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotDecreaseInheritedMemberVisibility
- CA2222
helpviewer_keywords:
- DoNotDecreaseInheritedMemberVisibility
- CA2222
ms.assetid: 066c8675-381f-43cc-956c-d757cc494028
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: d63f4509872cc117ae03ff3a668d38a6efb07ef9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541819"
---
# <a name="ca2222-do-not-decrease-inherited-member-visibility"></a>CA2222: Nesnižujte viditelnost zděděného členu

|||
|-|-|
|TypeName|DoNotDecreaseInheritedMemberVisibility|
|CheckId|CA2222|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Soukromé metody v nezapečetěný typ má podpis, který je stejný jako veřejné metody deklarované v základním typu. Privátní metoda není konečný.

## <a name="rule-description"></a>Popis pravidla

Neměnit modifikátor přístupu u zděděných členů. Změna zděděného členu na soukromý nezabrání volajícím v přístupu k implementaci základní třídy dané metody. Pokud je k privátní člen a typ nezapečetěná, odvozující typy může volat poslední veřejné implementace metody v hierarchii dědičnosti. Pokud potřebujete změnit modifikátor přístupu, metoda by měla být označena finální nebo jeho typ by měl být zapečetěný zabránit přepsání metody.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, změňte přístup být veřejné. Případně pokud svůj oblíbený programovací jazyk podporuje, můžete vytvořit metodu finální.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad

Následující příklad ukazuje typ, který porušuje tato pravidla.

[!code-vb[FxCop.Usage.InheritedPublic#1](../code-quality/codesnippet/VisualBasic/ca2222-do-not-decrease-inherited-member-visibility_1.vb)]
[!code-csharp[FxCop.Usage.InheritedPublic#1](../code-quality/codesnippet/CSharp/ca2222-do-not-decrease-inherited-member-visibility_1.cs)]