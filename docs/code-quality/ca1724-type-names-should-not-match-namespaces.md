---
title: 'CA1724: Názvy typů by se neměly shodovat s obory názvů'
ms.date: 09/28/2018
ms.topic: reference
f1_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f81327324de937df57edfb36cae34d613f6298a5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546017"
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724: Názvy typů by neměly odpovídat oborům názvů

|||
|-|-|
|TypeName|TypeNamesShouldNotMatchNamespaces|
|CheckId|CA1724|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Název typu odpovídá názvu odkazovaného oboru názvů, který má jeden nebo více externě viditelné typy. Název porovnání nerozlišuje velká a malá písmena.

## <a name="rule-description"></a>Popis pravidla

Názvy uživatelsky vytvořených typů by neměly odpovídat názvům odkazované obory názvů, které mají externě viditelné typy. Porušení tohoto pravidla může snížit použitelnost knihovny.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Přejmenujte typ tak, aby neodpovídá názvu odkazovaného oboru názvů, který má externě viditelné typy.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pro vývoj nových projektů, žádné známé scénáře nastat, pokud je třeba potlačit upozornění tohoto pravidla. Předtím, než můžete potlačit upozornění, pečlivě zvažte, jak uživatele vaše knihovna může být matoucí odpovídající název. Pro přesouvání knihovny, budete muset potlačit upozornění tohoto pravidla.