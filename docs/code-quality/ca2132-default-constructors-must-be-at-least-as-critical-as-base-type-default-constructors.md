---
title: 'CA2132: Výchozí konstruktory musí být alespoň tak kritické, jako výchozí konstruktory základního typu'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2132
ms.assetid: e758afa1-8bde-442a-8a0a-bd1ea7b0ce4d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cfe6e4f3ce896e5ae3d728a002bf2caf9f1948ef
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55013532"
---
# <a name="ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors"></a>CA2132: Výchozí konstruktory musí být alespoň tak kritické, jako výchozí konstruktory základního typu

|||
|-|-|
|TypeName|DefaultConstructorsMustHaveConsistentTransparency|
|CheckId|CA2132|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

> [!NOTE]
> Toto upozornění se použije pouze na kód, který je spuštěn CoreCLR (verze CLR, který je specifický pro webové aplikace Silverlight).

## <a name="cause"></a>Příčina

Atribut transparentnosti výchozího konstruktoru odvozené třídy není tak kritický jako transparentnosti základní třídy.

## <a name="rule-description"></a>Popis pravidla

Typy a členy, které mají <xref:System.Security.SecurityCriticalAttribute> nelze použít kódem aplikace Silverlight. Typy a členy kritické z hlediska zabezpečení lze použít pouze prostřednictvím důvěryhodného kódu v knihovně tříd rozhraní .NET Framework aplikace Silverlight. Protože veřejné nebo chráněné konstrukce v odvozené třídě musí mít stejnou nebo větší transparentnost než jejich základní třída, nelze třídu v aplikaci odvodit z třídy označené jako SecurityCritical.

Pro CoreCLR kód platformy Pokud základní typ nemá veřejný nebo chráněný neprůhledné výchozí konstruktor. potom odvozený typ musí dodržovat pravidla dědičnosti výchozí konstruktor. Odvozený typ musí také mít výchozí konstruktor a tento konstruktor musí být dlouhý aspoň jako kritické výchozí konstruktor třídy základního typu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li vyřešit porušení zásady, odeberte typ nebo není odvozen od neprůhledných typ zabezpečení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění tohoto pravidla. Porušení tohoto pravidla kódem aplikace, bude výsledkem CoreCLR odmítá načíst typ s <xref:System.TypeLoadException>.

### <a name="code"></a>Kód

[!code-csharp[FxCop.Security.CA2132.DefaultConstructorsMustHaveConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors_1.cs)]