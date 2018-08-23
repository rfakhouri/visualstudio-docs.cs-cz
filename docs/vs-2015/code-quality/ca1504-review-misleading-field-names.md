---
title: 'CA1504: Revize zavádějících názvů polí | Dokumentace Microsoftu'
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
ms.openlocfilehash: 6448d6e4c445b89e1910a5f67af6215bbf21d215
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628409"
---
# <a name="ca1504-review-misleading-field-names"></a>CA1504: Revize zavádějících názvů polí
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1504: revize zavádějících názvů polí](https://docs.microsoft.com/visualstudio/code-quality/ca1504-review-misleading-field-names).  
  
TypeName | ReviewMisleadingFieldNames |  
| ID kontroly | CA1504 |  
| Kategorie | Microsoft.Maintainability|  
| Zásadní změna | Ukončování bez |  
  
## <a name="cause"></a>příčina  
 Název pole instance začíná řetězcem "s_" a název `static` (`Shared` v [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) pole začíná předponou "m_".  
  
## <a name="rule-description"></a>Popis pravidla  
 Názvy polí, které začínají předponou "s_" jsou spojeny s statických dat mnoha uživateli. Podobně jsou spojeny s data instance (člen) názvy polí, které začínají předponou "m_". Snadněji udržována kódu názvy by měly dodržovat obecně používaných konvence.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, přejmenuje pole pomocí příslušné předpony. Pole souhlas s příponou aktuální přidáním nebo odebráním můžete také nastavit `static` modifikátor.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.



