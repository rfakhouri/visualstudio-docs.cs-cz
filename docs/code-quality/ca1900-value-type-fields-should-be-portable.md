---
title: 'CA1900: Pole typů hodnot by měla být přenosná'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 84861aa1d17f041061d1666d6f78c9d273b948b4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55037769"
---
# <a name="ca1900-value-type-fields-should-be-portable"></a>CA1900: Pole typů hodnot by měla být přenosná

|||
|-|-|
|TypeName|ValueTypeFieldsShouldBePortable|
|CheckId|CA1900|
|Kategorie|Microsoft.Portability|
|Narušující změna|Zásadní – Pokud je pole viditelné mimo sestavení.<br /><br /> Bez konce – Pokud pole není viditelné mimo sestavení.|

## <a name="cause"></a>Příčina
 Toto pravidlo zkontroluje, že budou při zařazení na nespravovaný kód v 64bitových operačních systémech správně zarovnány struktury, které jsou deklarovány pomocí explicitního rozložení. Nezarovnané přístupy a proces se chybově ukončit, pokud toto porušení nebyl vyřešen IA-64 není povolena.

## <a name="rule-description"></a>Popis pravidla
 Struktury, které mají explicitní rozložení obsahující nezarovnané pole příčina selhání v 64bitových operačních systémech.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Všechna pole, která jsou menší než 8 bajtů musí mít posuny, které jsou násobkem jejich velikost a pole, které mají 8 bajtů nebo více musí mít posuny, které jsou násobkem 8. Druhým řešením je použití `LayoutKind.Sequential` místo `LayoutKind.Explicit`, pokud přiměřené.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Toto upozornění má výjimka potlačit pouze v případě, že dojde k chybě.