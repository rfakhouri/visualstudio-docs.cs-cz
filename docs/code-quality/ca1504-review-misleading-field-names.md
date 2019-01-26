---
title: 'CA1504: Zkontrolujte zavádějící názvy polí'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- ReviewMisleadingFieldNames
- CA1504
helpviewer_keywords:
- CA1504
- ReviewMisleadingFieldNames
ms.assetid: 94136ff1-4aaf-4dc2-9170-48c171ab7499
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: da99bab4235028f75146be1807162e93759d3eb9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54926459"
---
# <a name="ca1504-review-misleading-field-names"></a>CA1504: Zkontrolujte zavádějící názvy polí

|||
|-|-|
|TypeName|ReviewMisleadingFieldNames|
|CheckId|CA1504|
|Kategorie|Microsoft.Maintainability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Název pole instance začíná řetězcem "s_" a název `static` (`Shared` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) pole začíná předponou "m_".

## <a name="rule-description"></a>Popis pravidla
 Názvy polí, které začínají předponou "s_" jsou spojeny s statických dat mnoha uživateli. Podobně jsou spojeny s data instance (člen) názvy polí, které začínají předponou "m_". Snadněji udržována kódu názvy by měly dodržovat obecně používaných konvence.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, přejmenuje pole pomocí příslušné předpony. Pole souhlas s příponou aktuální přidáním nebo odebráním můžete také nastavit `static` modifikátor.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.