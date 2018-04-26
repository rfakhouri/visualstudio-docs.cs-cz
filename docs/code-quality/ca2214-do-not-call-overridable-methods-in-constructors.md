---
title: 'CA2214: Nevolejte přepisovatelné metody v konstruktorech'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotCallOverridableMethodsInConstructors
- CA2214
helpviewer_keywords:
- CA2214
- DoNotCallOverridableMethodsInConstructors
ms.assetid: 335b57ca-a6e8-41b4-a20e-57ee172c97c3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b5ebcd4164f9db28d4cb1f150ee3a4bb21b21cde
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca2214-do-not-call-overridable-methods-in-constructors"></a>CA2214: Nevolejte přepisovatelné metody v konstruktorech
|||
|-|-|
|TypeName|DoNotCallOverridableMethodsInConstructors|
|CheckId|CA2214|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Konstruktor typu nezapečetěných volá metodu virtuální definovaný ve své třídě.

## <a name="rule-description"></a>Popis pravidla
 Pokud virtuální metoda je volána, skutečný typ, který provede metodu nevyberete až při spuštění. Když Konstruktor volá virtuální metodu, je možné, že nebyl proveden v konstruktoru pro instanci, která volá metodu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, nevolejte virtuální metody typu z konstruktorů typu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Omezit volání virtuální metody by se měla změnit konstruktoru.

## <a name="example"></a>Příklad
 Následující příklad ukazuje účinek bychom při tom porušili toto pravidlo. Testovací aplikace vytvoří instanci `DerivedType`, což způsobí, že její základní třída (`BadlyConstructedType`) konstruktor provést. `BadlyConstructedType`pro konstruktor nesprávně volá metodu virtuální `DoSomething`. Jak ukazuje výstup `DerivedType.DoSomething()` provede a nebude proto před `DerivedType`na konstruktoru.

 [!code-csharp[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/CSharp/ca2214-do-not-call-overridable-methods-in-constructors_1.cs)]
 [!code-vb[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/VisualBasic/ca2214-do-not-call-overridable-methods-in-constructors_1.vb)]

 Tento příklad vytvoří následující výstup.

 **Volání metody základní konstruktoru. ** 
 **Odvozené DoSomething nazývá - inicializovat? Ne**
**odvozené volání konstruktoru.**