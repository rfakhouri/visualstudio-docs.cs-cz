---
title: Řešení potíží s zarážky v ladicím programu sady Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/23/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d587809a9690e312e923ba184c9d90c38405a5d6
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31477102"
---
# <a name="troubleshoot-breakpoints-in-the-visual-studio-debugger"></a>Řešení potíží s zarážky v ladicím programu sady Visual Studio

## <a name="breakpoint-warnings"></a>Breakpoint – upozornění

Při ladění, zarážku má dva možné stavy visual: plný kroužek red a prázdný (white vyplněno) kruh. Pokud bude možné úspěšně zarážku v tento cílový proces ladicí program, zůstane plnou červeném kroužku. Pokud zarážkou na prázdný kruh zarážce je zakázán nebo upozornění došlo k chybě při pokusu o nastavení zarážku. K určení rozdílu, najeďte myší na zarážce a jestli je upozornění.

Následující dvě části popisují výrazné upozornění a jejich řešení. 

### <a name="no-symbols-have-been-loaded-for-this-document"></a>"Žádné symboly jsou načteny tohoto dokumentu" 

Přejděte na **moduly** okno (**ladění** > **Windows** > **moduly**) a zkontrolujte, zda je modul načíst.  
* Pokud modul je načtena, podívejte se **Symbol stav** sloupec a zjistěte, zda jsou načteny symboly. 
  * Pokud symboly nebyly načteny, zkontrolujte stav symbol diagnostikovat problém. V místní nabídce v modulu v **moduly** okně klikněte na tlačítko **Symbol načíst informace o...**  zobrazíte, kde hledá ladicího programu a zkuste to načíst symboly. Další informace o načtení symbolů najdete v tématu [zadejte symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  * Pokud se načtou symboly, to znamená, že PDB neobsahuje informace o zdrojových souborech. Toto jsou několik možných příčin: 
    * Pokud zdrojové soubory vašeho byly nedávno přidali, potvrďte, že je právě načítán aktuální verzi modulu.  
    * Je možné vytvořit odřapíkovaného soubory PDB pomocí **/PDBSTRIPPED** – možnost linkeru. Soubory PDB odřapíkovaného neobsahují zdroje informací o souboru. Potvrďte, že pracujete s úplnou PDB a není odřapíkovaného PDB.  
    * Soubor PDB částečně je poškozený. Pokuste se soubor odstranit a provádění čisté sestavení modulu a zjistěte, zda tento postup problém vyřešil. 

* Pokud modul není načteno, zkontrolujte následující najít příčinu. 
  * Potvrďte, že ladíte proces správné. 
  * Zkontrolujte, že ladíte správné typy kódu. Můžete zjistit, jaký typ ladicí program nakonfigurovaný tak, aby ladění v kódu **procesy** okno (**ladění** > **Windows**  >  **Procesy**). Například se pokud chcete ladit kód C#, ověřte, že vaše ladicí program je nakonfigurován pro odpovídající typ rozhraní .NET Framework (například spravované (v4\*) a spravované (v2\*/v3\*) a spravované (CoreCLR)). 

### <a name="-the-current-source-code-is-different-from-the-version-built-into"></a>"… aktuální zdrojový kód je odlišná od verze součástí..." 

Pokud došlo ke změně zdrojového souboru a zdroj už neodpovídá kódu, kterou ladíte, nebude ladicího programu nastavte zarážky v kódu ve výchozím nastavení. Za normálních okolností tento problém se stane, když dojde ke změně zdrojového souboru, ale nebyl znovu vytvořen, zdrojový kód. Chcete-li tento problém vyřešit, znovu sestavte projekt. Pokud systém sestavení se domnívá, že projekt již aktuální, i když není, můžete v systému projekt znovu sestavit buď znovu uložit. zdrojový soubor nebo podle čištění projektu sestavení výstupu před vytvořením. 

Ve výjimečných případech můžete chtít ladění bez nutnosti odpovídající zdrojového kódu. To může vést k velmi matoucí ladění zkušenosti, proto se ujistěte, že toto je, jak chcete pokračovat.  

Pokud chcete zakázat tyto kontroly zabezpečení, proveďte jednu z následujících akcí: 
* K úpravě jeden zarážek, najeďte myší na ikonu zarážek v editoru a klikněte na ikonu nastavení (ozubené kolečko). Okno náhledu se přidá do editoru. V horní části okna funkce Náhled je hypertextový odkaz, který určuje umístění zarážku. Klikněte na odkaz, pokud chcete povolit změnu zarážek umístění a zkontrolovat **povolit zdrojovém kódu, aby se liší od originálu**.
* Chcete-li změnit toto nastavení pro všechny zarážky, přejděte na **ladění** > **možnosti a nastavení**. Na **ladění nebo Obecné** zrušte zaškrtnutí políčka **vyžadují zdrojové soubory, které přesně odpovídají původní verze** možnost. Zajistěte, abyste po dokončení je znovu povolit tuto možnost ladění. 

## <a name="the-breakpoint-was-successfully-set-no-warning-but-didnt-hit"></a>Zarážce byl úspěšně nastaven (bez upozornění), ale nebyla průchodu 

Tato část obsahuje informace o řešení problémů při ladicí program nezobrazuje všechna upozornění – zarážkou plný kroužek red při ladění aktivně ještě není právě průchodu zarážkou. 

Zde jsou pár věcí zkontrolovat: 
1. Pokud váš kód běží v procesu více než jeden nebo více počítačů, ujistěte se, že ladíte správné procesu nebo počítače.  
2. Potvrďte, že váš kód běží. Jeden jednoduchý způsob, jak toto vyzkoušíte je přidání volání `System.Diagnostics.Debugger.Break` (C# / VB.) nebo `__debugbreak` (C++) na řádek kódu, který se pokoušíte nastavit bod přerušení a pak znovu sestavte projekt. 
3. Pokud jsou ladění optimalizovaného kódu, není ani Ujistěte se, že funkce, kde je nastaven vaší zarážce vložená do jiné funkce. `Debugger.Break` Testovací popsané v předchozí kontroly můžete pracovat také otestovat. 

## <a name="i-deleted-a-breakpoint-but-i-continue-to-hit-it-when-i-start-debugging-again"></a>Po odstranění zarážku, ale I nadále stiskněte tlačítko při spuštění ladění znovu 

Pokud jste odstranili zarážku při ladění, můžete narazit zarážek znovu při příštím spuštění ladění. Pokud chcete zastavit stiskne tento bod přerušení, zajistěte, aby všechny instance zarážce se odeberou z **zarážky** okno.  
