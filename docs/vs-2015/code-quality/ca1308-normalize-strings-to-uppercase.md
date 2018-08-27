---
title: 'CA1308: Normalizujte řetězce na velká písmena | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1308
- NormalizeStringsToUppercase
helpviewer_keywords:
- NormalizeStringsToUppercase
- CA1308
ms.assetid: 7e9a7457-3f93-4938-ac6f-1389fba8d9cc
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8f5a40d412b8ea9616dd75d7e0424ba447b5a185
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900779"
---
# <a name="ca1308-normalize-strings-to-uppercase"></a>CA1308: Normalizujte řetězce na velká písmena
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1308: Normalizujte řetězce na velká písmena](https://docs.microsoft.com/visualstudio/code-quality/ca1308-normalize-strings-to-uppercase).

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

## <a name="see-also"></a>Viz také
 [Upozornění globalizace](../code-quality/globalization-warnings.md)



