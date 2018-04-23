---
title: 'Postupy: ladění optimalizovaného kódu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- breakpoints, in optimized code
- debugging [C++], optimized code
- optimization, debug builds
- debug builds, optimizing
- optimized code, debugging
ms.assetid: fc8eeeb8-6629-4c9b-99f7-2016aee81dff
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9610f71a197c47521e2139d40aff1afde6a8a894
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-debug-optimized-code"></a>Postupy: Ladění optimalizovaného kódu
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, vyberte v nabídce Nástroje pro nastavení importu a exportu. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
> [!NOTE]
>  [/Zo (vylepšit optimalizované ladění)](/cpp/build/reference/zo-enhance-optimized-debugging)– možnost kompilátoru (dostupné v sadě Visual Studio Update 3) generuje rozsáhlejší ladění informace pro optimalizovaný kód (projekty, které nejsou sestavené s **/Od** – možnost kompilátoru. V tématu [/O možnosti (Optimalizace kódu)](/cpp/build/reference/o-options-optimize-code)). To zahrnuje vylepšenou podporou pro ladění, místní proměnné a vložená funkce.  
>   
>  [Upravit a pokračovat](../debugger/edit-and-continue-visual-csharp.md) vypnutá, pokud **/Zo** ocompiler možnost se používá.  
  
 Když kompilátor optimalizuje kódu, přemístí a změní uspořádání pokyny. Výsledkem je efektivnější zkompilovaný kód. Z důvodu této změně uspořádání ladicí program nemůže vždy identifikovat zdrojový kód, která odpovídá sadu pokynů.  
  
 Optimalizace může ovlivnit:  
  
-   Lokální proměnné, které lze odebrat pomocí pro optimalizaci nebo přesunout do umístění, které nerozumí ladicího programu.  
  
-   Pozice uvnitř funkce, které jsou změnit, pokud pro optimalizaci sloučí bloky kódu.  
  
-   Názvy funkcí pro rámce v zásobníku volání, což může být nesprávný, pokud pro optimalizaci sloučí dvě funkce.  
  
 Rámců, které se zobrazí v zásobníku volání jsou téměř vždy správné, ale za předpokladu, že máte symboly pro všechny snímky. Pokud máte poškození zásobníku, pokud máte funkce napsán v jazyce sestavení, nebo pokud nejsou rámce operačního systému bez odpovídající symboly v zásobníku volání, bude rámce v zásobníku volání nesprávný.  
  
 Globální a statické proměnné jsou vždy zobrazeny správně. Proto je struktura rozložení. Pokud je ukazatel na strukturu a hodnota ukazatele je správný, každé členské proměnné struktury zobrazí správnou hodnotu.  
  
 Z důvodu tato omezení by měl ladění, pokud možno pomocí neoptimalizované verze vašeho programu. Ve výchozím nastavení optimalizace vypnuté v konfiguraci ladicí program Visual C++ a spuštěn v rámci konfigurace verze.  
  
 Chyby, však může vypadat pouze v optimalizované verzi programu. V takovém případě musí ladění optimalizovaného kódu.  
  
### <a name="to-turn-on-optimization-in-a-debug-build-configuration"></a>Chcete-li optimalizace ladění konfigurace sestavení  
  
1.  Když vytvoříte nový projekt, vyberte `Win32 Debug` cíl. Použití `Win32``Debug` cíle, dokud je váš program plně ladit a jste připraveni k sestavení `Win32 Release` cíl. Kompilátor není optimální `Win32 Debug` cíl.  
  
2.  Vyberte projekt v Průzkumníku řešení.  
  
3.  Na **zobrazení** nabídky, klikněte na tlačítko **stránky vlastností**.  
  
4.  V **stránky vlastností** dialogové okno zkontrolujte, zda `Debug` vybrán **konfigurace** rozevíracího seznamu.  
  
5.  V zobrazení složky na levé straně vyberte **C/C++** složky.  
  
6.  V části **C++** složky, vyberte `Optimization`.  
  
7.  V seznamu vlastností na pravé straně najít `Optimization`. Nastavení vedle pravděpodobně uvádí `Disabled (` [/Od](/cpp/build/reference/od-disable-debug)`)`. Vyberte jednu z dalších možností (`Minimum Size``(`[/O1](/cpp/build/reference/o1-o2-minimize-size-maximize-speed)`)`, `Maximum Speed``(` [/O2](/cpp/build/reference/o1-o2-minimize-size-maximize-speed)`)`, `Full Optimization``(` [/Ox](/cpp/build/reference/ox-full-optimization) `)`, nebo `Custom`).  
  
8.  Pokud jste zvolili `Custom` možnost `Optimization`, teď můžete nastavit možnosti pro všechny ostatní vlastnosti zobrazené v seznamu vlastností.  
  
9. Vyberte vlastnosti konfiguračním, C/C++, příkazový řádek uzlu stránce vlastností projektu a přidejte `(` [/Zo](/cpp/build/reference/zo-enhance-optimized-debugging) `)` k **další možnosti** textové pole.  
  
    > [!WARNING]
    >  `/Zo` vyžaduje Visual Studio 2013 Update 3 nebo novější verze.  
    >   
    >  Přidání `/Zo` vypne [upravit a pokračovat](../debugger/edit-and-continue-visual-csharp.md).  
  
 Při ladění optimalizovaného kódu, použijte **zpětný překlad** okna zobrazíte jaké pokyny jsou ve skutečnosti vytvořit a spustit. Když nastavíte zarážky, je třeba vědět, že zarážce může přesunout společně s instrukce. Zvažte například následující kód:  
  
```  
for (x=0; x<10; x++)  
```  
  
 Předpokládejme, že je na tomto řádku nastavit zarážky. By se dalo očekávat zarážek být narazí 10krát, ale pokud kód je optimalizována, zarážce je dosáhl pouze jednou. Důvodem je, že první pokyn nastaví hodnotu `x` na hodnotu 0. Kompilátor rozpozná, že to jenom je nutné provést jednou a přesouvá ji mimo smyčku. Zarážce se přesune s ním. Pokyny, které porovnávání a zvýšit `x` zůstávají uvnitř smyčky. Při prohlížení **zpětný překlad** okně [jednotka kroku](http://msdn.microsoft.com/en-us/8791dac9-64d1-4bb9-b59e-8d59af1833f9) se automaticky nastaví na instrukce pro větší kontrolu, což je užitečné, když v průběhu optimalizovaný kód.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)