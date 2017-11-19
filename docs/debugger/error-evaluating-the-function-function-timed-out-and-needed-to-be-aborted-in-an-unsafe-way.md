---
title: "Chyba: Vyhodnocení funkce & č. 39; funkce & č. 39; Vypršel časový limit a potřeby unsafe způsobem přerušena | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.unsafe_func_eval_abort
ms.assetid: 0a9f70ed-21ad-4a10-8535-b9c5885ad8f4
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 722abd91cb9f97aab67d0d9a5e77ff9e3a4f080d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-evaluating-the-function-39function39-timed-out-and-needed-to-be-aborted-in-an-unsafe-way"></a>Chyba: Vyhodnocení funkce & č. 39; funkce & č. 39; Vypršel časový limit a potřeby unsafe způsobem přerušena

Úplný text zprávy: vyhodnocování funkce 'function' vypršel časový limit a potřeby unsafe způsobem přerušena. To může mít poškozena tento cílový proces. 

Aby bylo snazší ke kontrole stavu objektů .NET, bude ladicí program automaticky vynutit vyladěnou procesu spustit další kód (obvykle metody getter vlastnosti a funkce ToString). Ve většině scénářů všechny tyto funkce dokončete rychle a usnadnění ladění mnohem. Ladicí program však není spuštění aplikace v izolovaném prostoru. Výsledkem je metoda getter vlastnosti nebo metody ToString, který volá do nativní funkce, která existuje v může vést k dlouhé časové limity, které nemusí být použitelná pro obnovení. Pokud narazíte na tato chybová zpráva, došlo k to.
 
Jeden běžným důvodem tohoto problému je při ladicího programu vlastnost se pouze možnost vlákno ke kontrole provést. Takže pokud je vlastnost čekání na další podprocesů pro spuštění uvnitř vyladěnou aplikace a čeká, tak, aby modul Runtime rozhraní .NET není možné přerušit, tento problém proběhne.
 
## <a name="to-correct-this-error"></a>Oprava této chyby
 
Existují tři možná řešení tohoto problému.
 
### <a name="solution-1-prevent-the-debugger-from-calling-the-getter-property-or-tostring-method"></a>Řešení #1: Zabránit volání metoda getter vlastnosti nebo metody ToString ladicí program
 
Chybová zpráva vám oznámí, název funkce, které se pokusil volat ladicího programu. Pokud tuto funkci můžete upravit, můžete zabránit ladicího programu volání metoda getter vlastnosti nebo metody ToString. Použijte jeden z následujících akcí:
 
* Změnit metodu na jiný typ kódu kromě metoda getter vlastnosti nebo metody ToString a problém zmizí.
    -nebo-
* (Pro ToString) Definování atributu DebuggerDisplay na typu a máte vyhodnotit něco jiného než ToString ladicího programu.
    -nebo-
* (Pro vlastnost getter) Umístit `[System.Diagnostics.DebuggerBrowsable(DebuggerBrowsableState.Never)]` atributu pro vlastnost. To může být užitečné, pokud máte metodu, která musí zůstat vlastnost důvodů kompatibility rozhraní API, ale musí být skutečně metodu.
 
### <a name="solution-2-have-the-target-code-ask-the-debugger-to-abort-the-evaluation"></a>Řešení #2: Mají cílový kód, požádejte ladicí program na přerušení vyhodnocení
 
Chybová zpráva vám oznámí, název funkce, které se pokusil volat ladicího programu. Metoda getter vlastnosti nebo metody ToString někdy nepodaří spustit správně, hlavně v situacích, kde je problém které kód potřebuje další vlákno spuštění kódu a pak můžete volat funkci implementace `System.Diagnostics.Debugger.NotifyOfCrossThreadDependency` požádat ladicí program na abort – funkce vyhodnocení. S tímto řešením je stále možné explicitně vyhodnotit tyto funkce, ale výchozí chování je, že provádění zastaví, když dojde k volání NotifyOfCrossThreadDependency.
 
### <a name="solution-3-disable-all-implicit-evaluation"></a>Řešení #3: Zakažte všechny implicitní vyhodnocení
 
Pokud předchozí řešení není opravit problém, přejděte na *nástroje* > *možnosti*a zrušte zaškrtnutí políčka nastavení *ladění*  >   *Obecné* > *povolit vyhodnocení vlastnosti a další funkce implicitní volání*. Tím zakážete většina implicitní funkce hodnocení a má problém vyřešit.



  
