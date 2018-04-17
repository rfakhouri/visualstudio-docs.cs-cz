---
title: 'CA1504: Revize zavádějících názvů polí | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- ReviewMisleadingFieldNames
- CA1504
helpviewer_keywords:
- CA1504
- ReviewMisleadingFieldNames
ms.assetid: 94136ff1-4aaf-4dc2-9170-48c171ab7499
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 592fc516dad51db10e80cdcbdf652cbf4329f4ec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1504-review-misleading-field-names"></a>CA1504: Revize zavádějících názvů polí
|||  
|-|-|  
|TypeName|ReviewMisleadingFieldNames|  
|CheckId|CA1504|  
|Kategorie|Microsoft.Maintainability|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Název pole instance začíná "s_" nebo název `static` (`Shared` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) pole začíná "m_".  
  
## <a name="rule-description"></a>Popis pravidla  
 Názvy polí, které začínají na "s_" jsou přidruženy k statických dat mnoha uživateli. Podobně platí jsou názvy polí, které začínají "m_" přidružené data instance (člen). Pro snadnější zachování kód postupujte podle názvy obvykle používané konvence.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, přejmenujte pole pomocí příslušnou předponu. Případně, ujistěte se, souhlasím s příponou aktuální přidáním nebo odebráním pole `static` modifikátor.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.