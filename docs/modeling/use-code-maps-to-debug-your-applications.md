---
title: Použití map kódu k ladění aplikací
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio Ultimate, visualizing code
- Visual Studio Ultimate, navigating code visually
- Visual Studio Ultimate, understanding code
- Visual Studio Ultimate, mapping code relationships
- Visual Studio Ultimate, code maps
- mapping code relationships
- code maps
- mapping relationships in code
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 006db4f3fd820a25b0c413deabce3da5faa70cec
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750269"
---
# <a name="use-code-maps-to-debug-your-applications"></a>Použití map kódu k ladění aplikací
Mapy kódu vám může pomoct vyhnout ztratili v rozsáhlých základů kódu, neznámého kódu nebo starší verze kódu. Například při ladění, budete možná muset podívejte se na kód napříč mnoha soubory a projekty. Použití map kódu k navigaci částí kódu a pochopit vztahy mezi nimi. Tímto způsobem, nemáte k udržování přehledu o tento kód ve vaší head nebo kreslení samostatné diagram. Takže když dojde k přerušení práci, kód mapuje nápovědy aktualizace vaší paměti o kód, který právě pracujete.

 ![Mapa kódu &#45; mapování vazeb v kódu](../modeling/media/codemapstoryboardpaint.png)

 **Zelenou šipku ukazuje, kde se zobrazí v editoru kurzor**

 Podrobnosti příkazů a akcích, které můžete použít při práci s map kódu najdete v tématu [Procházet a uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md).

## <a name="understand-the-problem"></a>Pochopení problému
 Předpokládejme, že je chyba v programu kreslení, na kterém právě pracujete. Chcete-li reprodukovat chyby, otevřete řešení v sadě Visual Studio a stiskněte klávesu **F5** spustit ladění.

 Při kreslení čáry a zvolte **vrátit zpět Moje poslední tahu**, dokud kreslení na další řádek se nic nestane.

 ![Mapa kódu &#45; zkopírujte chyb](../modeling/media/codemapstoryboardpaint0.png)

 Takže spustíte tak, že na odstranění příčin `Undo` metoda. Najdete ho v `PaintCanvas` třídy.

 ![Mapa kódu &#45; najít kódu](../modeling/media/codemapstoryboardpaint1.png)

## <a name="start-mapping-the-code"></a>Spuštění mapování kódu
 Nyní spustit mapování `undo` metoda a jeho relace. Z editoru kódu můžete přidat `undo` metoda a polí, která odkazuje na novou mapu kódu. Když vytvoříte nové mapování, může zaindexování kódu trvat nějakou dobu. To pomáhá rychlejšímu běhu pozdějších operací.

 ![Mapa kódu &#45; zobrazit metoda a související pole](../modeling/media/codemapstoryboardpaint3.png)

> [!TIP]
>  Zelené zvýraznění zobrazí poslední položky, které byly přidány do mapy. Na zelenou šipku ukazuje kurzor na pozici v kódu. Šipky mezi položkami představují různé vztahy. Pohyb myši nad nimi a jejich popisy tlačítek prozkoumáním můžete získat další informace o položky na mapě.

 ![Mapa kódu &#45; zobrazit tipy](../modeling/media/codemapstoryboardpaint4.png)

## <a name="navigate-and-examine-code-from-the-map"></a>Procházení a zkoumání kódu z mapy
 Viz definice kód pro každé pole, dvakrát klikněte na pole na mapě nebo vyberte pole a stiskněte klávesu **F12**. Zelená šipka se přesune mezi položkami na mapě. Kurzor v editoru kódu se také přesune automaticky.

 ![Mapa kódu &#45; zkontrolujte definice pole](../modeling/media/codemapstoryboardpaint5.png)

 ![Mapa kódu &#45; zkontrolujte definice pole](../modeling/media/codemapstoryboardpaint5a.png)

> [!TIP]
>  Zelenou šipku na mapě můžete také přesunout přesunutím kurzoru v editoru kódu.

## <a name="understand-relationships-between-pieces-of-code"></a>Pochopení vztahů mezi částmi kódu
 Teď chcete vědět, jaké další kód spolupracuje s `history` a `paintObjects` pole. Můžete do mapy přidat všechny metody, které odkazují na tato pole. Můžete to provést z mapy nebo z editoru kódu.

 ![Mapa kódu &#45; najít všechny odkazy](../modeling/media/codemapstoryboardpaint6.png)

 ![Otevření mapy kódu z editoru kódu](../modeling/media/codemapstoryboardpaint6a.png)

> [!NOTE]
>  Pokud přidáte položky z projektu, jež jsou sdílena mezi více aplikacemi, jako je Windows Phone nebo Windows Store, pak tyto položky vždy zobrazí s projekt aktuálně aktivní aplikace na mapě. Ano Pokud změna kontextu na jiný projekt aplikace, pak kontext na mapě změní také pro nově přidané položky z sdílený projekt. Operace, které provádíte s položkou na mapě, se vztahují pouze na ty položky, které sdílejí stejný kontext.

 Změňte rozložení a uspořádejte tak tok vztahů a usnadněte čtení z mapy. Položky kolem mapy lze také přesunout přetažením.

 ![Mapa kódu &#45; změnit rozložení](../modeling/media/codemapstoryboardpaint7a.png)

> [!TIP]
>  Ve výchozím nastavení **přírůstkové rozložení** je zapnutý. To při přidání nových položek mění uspořádání mapy co nejméně. Chcete-li změnit celý mapy pokaždé, když přidáte nové položky, vypněte **přírůstkové rozložení**.

 ![Mapa kódu &#45; změnit rozložení](../modeling/media/codemapstoryboardpaint7.png)

 Podívejme se na tyto metody. Na mapě, dvakrát klikněte **PaintCanvas** metoda, nebo vyberte tato metoda a stiskněte klávesu **F12**. Zjistíte, že tato metoda vytvoří `history` a `paintObjects` jako prázdný seznamy.

 ![Mapa kódu &#45; Zkontrolujte definici metody](../modeling/media/codemapstoryboardpaint8.png)

 Teď zopakujte stejný postup prozkoumat `clear` definici metody. Zjistíte, které `clear` provádí některé úlohy s `paintObjects` a `history`. Potom zavolá `Repaint` metoda.

 ![Mapa kódu &#45; Zkontrolujte definici metody](../modeling/media/codemapstoryboardpaint9.png)

 Nyní zkontrolujte `addPaintObject` definici metody. Provádí taky některé úlohy s `history` a `paintObjects`. Také voláním `Repaint`.

 ![Mapa kódu &#45; Zkontrolujte definici metody](../modeling/media/codemapstoryboardpaint10.png)

## <a name="find-the-problem-by-examining-the-map"></a>Nalezení příčiny problému prozkoumáním mapy
 Zdá se, že všechny metody, které mění `history` a `paintObjects` volání `Repaint`. Ale `undo` není volání metody `Repaint`, i když `undo` upraví stejných polí. Proto si myslíte, že tento problém můžete vyřešit voláním `Repaint` z `undo`.

 ![Mapa kódu &#45; najít chybí volání metody](../modeling/media/codemapstoryboardpaint11.png)

 Pokud by nebyla nastavena mapa k zobrazení tohoto chybějícího volání, mohlo by být nalezení tohoto problému obtížnější, zejména u složitějšího kódu.

## <a name="share-your-discovery-and-next-steps"></a>Sdílení zjištění a další kroky
 Předtím, než vy nebo někdo jiný tuto chybu vyřeší, si můžete dělat na mapě poznámky o problému a způsobu jeho řešení.

 ![Mapa kódu &#45; komentáře a příznak položky pro zpracování](../modeling/media/codemapstoryboardpaint12.png)

 Můžete například přidat komentáře do mapy a označit položky pomocí barev.

 ![Mapa kódu &#45; komentářem a označení položky](../modeling/media/codemapstoryboardpaint12a.png)

 Pokud máte nainstalovanou aplikaci Microsoft Outlook, můžete mapu e-mailem odeslat ostatním. Mapu taky můžete exportovat jako obrázek nebo jiný formát.

 ![Mapa kódu &#45; sdílenou složku, export, e-mailu](../modeling/media/codemapstoryboardpaint13.png)

## <a name="fix-the-problem-and-show-what-you-did"></a>Vyřešení problému a zobrazení provedené činnosti
 Pokud chcete vyřešit tuto chybu, přidejte volání pro `Repaint` k `undo`.

 ![Mapa kódu &#45; přidejte chybějící volání metody](../modeling/media/codemapstoryboardpaint14.png)

 Chcete-li potvrdit svou opravu, restartujte relaci ladění a zkuste chybu reprodukovat. Teď vyberete **vrátit zpět Moje poslední tahu** funguje podle očekávání a potvrdí provedené správná oprava.

 ![Mapa kódu &#45; potvrdit kódu oprava](../modeling/media/codemapstoryboardpaint15.png)

 Můžete aktualizovat mapu, aby zobrazovala provedené opravy.

 ![Mapa kódu &#45; mapa aktualizace s chybějící volání metody](../modeling/media/codemapstoryboardpaint16.png)

 Mapu nyní zobrazuje propojení mezi **vrátit zpět** a **překreslit**.

 ![Mapa kódu &#45; aktualizované mapa s volání metody](../modeling/media/codemapstoryboardpaint17.png)

> [!NOTE]
>  Při aktualizaci mapy se může zobrazit zpráva, že byl aktualizován index kódu použitý k vytvoření mapy. To znamená, že někdo změnil kód, což způsobilo, že se vaše mapa neshoduje s aktuálním kódem. To vám nezabrání v aktualizaci mapy, ale chcete-li ověřit, že mapa odpovídá kódu, pravděpodobně ji budete muset znovu vytvořit.

 Nyní jste hotovi s šetření. Úspěšně jste našli a opravili problém pomocí mapování kódu. Máte k dispozici také mapu, která usnadňuje navigaci v rámci kódu, zapamatuje si, co jste se naučili, a zobrazí kroky, které jste provedli v zájmu vyřešení problému.

## <a name="see-also"></a>Viz také

- [Mapování metod v zásobníku volání při ladění](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)
- [Vizualizace kódu](../modeling/visualize-code.md)
