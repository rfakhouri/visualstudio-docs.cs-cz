---
title: 'CA1724: Názvy typů by neměly odpovídat oborům názvů | Dokumentace Microsoftu'
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
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 5028646e5c937caad60a35e67ab9935a5755929a
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900224"
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724: Názvy typů by neměly odpovídat oborům názvů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1724: typ názvů by měl není shoda obory názvů](https://docs.microsoft.com/visualstudio/code-quality/ca1724-type-names-should-not-match-namespaces).

|||
|-|-|
|TypeName|TypeNamesShouldNotMatchNamespaces|
|CheckId|CA1724|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Název typu odpovídal tomu [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] názvy oborů názvů v porovnávání.

## <a name="rule-description"></a>Popis pravidla
 Názvy typů by neměly odpovídat názvům obory názvů, které jsou definovány v [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] knihovny tříd. Porušení tohoto pravidla může snížit použitelnost knihovny.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Vyberte název typu, který se neshoduje s názvem [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] oboru názvů pro knihovny tříd.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pro vývoj nových projektů, žádné známé scénáře nastat, pokud je třeba potlačit upozornění tohoto pravidla. Předtím, než můžete potlačit upozornění, pečlivě zvažte, jak uživatele vaše knihovna může být matoucí odpovídající název. Pro přesouvání knihovny, budete muset potlačit upozornění tohoto pravidla.



