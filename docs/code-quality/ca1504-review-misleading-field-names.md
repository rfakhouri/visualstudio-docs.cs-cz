---
title: "CA1504: Revize zavádějících názvů polí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ReviewMisleadingFieldNames
- CA1504
helpviewer_keywords:
- CA1504
- ReviewMisleadingFieldNames
ms.assetid: 94136ff1-4aaf-4dc2-9170-48c171ab7499
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: dc1317380eab4a63a7c60557fbec258485768885
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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