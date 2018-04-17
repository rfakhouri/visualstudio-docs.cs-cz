---
title: 'CA2228: Nedodávejte nevydané formáty prostředku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b244dda388e5044b910259a4e92266671722e562
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228: Nedodávejte nevydané formáty prostředku
|||  
|-|-|  
|TypeName|DoNotShipUnreleasedResourceFormats|  
|CheckId|CA2228|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Zdrojového souboru byl vytvořený pomocí verze [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] , se aktuálně nepodporuje.  
  
## <a name="rule-description"></a>Popis pravidla  
 Soubory prostředků, které byly vytvořené pomocí předprodejní verze [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] nemusí být použitelná pro podporované verze rozhraní .NET Framework.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, vytvoření prostředku, který používá podporovanou verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]kB.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.