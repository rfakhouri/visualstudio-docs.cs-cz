---
title: "Oznámení a postup pro sadu Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0ef65e9-0f1f-45f4-9f25-6e2398691168
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0721d0080ec135a8e969cc420dfbb51e81ac4454
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="notifications-and-progress-for-visual-studio"></a>Oznámení a postup pro sadu Visual Studio
##  <a name="BKMK_NotificationSystems"></a>Systémy oznámení  
  
### <a name="overview"></a>Přehled  
 Informujte uživatele, co se děje v sadě Visual Studio týkající se softwaru vývoj úkoly několika způsoby.  
  
 Při implementaci jakýkoli druh oznámení:  
  
-   **Zachovat počet oznámení na minimum** efektivní číslo. Zprávy s oznámením by se měly používat pro většinu uživatelů sady Visual Studio nebo uživatelům oblasti konkrétní funkce nebo funkce. Nadměrnému využití oznámení může sidetrack uživatele nebo snížit dosahovaný snadné použití systému.  
  
-   **Ujistěte se, jsou prezentací jasné, kterého lze provést akci zprávy** , uživatel může použít k vyvolání odpovídající kontext pro volby při složitější a další akci.  
  
-   **Synchronní a asynchronní zprávy k dispozici správně.** Synchronní oznámení znamenat, že něco vyžaduje okamžitou pozornost, například když dojde k chybě webové služby nebo kód je vyvolána výjimka. Uživatel by měl být informováni o těchto situacích hned způsobem, který vyžaduje jejich vstupu, například v modální dialogové okno. Asynchronní oznámení jsou ty, které uživatel byste se měli seznámit, ale nebyla požadované k provedení akce okamžitě, například po dokončení operace sestavení nebo dokončení nasazení webu. Tyto zprávy by měl být více vedlejším a přerušit tok úkolů uživatele.  
  
-   **Modální dialogová okna pouze v případě potřeby brání uživateli, provádět další akce pomocí** před to v úvahu zprávy nebo rozhodování uvedené v dialogovém okně.  
  
-   **Odeberte vedlejším oznámení, pokud již nejsou platné.** Nevyžadují, aby uživatelům zavření oznámení, pokud již provedli akce k vyřešení problému, které byly upozorněn.  
  
-   **Upozorňujeme, že oznámení může vést k false korelací.** Uživatelé možná se domníváte, že jeden nebo více svých akcí má aktivaci oznámení při ve skutečnosti se žádný příčinnou vztah. Být zrušte v oznámení o kontextu, aktivační události a zdroj oznámení.  
  
### <a name="choosing-the-right-method"></a>Volba správné metody  
 Použijte tato tabulka vám pomůže v výběr správné metody pro uživatele zprávu.  
  
|Metoda|Použití|Nepoužívejte|  
|------------|---------|----------------|  
|[Zpráva Chyba modální dialogová okna](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ModalErrorMessageDialogs)|Použijte v případě, že se před pokračováním vyžaduje odpověď uživatele.|Nepoužívejte při není třeba blokování uživatele a jejich toku přerušení. Pokud je možné zobrazit zprávu v jiné, šetrnější způsob nepoužívejte modální dialogová okna.|  
|[IDE stavového řádku](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_IDEStatusBar)|Použijte v případě, že je vedlejším textové informace týkající se stavu procesu.|Nepoužívejte samostatně. Nejlépe používá ve spojení s jiný mechanismus zpětnou vazbu.|  
|[Vložené informační panel](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_EmbeddedInfobar)|V okně nástroje nebo okna dokumentu do průběh, chybového stavu, výsledky a aktuální informace, s pomocí.|Nepoužívejte Pokud informace se nevztahuje na umístění, kde je umístěn na informační panel.<br /><br /> Nepoužívejte mimo okno dokumentu nebo nástroje.|  
|[Změny kurzor myši](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_MouseCursorChanges)|Slouží k upozornění, že se proces děje. Rovněž oznámit, že dojde ke změně stavu v myši, jako když přetažením v průběhu nebo který je ukazatelem myši v určitém režimu, jako je například režim kreslení.|Nepoužívejte krátká probíhající změny nebo pokud fluttering z kurzor může (například když svázané s částí delší běžící proces místo pro celý proces).|  
|[Indikátory průběhu](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_NotSysProgressIndicators)|Použijte v případě, že potřebujete sestavy průběhu (determinate nebo neurčitou). Existuje mnoho různých typů indikátor průběhu a konkrétní využití pro každou. V tématu [indikátory průběhu](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ProgressIndicators).||  
|[Visual Studio oznámení okna](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_VSNotificationsToolWindow)|Okno oznámení není veřejně extensible. Však se používá ke komunikaci řadu zprávy o sadě Visual Studio, včetně kritických problémů s licencí a informační upozornění na aktualizace pro Visual Studio nebo k balíčkům.|Nepoužívejte pro jiné typy oznámení.|  
|[Seznam chyb](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ErrorList)|Pokud tento problém má vztah přímo na uživatele s problém (chyby nebo upozornění nebo info) aktuálně otevřené řešení, se může být potřeba provést akci pro kód.<br /><br /> To zahrnuje, například:<br /><br /> -Kompilátoru zpráv (chyb nebo upozornění nebo info)<br /><br /> -Code analyzátor nebo diagnostiky zprávy o kód<br /><br /> -Sestavení zprávy<br /><br /> Může být vhodné pro problémy týkající se soubory projekt nebo řešení, ale nejprve zvažte indikace Průzkumníku řešení.|Nepoužívejte pro položky, které nemají žádné relace do řešení otevřeného kódu uživatele.|  
|Editor oznámení: žárovky|Použijte v případě, že máte k dispozici, chcete-li vyřešit problém, který existuje v otevření souboru opravu.<br /><br /> Všimněte si, že žárovky by měla být používána pro hostování rychlé akce, které se provádějí v kódu uživatele na vyžádání, jako je například refaktoring, ale v takovém případě se nebude zobrazovat "oznámení styl."|Nepoužívejte pro položky, které nemají žádnou relaci k otevření souboru.|  
|Editor oznámení: podtržení vlnovkou|Slouží k upozornění uživatele o problém s konkrétní rozpětí jejich otevřete kód (například červenou vlnovkou chyby).|Nepoužívejte pro položky, které nesouvisí se konkrétní rozpětí jejich otevřete kódu.|  
|[Vložené stavové řádky](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_EmbeddedStatusBars)|Pomocí lze zadat stav související s obsah nebo proces v kontextu okno konkrétní nástroje, okna dokumentu nebo dialogového okna.|Nepoužívejte pro obecnou oznámení, procesy nebo položky, které nemají žádnou relaci k obsahu v rámci konkrétní okno.|  
|[Oznámení panelu systému Windows](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_WindowsTray)|Pomocí surface oznámení pro procesy out-of-proc nebo doprovodné aplikace.|Nepoužívejte pro oznámení, které jsou relevantní pro rozhraní IDE.|  
|[Oznámení bublinách](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_NotificationBubbles)|Použít oznámit vzdáleného procesu nebo změňte **mimo** rozhraní IDE.|Nepoužívejte jako prostředek pro upozornění uživatele procesů **v rámci** rozhraní IDE.|  
  
### <a name="notification-methods"></a>Metody oznámení  
  
####  <a name="BKMK_ModalErrorMessageDialogs"></a>Zpráva Chyba modální dialogová okna  
 Dialogové okno modální chybová zpráva se používá k zobrazení chybovou zprávu, která vyžaduje potvrzení nebo akce uživatele.  
  
 ![Modální chybová zpráva](../../extensibility/ux-guidelines/media/0901-01_modalerrormessage.png "0901 01_ModalErrorMessage")  
  
 **Dialogové okno zprávy modální chyba výstrahy uživatele Neplatný připojovací řetězce k databázi**  
  
####  <a name="BKMK_IDEStatusBar"></a>IDE stavového řádku  
 Pravděpodobnost, že uživatelé, Všimněte si text stavového řádku koreluje s jejich počítače udělat prostředí a konkrétní zkušeností s platformou Windows. Základní sady Visual Studio zákazník obvykle být zkušeného v obou oblastech, i když i Pokročilí uživatelé Windows přijít o změny ve stavovém řádku. Proto stavový řádek je nejvhodnější pro informační účely nebo jako redundantní cue pro informace jsou uvedeny jinde. V dialogu nebo v okně nástroje oznámení třeba poskytnout jakýkoli druh důležitých informací, že uživatel se musí přeložit okamžitě.  
  
 Stavový řádek sady Visual Studio je navržena k umožnění pro několik typů informací, který se má zobrazit. Je rozdělený do oblasti pro zpětnou vazbu, Návrhář, indikátor průběhu, animace a klienta.  
  
 Oblast zpětnou vazbu a návrháře oblasti jsou vždy viditelné. Indikátor průběhu a animace oblasti jsou vždy dynamické a podle kontextu uživatele. Oblasti návrháře má statické šířka dáno délky řetězce, které pocházejí z prostředek doprovodné pro textové zprávy. To umožňuje lokalizace ke změně velikosti šířku bez nutnosti změny kódu. Pro angličtinu šířka tento řetězec je přibližně 220 pixelů. Oblasti návrháře budou chovat normálně a oblasti zpětnou vazbu malé zbývající místo.  
  
 Stavový řádek je také obarvené přidáte visual zájmu a funkční hodnota komunikaci různé změny stavu IDE třeba když prostředí IDE je v režimu ladění.  
  
 ![IDE stavovém řádku změny barev](../../extensibility/ux-guidelines/media/0901-02_idestatusbar.png "0901 02_IDEStatusBar")  
  
 **Barev na panelu Stav IDE**  
  
####  <a name="BKMK_EmbeddedInfobar"></a>Vložené informační panel  
 Informační panel můžete použít v horní části okna dokumentu nebo okno nástroje informovat uživatele o stavu nebo stavu. Příkazy může nabídnout také tak, aby uživatel může mít způsob, jak snadno provést akci. Informační panel je ovládací prvek standardní prostředí. Vyhněte se vytváření vlastní, který bude fungovat a zobrazí nekonzistentní s ostatními uživateli v prostředí IDE. V tématu [Infobars](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars) pro podrobné informace o nasazení a používání.  
  
 ![Vložené informační panel](../../extensibility/ux-guidelines/media/0901-03_embeddedinfobar.png "0901 03_EmbeddedInfobar")  
  
 **Informačního panelu vložených v okně dokumentu, zobrazení výstrah uživatele, který rozhraní IDE je v režimu historické ladění editor nebude odpovídat stejným způsobem jako ve standardním režimu ladění.**  
  
####  <a name="BKMK_MouseCursorChanges"></a>Změny kurzor myši  
 Při změně myší, pomocí barev, které jsou svázané s službu VSColor a jsou už přidružené kurzor. Kurzor změny lze použít pro probíhající operaci, jakož i dosáhl zóny, kde je uživatel ukazatele myši na cíl, který lze přetáhnout, umístění na nebo použít k výběru objektu.  
  
 Používejte myší zaneprázdněných/čekání jenom v případě, že všechny dostupné čas procesoru musí být vyhrazeno pro operace, brání vyjadřující žádný další vstup uživatele. Ve většině případů se dobře vytvořené aplikace pomocí více vláken musí být výjimečných časy, kdy by uživatelé nebudou moci provádění dalších operací.  
  
 Mějte na paměti, že změny kurzor jsou užitečné redundantní cue informace uvedenou jinde. Nespoléhejte na změnu kurzoru jako komunikaci s uživatelem, zejména v případě, že při pokusu o předání informací o tom něco jediný způsob, jakým je velmi důležité, že uživatel musí vyřešit.  
  
####  <a name="BKMK_NotSysProgressIndicators"></a>Indikátory průběhu  
 Indikátory průběhu jsou důležité pro poskytnutí zpětné vazby uživatele během procesů, které k dokončení více než pár sekund trvat. Indikátory průběhu lze zobrazit na místě (téměř spuštění bod akce v průběhu), na panelu embedded stav, v modální dialogové okno nebo ve stavovém řádku Visual Studio. Podle pokynů uvedených v [indikátory průběhu](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ProgressIndicators) o jejich používání a implementace.  
  
####  <a name="BKMK_VSNotificationsToolWindow"></a>Visual Studio oznámení okna  
 Okno Visual Studio oznámení upozorní vývojáře o licencování, prostředí (Visual Studio), rozšíření a aktualizace. Uživatele můžete zavřít jednotlivé oznámení nebo můžete ignorovat určitých typů oznámení. Seznam ignorovaných oznámení se spravuje přes **nástroje > Možnosti** stránky.  
  
 Okno oznámení není aktuálně extensible.  
  
 ![Visual Studio oznámení okno](../../extensibility/ux-guidelines/media/0901-06_vsnotificationswindow.png "0901 06_VSNotificationsWindow")  
  
 **Okno nástroje Visual Studio oznámení**  
  
####  <a name="BKMK_ErrorList"></a>Seznam chyb  
 Oznámení v seznamu chyb označení chyb a upozornění, které došlo k chybě během kompilace a nebo proces sestavení a umožňuje uživatelům procházet kód pro tuto chybu konkrétního kódu.  
  
 ![Seznam chyb](../../extensibility/ux-guidelines/media/0901-08_errorlist.png "0901 08_ErrorList")  
  
 **Seznam chyb v sadě Visual Studio**  
  
####  <a name="BKMK_EmbeddedStatusBars"></a>Vložené stavové řádky  
 Protože IDE stavový řádek je dynamická, s jeho kontext oblast klienta nastavena na okno aktivního dokumentu a informace o aktualizaci v kontextu uživatele a/nebo odpovědí systému, je obtížné spravovat průběžné zobrazení informací o nebo mu dávat stav na dlouhodobé asynchronní procesy. Například stavového řádku IDE není vhodná pro oznámení o výsledky testu pro více spustí nebo okamžitě řešitelné položku Možnosti. Je důležité zachovat takové informace o stavu v kontextu okna dokumentu nebo nástroj, kde uživatel provede výběr nebo spustí proces.  
  
 ![Vložené stavový řádek](../../extensibility/ux-guidelines/media/0901-09_embeddedstatusbar.png "0901 09_EmbeddedStatusBar")  
  
 **Vložené stavového řádku v sadě Visual Studio**  
  
####  <a name="BKMK_WindowsTray"></a>Oznámení panelu systému Windows  
 Na hlavním panelu Windows taktovací oznamovací oblasti je u systému Windows. Mnoho nástrojů a softwarové součásti poskytují ikony v této oblasti tak, aby uživatel můžete získat z kontextové nabídky pro systémové úlohy, jako je změna rozlišení obrazovky nebo získávání aktualizací softwaru.  
  
 Oznámení na úrovni prostředí by měl být prezentované v centru oznámení Visual Studio, není oznamovací oblasti systému Windows.  
  
####  <a name="BKMK_NotificationBubbles"></a>Oznámení bublinách  
 Oznámení bublinách se může zobrazit jako informační v rámci editor nebo Návrhář nebo jako součást oznamovací oblasti systému Windows. Uživatel zjistí tyto bublinách jako problémy, které můžete vyřešit později, což je výhody Nekritická oznámení. Bublinách nejsou vhodná pro důležité informace, které uživatel musí vyřešit hned. Pokud používáte bublinách oznámení v sadě Visual Studio, postupujte podle kroků [Windows Desktop pokyny pro oznámení bublinách](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742472\(v=vs.85\).aspx).  
  
 ![Oznámení bublin](../../extensibility/ux-guidelines/media/0901-07_notificationbubbles.png "0901 07_NotificationBubbles")  
  
 **Bublin oznámení v oznamovací oblasti systému Windows používá pro sadu Visual Studio**  
  
##  <a name="BKMK_ProgressIndicators"></a>Indikátory průběhu  
  
### <a name="overview"></a>Přehled  
 Indikátory průběhu jsou důležitou součástí oznámení systému pro poskytnutí zpětné vazby uživatele. Se informace pro uživatele, když se dokončí operace a procesy. Typy známé indikátor obsahují indikátory průběhu, roztočený kurzory a animovaný ikony. Typ a umístění indikátor průběhu, závisí na kontext, včetně obsah hlášení a jak dlouho proces nebo operace bude trvat dokončení.  
  
#### <a name="factors"></a>Faktory  
 Chcete-li určit, jaký typ ukazatele je vhodné, je nutné určit následující faktory.  
  
1.  **Načasování:** dobu operace bude trvat.  
  
2.  **Způsob:** jestli je operace modální prostředí (zámky rozhraní až do dokončení procesu)  
  
3.  **Trvalá nebo přechodná:** zda poslední výsledek průběh musí být hlášené nebo zobrazit později  
  
4.  **Determinate/Neurčitost:** určení, zda můžete vypočítat čas ukončení operace a průběh  
  
5.  **Umístění obrázku nebo Textual:** jestli průběh nebo procesu je zaznamenané vložené v těle zprávy nebo konkrétní ovládací prvek, jako je například ovládací prvek stromu  
  
6.  **Bezkontaktní komunikace:** jestli průběh by měla být v těsné blízkosti uživatelského rozhraní, která souvisí s. (Například může být ve stavovém řádku, což může být daleko, nebo nemusí být téměř tlačítko Spustit proces?)  
  
#### <a name="determinate-progress"></a>Determinate průběh  
  
|Typ průběh|Kdy a jak používat|Poznámky|  
|-------------------|-------------------------|-----------|  
|Indikátor průběhu (determinate)|Očekávané trvání > 5 sekund.<br /><br /> Může zahrnovat textový popis podrobnosti o procesu.|**Nemáte** vložení textu do animace.|  
|Informační panel|Zasílání zpráv přidružené kontextové uživatelského rozhraní. V tématu [Infobars](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars).<br /><br /> Může zahrnovat textový popis podrobnosti o procesu.|**Nemáte** použít více infobars při musíte určit více procesů. Místo toho použijte indikátory průběhu skládaný.|  
|Okno Výstup|Přechodný oznámení: proces úrovni aplikace chcete tohoto uživatele **zkontrolujte** podrobnosti po dokončení.|**Nemáte** použijte, pokud uživatel bude muset odkazovat na data později.|  
|Soubor protokolu|Spárovaný s intransient oznámení v případech, když je důležité **Uložit** podrobnosti po dokončení.||  
|Stavový řádek|Přechodný oznámení: proces úrovni aplikace bude tento uživatel **není nutné** podrobnosti po dokončení.<br /><br /> Zahrnuje embedded indikátor průběhu.<br /><br /> Může zahrnovat textový popis podrobnosti o procesu.||  
  
#### <a name="indeterminate-progress"></a>Neurčitém průběh  
  
|Typ průběh|Kdy a jak používat|Poznámky|  
|-------------------|-------------------------|-----------|  
|Indikátor průběhu (neurčitém)|Očekávané trvání > 5 sekund.<br /><br /> Může zahrnovat textový popis podrobnosti o procesu.|**Nemáte** vložení textu do animace.|  
|Rámeček (animovaný vodorovné tečky)|Odezvy na server.<br /><br /> V horní části nadřazený kontejner umístěn near bodu kontextu.|**Nemáte** použijte, pokud není nadřazena celého kontejneru.|  
|Číselník (průběh okruh)|Proces související s kontextové uživatelského rozhraní nebo je-li prostor zabývat.<br /><br /> Může zahrnovat textový popis podrobnosti o procesu.||  
|Informační panel|Zasílání zpráv přidružené kontextové uživatelského rozhraní. V tématu [Infobars](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars).|**Nemáte** použít více infobars při musíte určit více procesů. Místo toho použijte indikátory průběhu skládaný.|  
|Okno Výstup|Přechodný oznámení: proces úrovni aplikace tento uživatel bude chcete **zkontrolujte** podrobnosti po dokončení.|**Nemáte** používat pro informace, které je potřeba zachová napříč relacemi.|  
|Soubor protokolu|Spárovaný s intransient oznámení v případech, když je důležité **Uložit** podrobnosti po dokončení.||  
|Stavový řádek|Přechodný oznámení: proces úrovni aplikace bude tento uživatel **není nutné** podrobnosti po dokončení.<br /><br /> Zahrnuje embedded indikátor průběhu.<br /><br /> Může zahrnovat textový popis podrobnosti o procesu.||  
  
### <a name="progress-indicator-types"></a>Typy indikátor průběhu  
  
#### <a name="progress-bars"></a>Indikátory průběhu  
  
##### <a name="indeterminate"></a>Neurčitém  
 ![Indikátor průběhu neurčitém](../../extensibility/ux-guidelines/media/0901-04_indeterminate.png "0901 04_Indeterminate")  
  
 **Indikátor průběhu neurčitém**  
  
 "Neurčitém" znamená zjistit celkový průběh operace nebo procesu nelze určit. Použít indikátory neurčitém průběhu pro operace vyžadující bez vazby množství času nebo který přístup neznámé počet objektů. Používejte textový popis doprovázet, co se děje. Pomocí časových limitů předáte hranice založené na čase operace. Indikátory průběhu neurčitém znázornit animace průběhu se provádí, že žádné další informace. Nevolte zobrazí panel neurčitém průběh pouze podle případné nedostatky přesnost samostatně.  
  
##### <a name="determinate"></a>Determinate  
 ![Indikátor průběhu determinate](../../extensibility/ux-guidelines/media/0901-05_determinate.png "0901 05_Determinate")  
  
 **Indikátor průběhu determinate**  
  
 "Determinate" znamená, že operaci nebo proces vyžaduje ohraničené množství času, i v případě, že množství času, nelze přesně předpovědět. Jasně označují dokončení. Nenechte indikátor průběhu, přejděte do 100 procent, pokud bude dokončena operace. Animace panelu determinate průběhu přesune zleva doprava od 0 do 100 %.  
  
 Indikátor průběhu zpětné během operace se nikdy nepřesouvají. Na panelu měli přechod vytrvale při zahájení operace a dosáhnout 100 % při jeho ukončení. Je uživatel získat představu o tom, jak dlouho trvá celou operaci, bez ohledu na to, kolik kroků se podílejí bodem indikátor průběhu.  
  
##### <a name="concurrent-reporting-stacked-progress-bars"></a>Souběžných reporting (indikátory skládaný průběhu)  
 Pokud operace bude trvat dlouhou dobu - možná může používat několik minut - pak indikátory průběhu dvou, jednu, zobrazí celkový průběh operace a druhý pro průběh aktuálního kroku. Například pokud instalační program je kopírujete mnoho souborů, pak jeden indikátor průběhu slouží k označení, jak dlouho trvá celý proces, zatímco druhý můžete určit, jaké procento aktuální soubor nebo adresář je kopírování. Neoznamovat více než pěti souběžných operací nebo procesů pomocí indikátory průběhu skládaný. Pokud máte více než pěti souběžných operací nebo procesy do sestavy, použijte modální dialogové okno s tlačítko Zrušit a sestava podrobnosti o průběhu do okna výstupu.  
  
##### <a name="textual-descriptions"></a>Textový popis  
 Používejte textový popis, který může doprovázet, co se děje a odhadovaný čas dokončení. Pokud je možné určit, jak dlouho bude trvat operace, může být vhodnější pro poskytnutí zpětné vazby, animovaný ikonu místo indikátor průběhu.  
  
 Visual Studio poskytuje standardní indikátor ve stavovém řádku, které je možné některý z produktů integrované do sady Visual Studio. Textový popis co se děje, když je animovaný indikátor průběhu mohou být aktualizovány text stavového řádku.  
  
#### <a name="other-progress-indicators"></a>Další indikátory průběhu  
  
##### <a name="ants-animated-horizontal-dots"></a>Rámeček (animovaný vodorovné tečky)  
 ![Průběhu rámeček](../../extensibility/ux-guidelines/media/0903-01_ants.png "0903 01_Ants")  
  
 "Rámeček," animovaný vodorovné tečky, poskytují vizuální informace pro proces neurčitém odezvy serveru.  
  
##### <a name="spinner-progress-ring"></a>Číselník (průběh okruh)  
 ![Průběh číselník](../../extensibility/ux-guidelines/media/0903-02_spinner.png "0903 02_Spinner")  
  
 Číselník (označované také jako "průběh kruh") je indikátor průběhu neurčitém se používají primárně ve vztahu k kontextové uživatelského rozhraní. Zobrazí číselník v těsné blízkosti jeho související obsah, jako je záhlaví textovou kategorie, zasílání zpráv nebo ovládací prvek.  
  
##### <a name="cursor-feedback"></a>Zpětná vazba kurzoru  
 Pro operace, které trvat 2-7 sekund poskytnout zpětnou vazbu kurzoru. Obvykle to znamená použití čekání kurzor poskytované operačním systémem. Pokyny najdete v tématu článku na webu MSDN [Cursors.Wait vlastnost](https://msdn.microsoft.com/en-us/library/system.windows.input.cursors.wait\(v=vs.110\).aspx).  
  
#### <a name="progress-indicator-locations"></a>Umístění indikátoru průběhu  
  
##### <a name="status-bar"></a>Stavový řádek  
 Stavový řádek poskytuje místo, kde můžete zobrazit zprávy a užitečné informace pro uživatele bez přerušení uživatele pracovní aplikace. Obvykle se zobrazí v dolní části okna, bude stav pro průběh podokno tip nástroje, které obsahuje zprávu o míru průběh v kombinaci s panelu indikátor průběhu.  
  
 ![Stavový řádek s indikátor průběhu](../../extensibility/ux-guidelines/media/0903-03_statusbarprogressbar.png "0903 03_StatusBarProgressBar")  
  
 **Stavový řádek s indikátor průběhu**  
  
 ![Stavový řádek s zasílání zpráv](../../extensibility/ux-guidelines/media/0903-04_statusbarmessage.png "0903 04_StatusBarMessage")  
  
 **Stavový řádek s textový popis**  
  
##### <a name="infobar"></a>Informační panel  
 Podobá se na stavovém řádku, informační panel poskytuje kontextové oznámení a zasílání zpráv, které může být také spárována s indikátory průběhu neurčitém například indikátor průběhu nebo číselník. Informační panel nesmí poskytují podrobné úrovni průběh nebo označení determinate průběh. V tématu [Infobars](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars).  
  
 ![Informační panel s indikátor průběhu a zasílání zpráv](../../extensibility/ux-guidelines/media/0903-05_infobar.png "0903 05_InfoBar")  
  
 **Informační panel s indikátor průběhu a textový popis**  
  
 ![Informační panel uvnitř okna](../../extensibility/ux-guidelines/media/0903-06_infobarinwindow.png "0903 06_InfoBarInWindow")  
  
 **Informační panel uvnitř okna Analýza kódu**  
  
##### <a name="inline"></a>Vložené  
 Vložené průběh indikace může být reprezentovaný jakýkoli z typů zavaděč průběh. Obvykle je indikátor průběhu spárován s zasílání zpráv, ale to není povinné.  
  
 ![Vložené průběh číselník](../../extensibility/ux-guidelines/media/0903-07_inlinespinner.png "0903 07_InlineSpinner")  
  
 **V kombinaci s textový popis číselník**  
  
 ![Vložené skládaný indikátory průběhu](../../extensibility/ux-guidelines/media/0903-08_inlinestackedprogress.png "0903 08_InlineStackedProgress")  
  
 **Indikátory průběhu determinate skládaný**  
  
 ![Zasílání zpráv průběhu vložené](../../extensibility/ux-guidelines/media/0903-09_inlinetext.png "0903 09_InlineText")  
  
 **Vložený text Průzkumníka serveru: aktualizace...**  
  
##### <a name="tool-windows"></a>Nástroje systému windows  
 Globální průběh indikace je reprezentována neurčitém indikátor průběhu, který je umístěný přímo pod panelu nástrojů.  
  
 ![Indikátor průběhu globální neurčitém](../../extensibility/ux-guidelines/media/0903-23_globalindeterminate.png "0903 23_GlobalIndeterminate")  
  
 **Indikátor globální neurčitém průběhu Team Explorer**  
  
##### <a name="dialogs"></a>Dialogová okna  
 Dialogová okna může obsahovat jakýkoli z typů zavaděč průběh. Indikátory průběhu může být spárována s zasílání zpráv, stejně jako v kombinaci s více úrovní průběh indikace představují granulární a dílčí procesy.  
  
 ![Dialogové okno s více typy indikátor průběhu](../../extensibility/ux-guidelines/media/0903-11_dialog.png "0903 11_Dialog")  
  
 **Visual Studio dialogové okno s souběžných procesů a víc typů indikátor průběhu**  
  
 ![Dialogové okno s zavaděč průběh a zasílání zpráv](../../extensibility/ux-guidelines/media/0903-12_dialog2.png "0903 12_Dialog2")  
  
 **Visual Studio dialogové okno s zavaděč průběh a zasílání zpráv vložené tvorba příkazů**  
  
##### <a name="document-well"></a>Dobře dokumentu  
 Dokument dobře můžete zobrazit více typů zavaděč průběh v kombinaci s ovládacími prvky.  
  
 ![Průběh zasílání zpráv v dokumentu dobře](../../extensibility/ux-guidelines/media/0903-13_documentwell.png "0903 13_DocumentWell")  
  
 **Indikátor průběhu neurčitém pod nástrojů**  
  
##### <a name="output-window"></a>Okno Výstup  
 Ve výstupním okně jsou vhodné pro zpracování procesu průběh a stav probíhající prostřednictvím vloženého textové zprávy. Měli byste použít stavový řádek společně s žádné výstup – okno průběhu reporting.  
  
 ![Průběh zasílání zpráv v okně výstupu](../../extensibility/ux-guidelines/media/0903-14_outputwindow.png "0903 14_OutputWindow")  
  
 **Výstup – okno stavem probíhající proces a počkejte, než zasílání zpráv**  
  
##  <a name="BKMK_Infobars"></a>Infobars  
  
### <a name="overview"></a>Přehled  
 Infobars uživateli přidělit, slouží jako ukazatel blízko jejich bodu pozornost a pomocí ovládacího prvku sdílené informační panel zajišťuje konzistenci vzhled a interakce.  
  
 ![Informační panel](../../extensibility/ux-guidelines/media/0904-01_infobar.png "0904 01_Infobar")  
  
 **Infobars v sadě Visual Studio**  
  
#### <a name="appropriate-uses-for-an-infobar"></a>Vhodné pro použití pro informační panel  
  
-   Chcete-li uživateli přidělit neblokující ale důležité zprávy relevantní pro aktuální kontext  
  
-   K označení, že uživatelské rozhraní je ve stavu nebo podmínku, která představuje některé interakce důsledky, jako je například historické ladění  
  
-   Upozorní uživatele, že systém zjistil problémy, například když je rozšíření způsobují problémy s výkonem  
  
-   Poskytuje způsob, jak snadno provedení akce, třeba když editoru zjistí, že soubor se smíšenými karty a prostory uživateli  
  
##### <a name="do"></a>Proveďte:  
  
-   Text zprávy informační panel zachovat prostě a do bodu.  
  
-   Zachovat text na odkazy a tlačítka, stručného.  
  
-   Zkontrolujte, zda jsou možnosti "action", které poskytnete uživatelům minimální, zobrazuje pouze požadované akce.  
  
##### <a name="dont"></a>Ne:  
  
-   Pomocí informačního panelu nabízet standardní příkazy, které má být umístěn v panelu nástrojů.  
  
-   Pomocí informačního panelu místo modální dialogové okno.  
  
-   Vytvořte plovoucí zprávu mimo okno.  
  
-   Pomocí několika infobars v několika umístění v rámci stejného časového období.  
  
#### <a name="can-multiple-infobars-show-at-the-same-time"></a>Můžete zobrazit více infobars současně?  
 Ano, můžete zobrazit více infobars ve stejnou dobu. Zobrazí se v první přijde, dřív pořadí s první informační panel zobrazuje v horní a další infobars zobrazující níže.  
  
 Uživatel uvidí maximálně tři infobars současně, po který, pokud další infobars jsou k dispozici, oblasti informační panel se stanou posouvatelného.  
  
### <a name="creating-an-infobar"></a>Vytvoření informačního panelu  
 Informační panel má čtyři části zprava doleva:  
  
-   **Ikona:** Toto je, kde by přidat libovolnou ikonu byste chtěli zobrazí informační panel, jako je například ikona upozornění.  
  
-   **Text:** můžete přidat text, který se popisují scénáře/situace uživatel je v, spolu s odkazy v rámci textu, v případě potřeby. Mějte na paměti, aby stručného text.  
  
-   **Akce:** v této části by měl obsahovat odkazy a tlačítka pro akce, které může uživatel provádět vaší informačním.  
  
-   **Tlačítko Zavřít:** poslední část vpravo může mít tlačítko Zavřít.  
  
#### <a name="creating-a-standard-infobar-in-managed-code"></a>Vytváření standardní informačním panelu ve spravovaném kódu  
 Třída InfoBarModel slouží k vytvoření zdroje dat pro informační panel. Použijte jednu z těchto čtyř konstruktory:  
  
```  
public InfoBarModel(IEnumerable<IVsInfoBarTextSpan> textSpans, ImageMoniker image = default(ImageMoniker), bool isCloseButtonVisible = true);  
  
```  
  
```  
public InfoBarModel(string text, ImageMoniker image = default(ImageMoniker), bool isCloseButtonVisible = true);  
  
```  
  
```  
public InfoBarModel(IEnumerable<IVsInfoBarTextSpan> textSpans, IEnumerable<IVsInfoBarActionItem> actionItems, ImageMoniker image = default(ImageMoniker), bool isCloseButtonVisible = true);  
  
```  
  
```  
public InfoBarModel(string text, IEnumerable<IVsInfoBarActionItem> actionItems, ImageMoniker image = default(ImageMoniker), bool isCloseButtonVisible = true);  
```  
  
 Tady je příklad, který vytvoří InfoBarModel s textem s hypertextový odkaz, tlačítko akce a ikonu.  
  
 ![Informační panel s hypertextovým odkazem](../../extensibility/ux-guidelines/media/0904-02_infobarhyperlink.png "0904 02_InfobarHyperlink")  
  
```  
var infoBar = new InfoBarModel(  
    textSpans: new[]  
    {  
        new InfoBarTextSpan("This is a "),  
        new InfoBarHyperlink("hyperlink"),  
        new InfoBarTextSpan(" InfoBar.")  
    },  
    actionItems: new[]  
    {  
        new InfoBarButton("Click Me")  
    },  
    image: KnownMonikers.StatusInformation,  
    isCloseButtonVisible: true);  
  
```  
  
#### <a name="creating-a-standard-infobar-in-native-code"></a>Vytvoření standardní informačním panelu v nativním kódu  
 Chcete-li poskytovat informačního panelu z nativního kódu implementovat IVsInfoBar rozhraní.  
  
```  
public interface IVsInfoBar  
{  
    IVsInfoBarActionItemCollection ActionItems { get; }  
    ImageMoniker Image { get; }  
    bool IsCloseButtonVisible { get; }  
    IVsInfoBarTextSpanCollection TextSpans { get; }  
}  
  
```  
  
#### <a name="getting-an-infobar-uielement-from-an-infobar"></a>Získávání z informačního panelu informačního panelu prvků uživatelského rozhraní  
 Implementace InfoBarModel nebo IVsInfoBar jsou datové modely, které musí převedena na prvků uživatelského rozhraní, aby bylo možné zobrazit v uživatelském rozhraní. Se službou SVsInfoBarUIFactory/IVsInfoBarUIFactory je možné načíst prvků uživatelského rozhraní.  
  
```  
private bool TryCreateInfoBarUI(IVsInfoBar infoBar, out IVsInfoBarUIElement uiElement)  
{  
    IVsInfoBarUIFactory infoBarUIFactory = serviceProvider.GetService(typeof(SVsInfoBarUIFactory)) as IVsInfoBarUIFactory;  
    if (infoBarUIFactory == null)  
    {  
        uiElement = null;  
        return false;  
    }  
  
    uiElement = infoBarUIFactory.CreateInfoBar(infoBar);  
    return uiElement != null;  
}  
```  
  
### <a name="placement"></a>Umístění  
 Infobars lze zobrazit v jedné nebo více z následujících umístění:  
  
-   Nástroje systému windows  
  
-   V rámci na kartě dokumentu  
  
> [!IMPORTANT]
>  Je možné umístit informačního panelu umožnit zprávu o globálním kontextu. Se potom zobrazí mezi panely nástrojů a dobře dokumentu. Toto se nedoporučuje, protože způsobuje problémy s "jump a jerk" rozhraní IDE a je nutno Pokud absolutně nezbytné a vhodné.  
  
#### <a name="placing-an-infobar-in-a-toolwindowpane"></a>Uvedení informačního panelu ToolWindowPane  
 Metoda ToolWindowPane.AddInfoBar(IVsInfoBar) slouží k přidání informačního panelu pro okno nástroje. Toto rozhraní API můžete přidat buď IVsInfoBar (které InfoBarModel je výchozí implementace), nebo IVsUIElement.  
  
#### <a name="placing-an-infobar-in-a-document-or-non-toolwindowpane"></a>Umístění informačního panelu do dokumentu nebo jiných ToolWindowPane  
 Umístit do jakékoli IVsWindowFrame informační panel, použijte vlastnost VSFPROPID_InfoBarHost získat IVsInfoBarHost pro rámečku a poté přidejte informační panel prvků uživatelského rozhraní.  
  
```  
private void AddInfoBar(IVsWindowFrame frame, IVsUIElement uiElement)  
{  
    IVsInfoBarHost infoBarHost;  
    if (TryGetInfoBarHost(frame, out infoBarHost))  
    {  
        infoBarHost.AddInfoBar(uiElement);  
    }  
}  
private bool TryGetInfoBarHost(IVsWindowFrame frame, out IVsInfoBarHost infoBarHost)  
{  
    object infoBarHostObj;  
    if (ErrorHandler.Failed(frame.GetProperty((int)__VSFPROPID7.VSFPROPID_InfoBarHost, out infoBarHostObj)))  
    {  
        infoBarHost = null;  
        return false;  
    }  
  
    infoBarHost = infoBarHostObj as IVsInfoBarHost;  
    return infoBarHost != null;  
}  
  
```  
  
#### <a name="placing-an-infobar-in-the-main-window"></a>Umístění informačního panelu v hlavním okně  
 Umístit informačního panelu v hlavním okně, používat VSSPROPID_MainWindowInfoBarHost IVsShell služby k získání IVsInfoBarHost hlavní okno a potom k němu přidejte informační panel prvků uživatelského rozhraní.  
  
### <a name="will-i-know-when-the-user-takes-action-in-my-infobar"></a>Poznám, že když uživatel provede akci Moje informačním?  
 Ano, bude vrátíme každou akci událostí autorovi informační panel. Je pak autora informační panel, který v integrovaném vývojovém prostředí na základě výběru v informačním panelu provést akci. Infobars bude automaticky odebrána z hostitele, jehož tlačítko Zavřít označeného, ale další pracovní je povinný, pokud jiné infobars potřeba odebrat po zavřete. Telemetrie bude muset být nezávisle zaznamenaných každý informační panel.  
  
#### <a name="receiving-infobar-events-in-a-toolwindowpane"></a>Příjem událostí informačním panelu v ToolWindowPane  
 ToolWindowPane má dvě události pro infobars. InfoBarClosed událost se vyvolá, když informačního panelu v ToolWindowPane je uzavřený. InfoBarActionItemClicked událost se vyvolá, když po kliknutí na hypertextový odkaz nebo tlačítko uvnitř informační panel.  
  
#### <a name="receiving-infobar-events-directly-from-the-uielement"></a>Přijímání událostí informační panel přímo z prvků uživatelského rozhraní  
 IVsInfoBarUIElement.Advise lze použít k odběru události přímo z prvků uživatelského rozhraní informační panel. Implementace IVsInfoBarUIEvents vám umožní Autor zavřete přijmout a klikněte na události.  
  
```  
public interface IVsInfoBarUIEvents  
{  
    void OnActionItemClicked(IVsInfoBarUIElement infoBarUIElement, IVsInfoBarActionItem actionItem);  
    void OnClosed(IVsInfoBarUIElement infoBarUIElement);  
}  
  
```  
  
##  <a name="BKMK_ErrorValidation"></a>Chyba ověření  
 Když uživatel zadá informace, které není přijatelné, například když je povinné pole vynecháno nebo má nesprávný formát zadávání dat, je lepší ověření použijte ovládací prvek nebo připomínky téměř místo použití blokování dialogové okno chyby místní ovládacího prvku.  
  
### <a name="field-validation"></a>Ověření pole  
 Ověření formuláře a pole se skládá ze tří součástí: ovládací prvek, ikonu a popis tlačítka. Během několik typů ovládacích prvků můžete použít, použije se jako příklad textového pole.  
  
 ![Ověření pole &#40; prázdné &#41; ] (../../extensibility/ux-guidelines/media/0905-01_fieldvalidation.png "0905 01_FieldValidation")  
  
 Pokud pole je požadováno, měla by existovat vodoznaku s informacemi o tom text  **\<požadované >** a na pozadí pole by měl být light žlutý (VSColor: `Environment.ControlEditRequiredBackground`) a popředí by měl být šedá (VSColor: `Environment.ControlEditRequiredHintText`):  
  
 ![Pole s popiskem "Požadované" ověření](../../extensibility/ux-guidelines/media/0905-02_fieldvalidationrequired.png "0905 02_FieldValidationRequired")  
  
 Program můžete určit, že ovládací prvek, je stav *neplatný obsah zadali* při je přesunout fokus na jiný ovládací prvek nebo když uživatel klikne na tlačítko potvrzení [OK] nebo když uživatel uloží dokument nebo formuláře.  
  
 Pokud je určen neplatný stav obsahu, zobrazí ikona buď uvnitř ovládacího prvku, nebo u ní. Popisek popisující chybu by se zobrazit při přechodu myší na ikonu nebo ovládací prvek. Kromě toho ohraničení 1 pixel ohraničeny rámečkem ovládací prvek, který vytváří v neplatném stavu.  
  
 ![Pole Specifikace rozložení ověření](../../extensibility/ux-guidelines/media/0905-03_layoutspecs.png "0905 03_LayoutSpecs")  
  
 **Specifikace rozložení pro ověření pole**  
  
#### <a name="acceptable-variations-for-icon-location"></a>Přijatelné variace umístění ikony  
 Existují obrovském množství jedinečný případy, ve kterých se uživatelé muset být informováni o chyby ověření. Vzhledem k tomu – typ ovládacího prvku a konfigurace rozhraní zvolte ikonu umístění situace.  
  
 ![Přijatelné umístění pro umístění ikony](../../extensibility/ux-guidelines/media/0905-04_iconlocation.png "0905 04_IconLocation")  
  
 **Přijatelné variace pole ověření ikonu umístění**  
  
#### <a name="validation-requiring-a-round-trip-to-a-server-or-network-connection"></a>Ověření nutnosti dobu odezvy na server nebo síťové připojení  
 V některých případech dobu odezvy na server se vyžaduje k ověření obsahu a je důležité pro zobrazení průběhu uživatele, ověření a chybové stavy. Následující obrázek ukazuje příklad tento případ a doporučené uživatelské rozhraní.  
  
 ![Ověření zahrnující dobu odezvy na server](../../extensibility/ux-guidelines/media/0905-05_roundtrip.png "0905 05_RoundTrip")  
  
 **Ověření zahrnující dobu odezvy na server**  
  
 Všimněte si, že je třeba zadat dostatečné volné místo napravo od ovládacího prvku mohla pojmout text "Ověření..." a "Opakování".  
  
#### <a name="in-place-warning-text"></a>Text upozornění na místě  
 Když je místo, které jsou k dispozici pro umístění chybová zpráva blízko ovládacího prvku ve stavu chyby, je to vhodnější než pomocí popisek samostatně.  
  
 ![V & č. 45; místní upozornění](../../extensibility/ux-guidelines/media/0905-06_inplacewarning.png "0905 06_InPlaceWarning")  
  
 **Text upozornění na místě**  
  
#### <a name="watermarks"></a>Vodoznaky  
 Celý ovládací prvek nebo okno, v některých případech je v chybovém stavu. V této situaci používá se k označení chyba vodoznak.  
  
 ![Vodoznak](../../extensibility/ux-guidelines/media/0905-07_watermark.png "0905 07_Watermark")  
  
 **Ověření pole vodoznak**