---
title: Upravit a pokračovat (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 05/31/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [C++]
- debugging [C++], Edit and Continue
- C/C++, Edit and Continue
ms.assetid: 1815251e-a877-433e-9e5e-69bd9ba254c7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 107014740c9d976be65fb2a268723184a9134868
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="edit-and-continue-visual-c"></a>Upravit a pokračovat (Visual C++)
Můžete upravit a pokračovat v projektech Visual C++. V tématu [podporované změny kódu (C++)](../debugger/supported-code-changes-cpp.md) informace o omezeních upravit a pokračovat.
  
Další informace o vylepšení Visual Studio 2015 Update 3 najdete v tématu [C++ upravit a pokračovat v sadě Visual Studio 2015 Update 3](https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/).  
  
 [/Zo (vylepšit optimalizované ladění)](/cpp/build/reference/zo-enhance-optimized-debugging) – možnost kompilátoru byla zavedena v sadě Visual Studio 2013 Update 3 přidá další informace o soubory PDB (symbol) pro binární soubory zkompilovaný bez [/Od (zakázat (ladění)) ](http://msdn.microsoft.com/library/aafb762y.aspx) možnost.  
  
 **/Zo** zakáže upravit a pokračovat. V tématu [postupy: ladění optimalizovaného kódu](../debugger/how-to-debug-optimized-code.md).  
  
##  <a name="BKMK_Enable_or_disable_automatic_invocation_of_Edit_and_Continue"></a> Povolit nebo zakázat upravit a pokračovat  
 Chcete zakázat automatické volání upravit a pokračovat, pokud provádíte úpravy kód, který chcete použít během aktuální relace ladění. Můžete také znovu povolit automatické upravit a pokračovat.

> [!IMPORTANT]
> Sestavení požadovaná nastavení a další informace o kompatibilitě funkce najdete v tématu [C++ upravit a pokračovat v sadě Visual Studio 2015 Update 3] (https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/.
  
1.  Pokud jste v relaci ladění, zastavte ladění (**Shift + F5**).

2. Na **nástroje** nabídky, zvolte **možnosti**.
  
3.  V **možnosti** dialogové okno, vyberte **ladění > Obecné**.

4.  Chcete-li povolit, vyberte **povolit upravit a pokračovat**. Pokud chcete zakázat, zrušte zaškrtnutí tohoto políčka.
  
5.  V **upravit a pokračovat** skupiny, vyberte nebo zrušte **Povolit nativní upravit a pokračovat** zaškrtávací políčko.  
  
 Změna toto nastavení ovlivňuje všechny projekty, které pracujete na. Není nutné znovu sestavit aplikaci po změně nastavení. Pokud vytváříte aplikace z příkazového řádku nebo ze souboru pravidel, ale při ladění v prostředí Visual Studio, stále můžete upravit a pokračovat Pokud nastavíte **/ZI** možnost.  
  
##  <a name="BKMK_How_to_apply_code_changes_explicitly"></a> Jak se má použít změny kódu explicitně  
 V jazyce Visual C++ můžete upravit a pokračovat použít změny kódu dvěma způsoby. Změny kódu můžete použít implicitně, když zvolíte příkaz provádění nebo explicitně, pomocí **použít změny kódu** příkaz.  
  
 Při aplikování změn kódu explicitně, váš program zůstane v režimu pozastavení - žádné provádění dojde.  
  
-   Chcete-li použít změny kódu explicitně, na **ladění** nabídce zvolte **použít změny kódu**.  
  
##  <a name="BKMK_How_to_stop_code_changes"></a> Postup zastavení změn kódu  
 Sice upravit a pokračovat v procesu zavádění změn kódu, můžete zastavit operaci.  
  
 Chcete-li zastavit zavádění změn kódu:  
  
-   Na **ladění** nabídce zvolte **zastavit provádění změn kódu**.  
  
 Tato položka nabídky je viditelná jenom v případě, že jsou aplikovány změny kódu.  
  
 Pokud zvolíte tuto možnost, žádná změn kódu, které není potvrzena.  
  
##  <a name="BKMK_How_to_reset_the_point_of_execution"></a> Obnovení bodu provádění  
 Některé změny kódu může způsobit bod spuštění pro přesun do nového umístění, kdy upravit a pokračovat platí změny. Upravit a pokračovat umístí bodu provádění jako přesně, ale nemusí být správný ve všech případech výsledky.  
  
 V jazyce Visual C++ dialogové okno vás upozorní, když bod provedení změny. Ověřte, zda je umístění správné než budete pokračovat, ladění. Pokud není správný, použijte **další příkaz Set** příkaz. Další informace najdete v tématu [nastavit další příkaz k provedení](http://msdn.microsoft.com/library/y740d9d3.aspx#BKMK_Set_the_next_statement_to_execute).  
  
##  <a name="BKMK_How_to_work_with_stale_code"></a> Jak pracovat s zastaralý kód  
 V některých případech upravit a pokračovat nelze použít změny kódu spustitelný soubor, ale může být moct později použít změny kódu, pokud budete pokračovat, ladění. K tomu dojde, pokud chcete upravit funkci, která volá funkci current nebo pokud přidáte více než 64 bajtů nové proměnné funkce v zásobníku volání  
  
 V takových případech ladicího programu pokračuje v provádění původní kód, dokud můžete provést změny. Zastaralý kód se zobrazí jako okno dočasné zdrojového souboru v okně samostatného zdrojového s názvem, jako `enc25.tmp`. Upravená zdroj i nadále se zobrazují v okně původního zdroje. Pokud se pokusíte upravit zastaralý kód, zobrazí se zpráva s upozorněním.  
  
## <a name="see-also"></a>Viz také  
 [Podporované změny kódu (C++)](../debugger/supported-code-changes-cpp.md)