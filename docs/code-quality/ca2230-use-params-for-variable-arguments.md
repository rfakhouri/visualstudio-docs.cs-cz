---
title: "CA2230: Použijte parametry pro proměnné argumenty | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UseParamsForVariableArguments
- CA2230
helpviewer_keywords:
- CA2230
- UseParamsForVariableArguments
ms.assetid: bf98b733-4855-4110-9f16-eba5a9e79421
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 10920c4ff9083b52e2d35f7fa151644b89bb1102
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2230-use-params-for-variable-arguments"></a>CA2230: Použijte parametry pro proměnné argumenty
|||  
|-|-|  
|TypeName|UseParamsForVariableArguments|  
|CheckId|CA2230|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Typ veřejné nebo chráněného obsahuje veřejný nebo chráněné metody, která používá `VarArgs` konvence volání.  
  
## <a name="rule-description"></a>Popis pravidla  
 `VarArgs` Konvence volání se používá s určitým metoda definice, které trvat proměnný počet parametrů. Metoda pomocí `VarArgs` konvence volání není specifikace CLS (Common Language) kompatibilní a nemusí být dostupné v rámci programovacích jazyků.  
  
 V jazyce C# `VarArgs` konvence volání se používá při seznam parametrů metoda končí `__arglist` – klíčové slovo. Visual Basic nepodporuje `VarArgs` volání konvence a Visual C++ umožňuje jeho použití pouze v nespravovaném kódu, který používá se třemi tečkami `...` zápis.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla v jazyku C#, použijte [parametry](/dotnet/csharp/language-reference/keywords/params) – klíčové slovo místo `__arglist`.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje dva způsoby, jednu, která porušuje pravidlo a ten, který splňuje pravidlo.  
  
 [!code-csharp[FxCop.Usage.UseParams#1](../code-quality/codesnippet/CSharp/ca2230-use-params-for-variable-arguments_1.cs)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Reflection.CallingConventions?displayProperty=fullName>   
 [Jazyková nezávislost a jazykově nezávislé komponenty](http://msdn.microsoft.com/Library/4f0b77d0-4844-464f-af73-6e06bedeafc6)