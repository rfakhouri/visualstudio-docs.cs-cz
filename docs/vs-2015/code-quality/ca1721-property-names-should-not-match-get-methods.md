---
title: 'CA1721: Názvy vlastností by neměly odpovídat metodám get | Dokumentace Microsoftu'
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
- CA1721
- PropertyNamesShouldNotMatchGetMethods
helpviewer_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
ms.assetid: 45a0e853-1f06-4688-af1b-cc634409e295
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 78a87e13b7c97dbe3d6487a721b9b439892bae7f
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900879"
---
# <a name="ca1721-property-names-should-not-match-get-methods"></a>CA1721: Názvy vlastností by neměly odpovídat metodám Get
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1721: názvy vlastností by neměly odpovídat metodám get](https://docs.microsoft.com/visualstudio/code-quality/ca1721-property-names-should-not-match-get-methods).

|||
|-|-|
|TypeName|PropertyNamesShouldNotMatchGetMethods|
|CheckId|CA1721|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Název soukromého nebo chráněného členu začíná na "Get" a shoduje s názvem veřejné nebo chráněné vlastnosti. Typ, který obsahuje metodu s názvem 'Getcolor –' a vlastnost s názvem 'Color' Příklad poruší toto pravidlo.

## <a name="rule-description"></a>Popis pravidla
 Metody GET a vlastnosti by měly mít názvy, které zřetelně rozliší jejich funkce.

 Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. To snižuje čas, který se vyžaduje další nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Změňte název tak, aby neodpovídá názvu metody, která je s předponou "Get".

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

> [!NOTE]
>  Toto upozornění může vyloučit, je-li metodu Get implementací rozhraní IExtenderProvider.

## <a name="example"></a>Příklad
 Následující příklad obsahuje metody a vlastnosti, která toto pravidlo porušují.

 [!code-csharp[FxCop.Naming.GetMethod#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Naming.GetMethod/cs/FxCop.Naming.GetMethod.cs#1)]
 [!code-vb[FxCop.Naming.GetMethod#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Naming.GetMethod/vb/FxCop.Naming.GetMethod.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1024: Použijte vlastnosti, kde je to vhodné](../code-quality/ca1024-use-properties-where-appropriate.md)



