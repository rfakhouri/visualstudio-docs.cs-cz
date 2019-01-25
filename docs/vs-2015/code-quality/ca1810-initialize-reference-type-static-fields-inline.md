---
title: 'CA1810: Inicializujte odkazový typ statického pole vloženě | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- InitializeReferenceTypeStaticFieldsInline
- CA1810
helpviewer_keywords:
- InitializeReferenceTypeStaticFieldsInline
- CA1810
ms.assetid: e9693118-a914-4efb-9550-ec659d8d97d2
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2722286af0d4c95fec30593047bedf1fe0ba4d2d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54785411"
---
# <a name="ca1810-initialize-reference-type-static-fields-inline"></a>CA1810: Inicializujte odkazový typ statického pole vloženě
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|InitializeReferenceTypeStaticFieldsInline|
|CheckId|CA1810|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Odkaz na typ deklaruje explicitní statický konstruktor.

## <a name="rule-description"></a>Popis pravidla
 Pokud typ deklaruje explicitní statický konstruktor, kompilátor just-in-time (JIT) ke každé statické metodě a konstruktoru instance tohoto typu přidá kontrolu, zda již byl dříve statický konstruktor zavolán. Statická inicializace se aktivuje při přístupu k jakékoli statického člena, nebo když je vytvořena instance typu. Statická inicializace ale neaktivuje, pokud deklarujete proměnnou typu, ale nepoužívejte ho, což může být důležité v případě, že inicializace mění globální stav.

 Všechna statická data je inicializována vložené a explicitní statický konstruktor není deklarován, kompilátory Microsoft intermediate language (MSIL) přidá `beforefieldinit` příznak a implicitní statický konstruktor, který inicializuje statických dat na typ jazyka MSIL definice. Když kompilátor JIT narazí `beforefieldinit` příznak, ve většině případů se nepřidají kontroly statického konstruktoru. Statická inicializace je zaručeno, ke kterým dochází za nějakou dobu předtím, než jsou přístupné žádná statická pole, ale ne předtím, než se vyvolá statickou metodu nebo instanci konstruktoru. Všimněte si, že se, že statická inicializace může probíhat kdykoli po deklarovat proměnnou typu.

 Kontroly statického konstruktoru mohou snížit výkon. Statický konstruktor se často slouží jenom k inicializaci statická pole, ve kterých je jenom nutné, že statická inicializace v tomto případě před první přístup statické pole. `beforefieldinit` Chování je vhodné pro tyto a většinu ostatních typů. Je jenom nevhodný při Statická inicializace má vliv na globální stav a je splněna jedna z následujících akcí:

-   Vliv na globální stav je nákladné a není potřeba, pokud typ není použit.

-   Globální stav účinky lze přistupovat bez přístupu k jakékoli statická pole typu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, inicializujte všechna statická data při deklaraci a statický konstruktor odeberte.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud výkon není žádný problém; nebo pokud globální stav změny, které jsou způsobeny Statická inicializace je vždycky musí zaručit udělat předtím, než je volána statická metoda typu nebo je vytvořena instance typu.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, `StaticConstructor`, který porušuje pravidla a typ, `NoStaticConstructor`, vložené inicializace splňovat pravidla, která nahradí statický konstruktor.

 [!code-csharp[FxCop.Performance.RefTypeStaticCtor#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.RefTypeStaticCtor/cs/FxCop.Performance.RefTypeStaticCtor.cs#1)]
 [!code-vb[FxCop.Performance.RefTypeStaticCtor#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.RefTypeStaticCtor/vb/FxCop.Performance.RefTypeStaticCtor.vb#1)]

 Poznámka: přidání `beforefieldinit` příznak na definici jazyka MSIL `NoStaticConstructor` třídy.

 **veřejné .class auto ansi StaticConstructor** **rozšiřuje [mscorlib]System.Object**
 **{**
 **} / / ukončení třídy StaticConstructor** 
 **.class veřejné automaticky ansi beforefieldinit NoStaticConstructor** **rozšiřuje [mscorlib]System.Object**
 **{** 
 **} / / ukončení třídy NoStaticConstructor**
## <a name="related-rules"></a>Související pravidla
 [CA2207: Inicializujte vloženou hodnotu statických polí](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)
