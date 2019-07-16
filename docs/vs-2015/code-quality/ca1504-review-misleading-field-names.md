---
title: 'CA1504: Zkontrolujte zavádějící názvy polí | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ReviewMisleadingFieldNames
- CA1504
helpviewer_keywords:
- CA1504
- ReviewMisleadingFieldNames
ms.assetid: 94136ff1-4aaf-4dc2-9170-48c171ab7499
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2203e99974e5f232e8c90badef7c28921b971cdb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68191203"
---
# <a name="ca1504-review-misleading-field-names"></a>CA1504: Zkontrolujte zavádějící názvy polí
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ReviewMisleadingFieldNames|
|CheckId|CA1504|
|Kategorie|Microsoft.Maintainability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Název pole instance začíná řetězcem "s_" a název `static` (`Shared` v [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) pole začíná předponou "m_".

## <a name="rule-description"></a>Popis pravidla
 Názvy polí, které začínají předponou "s_" jsou spojeny s statických dat mnoha uživateli. Podobně jsou spojeny s data instance (člen) názvy polí, které začínají předponou "m_". Snadněji udržována kódu názvy by měly dodržovat obecně používaných konvence.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, přejmenuje pole pomocí příslušné předpony. Pole souhlas s příponou aktuální přidáním nebo odebráním můžete také nastavit `static` modifikátor.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.
