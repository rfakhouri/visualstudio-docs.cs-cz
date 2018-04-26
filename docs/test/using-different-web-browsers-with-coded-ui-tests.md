---
title: Používání jiných webových prohlížečů v programových testů uživatelského rozhraní v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 0f8efe8f64c166a549080d10432fd0dd7e241f79
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="use-different-web-browsers-with-coded-ui-tests"></a>Jiných webových prohlížečů pomocí programových testů uživatelského rozhraní

Programové testy UI mohou automatizovat testování webových aplikací tím, že zaznamenají vaše testy pomocí aplikace Internet Explorer. Potom můžete přizpůsobit test a přehrát jej buď pomocí aplikace Internet Explorer, nebo jiných typů prohlížečů pro tyto webové aplikace.

Nejdřív nainstalujte [selenu součásti pro programové testování uživatelského rozhraní mezi prohlížeče](https://marketplace.visualstudio.com/items?itemName=AtinBansal.SeleniumcomponentsforCodedUICrossBrowserTesting).

## <a name="whats-supported-across-all-web-browsers"></a>Co je podporovaná ve všech webových prohlížečů?

-   [Přidat vlastní kód pro řízení funkcí](http://blogs.msdn.com/b/visualstudioalm/archive/2012/12/10/coded-ui-test-configuring-search-properties-while-recording-on-internet-explorer.aspx) například procesy čekající vlastnosti, vyhledávání a přehrávání.

-   Automaticky otevíraná okna a dialogová okna

-   [Provedení základní JavaScript s žádný návratový typ](http://blogs.msdn.com/b/visualstudioalm/archive/2013/01/18/introducing-jscript-execution-on-internetexplorer-and-crossbrowser-in-coded-ui-test.aspx)

-   Hledání odolnost (pomocí inteligentní shoda) a [vylepšení výkonu](http://blogs.msdn.com/b/visualstudioalm/archive/2012/02/01/guidelines-on-improving-performance-of-coded-ui-test-playback.aspx)

## <a name="why-should-i-use-coded-ui-tests-across-multiple-web-browser-types"></a>Proč bych měl používat programové testy UI napříč několika typy webových prohlížečů?

Při testování webové aplikace pomocí různých typů webových prohlížečů můžete lépe emulovat zkušenosti vašich uživatelů s uživatelským rozhraním na různých prohlížečích. Aplikace může například obsahovat ovládací prvek nebo kód v aplikaci Internet Explorer, který není kompatibilní s jinými webovými prohlížeči. Spuštěním programových testů UI na různých prohlížečích můžete objevit a opravit jakýkoliv problém předtím, než ovlivní vaše zákazníky.

## <a name="how-do-i-record-and-play-back-coded-ui-tests-on-web-applications-using-the-supported-web-browsers"></a>Jak mohu zaznamenat a přehrát programové testy UI webových aplikacích pomocí podporovaných webových prohlížečů?

**Záznam:** Tvůrce testování uživatelského rozhraní programového musíte použít k zaznamenání test vaší webové aplikace pomocí Internet Exploreru. Volitelně můžete pomocí předdefinované sady vlastností přidat kód pro ověření a přizpůsobení testovaných ovládacích prvků, jak byste to obvykle udělali v případě programových testů UI. Další informace najdete v tématu [uživatelského rozhraní automatizace k testu si kód použití](../test/use-ui-automation-to-test-your-code.md).

> [!NOTE]
> Programové testy UI nelze zaznamenat pomocí prohlížečů Google Chrome nebo Mozilla Firefox.

 **Přehrání s aplikací Internet Explorer:** když je explicitně zadané žádné prohlížeče, budou spuštěny testy v Internet Exploreru ve výchozím nastavení. Můžete explicitně stavu prohlížeče, který má být používána nastavení **BrowserWindow.CurrentBrowser** vlastnost testovacího kódu. Internet Explorer, musí být tato vlastnost nastavená na **IE** nebo **Internet Explorer**.

 **Přehrání u webových prohlížečů Internet Explorer:** přehrání na webové prohlížeče Internet Explorer, změňte vlastnost BrowserWindow.CurrentBrowser v testovacího kódu na buď **Firefox** nebo **Chrome** .

 Přehrát testy na jiný IE webových prohlížečů, je nutné nainstalovat **selenu součásti pro programové testování uživatelského rozhraní mezi prohlížeče**.

### <a name="install-selenium-components"></a>Nainstalujte komponenty selenu

1.  Na **nástroje** nabídce zvolte **rozšíření a aktualizace**.

2.  V dialogovém okně rozšíření a aktualizace vyhledejte `Selenium components for Cross Browser Testing`.

3.  Zvýrazněte rozšíření a zvolte **Stáhnout**.

    > [!TIP]
    > Můžete také stáhnout komponenty selenu pro programové testování uživatelského rozhraní mezi prohlížeče z [zde](https://marketplace.visualstudio.com/items?itemName=AtinBansal.SeleniumcomponentsforCodedUICrossBrowserTesting).

Další informace o vytváření a používání uživatelského rozhraní programových testů, najdete v části [vytváření programových testů uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md).

### <a name="enable-debugging"></a>Povolení ladění

Chcete-li povolit ladění webové aplikace, je nutné dokončit následující možnosti konfigurace:

1.  Povolit volbu Pouze vlastní kód:

    1.  Na **nástroje** nabídce zvolte **možnosti** a potom zvolte **ladění**.

    2.  Vyberte **povolit pouze můj kód**.

2.  Zakázání výjimek CLR:

    1.  Na **ladění** nabídce zvolte **výjimky**.

    2.  Pro **výjimky modulu CLR**, zrušte zaškrtnutí políčka **neošetřené uživatelem**.

Pokud nevidíte možnost změnit `BrowserWindow.CurrentBrowser` v programového testu uživatelského rozhraní používáte verzi Visual Studia, která nepodporuje programových testů uživatelského rozhraní pomocí různých webových prohlížečů. Pokud chcete používat takové programové testy uživatelského rozhraní, musíte použít Visual Studio Enterprise edition.

Zde jsou některé věci, které byste měli vědět:

- Webový prohlížeč Apple Safari není podporován.

- Akce spuštění webového prohlížeče musí být součástí programového testu UI.

   Pokud je již webový prohlížeč otevřen a chcete v něm spustit příslušné kroky, aniž byste používali aplikaci Internet Explorer, přehrávání selže. Je proto vhodné zahrnout spuštění webového prohlížeče jako součást programových testů UI.

- Automatizace akcí UI specifických podle prohlížeče, jako je maximalizace, minimalizace a obnovení, není podporována.

## <a name="tips"></a>Tipy

Můžete nakonfigurovat výstup tak, aby obsahoval snímky obrazovky v kódovaných protokolech UI. Chcete-li to provést, musíte nastavit některá nastavení konfigurace *QTAgent32.exe.config* souboru. Ve výchozím nastavení je tento soubor nainstalován v následujícím umístění:

     *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*

Nastavte následující hodnoty:

- `EqtTraceLevel` v `system.diagnostics` oddílu.

- `<add name="EqtTraceLevel" value="4" />`

   Nastavení na hodnotu 3 nebo vyšší, jsou snímky obrazovky převzat pro každou akci. Pokud je hodnota nastavena na 1 nebo 2, budou snímky obrazovky pořízeny pouze pro chybové akce.

Další informace najdete v tématu [analýza programových testů pomocí programových uživatelského rozhraní protokolů z těchto testů](../test/analyzing-coded-ui-tests-using-coded-ui-test-logs.md).

## <a name="video-resources"></a>Grafické prostředky

 [Záznam v aplikaci Internet Explorer a přehrávání everywhere](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!183&authkey=!ANqaLtCZbtJrImU)

 [Autor křížové prohlížeč testů pomocí Tvůrce programového testu uživatelského rozhraní](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!184&authkey=!AKG8CSow_qmeTq8)

 [Autor křížové prohlížeč testů s použitím prostý ruční kódování bez mapy uživatelského rozhraní](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!186&authkey=!AJaEvxJnsefyAT4)

 [Testy křížové prohlížeče postupně na více prohlížečů](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!187&authkey=!ADI8eCQkxHnpOR8)

 [Řešení potíží s křížové selhání při testu prohlížeče](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!182&authkey=!AEpS48i295B49FI)

## <a name="see-also"></a>Viz také

- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
- [Analýza programových testů uživatelského rozhraní pomocí protokolů z těchto testů](../test/analyzing-coded-ui-tests-using-coded-ui-test-logs.md)
