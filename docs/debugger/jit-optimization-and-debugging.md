---
title: JIT optimalizace a ladění | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], optimized code
- optimized code, debugging
ms.assetid: 19bfabf3-1a2e-49dc-8819-a813982e86fd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7346b6fd8fbd483021437638f9e134ead88a0b93
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56699142"
---
# <a name="jit-optimization-and-debugging"></a>Optimalizace a ladění JIT
**Optimalizace jak fungují v rozhraní .NET:** Pokud se pokoušíte ladit kód, je jednodušší při, že kód je **není** optimalizované. Je to proto, když je kód zoptimalizovaný, kompilovacími a běhovými provést změny emitovaný kód procesoru tak, že běží rychleji, ale je méně přímé mapování na původní zdrojový kód. To znamená, že ladicí programy jsou často nelze zjistit hodnotu místní proměnné a kódu, krokování a zarážky nemusí fungovat podle očekávání.

Obvykle optimalizovaný kód vytvoří konfigurace sestavení pro vydání a konfiguraci sestavení ladění nepodporuje. `Optimize` Vlastnost MSBuild Určuje, zda je má kompilátor optimalizovat kód.

V daném ekosystému .NET, kód bude převedena ze zdroje na využití procesoru podle pokynů v krocích: nejprve je potřeba C# kompilátor převede text, který zadáte na zprostředkující binárního formátu, která je volána MSIL a zapíše to na soubory .dll. Modul .NET Runtime později, převede tento jazyk MSIL instrukce procesoru. Oba kroky můžete optimalizovat do určité míry, ale druhý krok provést modul .NET runtime provádí více významné optimalizace.

**Možnost 'Potlačení optimalizace JIT při načtení modulu (pouze spravované)':** Ladicí program poskytuje možnosti, které řídí, co se stane při načtení knihovny DLL, který je kompilován s povolenými optimalizacemi v rámci cílového procesu. Pokud tato možnost není zaškrtnutá (výchozí stav), pak když modul .NET Runtime kompiluje kód jazyka MSIL do kódu procesoru, ponechá povolené optimalizace. Pokud je možnost je zaškrtnuto, ladicí program požadavků zakázat optimalizace.

Najít **potlačení optimalizace JIT při načtení modulu (pouze spravované)** možnosti, vyberte **nástroje** > **možnosti**a pak vyberte  **Obecné** stránky **ladění** uzlu.

**Pokud jste zaškrtněte tuto možnost:** Toto políčko zaškrtněte, pokud jste stáhli z jiného zdroje, jako je balíček nuget, knihovny DLL a který chcete ladit kód v této knihovně DLL. V pořadí, aby to fungovalo musí také najít soubor symbolů (PDB) pro tuto knihovnu DLL.

Pokud vás zajímá pouze při ladění kódu, který vytvářejí místně, je nejlepší, ponechejte tuto možnost není zaškrtnuto, protože v některých případech, povolením této možnosti bude výrazně zpomalit ladění. Zpomalit existují dvě z důvodů:

* Optimalizovaný kód běží rychleji. Pokud jsou vypnutím optimalizace pro velké množství kódu, dopad na výkon můžete ušetřit až.
* Pokud máte povoleným kódem Just My ladicí program dokonce ani akci a načíst symboly pro knihovny DLL, které jsou optimalizované. Hledání symbolů může trvat dlouhou dobu.

**Omezení této možnosti:** Existují dvě situace, kdy se tato možnost způsobí **není** pracovat:

1. V situacích, kde jsou k již běžícímu procesu připojování ladicího programu Tato možnost nebude mít žádný vliv na moduly, které již byly zavedeny v době, kdy byl připojen ladicí program.
2. Tato možnost nemá žádný vliv na knihovny DLL, které byly předem zkompilované (známé jako ngen'ed) do nativního kódu. Však můžete zakázat použití předkompilovaný kód, že spuštění procesu prostředí, proměnné 'COMPlus_ZapDisable' nastavena na hodnotu '1'.

## <a name="see-also"></a>Viz také
- [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)
- [Procházení kódu s ladicím programem](../debugger/navigating-through-code-with-the-debugger.md)
- [Připojení ke spuštěným procesům](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)
- [Proces spravovaného spuštění](/dotnet/standard/managed-execution-process)
