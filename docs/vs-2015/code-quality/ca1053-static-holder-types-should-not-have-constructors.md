---
title: 'CA1053: Statický vlastník typů by neměly mít konstruktory | Dokumentace Microsoftu'
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
ms.openlocfilehash: 896c77d5a1e3d6df65cd64134126d6e02ea3b9e5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668015"
---
# <a name="ca1053-static-holder-types-should-not-have-constructors"></a>CA1053: Statický vlastník typů by neměl mít konstruktory
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1053: statický vlastník typů by neměly mít konstruktory](https://docs.microsoft.com/visualstudio/code-quality/ca1053-static-holder-types-should-not-have-constructors).  
  
TypeName | StaticHolderTypesShouldNotHaveConstructors |  
| ID kontroly | CA1053 |  
| Kategorie | Microsoft.Design|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Veřejný nebo vnořený veřejný typ deklaruje pouze statické členy a má veřejný nebo chráněný výchozí konstruktor.  
  
## <a name="rule-description"></a>Popis pravidla  
 Konstruktor není nutný, protože volání statických členů nevyžaduje instanci typu. Navíc vzhledem k tomu, že typ nemá žádné nestatické členy, vytvoření instance neposkytuje přístup k libovolnému členy tohoto typu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, odeberte výchozí konstruktor nebo ji učiňte soukromou.  
  
> [!NOTE]
>  Některé kompilátory automaticky vytvořit výchozí veřejný konstruktor, pokud typ nedefinuje žádné konstruktory. Pokud tomu tak s typem, přidejte privátní výchozí konstruktor, chcete-li odstranit porušení zásady.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Přítomnost konstruktoru naznačuje, že typ není statický typ.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který porušuje tato pravidla. Všimněte si, že neexistuje žádný výchozí konstruktor ve zdrojovém kódu. Když tento kód je zkompilován do sestavení, kompilátor jazyka C# vloží výchozí konstruktor, který bude toto pravidlo porušují. Chcete-li opravit, deklarujte soukromý konstruktor.  
  
 [!code-csharp[FxCop.Design.StaticTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.StaticTypes/cs/FxCop.Design.StaticTypes.cs#1)]



