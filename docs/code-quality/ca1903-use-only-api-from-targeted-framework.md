---
title: 'CA1903: Použijte pouze API z cílového rozhraní .NET Framework'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseOnlyAPIFromTargetedFramework
- CA1903
helpviewer_keywords:
- UseOnlyApiFromTargetedFramework
- CA1903
ms.assetid: efdb5cc7-bbd8-4fa7-9fff-02b91e59350e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b4f49c8a4da3ad746e5221bb689285c89d48e6e1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca1903-use-only-api-from-targeted-framework"></a>CA1903: Použijte pouze API z cílového rozhraní .NET Framework
|||
|-|-|
|TypeName|UseOnlyApiFromTargetedFramework|
|CheckId|CA1903|
|Kategorie|Microsoft.Portability|
|Narušující změna|Ukončování řádků - při vyvolání s podpisem externě viditelné člen nebo typu.<br /><br /> Bez narušující - při vyvolání do těla metody.|

## <a name="cause"></a>příčina
 Používá typ nebo člena typu, která byla zavedená v aktualizaci service pack, která nebyla součástí cílové rozhraní projektu nebo člena.

## <a name="rule-description"></a>Popis pravidla
 Nové členy a typy byly zahrnuté v rozhraní .NET Framework 2.0 Service Pack 1 a 2, .NET Framework 3.0 Service Pack 1 a 2 a rozhraní .NET Framework 3.5 Service Pack 1. Projekty, které používají hlavní verze rozhraní .NET Framework neúmyslně může trvat závislostí na těchto nových rozhraní API. Pokud chcete zabránit tuto závislost, toto pravidlo aktivuje na použití jakékoli nové členy a typy, které nebyly zahrnuty ve výchozím nastavení s cílový framework projektu na.

 **Cílová architektura a závislosti sady Service Pack.**

|||
|-|-|
|Pokud je cílový framework|Aktivuje se na použití členů byla zavedená v|
|.NET Framework 2.0|Rozhraní .NET framework 2.0 SP1, .NET Framework 2.0 s aktualizací SP2|
|.NET Framework 3.0|Rozhraní .NET framework 2.0 SP1, .NET Framework 2.0 SP2, rozhraní .NET Framework 3.0 SP1, .NET Framework 3.0 SP2|
|.NET Framework 3.5|.NET Framework 3.5 SP1|
|.NET Framework 4|Není k dispozici|

 Chcete-li změnit cílový framework projektu na, [cílení na konkrétní verzi rozhraní .NET Framework](../ide/targeting-a-specific-dotnet-framework-version.md).

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li odebrat závislost na aktualizaci service pack, odeberte všechny použití nového člena nebo typu. Pokud je záměrné závislost, potlačení upozornění nebo vypnout toto pravidlo.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pokud jste to není záměrné závislost na zadaný service pack není potlačení upozornění od tohoto pravidla. V této situaci se nemusí podařit spustit bez této aktualizace service pack nainstalována v systémech vaší aplikace. Potlačit upozornění nebo vypněte toto pravidlo, pokud jste to byli záměrné závislost.

## <a name="example"></a>Příklad
 Následující příklad ukazuje třídu, která používá typ DateTimeOffset, který je dostupný jenom v rozhraní .NET 2.0 Service Pack 1. Tento příklad vyžaduje, aby vybral rozhraní .NET Framework 2.0 v rozevíracím seznamu cílové rozhraní ve vlastnostech projektu.

 [!code-csharp[FxCop.Portability.UseOnlyApiFromTargetedFramework#1](../code-quality/codesnippet/CSharp/ca1903-use-only-api-from-targeted-framework_1.cs)]

## <a name="example"></a>Příklad
 Následující příklad popisuje výš porušení opravy nahrazením použití typu DateTimeOffset typu datum a čas.

 [!code-csharp[FxCop.Portability.UseOnlyApiFromTargetedFramework2#1](../code-quality/codesnippet/CSharp/ca1903-use-only-api-from-targeted-framework_2.cs)]

## <a name="see-also"></a>Viz také
 [Upozornění přenositelnosti](../code-quality/portability-warnings.md) [cílení na konkrétní rozhraní .NET Framework verze](../ide/targeting-a-specific-dotnet-framework-version.md)