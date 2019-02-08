---
title: 'CA2228: Nedodávejte nevydané formáty prostředku'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4355db8b15a3869e785589170bec3f80e8f08fbb
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55923405"
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228: Nedodávejte nevydané formáty prostředku

|||
|-|-|
|TypeName|DoNotShipUnreleasedResourceFormats|
|CheckId|CA2228|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina
 Soubor prostředků bylo vytvořeno pomocí verze rozhraní .NET Framework, která se momentálně nepodporuje.

## <a name="rule-description"></a>Popis pravidla
 Soubory prostředků, které byly vytvořeny pomocí předprodejní verze rozhraní .NET Framework nemusí být použitelné podporovanými verzemi rozhraní .NET Framework.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, vytvoření prostředku, který používá podporovanou verzi rozhraní .NET Framework.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.
