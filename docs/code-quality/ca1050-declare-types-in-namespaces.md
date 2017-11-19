---
title: "CA1050: Deklarujte typy v oborech názvů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1050
- DeclareTypesInNamespaces
helpviewer_keywords:
- DeclareTypesInNamespaces
- CA1050
ms.assetid: 1002748d-ac8d-404f-85dd-7a12d1ad3e05
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c0aeaaf3531c45668b8804a6285be5df211c2754
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1050-declare-types-in-namespaces"></a>CA1050: Deklarujte typy v oborech názvů
|||  
|-|-|  
|TypeName|DeclareTypesInNamespaces|  
|CheckId|CA1050|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Typ veřejné nebo chráněného je definována mimo obor s názvem oboru názvů.  
  
## <a name="rule-description"></a>Popis pravidla  
 Typy jsou deklarované v oborech názvů, aby se zabránilo kolize názvů a jako způsob, jak uspořádat související typy v hierarchii objektu. Typy, které jsou mimo pojmenovaný obor názvů jsou v globálním oboru názvů, který nelze odkazovat v kódu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, zaškrtněte typ v oboru názvů.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 I když máte nikdy potlačit upozornění na toto pravidlo, je bezpečné k tomu, když sestavení nebude nikdy používat společně s ostatních sestavení.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje knihovnu, která má typ nesprávně deklarovaný mimo obor názvů a typ, který má stejný název deklarované v oboru názvů.  
  
 [!code-csharp[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_1.cs)]
 [!code-vb[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_1.vb)]  
  
## <a name="example"></a>Příklad  
 Následující aplikace používá knihovnu, která byla definována dříve. Všimněte si, že typ, který je deklarován mimo obor názvů se vytvoří při název `Test` není kvalifikovaná pomocí oboru názvů. Všimněte si také, že pro přístup `Test` zadejte `Goodspace`, je nutné zadat název oboru názvů.  
  
 [!code-csharp[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_2.cs)]
 [!code-vb[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_2.vb)]