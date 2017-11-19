---
title: "Používání jiných webových prohlížečů s programové testy uživatelského rozhraní | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a859595f-6517-43f2-9d61-c706cb55a388
caps.latest.revision: "23"
ms.author: douge
manager: douge
ms.openlocfilehash: 6c8e2cac9d6f2622bacae0b27cecc8f074ea3a15
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="using-different-web-browsers-with-coded-ui-tests"></a>Používání jiných webových prohlížečů v programových testech uživatelského rozhraní
Programové testy UI mohou automatizovat testování webových aplikací tím, že zaznamenají vaše testy pomocí aplikace Internet Explorer. Potom můžete přizpůsobit test a přehrát jej buď pomocí aplikace Internet Explorer, nebo jiných typů prohlížečů pro tyto webové aplikace.  
  
 **Požadavky**  
  
-   Visual Studio Enterprise  
  
-   Operační systémy:  
  
    -   Microsoft Windows 7  
  
    -   Microsoft Windows 8  
  
    -   Microsoft Windows Server 2008 R2 SP1  
  
-   Verze webového prohlížeče:  
  
    -   Windows Internet Explorer 9  
  
    -   Aplikaci Windows Internet Explorer 10  
  
    -   Podporované verze Mozilla Firefox a Google Chrome, přejděte [sem](http://visualstudiogallery.msdn.microsoft.com/11cfc881-f8c9-4f96-b303-a2780156628d/)  
  
-   Nainstalujte [selenu součásti pro programové testování uživatelského rozhraní mezi prohlížeče](http://visualstudiogallery.msdn.microsoft.com/11cfc881-f8c9-4f96-b303-a2780156628d/).  
  
 **Co je podporovaná ve všech webových prohlížečů?**  
  
-   [Přidat vlastní kód pro řízení funkcí](http://blogs.msdn.com/b/visualstudioalm/archive/2012/12/10/coded-ui-test-configuring-search-properties-while-recording-on-internet-explorer.aspx) například procesy čekající vlastnosti, vyhledávání a přehrávání.  
  
-   Automaticky otevíraná okna a dialogová okna  
  
-   [Provedení základní JavaScript s žádný návratový typ](http://blogs.msdn.com/b/visualstudioalm/archive/2013/01/18/introducing-jscript-execution-on-internetexplorer-and-crossbrowser-in-coded-ui-test.aspx)  
  
-   Hledání odolnost (pomocí inteligentní shoda) a [vylepšení výkonu](http://blogs.msdn.com/b/visualstudioalm/archive/2012/02/01/guidelines-on-improving-performance-of-coded-ui-test-playback.aspx)  
  
## <a name="why-should-i-use-coded-ui-tests-across-multiple-web-browser-types"></a>Proč bych měl používat programové testy UI napříč několika typy webových prohlížečů?  
 Při testování webové aplikace pomocí různých typů webových prohlížečů můžete lépe emulovat zkušenosti vašich uživatelů s uživatelským rozhraním na různých prohlížečích. Aplikace může například obsahovat ovládací prvek nebo kód v aplikaci Internet Explorer, který není kompatibilní s jinými webovými prohlížeči. Spuštěním programových testů UI na různých prohlížečích můžete objevit a opravit jakýkoliv problém předtím, než ovlivní vaše zákazníky.  
  
## <a name="how-do-i-record-and-play-back-coded-ui-tests-on-web-applications-using-the-supported-web-browsers"></a>Jak mohu zaznamenat a přehrát programové testy UI webových aplikacích pomocí podporovaných webových prohlížečů?  
 **Záznam:** Tvůrce testování uživatelského rozhraní programového musíte použít k zaznamenání test vaší webové aplikace pomocí Internet Exploreru. Volitelně můžete pomocí předdefinované sady vlastností přidat kód pro ověření a přizpůsobení testovaných ovládacích prvků, jak byste to obvykle udělali v případě programových testů UI. Další informace najdete v tématu [uživatelského rozhraní automatizace k testu si kód použití](../test/use-ui-automation-to-test-your-code.md).  
  
> [!NOTE]
>  Programové testy UI nelze zaznamenat pomocí prohlížečů Google Chrome nebo Mozilla Firefox.  
  
 **Přehrání s aplikací Internet Explorer:** když je explicitně zadané žádné prohlížeče, budou spuštěny testy v Internet Exploreru ve výchozím nastavení. Můžete explicitně stavu prohlížeče, který má být používána nastavení **BrowserWindow.CurrentBrowser** vlastnost testovacího kódu. Internet Explorer, musí být tato vlastnost nastavená na **IE** nebo **Internet Explorer**.  
  
 **Přehrání u webových prohlížečů Internet Explorer:** přehrání na webové prohlížeče Internet Explorer, změňte vlastnost BrowserWindow.CurrentBrowser v testovacího kódu na buď **Firefox** nebo **Chrome** .  
  
 Přehrát testy na jiný IE webových prohlížečů, je nutné nainstalovat **selenu součásti pro programové testování uživatelského rozhraní mezi prohlížeče**.  
  
#### <a name="installing-selenium-components"></a>Instalace součástí Selenium  
  
1.  Na **nástroje** nabídce zvolte **rozšíření a aktualizace**.  
  
2.  V dialogovém okně rozšíření a aktualizace vyhledejte `Selenium components for Cross Browser Testing`.  
  
3.  Zvýrazněte rozšíření a zvolte **Stáhnout**.  
  
    > [!TIP]
    >  Můžete také stáhnout komponenty selenu pro programové testování uživatelského rozhraní mezi prohlížeče z [zde](http://visualstudiogallery.msdn.microsoft.com/11cfc881-f8c9-4f96-b303-a2780156628d/).  
  
 Další informace o vytváření a používání uživatelského rozhraní programových testů, najdete v části [vytváření programových testů uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate).  
  
### <a name="enable-debugging"></a>Povolení ladění  
 Chcete-li povolit ladění webové aplikace, je nutné dokončit následující možnosti konfigurace:  
  
1.  Povolit volbu Pouze vlastní kód:  
  
    1.  Na **nástroje** nabídce zvolte **možnosti** a potom zvolte **ladění**.  
  
    2.  Vyberte **povolit pouze můj kód**.  
  
2.  Zakázání výjimek CLR:  
  
    1.  Na **ladění** nabídce zvolte **výjimky**.  
  
    2.  Pro **výjimky modulu CLR**, zrušte zaškrtnutí políčka **neošetřené uživatelem**.  
  
##  <a name="generate"></a>*Možnosti změnit BrowserWindow.CurrentBrowser v programového testu uživatelského rozhraní se nezobrazí.*  
 Používáte verzi [!INCLUDE[vs2011_first](../test/includes/vs2011_first_md.md)] nepodporuje programových testů uživatelského rozhraní pomocí různých webových prohlížečů. Pokud chcete používat takové programové testy uživatelského rozhraní, musíte použít Visual Studio Enterprise.  
  
 *Co je třeba vědět?*  
 **Poznámky**  
  
-   ![Prerequsite](../test/media/prereq.png "požadavků") Apple Safari webový prohlížeč není podporován.  
  
-   ![Prerequsite](../test/media/prereq.png "požadavků") akce spuštění webového prohlížeče musí být součástí programového testu uživatelského rozhraní.  
  
     Pokud je již webový prohlížeč otevřen a chcete v něm spustit příslušné kroky, aniž byste používali aplikaci Internet Explorer, přehrávání selže. Je proto vhodné zahrnout spuštění webového prohlížeče jako součást programových testů UI.  
  
-   ![Prerequsite](../test/media/prereq.png "požadavků") konkrétní automatizace prohlížeče na základě akcí uživatelského rozhraní, jako je maximalizovat, minimalizovat a obnovení není podporována.  
  
 **Tipy**  
  
-   ![Tip](../test/media/tip.png "Tip") můžete nakonfigurovat výstup programové uživatelského rozhraní protokolů zahrnout snímky obrazovky. Chcete-li tak učinit, musíte provést některá nastavení konfigurace v souboru QTAgent32.exe.config. Ve výchozím nastavení je tento soubor nainstalován v následujícím umístění:  
  
     **C:\Program soubory (x86) \Microsoft Visual Studio 11.0\Common7\IDE**  
  
     Nastavte následující hodnoty:  
  
    -   `EqtTraceLevel`v `system.diagnostics` oddílu.  
  
    -   `<add name="EqtTraceLevel" value="4" />`  
  
         Nastavíte-li hodnotu 3 nebo vyšší, budou snímky obrazovky pořízeny pro každou akci. Pokud je hodnota nastavena na 1 nebo 2, budou snímky obrazovky pořízeny pouze pro chybové akce.  
  
     Další informace najdete v tématu [analýza programových testů pomocí programových uživatelského rozhraní protokolů z těchto testů](../test/analyzing-coded-ui-tests-using-coded-ui-test-logs.md).  
  
## <a name="external-resources"></a>Externí zdroje  
  
### <a name="videos"></a>Videa  
 [Záznam v aplikaci Internet Explorer a přehrávání everywhere](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!183&authkey=!ANqaLtCZbtJrImU)  
  
 [Autor křížové prohlížeč testů pomocí Tvůrce programového testu uživatelského rozhraní](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!184&authkey=!AKG8CSow_qmeTq8)  
  
 [Autor křížové prohlížeč testů s použitím prostý ruční kódování bez mapy uživatelského rozhraní](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!186&authkey=!AJaEvxJnsefyAT4)  
  
 [Testy křížové prohlížeče postupně na více prohlížečů](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!187&authkey=!ADI8eCQkxHnpOR8)  
  
 [Řešení potíží s křížové selhání při testu prohlížeče](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!182&authkey=!AEpS48i295B49FI)  
  
### <a name="guidance"></a>Doprovodné materiály  
 [Testování pro nastavené průběžné doručování s Visual Studio 2012 – kapitoly 2: testování částí: testování uvnitř](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
 [Testování pro nastavené průběžné doručování s Visual Studio 2012 – kapitoly 5: automatizace systémových testů](http://go.microsoft.com/fwlink/?LinkID=255196)  
  
### <a name="faq"></a>Nejčastější dotazy  
 [Časté otázky – 1 testy programové uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=230576)  
  
 [Programové testy UI -2 – nejčastější dotazy](http://go.microsoft.com/fwlink/?LinkID=230578)  
  
### <a name="forum"></a>Fórum  
 [Visual Studio testování uživatelského rozhraní automatizace (zahrnuje programového uživatelského rozhraní)](http://go.microsoft.com/fwlink/?LinkID=224497)  
  
## <a name="see-also"></a>Viz také  
 [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)   
 [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)   
 [Analýza programových testů uživatelského rozhraní pomocí protokolů z těchto testů](../test/analyzing-coded-ui-tests-using-coded-ui-test-logs.md)
