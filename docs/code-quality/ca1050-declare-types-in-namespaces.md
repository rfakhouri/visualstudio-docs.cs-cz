---
title: 'CA1050: Deklarujte typy v oborech názvů'
ms.date: 11/04/2016
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
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 869ff99243349ae01c63da0a7d9e6544761cbd39
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922499"
---
# <a name="ca1050-declare-types-in-namespaces"></a>CA1050: Deklarujte typy v oborech názvů

|||
|-|-|
|TypeName|DeclareTypesInNamespaces|
|CheckId|CA1050|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Veřejný nebo chráněný typ je definován mimo rozsah pojmenovaného oboru názvů.

## <a name="rule-description"></a>Popis pravidla
Typy jsou deklarovány v oborech názvů, aby se zabránilo kolizím názvů a jako způsob uspořádání souvisejících typů v hierarchii objektů. Typy, které jsou mimo libovolný pojmenovaný obor názvů, jsou v globálním oboru názvů, na který nelze odkazovat v kódu.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, umístěte typ do oboru názvů.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
I když nikdy nemusíte potlačit upozornění z tohoto pravidla, je bezpečné to provést, pokud sestavení nebude nikdy použito společně s jinými sestaveními.

## <a name="example"></a>Příklad
Následující příklad ukazuje knihovnu, která má nesprávně deklarovaný typ mimo obor názvů a typ, který má stejný název deklarovaný v oboru názvů.

[!code-csharp[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_1.cs)]
[!code-vb[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_1.vb)]

## <a name="example"></a>Příklad
Následující aplikace používá knihovnu, která byla definována dříve. Všimněte si, že typ deklarovaný mimo obor názvů je vytvořen, pokud název `Test` není kvalifikován oborem názvů. Všimněte si také, že pro `Test` přístup k `Goodspace`typu v je požadován název oboru názvů.

[!code-csharp[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_2.cs)]
[!code-vb[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_2.vb)]