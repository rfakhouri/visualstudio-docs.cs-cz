---
title: 'CA1050: Deklarujte typy v oborech názvů'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1050
- DeclareTypesInNamespaces
helpviewer_keywords:
- DeclareTypesInNamespaces
- CA1050
ms.assetid: 1002748d-ac8d-404f-85dd-7a12d1ad3e05
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 5cb2000249e7e809f4570d93703c0c15093ec2cb
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53845230"
---
# <a name="ca1050-declare-types-in-namespaces"></a>CA1050: Deklarujte typy v oborech názvů

|||
|-|-|
|TypeName|DeclareTypesInNamespaces|
|CheckId|CA1050|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejný nebo chráněný typ definovaný vně rozsahu pojmenovaného oboru názvů.

## <a name="rule-description"></a>Popis pravidla
 Typy jsou deklarovány v oborech názvů, aby se zabránilo kolize názvů a zároveň jako způsob organizace souvisejících typů v hierarchii objektů. Typy, které jsou mimo všechny pojmenovaného oboru názvů jsou v globálním oboru názvů, který se nedá odkazovat v kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, umístěte typ v oboru názvů.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 I když si už nikdy nemusíte potlačit upozornění tohoto pravidla, je bezpečné k tomu, když sestavení nebude nikdy používat společně s ostatními sestaveními.

## <a name="example"></a>Příklad
 Následující příklad ukazuje knihovnu, která má typ nesprávně deklarované mimo obor názvů a typ, který má stejný název deklarovaný v oboru názvů.

 [!code-csharp[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_1.cs)]
 [!code-vb[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_1.vb)]

## <a name="example"></a>Příklad
 Následující aplikace používá knihovnu, která byla definována dříve. Všimněte si, že je vytvořen typ, který je deklarovaná mimo obor názvů, když název `Test` není kvalifikován pomocí oboru názvů. Všimněte si také, že pro přístup k `Test` zadejte `Goodspace`, vyžaduje se název oboru názvů.

 [!code-csharp[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_2.cs)]
 [!code-vb[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_2.vb)]