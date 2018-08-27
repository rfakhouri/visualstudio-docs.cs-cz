---
title: 'CA2222: Nesnižujte viditelnost zděděného členu | Dokumentace Microsoftu'
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
- DoNotDecreaseInheritedMemberVisibility
- CA2222
helpviewer_keywords:
- DoNotDecreaseInheritedMemberVisibility
- CA2222
ms.assetid: 066c8675-381f-43cc-956c-d757cc494028
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 9e631fc55a85e1d1a0383949d7e7592c6a5da44d
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42901981"
---
# <a name="ca2222-do-not-decrease-inherited-member-visibility"></a>CA2222: Nesnižujte viditelnost zděděného členu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2222: nesnižujte viditelnost zděděného členu](https://docs.microsoft.com/visualstudio/code-quality/ca2222-do-not-decrease-inherited-member-visibility).

|||
|-|-|
|TypeName|DoNotDecreaseInheritedMemberVisibility|
|CheckId|CA2222|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina
 Soukromé metody v nezapečetěný typ má podpis, který je stejný jako veřejné metody deklarované v základním typu. Privátní metoda není konečný.

## <a name="rule-description"></a>Popis pravidla
 Modifikátor přístupu byste neměli měnit u zděděných členů. Změna zděděného členu na soukromý nezabrání volajícím v přístupu k implementaci základní třídy dané metody. Pokud je k privátní člen a typ nezapečetěná, odvozující typy může volat poslední veřejné implementace metody v hierarchii dědičnosti. Pokud potřebujete změnit modifikátor přístupu, metoda by měla být označena finální nebo jeho typ by měl být zapečetěný zabránit přepsání metody.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte přístup být veřejné. Případně pokud svůj oblíbený programovací jazyk podporuje, můžete vytvořit metodu finální.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje tato pravidla.

 [!code-csharp[FxCop.Usage.InheritedPublic#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.InheritedPublic/cs/FxCop.Usage.InheritedPublic.cs#1)]
 [!code-vb[FxCop.Usage.InheritedPublic#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.InheritedPublic/vb/FxCop.Usage.InheritedPublic.vb#1)]



