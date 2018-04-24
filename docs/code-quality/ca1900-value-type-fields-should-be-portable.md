---
title: 'CA1900: Pole hodnot by měla být přenosná'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1900
- ValueTypeFieldsShouldBePortable
helpviewer_keywords:
- ValueTypeFieldsShouldBePortable
- CA1900
ms.assetid: 1787d371-389f-4d39-b305-12b53bc0dfb9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 56c779095a68fc61c25412e6b895ea2bb5a635c3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1900-value-type-fields-should-be-portable"></a>CA1900: Pole hodnot by měla být přenosná
|||
|-|-|
|TypeName|ValueTypeFieldsShouldBePortable|
|CheckId|CA1900|
|Kategorie|Microsoft.Portability|
|Narušující změna|Ukončování řádků - li pole si můžete prohlédnout mimo sestavení.<br /><br /> Non narušující – Pokud pole není viditelná mimo sestavení.|

## <a name="cause"></a>příčina
 Toto pravidlo zkontroluje, že struktury, které jsou deklarovány s explicitní rozložení zarovnané správně při zařazen do nespravovaného kódu v 64bitových operačních systémech. IA-64 neumožňuje přistupuje k nezarovnané paměti a proces bude selhat, pokud není tato porušení pevný.

## <a name="rule-description"></a>Popis pravidla
 Struktury, které mají explicitní rozložení, který obsahuje chybně zarovnaných pole příčina havárií na 64bitové operační systémy.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Všechna pole, které jsou menší než 8 bajtů musí mít posuny, které je násobkem jejich velikost a pole, které jsou 8 bajtů nebo více musí mít posuny, které je násobkem 8. Jiným řešením je použití `LayoutKind.Sequential` místo `LayoutKind.Explicit`, pokud je možné logicky.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Toto upozornění má být potlačeno pouze v případě, že se vyskytuje v chybě.