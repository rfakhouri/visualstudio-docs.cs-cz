---
title: 'CA1500: Názvy proměnných by neměly odpovídat názvům polí'
ms.date: 11/04/2016
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
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 740edb9861d2e3e758a36dfc067cb85fe4fc2c7e
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55918595"
---
# <a name="ca1500-variable-names-should-not-match-field-names"></a>CA1500: Názvy proměnných by neměly odpovídat názvům polí

|||
|-|-|
|TypeName|VariableNamesShouldNotMatchFieldNames|
|CheckId|CA1500|
|Kategorie|Microsoft.Maintainability|
|Narušující změna|Při vyvolání na parametr, který má stejný název jako pole:<br /><br /> – Pevná – Pokud pole a metody, která deklaruje parametr je nemohou vidět mimo sestavení, bez ohledu na to, které provedete změnu.<br />-Zásadní - li změnit název pole a jsou viditelné mimo sestavení.<br />-Zásadní – Pokud změníte název parametru a metodu, která deklaruje ji lze zobrazit mimo sestavení.<br /><br /> Při vyvolání na lokální proměnné, která má stejný název jako pole:<br /><br /> – Pevná – Pokud pole nejsou viditelné mimo sestavení, bez ohledu na to, které provedete změnu.<br />– Pevná – Pokud změníte název místní proměnné a neměňte název pole.<br />-Dopadem na dřívější kód - li změnit název pole a jsou viditelné mimo sestavení.|

## <a name="cause"></a>Příčina

Metoda instance deklaruje parametr nebo místní proměnná, jejíž název odpovídá poli instance deklarovaného typu. K zachycení místní proměnné, které porušují pravidlo, musí být sestaveny testované sestavení s použitím informací o ladění a přidružené programového souboru databáze (PDB) musí být k dispozici.

## <a name="rule-description"></a>Popis pravidla

Když se název pole instance shoduje, parametr nebo název místní proměnné, je přístup pole instance `this` (`Me` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) – klíčové slovo Pokud uvnitř těla metody. Při údržbě kódu, je snadné zapomenout tento rozdíl a předpokládá, že parametr/místní proměnná odkazuje na pole instance, což vede k chybám. To platí zejména pro delší těl metod.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, přejmenujte parametr nebo proměnná nebo pole.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad

Následující příklad ukazuje dva porušení tohoto pravidla.

[!code-vb[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/VisualBasic/ca1500-variable-names-should-not-match-field-names_1.vb)]
[!code-csharp[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/CSharp/ca1500-variable-names-should-not-match-field-names_1.cs)]