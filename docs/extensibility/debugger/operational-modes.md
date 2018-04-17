---
title: Provozní režimy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, modes
ms.assetid: f69972d0-809d-40df-9da3-04738791391c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 72ae5a36f9f0547635872f5c8ebe30f2f3c53d5a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="operational-modes"></a>Provozní režimy
Existují tři režimy, ve kterých IDE může fungovat, následovně:  
  
-   [Režim návrhu](#vsconoperationalmodesanchor1)  
  
-   [Režim spuštění](#vsconoperationalmodesanchor2)  
  
-   [Režim pozastavení](#vsconoperationalmodesanchor3)  
  
 Jak se vaše vlastní ladění modulu (DE) přechází mezi těmito režimy je rozhodnutí o implementace, která vyžaduje, abyste se seznamte s mechanismy přechodu. DE může nebo nemusí přímo implementovat tyto režimy. Tyto režimy jsou skutečně ladění balíček režimy, které přepínače na základě akce uživatele nebo události z DE. Například je přechod z režimu spuštění do režimu pozastavení podporováno zastavení událostí z DE. Přechod z rozdělení buď spustit režim nebo režim krok je podporováno uživatelem provádění operací, jako je například krok nebo spouštění. Další informace o DE přechody najdete v tématu [řízení provádění](../../extensibility/debugger/control-of-execution.md).  
  
##  <a name="vsconoperationalmodesanchor1"></a> Režim návrhu  
 Režim návrhu je nonrunning stav ladění v sadě Visual Studio, během které doby můžete nastavit ladění funkcí ve vaší aplikaci.  
  
 Pouze několik ladění funkcí se používají v režimu návrhu. Vývojář se může rozhodnout nastavit zarážky nebo vytvořit výrazů. DE se nikdy načten nebo volat rozhraní IDE je v režimu návrhu. Interakce s DE probíhá během spuštění a pozastavení režimy.  
  
##  <a name="vsconoperationalmodesanchor2"></a> Režim spuštění  
 Spuštění režimu nastane, když program spustí v relaci ladění v rozhraní IDE. Aplikace běží až do ukončení, dokud je dosáhl boru přerušení, nebo je vyvolána výjimka. Pokud aplikace používá k ukončení, DE přechody do režimu návrhu. Když je dosaženo zarážky nebo je vyvolána výjimka, DE přejde do režimu pozastavení.  
  
##  <a name="vsconoperationalmodesanchor3"></a> Režim pozastavení  
 Režim pozastavení nastane při spuštění ladění programu je pozastaveno. Režim pozastavení nabízí vývojářům snímku aplikace v době rozdělení a umožňuje vývojáři k analýze stav aplikace a změnit tak, jak bude aplikace spuštěna. Vývojář můžete zobrazit a upravit kód, zkontrolujte nebo měnit data, restartování aplikace, ukončení provádění nebo pokračovat v provádění ze stejného bodu.  
  
 Režim pozastavení se zadá, když je DE odesílá události synchronní zastavit. Synchronní zastavení události, označované taky jako události zastavení, upozornění správce ladicí relace (SDM) a rozhraní IDE, který laděné aplikace byla zastavena, provádění kódu. [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) a [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md) rozhraní jsou příklady zastavení události.  
  
 Ukončení události pocházejí voláním na jednu z následujících metod, které přechod ladicí program z režimu pozastavení ke spuštění nebo krok režimu:  
  
-   [Spuštění](../../extensibility/debugger/reference/idebugprocess3-execute.md)  
  
-   [Krok](../../extensibility/debugger/reference/idebugprocess3-step.md)  
  
-   [Pokračovat](../../extensibility/debugger/reference/idebugprocess3-continue.md)  
  
###  <a name="vsconoperationalmodesanchor4"></a> Krok režimu  
 Režim krok nastává, když program kroky na další řádek kódu, nebo do, přes nebo mimo funkci. Krok provede voláním metody [krok](../../extensibility/debugger/reference/idebugprocess3-step.md). Tato metoda vyžaduje `DWORD`s určeným [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) a [STEPKIND](../../extensibility/debugger/reference/stepkind.md) výčty jako vstupní parametry.  
  
 Pokud program úspěšně kroky na další řádek kódu nebo do funkce nebo spuštění kurzor nebo sadu zarážek, DE automaticky přejde zpět do režimu pozastavení.  
  
## <a name="see-also"></a>Viz také  
 [Řízení spouštění](../../extensibility/debugger/control-of-execution.md)