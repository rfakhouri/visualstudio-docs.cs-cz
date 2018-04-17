---
title: 'CA1025: Nahraďte opakované argumenty parametry pole | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1025
- ReplaceRepetitiveArgumentsWithParamsArray
helpviewer_keywords:
- ReplaceRepetitiveArgumentsWithParamsArray
- CA1025
ms.assetid: f009b340-dea3-4459-8fe1-2143aa8b5d0b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a9d42e7109d75f14d51e0e7834bc996f6f8864dc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1025-replace-repetitive-arguments-with-params-array"></a>CA1025: Nahraďte opakované argumenty polem parametrů
|||  
|-|-|  
|TypeName|ReplaceRepetitiveArgumentsWithParamsArray|  
|CheckId|CA1025|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Metoda veřejných nebo chráněné v veřejného typu má víc než třemi parametry a jeho poslední tři parametry jsou stejného typu.  
  
## <a name="rule-description"></a>Popis pravidla  
 Pole parametrů místo opakované argumenty používejte při přesný počet argumentů neznámý a proměnné argumenty jsou stejného typu, nebo může být předána jako stejného typu. Například <xref:System.Console.WriteLine%2A> metoda poskytuje pro obecné účely přetížení, které používá pole parametrů tak, aby přijímal libovolný počet <xref:System.Object> argumenty.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, nahraďte opakované argumenty pole parametrů.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečně potlačit upozornění na toto pravidlo; Tento návrh však může způsobit problémy použitelnost.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který je v rozporu toto pravidlo.  
  
 [!code-csharp[FxCop.Design.RepeatArgs#1](../code-quality/codesnippet/CSharp/ca1025-replace-repetitive-arguments-with-params-array_1.cs)]