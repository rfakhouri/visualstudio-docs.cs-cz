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
ms.openlocfilehash: 84dc7c20f4109f7d66ed83b22fcec36dacc5eb3f
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902935"
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228: Nedodávejte nevydané formáty prostředku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2228: Nedodávejte nevydané formáty prostředku](https://docs.microsoft.com/visualstudio/code-quality/ca2228-do-not-ship-unreleased-resource-formats).

|||
|-|-|
|TypeName|DoNotShipUnreleasedResourceFormats|
|CheckId|CA2228|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina
 Soubor prostředků bylo vytvořeno prostřednictvím verze [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] , která se momentálně nepodporuje.

## <a name="rule-description"></a>Popis pravidla
 Soubory prostředků, které byly vytvořeny pomocí předprodejní verze [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] nemusí být použitelné podporovanými verzemi rozhraní .NET Framework.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, vytvoření prostředku, který používá podporovanou verzi [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]tis.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.



