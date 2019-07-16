---
title: 'CA1821: Odstraňte prázdné finalizační metody | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RemoveEmptyFinalizers
- CA1821
helpviewer_keywords:
- CA1821
ms.assetid: 3f4855a0-e4a0-46e6-923c-4c3b7074048d
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 5a6175871e74bf3cb99610dce0926f0982f331d4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201672"
---
# <a name="ca1821-remove-empty-finalizers"></a>CA1821: Odeberte prázdné finalizační metody
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|RemoveEmptyFinalizers|
|CheckId|CA1821|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Typ implementuje finalizační metodu, která je prázdný, vyžaduje pouze základní typ finalizační metodu nebo volá pouze podmíněně vyslané metody.

## <a name="rule-description"></a>Popis pravidla
 Kdykoli je to možné, vyhněte se použití finalizačních metod kvůli dodatečným nárokům na výkon spojeným se sledováním životního cyklu objektu. Uvolňování paměti spustí finalizační metodu, předtím, než se shromáždí objektů. To znamená, že dvě kolekce se bude vyžadovat ke shromažďování objektu. Prázdná finalizační metoda zvyšuje touto přidanou režie bez žádnou výhodu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Odstraňte prázdné finalizační metody. Pokud se vyžaduje pro ladění finalizační metodu, uzavřete celý finalizační metodu v `#if DEBUG / #endif` direktivy.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte zprávy z tohoto pravidla. Selhání pro potlačení dokončení snižuje výkon a poskytuje žádné výhody.

## <a name="example"></a>Příklad
 Následující příklad ukazuje prázdná finalizační metoda, která by měla být odebrána, finalizační metodu, která by měl být uzavřen v `#if DEBUG / #endif` směrnicemi a finalizační metodu, která používá `#if DEBUG / #endif` direktivy správně.

 [!code-csharp[FxCop.Performance.RemoveEmptyFinalizers#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.RemoveEmptyFinalizers/cs/FxCop.Performance.RemoveEmptyFinalizers.cs#1)]
