---
title: 'CA1047: Nedeklarujte chráněné členy v zapečetěných typech | Dokumentace Microsoftu'
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
- DoNotDeclareProtectedMembersInSealedTypes
- CA1047
helpviewer_keywords:
- CA1047
- DoNotDeclareProtectedMembersInSealedTypes
ms.assetid: 829033b5-a9d8-4f26-a719-45494c9dd035
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 23d37fe2fbd580c3d5eab8b60db3b435776c2d55
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668145"
---
# <a name="ca1047-do-not-declare-protected-members-in-sealed-types"></a>CA1047: Nedeklarujte chráněné členy v zapečetěných typech
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1047: nedeklarujte chráněné členy v zapečetěných typech](https://docs.microsoft.com/visualstudio/code-quality/ca1047-do-not-declare-protected-members-in-sealed-types).  
  
TypeName | DoNotDeclareProtectedMembersInSealedTypes |  
| ID kontroly | CA1047 |  
| Kategorie | Microsoft.Design|  
| Zásadní změna | Ukončování bez |  
  
## <a name="cause"></a>příčina  
 Je veřejný typ `sealed` (`NotInheritable` v jazyce Visual basic) a deklaruje chráněný člen nebo chráněné vnořeného typu. Toto pravidlo nevytváří sestavu porušení pro <xref:System.Object.Finalize%2A> metody, které musí postupovat podle tohoto vzoru.  
  
## <a name="rule-description"></a>Popis pravidla  
 Typy deklarují chráněné členy, aby k nim odvozené typy mohly přistupovat nebo je přepisovat. Podle definice nelze dědit ze zapečetěného typu, což znamená, že chráněné metody zapečetěných typů nelze volat.  
  
 Kompilátor jazyka C# vyvolá upozornění pro tuto chybu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, změnit úroveň přístupu členu na soukromý nebo učiňte typ odvoditelný.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Opuštění typu v jejím aktuálním stavu může způsobit problémy s údržbou a nepřináší žádné výhody.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který porušuje tato pravidla.  
  
 [!code-csharp[FxCop.Design.SealedNoProtected#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.SealedNoProtected/cs/FxCop.Design.SealedNoProtected.cs#1)]
 [!code-vb[FxCop.Design.SealedNoProtected#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.SealedNoProtected/vb/FxCop.Design.SealedNoProtected.vb#1)]



