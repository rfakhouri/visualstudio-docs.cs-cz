---
title: 'CA2001: Vyhněte se volání problematických metod'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8053a3317e75959f030a0df6e11ead3bed17f02e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca2001-avoid-calling-problematic-methods"></a>CA2001: Vyhněte se volání problematických metod
|||
|-|-|
|TypeName|AvoidCallingProblematicMethods|
|CheckId|CA2001|
|Kategorie|Microsoft.Reliability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Člen volá potencionálně nebezpečnou nebo problematickou metodu.

## <a name="rule-description"></a>Popis pravidla
 Vyhněte se volání nepotřebné a potenciálně nebezpečná metoda.

 Toto pravidlo je porušení nastane, když volá členem jedné z následujících metod.

|Metoda|Popis|
|------------|-----------------|
|<xref:System.GC.Collect%2A?displayProperty=fullName>|Volání metody GC. Shromažďování může výrazně ovlivnit výkon aplikace a obvykle není nutný. Další informace najdete v tématu [Portoriku Mariani výkonu Tidbits](http://go.microsoft.com/fwlink/?LinkId=169256) položku blogu na webu MSDN.|
|<xref:System.Threading.Thread.Resume%2A?displayProperty=fullName><br /><br /> <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>|Thread.Suspend a Thread.Resume jsou zastaralé z důvodu jejich nepředvídatelné chování.  Použít jiné třídy v <xref:System.Threading> obor názvů, jako například <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex>, <xref:System.Threading.Mutex>, a <xref:System.Threading.Semaphore> synchronizovat vláken, nebo chránit prostředky.|
|<xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A?displayProperty=fullName>|Metoda DangerousGetHandle představuje bezpečnostní riziko, protože se může vrátit popisovač, který není platný. Najdete v článku <xref:System.Runtime.InteropServices.SafeHandle.DangerousAddRef%2A> a <xref:System.Runtime.InteropServices.SafeHandle.DangerousRelease%2A> metody pro další informace o tom, jak použít metodu DangerousGetHandle bezpečně.|
|<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName><br /><br /> <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName><br /><br /> <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName>|Tyto metody lze načítat sestavení z neočekávaných umístěních. Například najdete v příspěvcích na blogu .NET CLR poznámky Suzanne Cookovy [funkci LoadFile vs. LoadFrom –](http://go.microsoft.com/fwlink/?LinkId=164450) a [výběr kontextu vazby](http://go.microsoft.com/fwlink/?LinkId=164451) na webu MSDN informace o metodách, které načtení sestavení.|
|[Funkce CoSetProxyBlanket](http://go.microsoft.com/fwlink/?LinkID=169250) (Ole32)<br /><br /> [U funkce CoInitializeSecurity](http://go.microsoft.com/fwlink/?LinkId=169255) (Ole32)|Při spuštění uživatelského kódu spravovaného procesu prováděny v době se příliš pozdní spolehlivě volání funkce CoSetProxyBlanket. Modul CLR (CLR) má inicializace akce, které mohou bránit úspěšné uživatelé P/Invoke.<br /><br /> Pokud máte k volání funkce CoSetProxyBlanket pro spravované aplikace, doporučujeme spustit proces pomocí spustitelného souboru nativního kódu (C++), volání funkce CoSetProxyBlanket v nativním kódu a pak spusťte aplikaci spravovaného kódu v procesu. (Nezapomeňte zadat číslo verze modulu runtime.)|

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, odeberte nebo nahraďte volání metody nebezpečná nebo problematické.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Zprávy z tohoto pravidla můžete potlačit jenom v případě, že jsou k dispozici žádné alternativy problematické metodě.

## <a name="see-also"></a>Viz také
 [Upozornění spolehlivosti](../code-quality/reliability-warnings.md)