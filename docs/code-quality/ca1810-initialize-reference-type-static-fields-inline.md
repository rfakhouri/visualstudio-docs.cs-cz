---
title: 'CA1810: Inicializujte odkazový typ statického pole vloženě'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- InitializeReferenceTypeStaticFieldsInline
- CA1810
helpviewer_keywords:
- InitializeReferenceTypeStaticFieldsInline
- CA1810
ms.assetid: e9693118-a914-4efb-9550-ec659d8d97d2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b31a0bbea244d5d196364517b5c5a2ca8d7a53a1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31914637"
---
# <a name="ca1810-initialize-reference-type-static-fields-inline"></a>CA1810: Inicializujte odkazový typ statického pole vloženě
|||
|-|-|
|TypeName|InitializeReferenceTypeStaticFieldsInline|
|CheckId|CA1810|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Typ odkazu deklaruje explicitní statického konstruktoru.

## <a name="rule-description"></a>Popis pravidla
 Pokud typ deklaruje explicitní statický konstruktor, kompilátor just-in-time (JIT) ke každé statické metodě a konstruktoru instance tohoto typu přidá kontrolu, zda již byl dříve statický konstruktor zavolán. Statické inicializace se aktivuje při přístupu k jakékoli statický člen, nebo když je vytvořena instance typu. Statické inicializace však není aktivuje, pokud deklarovat proměnnou typu, ale nepoužívá, může být důležité, pokud se inicializace změní globální stav.

 Všechny statických dat je inicializovaného vložené a není deklarovaný explicitní statického konstruktoru, kompilátory (MSIL intermediate language) Microsoft přidá `beforefieldinit` příznak a implicitní statický konstruktor, který inicializuje statických dat na typ MSIL definice. Když kompilátor JIT narazí `beforefieldinit` příznak, ve většině případů nejsou přidány kontroly statického konstruktoru. Statické inicializace záruku, že každý v jiné době před všechny statické pole ke kterým se přistupuje, ale není, před vyvoláním konstruktoru statickou metodu nebo instanci. Všimněte si, že statické inicializace situaci může dojít, kdykoli po proměnné typu je deklarován.

 Kontroly statického konstruktoru mohou snížit výkon. Statický konstruktor se často používají pouze pro inicializaci statická pole, ve kterých pouze ujistěte se, že statické inicializace v tomto případě před prvním přístupu statické pole. `beforefieldinit` Chování je vhodné pro tyto a většina ostatních typů. Je pouze nevhodných při statické inicializace ovlivňuje globální stav a je splněna jedna z následujících akcí:

-   Vliv na globální stav je nákladná a pokud se nepoužívá typ není potřeba.

-   Globální stav důsledky dalo přistupovat bez přístupu k jakékoli statická pole typu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, inicializujte všechna statická data při deklaraci a statický konstruktor odeberte.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění na toto pravidlo, pokud výkon není důležité; nebo pokud globální stav změny, které jsou způsobeny statické inicializace je nákladná, nebo musí být zaručeno udělat předtím, než se nazývá statickou metodu typu nebo vytvoření instance typu.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typu, `StaticConstructor`, která porušuje pravidlo a typu, `NoStaticConstructor`, který nahradí statického konstruktoru vložené inicializace splňovat pravidla.

 [!code-csharp[FxCop.Performance.RefTypeStaticCtor#1](../code-quality/codesnippet/CSharp/ca1810-initialize-reference-type-static-fields-inline_1.cs)]
 [!code-vb[FxCop.Performance.RefTypeStaticCtor#1](../code-quality/codesnippet/VisualBasic/ca1810-initialize-reference-type-static-fields-inline_1.vb)]

 Poznámka: přidání `beforefieldinit` příznak na definici MSIL `NoStaticConstructor` třídy.

 **.class veřejné automaticky ansi StaticConstructor** **rozšiřuje [mscorlib]System.Object**
 **{**
 **} / / konec třídy StaticConstructor** 
 **.class veřejné automaticky ansi beforefieldinit NoStaticConstructor** **rozšiřuje [mscorlib]System.Object**
 **{** 
 **} / / konec třídy NoStaticConstructor**
## <a name="related-rules"></a>Související pravidla
 [CA2207: Inicializujte vloženou hodnotu statických polí](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)