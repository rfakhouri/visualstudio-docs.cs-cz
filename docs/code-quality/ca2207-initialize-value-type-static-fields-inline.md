---
title: 'CA2207: Inicializujte statická pole s typem hodnoty vloženě'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- InitializeValueTypeStaticFieldsInline
- CA2207
helpviewer_keywords:
- CA2207
- InitializeValueTypeStaticFieldsInline
ms.assetid: d1ea9d8b-ecc2-46ca-86e2-c41dd0e76658
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d2caeb78af5fed0c74c02c6e3f578fa34e765355
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920376"
---
# <a name="ca2207-initialize-value-type-static-fields-inline"></a>CA2207: Inicializujte statická pole s typem hodnoty vloženě

|||
|-|-|
|TypeName|InitializeValueTypeStaticFieldsInline|
|CheckId|CA2207|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez přerušení|

## <a name="cause"></a>příčina
Typ hodnoty deklaruje explicitní statický konstruktor.

## <a name="rule-description"></a>Popis pravidla
Je-li deklarován typ hodnoty, je napřed výchozí inicializací, kde jsou všechna pole typu hodnoty nastavena na hodnotu nula a všechna pole typu odkazu jsou nastavena na `null` hodnotu (`Nothing` v Visual Basic). Explicitní statický konstruktor je zaručen pouze před tím, než je volán konstruktor instance nebo statický člen typu. Proto pokud je typ vytvořen bez volání konstruktoru instance, není zaručeno spuštění statického konstruktoru.

Pokud jsou všechna statická data inicializována vložená a není deklarován žádný explicitní statický konstruktor C# , kompilátory a Visual Basic přidá `beforefieldinit` příznak do definice třídy jazyka MSIL. Kompilátory také přidávají privátní statický konstruktor, který obsahuje kód statické inicializace. Pro tento soukromý statický konstruktor je zaručeno, že bude spuštěn před tím, než budou k dispozici jakákoliv statická pole typu.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, proveďte inicializaci všech statických dat, je-li deklarována a odeberte statický konstruktor.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo.

## <a name="related-rules"></a>Související pravidla
[CA1810: Inicializovat vložená statická pole typu odkazu](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)