---
title: 'CA1500: Názvy proměnných by neměly odpovídat názvům polí'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
helpviewer_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
ms.assetid: fa0e5029-79e9-4a33-8576-787ac3c26c39
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f291b603c94292cc86536a212a4ab8286600740b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1500-variable-names-should-not-match-field-names"></a>CA1500: Názvy proměnných by neměly odpovídat názvům polí
|||
|-|-|
|TypeName|VariableNamesShouldNotMatchFieldNames|
|CheckId|CA1500|
|Kategorie|Microsoft.Maintainability|
|Narušující změna|Při vyvolání na parametr, který má stejný název jako pole:<br /><br /> Pevné – Pokud pole i metoda, který deklaruje parametr je nemohou vidět mimo sestavení, bez ohledu na změny, které provedete.<br />-Narušující – Pokud změníte název pole a mimo sestavení si můžete prohlédnout.<br />-Nejnovější – Pokud změníte název parametru, a metody, která ji deklaruje si můžete prohlédnout mimo sestavení.<br /><br /> Při vyvolání na místní proměnné, která má stejný název jako pole:<br /><br /> Pevné – Pokud toto pole je nemohou vidět mimo sestavení, bez ohledu na změny, které provedete.<br />Pevné – Pokud změníte název místní proměnné a neměňte název pole.<br />-Nejnovější – Pokud měníte název pole a lze je zobrazit mimo sestavení.|

## <a name="cause"></a>příčina
 Metoda instance deklaruje parametr nebo místní proměnné, jejíž název odpovídá deklarující typ pole instance. K zachycení lokální proměnné, které porušují pravidlo, musí být vytvořené otestované sestavení pomocí informace o ladění a přidružené programového souboru databáze (.pdb) musí být k dispozici.

## <a name="rule-description"></a>Popis pravidla
 Pokud název pole instance odpovídá parametru nebo místní název proměnné, instance pole je přístupné pomocí `this` (`Me` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) – klíčové slovo při uvnitř těla metody. Při údržbě kódu, je snadné zapomněli tento rozdíl a předpokládá, že parametr/místní proměnná odkazuje na pole instance, což vede k chybám. To platí především pro těla náročná metoda.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, přejmenujte parametr nebo proměnná nebo pole.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje dva porušení pravidla.

 [!code-vb[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/VisualBasic/ca1500-variable-names-should-not-match-field-names_1.vb)]
 [!code-csharp[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/CSharp/ca1500-variable-names-should-not-match-field-names_1.cs)]