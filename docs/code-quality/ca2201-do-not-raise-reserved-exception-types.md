---
title: 'CA2201: Nevyvolávejte vyhrazené typy výjimek'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotRaiseReservedExceptionTypes
- CA2201
helpviewer_keywords:
- CA2201
- DoNotRaiseReservedExceptionTypes
ms.assetid: dd14ef5c-80e6-41a5-834e-eba8e2eae75e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 696eed674dd2b85ec048290ba88084751230635d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca2201-do-not-raise-reserved-exception-types"></a>CA2201: Nevyvolávejte vyhrazené typy výjimek
|||
|-|-|
|TypeName|DoNotRaiseReservedExceptionTypes|
|CheckId|CA2201|
|Kategorie|Microsoft.Usage|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Metoda vyvolá typ výjimky, která je příliš obecné nebo který je vyhrazený modulem runtime.

## <a name="rule-description"></a>Popis pravidla
 Následující typy výjimek jsou příliš široké, chcete-li poskytovat dostatečné informace pro uživatele:

-   <xref:System.Exception?displayProperty=fullName>

-   <xref:System.ApplicationException?displayProperty=fullName>

-   <xref:System.SystemException?displayProperty=fullName>

 Následující typy výjimek jsou vyhrazeny a by měl být vyvolané pouze modul common language runtime:

-   <xref:System.ExecutionEngineException?displayProperty=fullName>

-   <xref:System.IndexOutOfRangeException?displayProperty=fullName>

-   <xref:System.NullReferenceException?displayProperty=fullName>

-   <xref:System.OutOfMemoryException?displayProperty=fullName>

 **Nevyvolá výjimku obecné výjimky**

 Pokud jste výjimku typu obecné výjimce, jako <xref:System.Exception> nebo <xref:System.SystemException> do knihovny nebo framework, vynutí si příjemci k zachycení všechny výjimky, včetně neznámé výjimky, které neznáte určuje způsob zpracování.

 Místo toho buď výjimku více odvozený typ, který již existuje v rozhraní framework, nebo vytvořit vlastní typ odvozený z <xref:System.Exception>.

 **Vyvolat konkrétní výjimky**

 V následující tabulce jsou uvedeny parametry a výjimek, které má být vyvolána při ověření parametru, včetně parametr hodnoty v přistupující objekt set vlastnosti:

|Popis parametru|Výjimka|
|---------------------------|---------------|
|`null` Referenční dokumentace|<xref:System.ArgumentNullException?displayProperty=fullName>|
|Mimo povolený rozsah hodnot (například index pro kolekci nebo seznamu)|<xref:System.ArgumentOutOfRangeException?displayProperty=fullName>|
|Neplatný `enum` hodnota|<xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=fullName>|
|Obsahuje formátu, který nesplňuje specifikace parametru metody (například řetězec formátu pro `ToString(String)`)|<xref:System.FormatException?displayProperty=fullName>|
|Jinak neplatných|<xref:System.ArgumentException?displayProperty=fullName>|

 Když je neplatný pro aktuálního stavu k objektu throw operace <xref:System.InvalidOperationException?displayProperty=fullName>

 Při provádění operace v objektu, který byl zlikvidován throw <xref:System.ObjectDisposedException?displayProperty=fullName>

 Pokud není podporována operace (například v překryté **Stream.Write** v datovém proudu otevřít pro čtení) throw <xref:System.NotSupportedException?displayProperty=fullName>

 Při převodu z by způsobilo přetečení (například na přetížení operátoru explicitní přetypování) throw <xref:System.OverflowException?displayProperty=fullName>

 U všech jiných situacích zvažte vytvoření vlastního typu, která je odvozena od <xref:System.Exception> a která výjimku.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, změňte typ vyvolaná výjimka na konkrétní typ, který není jedním z vyhrazené typy.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="related-rules"></a>Související pravidla
 [CA1031: Nezachycujte výjimky obecného typu](../code-quality/ca1031-do-not-catch-general-exception-types.md)