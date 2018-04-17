---
title: Pozastavení automatické funkce v sadě Visual Studio | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- full solution analysis
- performance
- low-memory
ms.assetid: 572c15aa-1fd0-468c-b6be-9fa50e170914
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-code-analysis
ms.workload:
- multiple
ms.openlocfilehash: bf11b7d0723f3ecabf9fc794fb244f48daa95672
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="automatic-feature-suspension"></a>Funkce Automatické pozastavení

Pokud dostupné systémové paměti klesne na 200 MB nebo méně, Visual Studio zobrazí následující zprávu v editoru kódu:

![Pozastavení úplnou analýzu řešení textu výstrahy](../code-quality/media/fsa_alert.png)

Když Visual Studio zjistí ke stavu nedostatku paměti, automaticky pozastaví některé pokročilé funkce, které pomáhají se zůstat stabilní. Visual Studio i nadále fungovat jako předtím, ale dojde ke snížení jeho výkon.

Se ke stavu nedostatku paměti tyto akce uskutečnit:

- Úplnou analýzu řešení pro Visual C# a Visual Basic je zakázána.

- [Uvolňování paměti](/dotnet/standard/garbage-collection/index) režimu s nízkou latencí (GC) pro Visual C# a Visual Basic je zakázána.

- Jsou vyprázdněných mezipamětí Visual Studio.

## <a name="improve-visual-studio-performance"></a>Zlepšení výkonu sady Visual Studio

Tipy a triky pro zlepšení výkonu sady Visual Studio při plánování práce s nedostatku paměti nebo velké řešení najdete v tématu [důležité informace o výkonu pro velká řešení](https://github.com/dotnet/roslyn/wiki/Performance-considerations-for-large-solutions).

## <a name="full-solution-analysis-suspended"></a>Úplnou analýzu řešení pozastaveno

Ve výchozím nastavení úplnou analýzu řešení povoleno jazyka Visual Basic a zakázáno pro Visual C#. Ale v ke stavu nedostatku paměti, úplnou analýzu řešení je automaticky zakázaná pro Visual Basic a Visual C#, bez ohledu na jejich nastavení v dialogovém okně Možnosti. Však můžete znovu povolit úplnou analýzu řešení tak, že zvolíte **znovu povolit** tlačítka na panelu když se zobrazí, výběrem informace o službě **povolit úplnou analýzu řešení** políčko v dialogovém okně Možnosti, případně podle spustit sadu Visual Studio. Dialogové okno Možnosti vždy zobrazuje aktuální úplné řešení nastavení analýzy. Další informace najdete v tématu [postupy: povolení a zákaz analýzy celého řešení](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md).

## <a name="gc-low-latency-disabled"></a>Globální Katalog s nízkou latencí zakázáno

Znovu povolit GC režimu s nízkou latencí, restartujte Visual Studio. Ve výchozím nastavení povoluje Visual Studio režimu s nízkou latencí GC vždy, když napíšete zajistit, že zadání nebrání žádné operace GC. Pokud ke stavu nedostatku paměti způsobí, že chcete zobrazit upozornění na automatické pozastavení Visual Studio, režimu s nízkou latencí GC zakázána dané relace. Spustit sadu Visual Studio znovu povolí výchozí chování GC. Další informace naleznete v tématu <xref:System.Runtime.GCLatencyMode>.

## <a name="visual-studio-caches-flushed"></a>Visual Studio mezipaměti vyprázdněny

Je-li pokračovat v aktuální relaci vývoj nebo restartujte Visual Studio, jsou všechny sady Visual Studio mezipaměti okamžitě vyprázdněny, ale začít znovu vytvořit. Mezipaměti vyprázdněny patří mezipaměti pro následující funkce:

- Najít všechny odkazy

- Přejděte na

- Přidání direktivy Using

Kromě toho jsou vymazány mezipamětí použít pro interní operace v sadě Visual Studio.

> [!NOTE]
> Upozornění na automatické funkce pozastavení dojde pouze jednou na základě za řešení, ne na bázi relací. To znamená, že pokud přepnete z jazyka Visual Basic, Visual C# (nebo naopak) a spustit do jiné ke stavu nedostatku paměti, pravděpodobně vám jiné funkce automatického pozastavení upozornění.

## <a name="see-also"></a>Viz také

- [Postupy: povolení a zákaz úplnou analýzu řešení](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md)
- [Základy kolekce paměti](/dotnet/standard/garbage-collection/fundamentals)
- [Důležité informace o výkonu pro velká řešení](https://github.com/dotnet/roslyn/wiki/Performance-considerations-for-large-solutions)