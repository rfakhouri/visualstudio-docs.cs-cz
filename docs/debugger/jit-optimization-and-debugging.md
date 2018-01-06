---
title: "JIT optimalizace a ladění | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], optimized code
- optimized code, debugging
ms.assetid: 19bfabf3-1a2e-49dc-8819-a813982e86fd
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2c3dcd57568bdfaac3ba0f7aff33cefca8a0ee32
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="jit-optimization-and-debugging"></a>Optimalizace a ladění JIT
Když ladíte spravované aplikace, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] potlačí optimalizace kódu v běhu (JIT) ve výchozím nastavení. Potlačení JIT optimalizace znamená, že ladíte Neaktivní optimalizované kódu. Spuštění kódu je něco o něco pomalejší, protože není optimalizovaná, ale je mnohem důkladnější prostředí ladění. Ladění optimalizovaného kódu je těžší a doporučené pouze, pokud narazíte na chyby, dojde v optimalizovaný kód, ale nelze reprodukovat v verzi Neaktivní optimalizované.  
  
 Řídí optimalizaci JIT ve [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pomocí **JIT potlačit optimalizaci pro načtení modulu** možnost. Tuto možnost můžete najít na **Obecné** v části **ladění** uzlu **možnosti** dialogové okno.  
  
 Pokud zrušíte výběr **JIT potlačit optimalizaci pro načtení modulu** možnost, můžete ladit optimalizované za běhu kódu, ale možnost ladění může být omezený, protože optimalizovaný kód neodpovídá zdrojového kódu. V důsledku toho ladicího programu windows, jako **místní hodnoty –** a **automobily** okno nemusí být zobrazeny tolik informací, stejně jako když byly ladění Neaktivní optimalizované kódu.  
  
 Další důležitý rozdíl obavy ladění pomocí pouze můj kód. Pokud ladění pouze můj kód zvažuje ladicího programu jako jiný uživatel kód, který by se neměly zobrazovat při ladění optimalizovaného kódu. V důsledku toho pokud jsou ladění za běhu optimalizovaného kódu, pravděpodobně chcete vypnout pouze můj kód. Další informace najdete v tématu [omezit zanoříte se pouze můj kód](../debugger/navigating-through-code-with-the-debugger.md#BKMK_Restrict_stepping_to_Just_My_Code).  
  
 Nezapomeňte, že **JIT potlačit optimalizaci pro načtení modulu** možnost potlačí optimalizace kódu, pokud se načtou moduly. Pokud jste se připojit k procesu, který je již spuštěn, může obsahovat kód, který je již načíst, kompilována a optimalizované. **JIT potlačit optimalizaci pro načtení modulu** možnost nemá žádný vliv na takový kód, i když bude mít vliv moduly, které jsou načtené po připojení. Kromě toho **JIT potlačit optimalizaci pro načtení modulu** možnost nemá vliv na moduly, například WinForms.dll, které jsou vytvořeny pomocí NGEN.  
  
## <a name="see-also"></a>Viz také  
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [Procházení kódu s ladicím programem](../debugger/navigating-through-code-with-the-debugger.md)   
 [Připojení ke spuštěným procesům](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Proces spravovaného spuštění](/dotnet/standard/managed-execution-process)