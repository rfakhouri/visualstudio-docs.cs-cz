---
title: 'CA2001: Vyhněte se volání problematických metod | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2001
- AvoidCallingProblematicMethods
helpviewer_keywords:
- CA2001
- AvoidCallingProblematicMethods
ms.assetid: 19db8edb-31ce-441c-b0de-a0f2746155b7
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 26f50580c8d29e24b25a9dad520a81d22a3dfc0c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68189075"
---
# <a name="ca2001-avoid-calling-problematic-methods"></a>CA2001: Vyhněte se volání problematických metod
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidCallingProblematicMethods|
|CheckId|CA2001|
|Kategorie|Microsoft.Reliability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Člen volá potencionálně nebezpečnou nebo problematickou metodu.

## <a name="rule-description"></a>Popis pravidla
 Vyhněte se volání zbytečných a potenciálně nebezpečných metod.

 Porušení tohoto pravidla vyvolá se v případě, že člen volá jedno z následujících metod.

|Metoda|Popis|
|------------|-----------------|
|<xref:System.GC.Collect%2A?displayProperty=fullName>|Volání uvolňování paměti. Shromáždit může výrazně ovlivnit výkon aplikace a je zřídka nezbytné. Další informace najdete v tématu [výkon Tidbits pro Rico Mariani](http://go.microsoft.com/fwlink/?LinkId=169256) blogu na webu MSDN.|
|<xref:System.Threading.Thread.Resume%2A?displayProperty=fullName><br /><br /> <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>|Thread.Suspend a Thread.Resume jsou zastaralé z důvodu jejich nepředvídatelné chování.  Použití jiných tříd v <xref:System.Threading> obor názvů, jako například <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex>, a <xref:System.Threading.Semaphore> pro synchronizaci vláken nebo chránit prostředky.|
|<xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A?displayProperty=fullName>|Metoda metody DangerousGetHandle představuje bezpečnostní riziko, protože může vrátit popisovač, který není platný. Zobrazit <xref:System.Runtime.InteropServices.SafeHandle.DangerousAddRef%2A> a <xref:System.Runtime.InteropServices.SafeHandle.DangerousRelease%2A> metody pro další informace o tom, jak použít metodu metody DangerousGetHandle bezpečně.|
|<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName><br /><br /> <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName><br /><br /> <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName>|Tyto metody můžete načítat sestavení z neočekávaných umístěních. Například zobrazit příspěvky blogu .NET CLR poznámky Suzanne Cookovy [funkci LoadFile vs. LoadFrom](http://go.microsoft.com/fwlink/?LinkId=164450) a [výběr kontextu vazby](http://go.microsoft.com/fwlink/?LinkId=164451) na webu MSDN pro informace o metodách, které načítají sestavení.|
|[CoSetProxyBlanket](http://go.microsoft.com/fwlink/?LinkID=169250) (Ole32)<br /><br /> [CoInitializeSecurity](http://go.microsoft.com/fwlink/?LinkId=169255) (Ole32)|Podle času uživatelský kód začne provádět v spravovaného procesu je příliš pozdě spolehlivě volání funkce CoSetProxyBlanket. Modul CLR (CLR) má inicializace akce, které mohou bránit úspěšné uživatelé P/Invoke.<br /><br /> Pokud máte k volání funkce CoSetProxyBlanket pro spravovanou aplikaci, doporučujeme spustit proces pomocí spustitelného souboru nativního kódu (C++), volání funkce CoSetProxyBlanket v nativním kódu a pak spusťte aplikaci spravovaného kódu v procesu. (Nezapomeňte zadat číslo verze modulu runtime.)|

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odeberte nebo nahraďte volání nebezpečnou nebo problematickou metodu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Zprávy z tohoto pravidla můžete potlačit pouze v případě, že jsou k dispozici žádné alternativy k metodě problematické.

## <a name="see-also"></a>Viz také
 [Upozornění spolehlivosti](../code-quality/reliability-warnings.md)
