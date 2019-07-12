---
title: Animace pro sadu Visual Studio | Dokumentace Microsoftu
ms.date: 04/26/2017
ms.topic: conceptual
ms.assetid: 446773a9-e6f7-4c0c-8dbc-9e303bf32eb1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3f113bf8d9a77e8569126a6f0c7d96f1fe4f0eea
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67825244"
---
# <a name="animations-for-visual-studio"></a>Animace pro sadu Visual Studio
## <a name="animation-fundamentals"></a>Základy animace

### <a name="animation-best-practices-in-visual-studio"></a>Osvědčené postupy animace v sadě Visual Studio
Postupujte podle těchto pravidel zajistit konzistentní a uživatelsky přívětivé animace, styly v integrovaném vývojovém prostředí sady Visual Studio.

- **Pečlivě.** Omezit animací na ty, které mají konkrétní účely.

- **Načasování a rychlost jsou důležité** zajistit, že přechody pocit, že rychlé a přirozené:

  - Dokončení animovaný přechodů v rámci jedné půl sekundy (500 milisekund).

  - Animace, které by tomu bylo, často je potřeba dostatečně rychle, že jejich není přerušení pracovního postupu uživatele. Podívejte se na animace ve smyčce a upravit načasování, dokud je správný.

  - Animace by neměl být tak rychlé nebo jarring, že je obtížné porozumět, ale ne tak pomalé, že je jeden netrpělivý pro přechod na Dokončit.

  - Pomocí proměnné časování zdůraznění důležitosti. Během procházení posloupnost položek v diagramu tříd, rychlost prostřednictvím přechody mezi položkami pak zpomalit soustředit na důležité položky.

- **Použití postupné nelineárních usnadnění** z jednoho stavu do druhého, dává smysl klidné a přirozené pohybu.

- Pokud je to možné, **použijte drobným animaci při najetí myší** udávajících interaktivní prvky pod myší.

- Pokud se spoléháte silně na animace ve funkcích, pak **prostředkem, chcete-li vypnout** místně (pro všechny funkce) jako možnost v **nástroje > Možnosti** dialogového okna.

- **Pouze jedné animace se budou objevovat v čase** a sdělit pouze jednu část informací. Více než jeden objekt přesunutí nebo pokus o předání několika věcech může být matoucí.

- **Subtlety je důležité.** Ve většině případů animace nemusí pozornost uživatele vyžádání její účel. Malých změn časování, pořadí a chování může významně ovlivnit vnímání a může být rozdíl mezi animace efektivní a neefektivní.

- Při použití animace k přitažení pozornosti ke něco, **Ujistěte se, že je vhodné by to ovlivnilo uživatele**společnosti myšlenek.

- **Při zobrazení stav nebo průběh** prostřednictvím animace:

  - Zastavte zobrazující průběh přesunu, pokud není posunutí základního procesu.

  - Neurčitá procesy odlišili od determinate procesy.

  - Zajistěte, aby animace identifikovatelné stavy ukončení a selhání.

  - Minimalizujte použití animací efekt, které zobrazují stav a ujistěte se, jestli obsahují skutečné hodnoty tím, že poskytuje další informace o skutečném použití. Mezi příklady patří přechodný stav se změní a nouzové situace co

#### <a name="animation-donts"></a>Animace proti:

- Nepoužívejte malé pohybů plb typu (pohyb v malé náklady). Preferovat pomalu a změny v průběhu přesouvání objektů.

- Nepoužívejte animace, které probíhat přes velké části plochy obrazovky. Bez ohledu na velikost je tento styl animace rušivé uživateli.

- Nepoužívejte animace nesouvisející objekt, který uživatel právě fokus na nebo interakci s.

- Nepoužívejte animace, které vyžaduje interakci uživatele resetovat stav, jako je vynucení uživatele blikající oznámení, aby bylo možné ho zastavit blikat reagovat. Interakce s nimi žádným způsobem by měla stačit zrušit je.

Další informace o aplikacích pro tyto osvědčené postupy najdete v tématu [animace vzory](../../extensibility/ux-guidelines/animations-for-visual-studio.md#BKMK_AnimationPatterns).

### <a name="animation-metrics"></a>Animace metriky

- Systém by měl viditelně reakce na ně uživatel gesta v méně než 10 milisekund.

- Animované přechody by neměl trvat déle než 500 milisekund do dokončení.

- Jedním ze způsobů, aby se vykompenzovalo přechody, které vyžadují delší dobu je rozdělit do dvou částí. První část animace například může být prázdný obsah kontejner (až 500 milisekund), za nímž následuje obsahu vyblednutí do kontejneru (až 500 milisekund).

- Pro dobu načítání, které je možné vypočítat indikátor průběhu určujícím (v procentech průběhu) je upřednostňována.

- Pro dobu načítání, které nelze vypočítat je vhodné indikátor zaneprázdnění jako kurzoru nebo vložený pokryjte animace (pracovní ukazatele nebo načítání).

### <a name="animation-as-communicator"></a>Animace jako communicator
V uživatelském rozhraní aplikace Visual Studio animace funguje pouze jako nástroj pro komunikaci.  Používá se pro komunikaci širokou škálu informace, jako jsou změny struktury v uživatelském rozhraní (například když se otevře nabídka nebo ukončí). Animace pomáhají vizualizovat chování závislé na čase komplexních systémů, jako je vizualizace průběhu instalace. Animace lze také přitahují pozornost výstrahy a oznámení.

 Animace v uživatelském rozhraní funkce obvykle čtyři způsoby: vizualizace, které upoutat pozornost, simulace, a časy odezvy/průběh indikátory.

#### <a name="visualize"></a>Vizualizace
Animace lze zvýraznění trojrozměrného povaze objektů a usnadňují uživatelům vizualizovat svá prostorová struktury. Za tím účelem animace může potřebovat aktivovat objekt v úplné kruh, pomalu zapnout vpřed a zpět, nebo Přenést blíž objekt a mírně se zvýší velikost zdůraznit výměny nebo fokus.

I když trojrozměrné objekty mohou být přesunuty s uživatelský ovládací prvek, Návrhář ujasnit některé věci předem (prostřednictvím kódu programu nebo ručně) jak pro nejlepší animace pohybu, která poskytuje optimální Principy objektu. To naprogramovat animace může pak být uživatel aktivoval tím, že kurzor umístíte na objekt, zatímco řízené uživatelem pohybů plb typu vyžadovat, aby pochopit, jak pracovat s objektu. Omezit pohyb jednu osu nebo orientace najednou. buď škálování, otočit, nebo přeložit, ale neprovádějte více než jeden současně.

Vizualizace kategorie zahrnuje aspekty dat, relace, stavu, struktura, pořadí a čas.

##### <a name="data"></a>Data
Ukazuje proměnné a komplexní informace:

- Procházení vizualizace informace, jako jsou tabulky a grafy

- Krokování sekvenci, průvodce a stránkování

- Volání podrobnosti, odkazující a zvýraznění konkrétních informací

- Překryvné podrobnosti a další informace o element s fokusem

- Morfingu prvku z jednoho znázornění strukturální nebo organizace do jiného

- Představující změny v čase pomocí jezdců, rozsvítit shuttle kola a ovládací prvky pro přenos (přehrávání, zastavení a pozastavit)

##### <a name="relationships"></a>Relace

- Ukazuje, jak k sobě vztahují položky nebo položky, které se vztahují na danou položku

- Zobrazení hierarchie a nadřazenosti a podřízenosti nebo na stejné úrovni vztahů

- Jiné vytvoří jeden element.

- Jeden element minimalizuje na jiný element

- Jeden element připojeném do jiného

##### <a name="state"></a>Stav

- Aktualizace obsahu

- Výběr a fokus uživatele

- Průběh

- Chyby

##### <a name="structure"></a>Struktura

- Přesun konstrukce na jeden uzel

- Převedení

- Minimalizovat a maximalizovat, nebo rozbalit nebo sbalit

##### <a name="sequence"></a>Pořadí

- Prezentace pořadí

- Překlopení prostřednictvím obrázky

##### <a name="time"></a>čas

- Zobrazení změn v průběhu času, časová prodleva a záznam dění na monitoru

- Přesunout do koše, vrátit zpět a znovu:

- Obnovit Historický stav

#### <a name="attract-attention"></a>Upoutat pozornost
Pokud je cílem upozornit uživatele na jeden element z několika nebo o upozornění uživatele, aby aktualizované informace, může být vhodné animace. Úvodní stránky aplikace může například použít tlačítko Začínáme, který se posune na místě po načtení stránky.

Poslední přesunutí prvek na obrazovce jako pravidlo, upoutat pozornost uživatele.  V řadě animované elementy postupujte podle uživatele pozornost poslední přesunutí objektu.

##### <a name="alert"></a>Výstrahy

- Upozornit uživatele, získejte pozornost, zobrazit průběh

- Zobrazit, že něco se provádí správně nebo nesprávně nebo zobrazit průběh nebo probíhající změny

- Dotázat se uživatele během úlohy, jako je hledání další informace online nebo získávání informací o aktuální úloze

##### <a name="notifications"></a>Oznámení

- Upozornit uživatele o chybovou podmínku

- Přerušit uživatelům zobrazit, pokud se chcete věnovat jiné činnosti

- Jemně uživatele informuje, že dokončení procesu nebo změnit, jako je po dokončení stahování.

#### <a name="simulate"></a>Simulace
Tato kategorie zahrnuje physicality a dimenzionalitu.

- Ukazuje, odkud pochází objekty nebo kde přejdou na

- Rozbalení a sbalení nebo otevření a zavření

- Posouvání, posouvání a stránku displeje

- Překrývání a pořadí z-ordering

- Prezentace a prvku typu accordion

- Převracení a otáčení uživatelského rozhraní

#### <a name="response-and-progress-indicators"></a>Indikátory odpovědi a průběh
Indikátory průběhu mají několik významné výhody:

- Oba indikátory determinate a neurčitého průběhu ujišťovat uživatele, který systém nebyl došlo k chybě a pracuje na problém.

- Determinate indikátory dát uživateli, který představu o tom, jak daleko podél akce probíhá, a také pocit blíž k dokončení.

## <a name="BKMK_AnimationPatterns"></a> Vzory animace

### <a name="overview"></a>Přehled
Animace v sadě Visual Studio jsou určené k obsluhuje konkrétní funkce omezování snížení produktivity uživatelů. Obecně platí by měla být animace v sadě Visual Studio:

- Malé a nerušivý

- Fyzická a realistické

- Tlumeném a současně lákavé

- Rychlé a efektivní

- Volný, ne hurried

Tento obrázek ukazuje styly animace, že doporučujeme pro sadu Visual Studio. Žádné animaci nebo drobným animace jako fade / zesvětlit nejčastěji používané. Omezené aplikace animace pohybu jako rozbalte a smlouvy, poloha změny a otáčení X a Y.

![Doporučuje se animace, styly pro Visual Studio](../../extensibility/ux-guidelines/media/1202-a_vsanimstyles.png "1202 a_VSAnimStyles")<br />Doporučené animace styly pro sadu Visual Studio

#### <a name="appear-and-disappear"></a>Zobrazí a zmizí
V tomto modelu přepne element z viditelné mimo zobrazení a zpět bez přechodu animace.

![Zobrazí a zmizí animace](../../extensibility/ux-guidelines/media/1202-b_appearanddisappear.png "1202 b_AppearAndDisappear")<br />Zobrazí a zmizí animace

##### <a name="correct-usage"></a>Správné použití
Nové prvky uživatelského rozhraní, které je potřeba okamžitě zobrazí nebo zmizí, takže uživatel odváděna ani nelze blokovat. Kromě toho pomalým pohybem animace může být vnímané jako výkonu přetažení, která obnoví se stylem jsou zobrazeny a zmizí.

##### <a name="incorrect-usage"></a>Nesprávné použití
Případy, ve kterých uživatelského rozhraní se zobrazí tak náhle že uživatel nemá žádné nápad co se stalo a přidání animace by pomohl s kontextové pochopení.

##### <a name="animation-properties"></a>Animace vlastností
Doba zpoždění je obvykle nula sekund.

##### <a name="examples"></a>Příklady
- Automatického skrytí oken nástrojů

- Aktivovat klávesnice editor uživatelského rozhraní, jako je IntelliSense a parametru nápovědy

- Oblasti rozbalení a sbalení kódu

#### <a name="fade-in-and-fade-out"></a>Vysouvaly a fade-out
V tomto modelu prvek uživatelského rozhraní změní z nejsou viditelné (krytí 0 %) na viditelné (100 % neprůhlednost) nebo naopak.

![Animace vysouvaly a fade-out](../../extensibility/ux-guidelines/media/1202-c_fadeinfadeout.png "1202 c_FadeInFadeOut")<br />Vysouvaly a fade-out animace

##### <a name="correct-usage"></a>Správné použití
Tato možnost se doporučuje nejčastěji animace uživatelského rozhraní. Je malý vliv, který přidá zájmu bez přerušení tok. V některých případech může uživatel nemusí i dobré si uvědomit, že je animace, vnímání hladký a tok uživatelského rozhraní systému.

##### <a name="animation-properties"></a>Animace vlastností

- Počáteční krytí: vysouvaly, 100 % po dobu fade-out % 0

- Neprůhlednost ukončení: 100 % po dobu vysouvaly 0 % fade-out

- Doba trvání: samostatné 200 MS, 100 milisekund, když se použije jako součást kombinaci animační sekvence.

- Usnadnění styl: Sinus vstup

##### <a name="examples"></a>Příklady

- Automatického skrytí oken nástrojů

- Nabídka otevřít a zavřít

- Na pozadí a popředí kartu přechody

#### <a name="color-blend-from-a-to-b"></a>Barva blendu od A do B
V tomto modelu prvek uživatelského rozhraní změní z barev A barvu B.

![Barva blend animace](../../extensibility/ux-guidelines/media/1202-d_colorblend.png "1202 d_ColorBlend")<br />Animace barev blendu

##### <a name="correct-usage"></a>Správné použití
Jako animovaný přechodu, když prvku uživatelského rozhraní změní barvu z kontextu nebo stavu do druhého.

##### <a name="animation-properties"></a>Animace vlastností

- Počáteční barva: Specifické pro uživatelské rozhraní

- Koncová barva: Specifické pro uživatelské rozhraní

- Doba trvání: samostatné 200 MS, 100 milisekund, když se použije jako součást kombinaci animační sekvence.

- Usnadnění styl: Sinus vstup

##### <a name="examples"></a>Příklady

- Zdokumentujte přechodů mezi stavy okno (aktivní, naposledy aktivní i neaktivní)

- Nástroj přechodů mezi stavy okno (zaměření a bez fokusu)

#### <a name="expand-and-contract"></a>Rozbalte a smlouvy
V tomto modelu se rozšíří prvku uživatelského rozhraní v X, Y nebo v obou směrech.

![Rozbalte a smlouvy animace](../../extensibility/ux-guidelines/media/1202-e_expandcontract.png "1202 e_ExpandContract")<br />Rozbalte a smlouvy animace

##### <a name="correct-usage"></a>Správné použití
Jako animovaný přechodu, když prvku uživatelského rozhraní se změní velikost z jednoho kontextu do jiného.

##### <a name="animation-properties"></a>Animace vlastností

- X rozsahu: % nebo konkrétní dimenzi (v pixelech)

- Y rozsahu: % nebo konkrétní dimenzi (v pixelech)

- Ukotvit pozice: obecně levou horní (pro jazyky zleva doprava) nebo pravém (pro jazyky zprava doleva)

- Doba trvání: samostatné 200 MS, 100 milisekund, když se použije jako součást kombinaci animační sekvence.

##### <a name="examples"></a>Příklady

- Panel Průzkumníka architektuře, rozbalíte nebo sbalíte

- Visual Studio 2017 úvodní stránku položky rozbalit nebo sbalit

#### <a name="x-y-position-change"></a>X-Y pozice změn
V tomto modelu prvek uživatelského rozhraní změní jeho pozice X nebo Y nebo obojí.

![Pozice X-Y Změna animace](../../extensibility/ux-guidelines/media/1202-f_xypositionchange.png "1202 f_XYPositionChange")<br />Animace změn pozice X-Y

##### <a name="correct-usage"></a>Správné použití
Jako animovaný přechodu, když prvku uživatelského rozhraní se změní pozice v jednom kontextu do jiného.

##### <a name="animation-properties"></a>Animace vlastností

- Spouští se X a Y pozice: Specifické pro uživatelské rozhraní

- Konec X a Y pozice: Specifické pro uživatelské rozhraní

- Dráhu pohybu: žádné

- Doba trvání: samostatné 200 MS, 100 milisekund, když se použije jako součást kombinaci animační sekvence.

- Usnadnění styl: Sinus vstup

##### <a name="example"></a>Příklad
Změna pořadí karty

#### <a name="rotate"></a>Otočit
V tomto modelu otočí prvek uživatelského rozhraní.

![Animace otočení prvek uživatelského rozhraní](../../extensibility/ux-guidelines/media/1202-g_rotate.png "1202 g_Rotate")<br />Animace otočení prvek uživatelského rozhraní

##### <a name="correct-usage"></a>Správné použití
Pouze pro neurčitý rotující indikátor průběhu.

##### <a name="animation-properties"></a>Animace vlastností

- Úhel otočení: 360

- Otočení center: střední objektu

- Doba trvání: průběžné

##### <a name="example"></a>Příklad
Indikátor neurčitého průběhu (rotujících)

### <a name="common-shell-ui-actions-and-recommended-animations"></a>Běžné akce uživatelského rozhraní prostředí a doporučené animace

#### <a name="tab-open"></a>Otevřete kartu
![Karta otevřít animace](../../extensibility/ux-guidelines/media/1202-h_tabopen.png "1202 h_TabOpen")<br />Otevřete kartu animace

- Style: Zobrazí

- Doba trvání: nula sekund

#### <a name="tab-close"></a>Zavřete kartu
![Karta zavřít animace](../../extensibility/ux-guidelines/media/1202-i_tabclose.png "1202 i_TabClose")<br />Animace Zavřít kartu

- Styl: Změna pozice X

- Doba trvání: 200 MS

#### <a name="tab-reorder"></a>Změnit pořadí karty
![Kartě animace přesunout v pořadí v sadě Visual Studio](../../extensibility/ux-guidelines/media/1202-j_tabreorder.png "1202 j_TabReorder")<br />Animace přesunout v pořadí karty

- Styl: Změna pozice X

- Doba trvání: 200 MS

#### <a name="close-floating-document"></a>Zavřít dokument s plovoucí desetinnou čárkou
![Zavřít s plovoucí desetinnou čárkou dokumentu animace](../../extensibility/ux-guidelines/media/1202-k_closefloatingdocument.png "1202 k_CloseFloatingDocument")<br />Zavřít s plovoucí desetinnou čárkou animace dokumentu

- Style: Zobrazí

- Doba trvání: 200 MS

#### <a name="window-state-transition"></a>Okno přechod stavu
![Okno stavu přechodu animace](../../extensibility/ux-guidelines/media/1202-l_windowstatetransition.png "1202 l_WindowStateTransition")<br />Okno stavu přechodu animace

- Style: pro zajištění konzistence s ostatními okny, umožňují definovat animace zavřít dokument aktuálního operačního systému.

- Doba trvání: 200 MS

#### <a name="menu-open"></a>Otevřete nabídku
![Nabídka otevřít animace](../../extensibility/ux-guidelines/media/1202-m_menuopen.png "1202 m_MenuOpen")<br />Nabídka otevřít animace

- Style: vysouvaly

- Doba trvání: 200 MS

#### <a name="menu-close"></a>Zavřete nabídku
![Nabídka animace Zavřít](../../extensibility/ux-guidelines/media/1202-n_menuclose.png "1202 n_MenuClose")<br />Zavřít nabídku animace

- Style: fade-out

- Doba trvání: 200 MS

#### <a name="auto-hide-tool-window-reveal"></a>Zobrazit okno nástroje automatického schovávání
![Automatického schovávání animace zobrazit okno nástroje](../../extensibility/ux-guidelines/media/1202-o_autohidetoolwindowreveal.png "1202 o_AutoHideToolWindowReveal")<br />Automatického schovávání animace zobrazit okno nástroje

- Style: Zobrazí

- Doba trvání: nula sekund
