---
title: 'CA1308: Normalizujte řetězce na velká písmena'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1308
- NormalizeStringsToUppercase
helpviewer_keywords:
- NormalizeStringsToUppercase
- CA1308
ms.assetid: 7e9a7457-3f93-4938-ac6f-1389fba8d9cc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 358910be4245c5c00541a7a4f686226b6250e902
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2018
ms.locfileid: "45545697"
---
# <a name="ca1308-normalize-strings-to-uppercase"></a>CA1308: Normalizujte řetězce na velká písmena
|||
|-|-|
|TypeName|NormalizeStringsToUppercase|
|CheckId|CA1308|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Operace normalizuje řetězec na malá písmena.

## <a name="rule-description"></a>Popis pravidla
 Řetězce by měly být normalizovány na velká písmena. Malá skupina znaků, když jsou převedeny na malá písmena, nelze provést zpáteční cestu. Chcete-li provést zpáteční cestu načíst prostředky pro převod znaků ze jeden národního prostředí na jiné národní prostředí, která představuje znak data jiným způsobem a potom na přesně původní znaky z převedené znaky.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Změňte operace, které provádějí převod řetězce na malá písmena, proto, že jsou převedeny řetězce na velká písmena místo. Například změnit `String.ToLower(CultureInfo.InvariantCulture)` k `String.ToUpper(CultureInfo.InvariantCulture)`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění, nejsou při rozhodnutí o zabezpečení založeno na výsledku (například, když zobrazujete v uživatelském rozhraní).

## <a name="see-also"></a>Viz také:
 [Upozornění globalizace](../code-quality/globalization-warnings.md)