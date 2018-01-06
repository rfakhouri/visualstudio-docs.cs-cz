---
title: "CA2228: Nedodávejte nevydané formáty prostředku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: dcbd6627e17a4dfe179f485a2439aaf04c1a01ae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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