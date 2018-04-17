---
title: 'CA2104: Nedeklaruje čtení proměnlivé odkazové typy pouze | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- DoNotDeclareReadOnlyMutableReferenceTypes
- CA2104
helpviewer_keywords:
- CA2104
- DoNotDeclareReadOnlyMutableReferenceTypes
ms.assetid: 81b83ee5-4db5-4be0-9f8d-90b53894ec3b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e14bc99d49ed7e089b3d6d6f63f49eb5b8d3ecae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2104-do-not-declare-read-only-mutable-reference-types"></a>CA2104: Nedeklaruje proměnlivé odkazové typy pouze pro čtení
|||  
|-|-|  
|TypeName|DoNotDeclareReadOnlyMutableReferenceTypes|  
|CheckId|CA2104|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Externě viditelný typ obsahuje externě viditelné pole měnitelného referenčního typu, které je určeno jen pro čtení.  
  
## <a name="rule-description"></a>Popis pravidla  
 Měnitelný typ je typ, jehož instanční data lze upravit. <xref:System.Text.StringBuilder?displayProperty=fullName> Třída je příkladem typ Měnitelná odkazu. Obsahuje členy, kteří můžou měnit hodnoty instance třídy. Je například typ neměnné odkaz <xref:System.String?displayProperty=fullName> třídy. Po má po vytvoření instance, jeho hodnota může změnit nikdy.  
  
 Modifikátor jen pro čtení ([jen pro čtení](/dotnet/csharp/language-reference/keywords/readonly) v jazyce C#, [jen pro čtení](/dotnet/visual-basic/language-reference/modifiers/readonly) v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], a [const](/cpp/cpp/const-cpp) v jazyce C++) na odkaz na typ pole (ukazatel v jazyce C++) brání pole nahrazuje jinou instanci typu odkazu. Modifikátor ale nezabrání data instance pole upravována prostřednictvím odkazového typu.  
  
 Pole pouze pro čtení se vyloučí z tohoto pravidla, ale místo toho způsobit porušení [CA2105: pole polí by neměly jen pro čtení](../code-quality/ca2105-array-fields-should-not-be-read-only.md) pravidlo.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, odeberte modifikátor jen pro čtení, nebo pokud narušující změně je přijatelné, nahraďte pole neměnné typu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, je-li typ pole se nedá změnit.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje deklaraci pole, která způsobí, že porušení tohoto pravidla.  
  
 [!code-cpp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CPP/ca2104-do-not-declare-read-only-mutable-reference-types_1.cpp)]
 [!code-csharp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CSharp/ca2104-do-not-declare-read-only-mutable-reference-types_1.cs)]
 [!code-vb[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/VisualBasic/ca2104-do-not-declare-read-only-mutable-reference-types_1.vb)]