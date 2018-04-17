---
title: Funkce IntelliTrace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- IntelliTrace, debugging with events
- IntelliTrace, recording execution history
- debugging [Visual Studio ALM], recording execution history
- IntelliTrace, turn off
- IntelliTrace, navigating event and call history
- IntelliTrace, saving your session
- IntelliTrace, enabling
- IntelliTrace, start debugging
- IntelliTrace, debugging with events and call information
- IntelliTrace, disabling
- IntelliTrace, turn on
- debugging [Visual Studio ALM], IntelliTrace
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6f4d407414c941d8c7658aa0d6f98f5b18d60244
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="intellitrace-features"></a>Funkce IntelliTrace

Můžete zaznamenat události IntelliTrace a metoda volá vaší aplikaci, což umožňuje zkontrolovat stav (zásobník volání a místní proměnné hodnoty) v různých okamžicích v provádění. Stačí spustit ladění obvyklým – IntelliTrace je zapnutá ve výchozím nastavení a zobrazí se informace, které je v novém záznamu IntelliTrace **diagnostické nástroje** v části **události** kartě. Vyberte událost a klikněte na **aktivovat historické ladění** zobrazíte zásobník volání a místní hodnoty zaznamenány pro tuto událost.

Podrobný popis naleznete v tématu [návod: použití IntelliTrace](../debugger/walkthrough-using-intellitrace.md).

IntelliTrace je k dispozici v Visual Studio Enterprise edition, ale není v edice Visual Studio Professional nebo komunity.

Pokud chcete ověřit, jestli je zapnutá IntelliTrace, otevřete **nástroje > Možnosti > IntelliTrace** stránka Možnosti. **Povolit IntelliTrace** by měl být ve výchozím nastavení zaškrtnuto.

> [!NOTE]
> Rozsah všechna nastavení na **IntelliTrace** stránka možnosti je jako celek, ne z individuálních projekty nebo řešení sady Visual Studio. Ke změně těchto nastavení se vztahuje na všechny instance sady Visual Studio, všechny ladění relací a všechny projekty nebo řešení.

## <a name="ChooseEvents"></a> Zvolte události, že záznamy IntelliTrace

Můžete zapnout nebo vypnout záznam pro konkrétní události IntelliTrace.

Pokud ladíte, zastavte ladění. Přejděte na **nástroje > Možnosti > IntelliTrace > události IntelliTrace**. Vyberte události, které chcete IntelliTrace k zaznamenání.

## <a name="Snapshots"></a> Shromažďovat události a snímky

Tato možnost není povolena ve výchozím nastavení, ale IntelliTrace můžete zachycení snímků vaší aplikace na každý krok události zarážek a ladicí program a tato snímky si můžete prohlédnout v historické ladicí relace. Snímek nabízí zobrazení stavu vaší celou aplikaci. Chcete-li povolit zachytávání snímků, přejděte na **nástroje > Možnosti > IntelliTrace > Obecné**a vyberte **IntelliTrace události a snímky**. Další informace najdete v tématu [zobrazit snímky pomocí zpětný krok IntelliTrace](../debugger/how-to-use-intellitrace-step-back.md)

Snímky jsou k dispozici v aplikaci Visual Studio Enterprise 2017 verze 15,5 a vyšší a vyžaduje Windows 10 Anniversary Update nebo vyšší.  Pro aplikace .NET Core a ASP.NET Core je požadovaná verze Visual Studio Enterprise 2017 15.7 preview 1.

## <a name="GoingFurther"></a> Shromáždit události IntelliTrace a informace o voláních

Tato možnost není povolena ve výchozím nastavení, ale IntelliTrace můžete zaznamenat volání metod společně s událostí. Chcete-li povolit shromažďování metoda volání přejděte na **nástroje > Možnosti > IntelliTrace > Obecné**a vyberte **události IntelliTrace a volání informace**.

Informace o volání není aktuálně k dispozici pro aplikace .NET Core a ASP.NET Core. 

To vám umožní naleznete v historii zásobník volání a krok zpět a předávat prostřednictvím volání do vašeho kódu. IntelliTrace zaznamenává data, jako jsou názvy metod, metoda vstupní a výstupní místa a určité hodnoty parametrů a návratové hodnoty.

> [!TIP]
> Tato možnost není ve výchozím nastavení povolená, protože přidá značné režijní náklady na. Nejen zachytávat každé volání metody, které vaše aplikace provede má IntelliTrace, ale má také jak nakládat s mnohem větší sady dat, pokud jde o zobrazují na obrazovce nebo uložením na disk.
>
> Můžete snížit režijní výkon omezením seznam událostí, že záznamy IntelliTrace a tak počet modulů shromažďujete na minimum. Další informace najdete v tématu [řízení kolik volání informace IntelliTrace záznamy](../debugger/intellitrace-features.md#ControlCallData).

### <a name="use-the-navigation-gutter"></a>Použití navigační mezera

Můžete navigační mezera, který se zobrazí vlevo od okno kódu. Pokud nevidíte navigační mezera, přejděte na **nástroje > Možnosti > IntelliTrace > Upřesnit**a vyberte **zobrazit navigační mezera v režimu ladění**.

Navigační mezera umožňuje přesunout dopředný a zpětné volání metod a události v historické ladění režimu. Další informace o historické ladění najdete v tématu [historické ladění](../debugger/historical-debugging.md). Má řadu příkazů:

|||
|-|-|
|**Zde nastaveného kontextu ladicího programu**|Nastavte ladění kontext na volání časový rámec, ve kterém se zobrazí.<br /><br /> Tato ikona se zobrazí pouze v aktuální zásobníku volání.|
|**Vraťte se na volání lokality**|Přesuňte ukazatel a ladění kontextu zpět na kde byl volán aktuální funkce.<br /><br /> Pokud jste v režimu ladění za provozu, tento příkaz zapne historické ladění. Pokud přejdete zpět na původní pozastavení provádění, historické ladění je vypnutý a živé ladění je zapnutý.|
|**Přejít na předchozí volání nebo události IntelliTrace**|Přesuňte ukazatel a ladění kontextu zpět do předchozího volání nebo událost.<br /><br /> Pokud jste v režimu ladění za provozu, zapne se tento příkaz historické ladění.|
|**Krok v**|Krokovat s vnořením aktuálně vybrané funkce.<br /><br /> Tento příkaz je k dispozici jenom v případě, že jste v režimu historické ladění.|
|**Přejděte na další volání nebo události IntelliTrace**|Další volání nebo událostí, pro které IntelliTrace dat existuje, přesuňte ukazatel a ladění kontextu.<br /><br /> Tento příkaz je k dispozici jenom v případě, že jste v režimu historické ladění.|
|**Přejděte do režimu za provozu**|Vrátí do režimu ladění za provozu.|

### <a name="search-for-a-line-or-method-in-intellitrace"></a>Vyhledejte řádek nebo v IntelliTrace – metoda

Metody můžete hledat pouze v případě, že bylo povoleno informace volání metody. Můžete hledat historie IntelliTrace pro konkrétní řádek nebo metoda. Při spuštění ladicího programu je zastavit, klikněte pravým tlačítkem uvnitř tělo funkce zobrazíte v místní nabídce a klikněte na možnost **vyhledávání pro tento řádek v IntelliTrace** nebo **vyhledávání pro tato metoda v IntelliTrace**.

### <a name="ControlCallData"></a> Řízení záznamy IntelliTrace informace o tom, kolik volání

Ve výchozím nastavení IntelliTrace zaznamenává informace pro všechny moduly používané v řešení. IntelliTrace můžete nastavit na informace o záznamu volání pouze pro moduly, které vás zajímají. V **nástroje > Možnosti > IntelliTrace > moduly**, můžete zadat moduly, které chcete zahrnout nebo moduly, které chcete vyloučit z IntelliTrace. IntelliTrace bude shromažďovat jenom události, které pochází z modulů, které jste zadali, a volání metod, které bylo provedeno v rámci moduly se zajímáte.

Chcete-li přidat více modulů, použijte zástupný znak * na začátku nebo konci řetězce. V případě názvů modulů použijte názvy souborů, nikoli názvy sestavení. Není možné použít cesty k souborům.

Pokuste se zachovat počet modulů na minimum. Můžete získat lepší výkon, protože je méně dat, které se mají shromažďovat. Můžete také získat méně šumu v uživatelském rozhraní protože méně dat, projděte.

## <a name="SaveSession"></a> Uložit do souboru dat technologie IntelliTrace

Můžete uložit data, která shromáždil IntelliTrace chystáte **ladění > IntelliTrace > Uložit relace IntelliTrace** při ladění a aplikace je ve stavu pozastavení. Položky nabídky je zakázána a nebudete moci ukládat data, která shromáždil IntelliTrace, pokud aplikace stále běží, nebo pokud je nutné zastavit ladění.

Můžete nakonfigurovat IntelliTrace automaticky uložit do souboru přechodem na **nástroje > Možnosti > IntelliTrace > Upřesnit** a výběrem **IntelliTrace úložiště záznamy v tomto adresáři**. Můžete také nakonfigurovat nastavení velikosti pro vygenerovaný soubor, což způsobí, že IntelliTrace zapisovat přes starší data, pokud jí dojde místo. Visual Studio vytvoří dva soubory pro každou relaci IntelliTrace, když se automaticky uloží a proces hostování (vshost.exe) sady Visual Studio je zapnutý.

> [!TIP]
> Chcete-li ušetřit místo na disku, vypněte ukládání souborů automaticky, když je již nejsou potřebné. Všechny existující soubory nebudou odstraněna. Můžete vždy uložit do souboru na vyžádání v místní nabídce.

Při ukládání dat technologie IntelliTrace do souboru, získáte jeden soubor .itrace pro jednotlivé procesy, které IntelliTrace shromážděny z. Pak můžete otevřít soubor .itrace v sadě Visual Studio přechodem na **soubor > Otevřít > soubor** a vyberete soubor .itrace z dialogové okno otevřít soubor. Další informace najdete v tématu [pomocí uložit dat technologie IntelliTrace](../debugger/using-saved-intellitrace-data.md).

## <a name="blogs"></a>Blogy

[IntelliTrace v sadě Visual Studio Enterprise 2015](http://blogs.msdn.com/b/visualstudioalm/archive/2015/01/16/intellitrace-in-visual-studio-ultimate-2015.aspx)

[Návod systému za provozu ladění použití IntelliTrace ve Visual Studiu 2015 (textovém editoru)](http://blogs.msdn.com/b/visualstudioalm/archive/2015/01/16/walkthrough-of-live-debugging-using-intellitrace-in-visual-studio-2015-text-editor.aspx)

[Návod systému za provozu ladění použití IntelliTrace ve Visual Studiu 2015 (sociální křížovou kartou)](http://blogs.msdn.com/b/visualstudioalm/archive/2000/1/1/walkthrough-of-live-debugging-using-intellitrace-in-visual-studio-2015-social-club.aspx)

[IntelliTrace v sadě Visual Studio Enterprise 2015 teď podporuje připojení!](http://blogs.msdn.com/b/visualstudioalm/archive/2015/05/14/intellitrace-in-visual-studio-enterprise-2015-now-supports-attach.aspx)

[Shromažďování dat ze služby systému windows pomocí samostatného sběrače IntelliTrace](http://blogs.msdn.com/b/visualstudioalm/archive/2015/05/14/collect-data-from-a-windows-service-using-the-intellitrace-standalone-collector.aspx)

[Úpravy plán kolekce IntelliTrace](http://blogs.msdn.com/b/visualstudioalm/archive/2015/03/09/editing-the-intellitrace-collection-plan.aspx)

[Vlastní třídy TraceSource a ladění použití IntelliTrace](http://blogs.msdn.com/b/visualstudioalm/archive/2014/12/17/custom-tracesource-and-debugging-using-intellitrace.aspx)

[Spuštění samostatného sběrače IntelliTrace a fondů aplikací v rámci účtů služby Active Directory](http://blogs.msdn.com/b/visualstudioalm/archive/2014/12/22/intellitrace-standalone-collector-and-application-pools-running-under-active-directory-accounts.aspx)

## <a name="forums"></a>Diskuzní fóra

[Ladicí program Visual Studio](http://go.microsoft.com/fwlink/?LinkId=262263)

## <a name="videos"></a>Videa

[Prostředí IntelliTrace](https://channel9.msdn.com/Series/Visual-Studio-2015-Enterprise-Videos/IntelliTrace-Experience)

[Historické ladění pomocí technologie IntelliTrace v sadě Microsoft Visual Studio Ultimate 2015](https://channel9.msdn.com/events/Ignite/2015/BRK3716)
