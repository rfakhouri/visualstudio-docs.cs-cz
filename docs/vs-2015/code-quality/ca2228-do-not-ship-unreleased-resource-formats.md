---
title: 'CA2228: Nedodávejte nevydané formáty prostředku | Dokumentace Microsoftu'
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
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 324803c5a840d1ef728d47845e548acc886348ad
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667373"
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228: Nedodávejte nevydané formáty prostředku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2228: Nedodávejte nevydané formáty prostředku](https://docs.microsoft.com/visualstudio/code-quality/ca2228-do-not-ship-unreleased-resource-formats).  
  
TypeName | DoNotShipUnreleasedResourceFormats |  
| ID kontroly | CA2228 |  
| Kategorie | Microsoft.Usage|  
| Zásadní změna | Bez zásadní |  
  
## <a name="cause"></a>příčina  
 Soubor prostředků bylo vytvořeno prostřednictvím verze [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] , která se momentálně nepodporuje.  
  
## <a name="rule-description"></a>Popis pravidla  
 Soubory prostředků, které byly vytvořeny pomocí předprodejní verze [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] nemusí být použitelné podporovanými verzemi rozhraní .NET Framework.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, vytvoření prostředku, který používá podporovanou verzi [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]tis.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.



