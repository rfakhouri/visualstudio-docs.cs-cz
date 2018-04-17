---
title: 'CA1034: Vnořené typy by neměly být viditelné | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
helpviewer_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
ms.assetid: e9789a2c-2540-42a1-8705-ae7104011194
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: db5983dff8bf100c3215fd457f4dfbc5170c2d30
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1034-nested-types-should-not-be-visible"></a>CA1034: Vnořené typy by neměly být viditelné
|||  
|-|-|  
|TypeName|NestedTypesShouldNotBeVisible|  
|CheckId|CA1034|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Typ externě viditelné obsahuje deklaraci externě viditelného typu. Vnořené výčty a chráněné typy vyjmuté z tohoto pravidla.  
  
## <a name="rule-description"></a>Popis pravidla  
 Vnořené typy je typ deklarované v rámci oboru jiného typu. Vnořené typy jsou užitečné pro zapouzdření podrobnosti privátní implementace nadřazeného typu. Jsou-li vnořené typy používány za tímto účelem, neměly by být externě viditelné.  
  
 Nepoužívejte viditelné vnořené typy pro logické seskupení nebo aby se zabránilo kolize názvů; Místo toho použijte obory názvů.  
  
 Vnořené typy zahrnují představu o usnadnění člen, který není srozumitelný jasně některé programátory v jazyce.  
  
 Chráněné typy lze v podtřídách a vnořené typy ve scénářích přizpůsobení zálohy.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Pokud nemáte v úmyslu vnořené typ, který má být externě viditelné, změňte přístupnost typu. Vnořené typy, jinak hodnota odebrání jeho nadřazený objekt. Pokud účelem vnoření je zařadit do kategorií vnořeného typu, použijte místo toho vytvořit hierarchii oboru názvů.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který porušuje pravidlo.  
  
 [!code-cpp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CPP/ca1034-nested-types-should-not-be-visible_1.cpp)]
 [!code-csharp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CSharp/ca1034-nested-types-should-not-be-visible_1.cs)]
 [!code-vb[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/VisualBasic/ca1034-nested-types-should-not-be-visible_1.vb)]