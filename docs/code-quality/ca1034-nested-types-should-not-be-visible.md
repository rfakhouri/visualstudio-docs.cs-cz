---
title: "CA1034: Vnořené typy by neměly být viditelné | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
helpviewer_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
ms.assetid: e9789a2c-2540-42a1-8705-ae7104011194
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: dc35514eab2344c086305ec88435ff8a32285e4f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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