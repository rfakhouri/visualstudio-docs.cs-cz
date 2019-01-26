---
title: 'CA2001: Vyhněte se volání problematických metod'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2001
- AvoidCallingProblematicMethods
helpviewer_keywords:
- CA2001
- AvoidCallingProblematicMethods
ms.assetid: 19db8edb-31ce-441c-b0de-a0f2746155b7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1c3a20179bb8463d059b5e7d7c82e045b3517f47
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54957622"
---
# <a name="ca2001-avoid-calling-problematic-methods"></a>CA2001: Vyhněte se volání problematických metod

|||
|-|-|
|TypeName|AvoidCallingProblematicMethods|
|CheckId|CA2001|
|Kategorie|Microsoft.Reliability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina

Člen volá potencionálně nebezpečnou nebo problematickou metodu.

## <a name="rule-description"></a>Popis pravidla

Vyhněte se volání zbytečných a potenciálně nebezpečných metod. Porušení tohoto pravidla vyvolá se v případě, že člen volá jedno z následujících metod:

|Metoda|Popis|
|------------|-----------------|
|<xref:System.GC.Collect%2A?displayProperty=fullName>|Volání uvolňování paměti. Shromáždit může výrazně ovlivnit výkon aplikace a je zřídka nezbytné. Další informace najdete v tématu [výkon Tidbits pro Rico Mariani](http://go.microsoft.com/fwlink/?LinkId=169256) blogu na webu MSDN.|
|<xref:System.Threading.Thread.Resume%2A?displayProperty=fullName><br /><br /> <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>|Thread.Suspend a Thread.Resume jsou zastaralé z důvodu jejich nepředvídatelné chování.  Použití jiných tříd v <xref:System.Threading> obor názvů, například <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex>, a <xref:System.Threading.Semaphore>, k synchronizaci vláken nebo chránit prostředky.|
|<xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A?displayProperty=fullName>|Metoda metody DangerousGetHandle představuje bezpečnostní riziko, protože může vrátit popisovač, který není platný. Zobrazit <xref:System.Runtime.InteropServices.SafeHandle.DangerousAddRef%2A> a <xref:System.Runtime.InteropServices.SafeHandle.DangerousRelease%2A> metody pro další informace o tom, jak použít metodu metody DangerousGetHandle bezpečně.|
|<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName><br /><br /> <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName><br /><br /> <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName>|Tyto metody můžete načítat sestavení z neočekávaných umístěních. Například zobrazit příspěvky blogu .NET CLR poznámky Suzanne Cookovy [funkci LoadFile vs. LoadFrom](http://go.microsoft.com/fwlink/?LinkId=164450) a [výběr kontextu vazby](http://go.microsoft.com/fwlink/?LinkId=164451) informace o metodách, které načítají sestavení.|
|[CoSetProxyBlanket](http://go.microsoft.com/fwlink/?LinkID=169250) (Ole32)<br /><br /> [CoInitializeSecurity](http://go.microsoft.com/fwlink/?LinkId=169255) (Ole32)|Podle času uživatelský kód začne provádět v spravovaného procesu je příliš pozdě spolehlivě volání funkce CoSetProxyBlanket. Modul CLR (CLR) má inicializace akce, které mohou bránit úspěšné uživatelé P/Invoke.<br /><br /> Pokud máte k volání funkce CoSetProxyBlanket pro spravovanou aplikaci, doporučujeme spustit proces pomocí spustitelného souboru nativního kódu (C++), volání funkce CoSetProxyBlanket v nativním kódu a pak spusťte aplikaci spravovaného kódu v procesu. (Nezapomeňte zadat číslo verze modulu runtime.)|

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, odeberte nebo nahraďte volání nebezpečnou nebo problematickou metodu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Zprávy z tohoto pravidla můžete potlačit pouze v případě, že jsou k dispozici žádné alternativy k metodě problematické.

## <a name="see-also"></a>Viz také:

- [Upozornění spolehlivosti](../code-quality/reliability-warnings.md)