---
title: 'Chyba: Tento cílový proces byl ukončen s kódem &#39;kód&#39; při vyhodnocování funkce &#39;funkce&#39; | Microsoft Docs'
ms.custom: ''
ms.date: 4/06/2018
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.process_exit_during_func_eval
ms.technology: vs-ide-debug
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d5e9221ccf162180a89cc88b1ceebcf55be39eef
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="error-the-target-process-exited-with-code-39code39-while-evaluating-the-function-39function39"></a>Chyba: Tento cílový proces byl ukončen s kódem &#39;kód&#39; při vyhodnocování funkce &#39;– funkce&#39;

Úplný text zprávy: tento cílový proces byl ukončen s kódem 'kódu' při vyhodnocování funkce 'function'.

Aby bylo snazší ke kontrole stavu objektů .NET, ladicí program automaticky vynutit vyladěnou procesu spouštět další kód (obvykle vlastnost metody getter a `ToString` funkce). Ve většině případů tyto funkce úspěšně dokončit nebo generování výjimek, které může být zachycen ladicího programu. Existují však některých případech, ve kterých nelze zachycení výjimky, protože napříč hranicemi jádra, vyžadují čerpání zpráv uživatele nebo neopravitelné. Jako výsledek, metoda getter vlastnosti nebo metody ToString, který provede kód této buď ukončit proces (například volá `ExitProcess()`) nebo vyvolá výjimku, k neošetřené výjimce, která nemůže být zachycena (například `StackOverflowException`) bude ukončen ladit proces a end relace ladění. Pokud narazíte na tato chybová zpráva, došlo k to.
 
Jeden běžným důvodem tohoto problému je, že při ladicího programu vlastnost, která volá sama se může dojít k výjimce přetečení zásobníku. Výjimce přetečení zásobníku nelze obnovit, a tento cílový proces bude ukončen.
 
## <a name="to-correct-this-error"></a>Oprava této chyby
 
Existují dvě možná řešení tohoto problému.
 
### <a name="solution-1-prevent-the-debugger-from-calling-the-getter-property-or-tostring-method"></a>Řešení #1: Zabránit volání metoda getter vlastnosti nebo metody ToString ladicí program 

Chybová zpráva vám oznámí, název funkce, které ladicí program ke volání. S názvem funkce, můžete zkusit znovu vyhodnocování této funkce z **Immediate** okno k ladění vyhodnocení. Ladění je možné při vyhodnocování z **Immediate** okno proto, že na rozdíl od implicitní hodnocení z **automobily/místní hodnoty nebo sledování** windows, ladicího programu dělí na neošetřených výjimek.

Pokud tuto funkci můžete upravit, můžete zabránit v ladicím programu volání metoda getter vlastnosti nebo `ToString` metoda. Použijte jeden z následujících akcí:
 
* Změnit metodu na jiný typ kódu kromě metoda getter vlastnosti nebo metody ToString a problém zmizí.
    -nebo-
* (Pro `ToString`) definovat `DebuggerDisplay` atribut na typ a může mít ladicí program vyhodnotit něco jiné než `ToString`.
    -nebo-
* (Pro vlastnost getter) Umístit `[System.Diagnostics.DebuggerBrowsable(DebuggerBrowsableState.Never)]` atributu pro vlastnost. To může být užitečné, pokud máte metodu, která musí zůstat vlastnost důvodů kompatibility rozhraní API, ale musí být skutečně metodu.

Pokud tuto metodu nelze upravit, bude pravděpodobně možné rozdělit tento cílový proces na alternativní instrukce, a opakujte vyhodnocení.
 
### <a name="solution-2-disable-all-implicit-evaluation"></a>Řešení #2: Zakažte všechny implicitní vyhodnocení
 
Pokud předchozí řešení není opravit problém, přejděte na **nástroje** > **možnosti**a zrušte zaškrtnutí políčka nastavení **ladění**  >   **Obecné** > **povolit vyhodnocení vlastnosti a další funkce implicitní volání**. Tím zakážete většina implicitní funkce hodnocení a má problém vyřešit.



  
