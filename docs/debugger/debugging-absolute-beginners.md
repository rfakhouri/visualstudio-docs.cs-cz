---
title: Ladění kódu pro začátečníky absolutní
description: Pokud ladíte poprvé, přečtěte si několik zásady, které je vám pomůže při ladění aplikace pomocí sady Visual Studio
ms.custom: ''
ms.date: 06/18/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugger
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 497479ea7b49581e478534e2f8d83d0dd917a2da
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2018
ms.locfileid: "36326948"
---
# <a name="how-to-debug-for-absolute-beginners"></a>Postup ladění pro začátečníky absolutní

Získejte velmi základní informace o tom, jak ladit pomocí ladicího programu. Pokud jsou Příprava vyzkoušet ladicí nástroj jako v aplikaci Visual Studio a toto je první čas, který jste se pokusili ladění aplikace, pak jste na správném místě. Při prvním použití ladicí program, je normální, že se naděje (a očekávají, že), ať ladicí nástroj používáte vám magically ukáže všechny chyby v kódu. Bohužel není to snadné. Ladění je zjištěné dovedností a trvá čas a postup se dozvíte, jak efektivně ladit. Proto před jsme naučit ladění, můžeme dát některé obecné tipy a zásady.

První, může být užitečné k odpovědi na některé základní otázky, jako "Co je ladění?" a "Co je ladění režimu?"

* *Ladění* je proces odebrání chyby z vašeho kódu.

* *Režim ladění* znamená používající vaši aplikaci (provádění kódu) při ladicí program je připojen k vaší aplikaci. Pomocí ladicího programu připojit, uvidíte, co kód dělá při spuštění. Například si můžete prohlédnout aplikace stavu (pohled na proměnné), najdete v části co funkce získávání, se nazývají a zkuste najít chyby. V dokumentaci sady Visual Studio režim ladění, obvykle stačí říkáme, když chceme, abyste zadali "Spuštění ladicího programu" nebo "Spuštění aplikace v ladicím programu".

## <a name="clarify-the-problem-by-asking-yourself-the-right-questions"></a>Vysvětlení problému tím, že požádá sami správné otázky

Pomáhá vysvětlení problému, který jste narazili teprve pak zkuste to opravit. Očekáváme, že jste již narazili na problém ve vašem kódu, jinak nebude možné zde pokoušíte zjistit, jak ho ladit! Ano než začnete, ladění, položte si několik otázky.

* Co očekává, že kód udělat?

* Co se stalo místo?

    Pokud jste spustili (výjimek) došlo k chybě při spuštění aplikace, který může být dobré! Výjimkou je neočekávané události došlo při spuštění kódu, obvykle chybu určitého druhu. [Pomocníka výjimka](../debugger/debugger-feature-tour.md#exception) v sadě Visual Studio vloží vaší aplikace do režimu ladění, přejdete na přesné místo ve vašem kódu ve výjimce došlo k chybě kde vám pomohou zjistit možné opravy chybovou zprávu. (Ale předtím, než můžete prozkoumat, Dokončit přečtení tohoto článku.)

    Pokud došlo k něco jiného, co je tento příznak problému? Máte už podezření kde došlo k tomuto problému v kódu? Například pokud váš kód zobrazí text, ale text je nesprávný, víte, buď vaše data jsou chybné nebo kód, který nastavení textu zobrazovaného má nějaký druh chyb. K vyřešení problému takto, pravděpodobně musíte spustit aplikaci pomocí ladicího programu sady Visual Studio, připojené a podívejte se na proměnných. (Ale nejprve pokračujte ve čtení tohoto článku.)

## <a name="examine-your-assumptions"></a>Zkontrolujte předpokladů

Předtím, než můžete prozkoumat chyby nebo došlo k chybě, vezměte v úvahu předpokladů, které můžete očekávat, že určité výsledek provedeny. To může být dlouhý seznam, tady je několik příkladů předpoklady, které se snadno Ujistěte se, ale nemusí nutně jít hodnotu true.

* Používáte správné rozhraní API (to znamená, v pravém objektu, funkce, metoda nebo vlastnost). Rozhraní API, které používáte nemusí to, co si myslíte, že se nepodporuje. (Po byste zkontrolovat volání rozhraní API v ladicím programu, její opravu může vyžadovat cesty v dokumentaci k identifikaci správné rozhraní API.)

* Rozhraní API používáte správně. Možná použít právo rozhraní API ale nepoužili správné způsobem.

* Váš kód nemá žádné překlepům.

* Změny provedené kódu a předpokládá, že nemá vztah k problému, který se zobrazuje.

* Došlo ke změně ve vašem prostředí (například nástroje nebo knihovna aktualizací) a předpokládá, že nemá vztah k problému, který se zobrazuje.

* Očekáván objekt, nebo proměnnou pro uložení určitou hodnotu (nebo typ hodnoty), ale nepodporuje.

* Tento kód je porozumět dostatečně dobře k ladění ho. Je často je obtížné ladění někdo jiný kód. Pokud není kód, je možné, může být nutné věnovat času učení, co kód dělá předtím, než ho mohou ladit efektivně.

    > [!TIP]
    > Začněte v malém rozsahu a začněte s kódem, který funguje! V některých případech je snazší opravte sadu velké nebo složité kódu od malou část kódu, který ukazuje se základním úkolem chcete dosáhnout (to znamená, zkopírujte pracovní vzorek). Potom můžete upravit nebo postupně, přidejte kód testování u každého bodu chyby.

Musíte znát předpokladů, může snížit dobu potřebnou k vyhledání k problému v kódu. Může také snížit dobu potřebnou k vyřešení problému.

## <a name="step-through-your-code-in-debugging-mode-to-find-where-the-problem-occurred"></a>Krokovat kód při ladění režimu k nalezení, kde došlo k problému

Pokud jste neobdrželi výjimku, použijte ladicí program najít přesnou místě, kde došlo k problému (nebo příznakem chybě). Než začnete, abyste zkuste najít konkrétní oblasti kódu, kde k problému dochází, nastavte [zarážek](../debugger/using-breakpoints.md) kde začíná tento kód. Zarážky jsou základní a nejjednodušší funkcí spolehlivého ladění. Zarážka určuje, kde má Visual Studio spuštěný kód pozastavit, abyste mohli zkontrolovat hodnoty proměnných či chování paměti, nebo abyste zjistili, jestli se nějaká větev kódu spouští. Kliknutím na levém okraji vedle řádek kódu můžete nastavit zarážky.

![Nastavit zarážky](../debugger/media/dbg-tour-set-a-breakpoint.gif "SetABreakPoint")

Jakmile nastavíte zarážku, spuštění ladicího programu (stiskněte **F5** nebo **spustit ladění** tlačítko ![spustit ladění](../debugger/media/dbg-tour-start-debugging.png "spustit ladění") v panelu nástrojů ladění), a aplikace se pozastaví, když kód, kde je nastavena zarážka provede (pokud ji nemá pozastavit, kód nebyl spouštění). Potom pomocí [krok příkazy](../debugger/navigating-through-code-with-the-debugger.md) například **F10** a **F11** zálohy ladicího programu a spusťte váš kód. Při ladění, provede kódu aplikace jako normální. Při spuštění aplikace v ladicím programu, vyhledejte problém, který jste určili.

> [!NOTE]
> Pokud je obtížné určit oblasti kódu, kde k problému dochází, nastavte zarážky v kódu, který běží před výskytem problému a pak použít příkazy krok, dokud neuvidíte problém manifestu. Můžete také použít [tracepoints](../debugger/using-breakpoints.md#BKMK_Print_to_the_Output_window_with_tracepoints) protokolu zprávy pro **výstup** okno. Pomocí prohlížení zprávy zaznamenané (a vašeho povšimnutí zprávy, které ještě neprotokolovaly!), můžete často izolovat oblasti s problémem kódu. Možná budete muset tento postup opakujte několikrát zúžit zaměření. Pokud se problém vyskytuje někde v rámci smyčku, která se opakuje tolikrát, kolikrát (a proto je obtížné reprodukujte), [podmíněného zarážek](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) může pomoct.

## <a name="when-you-find-the-region-of-code-with-the-problem-use-the-debugger-to-investigate"></a>Pokud zjistíte, oblasti kódu s problémem, použijte ladicí program k prošetření

Chcete-li zjistit příčinu problému, zkontrolujte kód problém při spuštění aplikace v ladicím programu:

* [Zkontrolujte proměnné](../debugger/view-data-values-in-data-tips-in-the-code-editor.md) a zkontrolujte, zda obsahují typ hodnoty, které se musí obsahovat. Pokud zjistíte chybná hodnota, zjistit, kde byla nastavena chybná hodnota (najít, kde byla nastavena hodnota, budete pravděpodobně potřebovat restartovat ladicího programu, podívejte se na [zásobník volání](../debugger/how-to-use-the-call-stack-window.md), nebo obojí).

* Zkontrolujte, jestli vaše aplikace spouští kód, který jste očekávali. (Například možná kód, které používáte obslužné rutiny (skryje) výjimku a nebylo mějte na paměti, dokud neuvidíte získat vyvolat kód obslužné rutiny výjimky došlo k výjimce.)

## <a name="next-steps"></a>Další kroky

V tomto článku když jste se naučili několik obecné koncepty ladění. Potom můžete spustit naučit, jak k ladění pomocí sady Visual Studio.

> [!div class="nextstepaction"]
> [Prohlídka funkcí ladicího programu](../debugger/debugger-feature-tour.md)
