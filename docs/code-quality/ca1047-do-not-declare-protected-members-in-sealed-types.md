---
title: 'CA1047: Nedeklarujte chráněné členy v zapečetěných typech | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- DoNotDeclareProtectedMembersInSealedTypes
- CA1047
helpviewer_keywords:
- CA1047
- DoNotDeclareProtectedMembersInSealedTypes
ms.assetid: 829033b5-a9d8-4f26-a719-45494c9dd035
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4b4a8ec92b79fb7df72ebd1984fc49f3cf4396cf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1047-do-not-declare-protected-members-in-sealed-types"></a>CA1047: Nedeklarujte chráněné členy v zapečetěných typech
|||  
|-|-|  
|TypeName|DoNotDeclareProtectedMembersInSealedTypes|  
|CheckId|CA1047|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Veřejné typ je `sealed` (`NotInheritable` v jazyce Visual basic) a deklaruje chráněného člena nebo chráněného vnořené typy. Toto pravidlo nevytváří sestavu porušení pro <xref:System.Object.Finalize%2A> metody, které je třeba postupovat podle tohoto vzoru.  
  
## <a name="rule-description"></a>Popis pravidla  
 Typy deklarují chráněné členy, aby k nim odvozené typy mohly přistupovat nebo je přepisovat. Podle definice nemůže Zdědit z zapečetěné typu, což znamená, že chráněný v zapečetěných typech metody nelze volat.  
  
 Kompilátor jazyka C# vydá upozornění pro tuto chybu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, změnit úroveň přístupu tohoto člena do privátního, případně zajistěte typ zděditelné.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Ponechat typ v jejím aktuálním stavu může způsobit problémy s údržbou a neposkytuje žádné výhody.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který je v rozporu toto pravidlo.  
  
 [!code-vb[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/VisualBasic/ca1047-do-not-declare-protected-members-in-sealed-types_1.vb)]
 [!code-csharp[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/CSharp/ca1047-do-not-declare-protected-members-in-sealed-types_1.cs)]