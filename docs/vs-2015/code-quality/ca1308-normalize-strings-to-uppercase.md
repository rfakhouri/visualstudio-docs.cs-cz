---
title: 'CA1308: Normalizujte řetězce na velká písmena | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-devops-test
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
ms.openlocfilehash: 6b2145b86da9cbc792b5baf16f19e94f24e148d5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53913274"
---
# <a name="ca1308-normalize-strings-to-uppercase"></a>CA1308: Normalizujte řetězce na velká písmena
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
