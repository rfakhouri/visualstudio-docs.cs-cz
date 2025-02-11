---
title: 'CA1053: Statický vlastník typů by neměly mít konstruktory | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- StaticHolderTypesShouldNotHaveConstructors
- CA1053
helpviewer_keywords:
- CA1053
- StaticHolderTypesShouldNotHaveConstructors
ms.assetid: 10302b9a-fa5e-4935-a06a-513d9600f613
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 83000143674e7cc3bc412c0ca8a579660160514c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63444564"
---
# <a name="ca1053-static-holder-types-should-not-have-constructors"></a>CA1053: Statické typy vlastníků by neměly mít konstruktory
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|StaticHolderTypesShouldNotHaveConstructors|
|CheckId|CA1053|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Veřejný nebo vnořený veřejný typ deklaruje pouze statické členy a má veřejný nebo chráněný výchozí konstruktor.

## <a name="rule-description"></a>Popis pravidla
 Konstruktor není nutný, protože volání statických členů nevyžaduje instanci typu. Navíc vzhledem k tomu, že typ nemá žádné nestatické členy, vytvoření instance neposkytuje přístup k libovolnému členy tohoto typu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odeberte výchozí konstruktor nebo ji učiňte soukromou.

> [!NOTE]
> Některé kompilátory automaticky vytvořit výchozí veřejný konstruktor, pokud typ nedefinuje žádné konstruktory. Pokud tomu tak s typem, přidejte privátní výchozí konstruktor, chcete-li odstranit porušení zásady.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Přítomnost konstruktoru naznačuje, že typ není statický typ.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje tato pravidla. Všimněte si, že neexistuje žádný výchozí konstruktor ve zdrojovém kódu. Když tento kód je zkompilován do sestavení, kompilátor jazyka C# vloží výchozí konstruktor, který bude toto pravidlo porušují. Chcete-li opravit, deklarujte soukromý konstruktor.

 [!code-csharp[FxCop.Design.StaticTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.StaticTypes/cs/FxCop.Design.StaticTypes.cs#1)]
