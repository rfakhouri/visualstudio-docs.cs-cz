---
title: 'CA1900: Pole typů hodnot by měla být přenosná'
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f734d0cf28a5aec28ebbf635dd384efe176b1774
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921323"
---
# <a name="ca1900-value-type-fields-should-be-portable"></a>CA1900: Pole typů hodnot by měla být přenosná

|||
|-|-|
|TypeName|ValueTypeFieldsShouldBePortable|
|CheckId|CA1900|
|Kategorie|Microsoft. přenositelnost|
|Narušující změna|Přerušení – Pokud se pole může zobrazit mimo sestavení.<br /><br /> Bez přerušení – Pokud pole není viditelné mimo sestavení.|

## <a name="cause"></a>příčina
Toto pravidlo kontroluje, zda struktury, které jsou deklarovány s explicitním rozložením, budou správně zarovnány při zařazení do nespravovaného kódu v 64 operačních systémech. IA-64 neumožňuje nezarovnaný přístup k paměti a proces se nezdaří, pokud toto porušení není opraveno.

## <a name="rule-description"></a>Popis pravidla
Struktury, které mají explicitní rozložení obsahující nesprávně zarovnaná pole, způsobují chyby v 64 operačních systémech.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Všechna pole, která jsou menší než 8 bajtů, musí mít posuny, které mají násobek jejich velikosti, a pole, která jsou 8 bajtů nebo více, musí mít posuny, které jsou násobkem 8. Jiné řešení je vhodné použít `LayoutKind.Sequential` `LayoutKind.Explicit`místo, pokud je to přijatelné.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Toto upozornění by mělo být potlačeno pouze v případě, že dojde k chybě.