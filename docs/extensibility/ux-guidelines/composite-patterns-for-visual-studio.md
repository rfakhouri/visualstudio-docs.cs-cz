---
title: Složené vzory pro sadu Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: e48ecfb2-f4b5-4d3a-b4a2-7a4d62fa4ec0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6515b5aefc0536ea92f09a92b1a17050b820008d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="composite-patterns-for-visual-studio"></a>Složené vzory pro sadu Visual Studio
Složené vzory kombinovat interakce a prvky návrhu v různých konfiguracích. Mezi nejdůležitější složené vzory v sadě Visual Studio s ohledem na konzistence patří:  
  
-   [Vizualizace dat](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_DataVisualization)  
  
-   [Na objekt uživatelského rozhraní a prohlížení](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_OnObjectUI)  
  
-   [Výběr modely](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_SelectionModels)  
  
-   [Trvalosti a ukládá se nastavení](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_PersistenceAndSavingSettings)  
  
-   [Dotykové ovládání](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_TouchInput)  
  
##  <a name="BKMK_DataVisualization"></a> Vizualizace dat  
  
### <a name="overview"></a>Přehled  
 Grafy jsou vizuální způsob, jak agregovat a vizualizaci dat za účelem zvýšení rozhodnutí. Můžou pomoct potýkají s velkým množstvím dat, ale malé znamená, co si zaslouží pozornost a co může být nutné akce uživatele.  
  
 Uživatel bude mít užitek z grafu, pokud platí některá z následujících podmínek:  
  
-   Bude grafu uživatelům pomůže identifikovat úlohy, které může fungovat na?  
  
-   Graf umožňuje uživatelům prognózy dopadech potenciální změny?  
  
-   Pomohou grafu uživatelům zjišťovat trendy a identifikaci vzorů?  
  
-   Umožní grafu uživatelům lépe rozhodnout?  
  
-   Graf pomůže odpovědět konkrétní dotaz, který uživatelé mohou mít v daném kontextu?  
  
#### <a name="general-rules-for-charts"></a>Obecná pravidla pro grafy  
  
-   Jasně popisek data. Ilustrace bez vysvětlení jsou jenom velmi obrázky.  
  
-   Spusťte osy na nule, aby se zabránilo zkosení poměr stran. Velikost řádku délku a panelu jsou důležité vizuální upozornění k pochopení vztahy mezi datových bodů.  
  
-   Vytvořte grafy, není infographics. Infographics jsou uměleckého reprezentace dat a jejich primární cílem je visual příběhů. Grafy můžete (a měli) být přitažlivé, ale nechat datům vyniknout.  
  
-   Vyhněte se skeumorphism, obrazové pruhové grafy, hashmarks kontrast a další úpravy infografice.  
  
-   Nepoužívejte jako element dekorativní 3D účinky. Používat pouze v případě, že skutečně nedílnou součástí schopnost uživatele pochopit informace.  
  
-   Nepoužívejte více čar a výplní, stejně jako více než dvě barvy můžete provádět tento typ grafu obtížné číst a správně interpretovat.  
  
-   Nepoužívejte jako jediného prostředku k pochopení koncept nebo interakci s daty grafu (nebo všechny obrázek). To představuje problémy uživatelům se zrakovým postižením.  
  
-   Nepoužívejte grafy jako dobrovolný nebo dekorativní elementy na stránce. Jinými slovy Pokud graf nepřidá všechny hodnoty nebo nápovědy uživatele vyřešit problém, nepoužívejte ji.  
  
### <a name="chart-types"></a>Typy grafů  
 Typy grafů používá v sadě Visual Studio jsou pruhové grafy, spojnicových grafů, označovanou jako "prstenec grafu," časových os, nebo prstenec grafu upravené výsečového grafu bodový pozemcích (také nazývané "clusteru grafy") a Ganttova. Každý typ grafu je užitečný pro komunikaci jiný druh informací.  
  
### <a name="other-charting-considerations"></a>Další důležité informace o vytváření grafů  
  
#### <a name="color"></a>Barva  
 Neexistuje konkrétní paleta grafů barvy definované pro použití v sadě Visual Studio. Palety barev je přístupný pro hlavní typy barvoslepostí a barvy můžete rozlišené, i když se použije jako velmi krátkého řezy barvy. Můžete použít tyto barvy v libovolné kombinace pro jakýkoli typ grafu nebo grafu v uživatelském rozhraní. Nemusíte použít všechny sedm barvy, pokud není nutné tolika jednotlivé barvy. Tyto barvy obvykle nebyly navrženy pro použití s všech elementů popředí, neumísťujte text nebo glyfů na tyto barvy. Tyto odstíny by měl pevně a viditelné na vlastní nastavení uživatele v části **nástroje > Možnosti** (najdete v části [vystavení barvy pro koncové uživatele](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_ExposingColorsForEndUsers)).  
  
|Vzorníku|Hex|RGB|  
|------------|---------|---------|  
|![Vzorníku 71B252](../../extensibility/ux-guidelines/media/0711_71b252.png "0711_71B252")|#71B252|113,178,82|  
|![Vzorníku BF3F00](../../extensibility/ux-guidelines/media/0711_bf3f00.png "0711_BF3F00")|#BF3F00|191,63,0|  
|![Vzorníku FCB714](../../extensibility/ux-guidelines/media/0711_fcb714.png "0711_FCB714")|#FCB714|252,183,20|  
|![Vzorníku 903F8B](../../extensibility/ux-guidelines/media/0711_903f8b.png "0711_903F8B")|#903F8B|144,63,139|  
|![Vzorníku 117AD1](../../extensibility/ux-guidelines/media/0711_117ad1.png "0711_117AD1")|#117AD1|17,122,209|  
|![Vzorníku 79D7F2](../../extensibility/ux-guidelines/media/0711_79d7f2.png "0711_79D7F2")|#79D7F2|121,215,242|  
|![Vzorníku B5B5B5](../../extensibility/ux-guidelines/media/0711_b5b5b5.png "0711_B5B5B5")|#B5B5B5|181,181,181|  
  
##  <a name="BKMK_OnObjectUI"></a> Na objekt uživatelského rozhraní a prohlížení  
 Tato část poskytuje kontext k prohlížení, také známé jako zobrazení funkce Náhled kódu, typ-object uživatelského rozhraní pro Visual Studio jedinečné.  
  
### <a name="overview"></a>Přehled  
  
-   Uživatelského rozhraní na objekt měl dát uživatele Další informace nebo interaktivity bez zasahoval jejich hlavní úloh.  
  
-   Hlavní vzor pro-object uživatelského rozhraní v sadě Visual Studio se označuje jako "informace v místě pozornost."  
  
-   Na objekt uživatelského rozhraní v sadě Visual Studio je buď vložené nebo číslo s plovoucí čárkou a trvale nebo pouze dočasné.  
  
    -   Zobrazení funkce Náhled kódu, typ-object uživatelského rozhraní v sadě Visual Studio je vložené a trvale.  
  
    -   Codelensu, typ-object uživatelského rozhraní v sadě Visual Studio, se plovoucí a přechodné  
  
 Pochopení, jak funguje úsek kódu, nebo při hledání podrobnosti o tomto kódu, často vyžaduje vývojář přepnout kontext a přejděte na další obsah nebo jiné okno. Tyto posuny kontext může být rušivým zásahům, protože uživatelé ztratit zaměřit se na jejich původní úloh, pokud jejich nechte jejich hlavní okno. Kromě toho získávání, že původní zpět kontext může být složité, zejména v případě, že přepnutí systému windows kvůli jejich původní kód, chcete-li být skryty pomocí jiných uživatelského rozhraní.  
  
 Uživatelského rozhraní na objekt pracuje podle vzoru označované jako "informace v místě pozornost." Tyto zprávy, automaticky otevíraná okna a dialogová okna uživatelům poskytnout další, relevantní informace, které přidá vyjasnění nebo interaktivity bez ztráty zaměřit se na jejich hlavní úloh. Mezi příklady-object uživatelského rozhraní patří automaticky otevíraná okna, které se zobrazí při nastavení ukazatele jejich ukazatele myši na ikonu v oznamovací oblasti, červenou vlnovkou pod chybně a zobrazení funkce Náhled zavedená v sadě Visual Studio 2013.  
  
### <a name="decision-points"></a>Rozhodovací body  
 V sadě Visual Studio existuje několik způsobů použití tohoto vzoru informací v místě pozornost. Výběr správné mechanismus a implementace konzistentní a předvídatelné způsobem je nezbytně nutné, aby celkový dojem. Uživatelé, jinak může bude nabídnuta matoucí nebo nekonzistentní prostředí, které subjektů fokus ze samotného obsahu.  
  
#### <a name="relationships-between-master-and-detail-content"></a>Vztahy mezi seznamu a podrobností obsahu  
 Informace v místě pozornost se používá k zobrazení vztahu mezi obsah, aby uživatel byl zaměřují se na ("hlavní" obsah) a další související obsahu (obsah "podrobné"). V tomto vzoru se týká obsahu podrobností jasně obsah uživatel pracuje s a mohou být zobrazeny blízko hlavní obsah. Další informace nebo informace, které nelze souhrnu bez zahltí hlavní obsah by mělo vycházet jiný vzor, jako je například okno nástroje.  
  
-   **Vždy** zobrazení Podrobnosti o obsahu v těsné blízkosti hlavní obsah.  
  
-   **Vždy** Ujistěte se, že obsah podrobností stále umožňuje uživateli zůstanou zaměřují se na hlavní obsah. Často je nejlepší způsob, jak dosáhnout vykreslení obsahu podrobností jako blízko hlavní obsah nejblíže. Tento krok můžete provést vykreslování obsahu podrobností v místním okně vedle hlavní obsah, nebo vykreslování vloženého obsahu podrobností pod hlavní obsah.  
  
-   **Nikdy** pomocí informací v místě pozornost, uživatel od hlavního obsahu. Pokud uživatelé nepotřebují zobrazit podrobnosti o obsahu samostatně, vystavit explicitní akci, která umožňuje uživatelům provést.  
  
#### <a name="design-details"></a>Podrobnosti o návrhu  
 Jakmile zjistíte, že uživatelského rozhraní na objekt je správnou volbou, existují čtyři hlavní faktorů:  
  
1.  **Trvalost:** obsah musí být trvanlivý nebo přechodný?   
    Bude vhodné zachovat informace viditelné pro odkazovat na nebo interakci s uživatelů? Nebo se uživatelé chtějí rychle přehled na informace a potom pokračujte v jejich hlavní úloh?  
  
2.  **Typ obsahu:** obsah bude informační, kterého lze provést akci nebo navigačních?   
    Potřebuje uživatel další podrobnosti o obsahu, hlavní? Musí uživatel provést úlohu, která ovlivňuje hlavní obsah? Nebo uživatel potřebuje přesměrováni na jiný prostředek?  
  
3.  **Typ ukazatele:** vedlejším indikátor mít smysl?   
    Můžete informace souhrnu užitečným způsobem a zobrazit bez zahltí hlavní obsah?  
  
4.  **Gesta:** co gesta se použije k vyvolání a zavřít uživatelského rozhraní?   
    Jak se uživatel zprovoznit podrobnosti o obsahu a odesílá je rychle? Existuje hodnota v přidávání gesto například Připnutí přepínat mezi stavy přechodný a odolná?  
  
 Každý z těchto čtyř rozhodovací body bude mít dopad na hlavní součásti uživatelského rozhraní-object.  
  
### <a name="on-object-ui-components"></a>Součásti uživatelského rozhraní na objekt  
  
1.  Typ kontejneru (obsahu přednášejícího)  
  
    -   Plovoucí  
  
    -   Vložené  
  
2.  Typ obsahu  
  
    -   Informační: data, která může být statické nebo dynamické  
  
    -   Řešitelné: příkazy, které měnit hlavní obsah  
  
    -   Navigační: odkazy, které zavedou uživatele do jiného okna nebo na aplikaci, například MSDN  
  
3.  Gesta  
  
    -   Vyvolání  
  
    -   Propouštění  
  
    -   Připnutí  
  
    -   Další interakce  
  
4.  Model trvalosti a potvrzení  
  
    -   Dočasná  
  
    -   trvanlivý  
  
    -   Automatické  
  
    -   Na vyžádání  
  
5.  Vedlejším indikátory (volitelné)  
  
    -   Podtržení vlnovku  
  
    -   Ikona inteligentní značky  
  
    -   Další indikátory, vedlejším  
  
#### <a name="container-content-presenter-type"></a>Typ kontejneru (obsahu přednášejícího)  
 Existují dvě hlavní možnosti, které jsou k dispozici pro prezentovat obsah v místě pozornost:  
  
1.  **Vložené:** vložené přednášejícího, jako je například funkce Náhled zobrazení, která byla zavedena v Visual Studio 2013 editoru kódu, díky místa pro nový obsah přepínáním existujícího obsahu.  
  
    -   **Dáváte přednost** prezentovat předvádějící vložený, pokud očekáváte, že budou uživatelé chtít spoustu času odkazující na nebo interakci s obsahem.  
  
    -   **Vyhněte se** předvádějící vložený, pokud budou uživatelé chtít přehled si informace k dispozici a potom pokračujte jejich hlavní úloh s minimálním dopadem.  
  
2.  **Plovoucí:** plovoucí přednášejícího je umístěn co nejblíže vybraného obsahu nejdříve nedojde však ke změně rozložení existujícího obsahu. Mohou být použity různé strategie, jako je například zobrazení plovoucí obsahu panel přes nejbližší dostupné mezera vybraného symbolu.  
  
    -   **Dáváte přednost** plovoucí předvádějící, pokud budou uživatelé chtít přehled si informace k dispozici a potom pokračujte jejich hlavní úloh s minimálním dopadem.  
  
    -   **Vyhněte se** plovoucí předvádějící, pokud budou uživatelé chtít spoustu času odkazující na nebo interakci s obsahem je přítomen.  
  
#### <a name="content-type"></a>Typ obsahu  
 Existují tři hlavní typy obsahu, který lze zobrazit v kontejneru, uživatelského rozhraní na objekt. Libovolnou kombinaci těchto typů informací lze zobrazit. Tři typy jsou:  
  
1.  **Informační:** většinu na object kontejnery uživatelského rozhraní se zobrazí nějaké informační obsahu. Obsah může představovat informace o stavu prostředí nebo ho může představovat informace o potenciální budoucí stav prostředí. Například se může zobrazit účinku konkrétní příkaz, jako je například refaktoring, na existující kód.  
  
    -   **Vždy** použít kanonický reprezentaci informace, které můžete zobrazit. Například kód by měl vypadat jako kód, včetně zvýraznění syntaxe a by měly dodržovat ať písma a dalších nastaveních prostředí, má uživatel nastaven.  
  
    -   **Vždy** zvažte podpora všechny akce přes informační obsah, který by bylo možné v případě, že stejné informace jsou poskytovány jako hlavní obsah. Například pokud prezentací existující kód uvnitř kontejner uživatelského rozhraní na objekt, doporučujeme raději podpora možnost Procházet a upravit tento kód.  
  
    -   **Vždy** zvažte použití jinou barvu pozadí, pokud prezentací informační obsah, který představuje potenciální budoucí stav.  
  
2.  Řešitelné: některé kontejnery uživatelského rozhraní na objekt vám poskytne možnost provedení několika akcí přes hlavní obsahu, například při provádění operace refaktoringu.  
  
    -   **Vždy** umístit je možné použít příkazy odděleně od informační obsah.  
  
    -   **Vždy** povolení a zákaz akce v případě nutnosti.  
  
    -   **Vždy** viz standardní pokyny pro představující příkazy v dialogových oknech.  
  
    -   **Vždy** zachovat minimální počet akce, které jsou zveřejněné v kontejneru na objekt uživatelského rozhraní na absolutním. Interakci s uživatelským rozhraním ve objektu by měla být prostředí lightweight, rychlé. Uživatel by nemělo být rozbalte uzel energie na správu na objekt kontejneru uživatelského rozhraní samotného.  
  
    -   **Vždy** zvažte, jak a kdy kontejner uživatelského rozhraní na objekt bude uzavřen nebo zamítnuto. Jako osvědčený postup by měl jakoukoliv akci, která ukončí dialogové okno mezi seznamu a podrobností obsahu rovněž zavřete kontejneru na objektů uživatelského rozhraní, při vyvolání této akce.  
  
3.  **Navigační:** některé na object uživatelského rozhraní kontejnery obsahují odkazy, který přenese uživatele do jiného okna nebo na aplikaci, například otevírání článku na webu MSDN ve webovém prohlížeči uživatele.  
  
    -   **Vždy** předřazení žádné navigační odkaz s "Otevřené" tak, aby uživatelé nesmí být sledován se přešli některé další obsah.  
  
    -   **Vždy** nezávislá řešitelné odkazy na navigační odkazy.  
  
#### <a name="ambient-indicators-optional"></a>Vedlejším indikátory (volitelné)  
 Vedlejším indikátory může být jemně, včetně textu v kontrastní barvu od zbytku kód, nebo zřejmé, včetně tickler symboly, například podtržení vlnovku a ikony inteligentních značek. Vedlejším indikátory komunikovat dostupnost další relevantní informace. V ideálním případě poskytují užitečné informace i bez nutnosti uživatelům pracovat s nimi.  
  
-   **Vždy** umístěte vedlejším indikátor tak, aby nebudou oslabení a zahlcovat uživatele. Pokud není možné umístit vedlejším indikátor takovým způsobem, zvažte jiným řešením.  
  
-   **Vždy** umístit co nejblíže k obsahu, který je spojený s vedlejším indikátoru.  
  
-   **Vždy** pokusu o vytvoření indikátor, který shrnuje informace jsou k dispozici. Zvažte zadat počet počet datových položek, které jsou k dispozici (například "3 odkazy" místo jednoduše odkazy na"") nebo si můžete představit nějakým způsobem ke shrnutí dat.  
  
    -   V případech, kde data pro slouží jako ukazatel nelze vždy vypočítaného a zobrazuje okamžitě zvažte, poskytování zpětné vazby o progresivní jako hodnoty se vypočítávají v. Představte si třeba animace změny, které uplatňování aktualizací dostupnosti dat, podobně jako, který aktualizuje dlaždici za provozu e-mailu na Windows Phone jako číslo zvyšuje nepřečtené e-maily.  
  
-   **Nikdy** přidat další indikátory, než uživatel přiměřeně využít pro určitou část obsahu. Vedlejším indikátory by měl být užitečné bez nutnosti zásahu od uživatele. Indikátory ke ztrátě jejich podmínek, za vyžadují přetečení a jiných ovládacích prvků správy, aby byly do zobrazení.  
  
#### <a name="gestures"></a>Gesta  
 Klíčovým prvkem které uživateli umožňují zachovat fokus na hlavní obsah je podpora správné gesta k otevření a zavření obsah další podrobnosti.  
  
-   **Vždy** vyžadovat, aby uživatel k provedení některých explicitní gesto otevřít další obsah. Běžné otevřete gesta patří:  
  
    -   **Hover:** popisů tlačítek nebo neinteraktivní informační obsahu  
  
    -   **Explicitní příkaz:** vložené přednášejícího  
  
    -   **Dvakrát klikněte na indikátor vedlejším:** automaticky otevírané okno Codelensu  
  
-   **Vždy** zavřít podrobností obsah vždy, když uživatel stisknutím klávesy Esc.  
  
-   **Vždy** zvažte kontextu uživatelského rozhraní na objekt. Pro předvádějící obsahu, které umožňují interakci v rámci kontejneru pečlivě zvažte, jestli se má zobrazit upřesňující informace při přechodu myší, což je pravděpodobně rušivý pracovního postupu uživatele.  
  
-   **Nikdy** zobrazit obsah při přechodu, který se zdá být upravovat nebo vyzývá interakci s uživatelem. Toto chování může frustrovat uživatele, pokud se uživatel pokusí přesuňte kurzor na podrobnosti o obsahu, jako je standardní chování pro popisek okamžitě zrušíte, pokud se ukazatel už přes hlavní obsah, který ho vytvořil.  
  
##  <a name="BKMK_SelectionModels"></a> Výběr modely  
  
### <a name="overview"></a>Přehled  
 Výběr modelu je mechanismus používaný k označení a potvrďte operací na jeden nebo více objektů zájmu v rámci uživatelského rozhraní. Toto téma popisuje vzory interakce výběr v sadě Visual Studio dokumentu editory: textové editory, návrhové ploše a modelování ploch.  
  
 Uživatelé musí mít k sadě Visual Studio vyjadřuje, co pracují na a Visual Studio musí odpovědět předvídatelné s zpětnou vazbu pro uživatele, o co ho pracuje na. Rozdíly nebo chybnou komunikaci mezi uživatelem a uživatelské rozhraní může mít za následek uživatele není vašeho povšimnutí akce, která může mít nezamýšleným důsledky. Chyba přejde často bez povšimnutí, dokud uživatel uvidí něco chybí nebo se změnila. Výběr modely jsou proto jedním z nejdůležitějších kusy návrh uživatelského rozhraní. Přestože výběr modelů v sadě Visual Studio jsou konzistentní s Windows, jsou drobné rozdíly.  
  
 V sadě Visual Studio, jako v systému Windows výběr modely lišit v závislosti na kontextu, ve kterém dojde k interakci. Výběr se může objevit v čtyři typy objektů:  
  
-   Text  
  
-   Grafické objekty  
  
-   Seznamy a stromů  
  
-   Mřížky  
  
 V rámci tyto objekty existují tři typy výběr:  
  
-   Souvislý  
  
-   Nesouvislé  
  
-   Oblast  
  
#### <a name="scope"></a>Rozsah  
 Nejdůležitější komponenta výběr zajišťuje, že uživatel zná v okně, které pracují (aktivace) a kde je aktivní nachází (výběr). Visual Studio rozšiřuje funkce správy okna v systému Windows, ale schéma aktivace je stejný: interakci s okno přináší fokus do okna. Visual Studio má dva indikátory aktivace: jeden pro windows dokumentu a jeden pro nástroje systému windows.  
  
 Pro windows dokumentu aktivní okno je indikován kartu okna dokumentu přicházející na stránce do popředí a změníte barvu pozadí:  
  
 ![Výběr aktivní karty v sadě Visual Studio](../../extensibility/ux-guidelines/media/0713-01_activetab.png "0713 01_ActiveTab")  
  
 **Výběr aktivní karty**  
  
 Pro nástroj windows aktivní okno je indikován změnu barvu název oblasti panelu panel nástrojů:  
  
 ![Okno Výběr aktivního nástroje v sadě Visual Studio](../../extensibility/ux-guidelines/media/0713-02_activetoolwindow.png "0713 02_ActiveToolWindow")  
  
 **Okno Active nástroje zobrazující primární výběr uzlu**  
  
 ![Okno Výběr neaktivní nástrojů v sadě Visual Studio](../../extensibility/ux-guidelines/media/0713-03_inactivetoolwindow.png "0713 03_InactiveToolWindow")  
  
 **Okno nástroje neaktivní, zobrazující latentní výběr uzlu**  
  
 Po aktivní okno zaměřuje uvedené podle výběr modelů uvedených v této části podle pokynů.  
  
#### <a name="context"></a>Kontext  
 Visual Studio byla navržená tak, aby zachovat silné koncept kontextu, udržování zaznamenávat, kde uživatel pracuje. Pouze jeden interval je aktivní, jestli je okno nástroje nebo dokumentu. Okna nejhornější dokumentu však zachová vždy latentní výběr. I když v okně nástroj může být fokus, zobrazí okna dokumentu, který byl naposledy aktivní výběr, i v neaktivním stavu. Důvodem je, že bude potřeba uchovat kontextu uživatele v dokumentu, které byly úpravy, zobrazující, že Visual Studio si jejich stavu tak, aby se můžete vrátit a posunutí bezproblémově mezi nástroj windows a windows dokumentu.  
  
### <a name="text-selection"></a>Výběr textu  
 Visual Studio editory, které jsou výhradně textovou, jako jsou předdefinované textový editor, použijte stejný model výběr textu a vzhled popsané v [myši a ukazatele](https://msdn.microsoft.com/en-us/library/dn742466.aspx) pokyny interakce práci uživatelů systému Windows na stránce MSDN. Svislá čára volat kurzor je indikován zaměření pro vstup v textovém editoru. Kurzor je jeden pixelů silné a barevnou jako inverzní ať se zobrazí za ní. Ho bliká podle rychlost nastaven **kurzoru** nastavení v **rychlost** kartě **klávesnice** apletu ovládacího panelu.  
  
#### <a name="contiguous-and-disjoint-selection"></a>Souvislé a nesouvislý výběru  
 Výběr v textovém editoru je pouze souvislé. Nesouvislé text výběr nejsou povolené, ale mělo by se řešit editorů grafického objektu. Když ukazatel myši nad textová oblast, kurzoru změní na kurzor. Jedním kliknutím umístí kurzor v textovém editoru klikněte na umístění. Tlačítko myši stisknuté spustí zvýraznění výběr a uvolněním tlačítka myši končí výběr zvýraznění.  
  
#### <a name="region-selection-box-selection"></a>Výběr oblasti (Výběr pole)  
 Visual Studio podporuje výběr oblasti v textovém editoru a tento postup se nazývá výběr pole. Výběr pole umožňuje uživateli vybrat oblasti text, který neodpovídá pravidlům pro datový proud běžný text. Stejně jako u standardního textového výběru, musí být spojití výběr. Výběr pole inicializuje podržíte stisknutou klávesu Alt při přetahování myší. Výběr pole lze také zahájit podržením klávesy Alt a klávesy Shift a pomocí klávesy se šipkami k označení oblasti výběru. Výběr pole zobrazuje kurzor bod vložení blikat na konci oblasti pro výběr a využívá zvýraznění normální výběr.  
  
 ![Místní &#40;pole&#41; výběr v sadě Visual Studio](../../extensibility/ux-guidelines/media/0713-04_boxselection.png "0713 04_BoxSelection")  
  
 **Výběr oblasti (pole) v sadě Visual Studio**  
  
#### <a name="text-selection-appearance"></a>Vzhled výběr textu  
 Můžete přizpůsobit barvy použité pro aktivní i neaktivní výběr v editoru. Chcete-li přizpůsobit vzhled editoru, uživatel přejít **nástroje > Možnosti**a pak hledejte v části **prostředí > písma a barev > textový Editor**.  
  
### <a name="graphical-selection"></a>Výběr grafického rozhraní  
  
#### <a name="interaction"></a>Interakce  
 Výběr grafického objektu může být složité a závisí na počtu faktorů:  
  
-   **Model primární výběr editoru.** Editory, které obsahují grafické objekty lze také upravit text nebo mřížky. Editor může být například textový editor, který taky podporuje umístění grafické objekty, například návrháře Visual Studio XAML. Podpora více typů objektů může ovlivnit jak uživatel vybere skupiny složená z různých objektů.  
  
-   **Podpora pro výběr primární a sekundární stavy.** Editor může poskytovat primární a sekundární výběr, které stavy tak, aby objekty lze upravit v souladu, zarovnán s sebou po změně velikosti společně, a tak dále.  
  
-   **Podpora úpravy na místě.** Editory můžete povolit také obsah jejich grafické objekty k provádění úprav. Tvar obdélníku například může obsahovat text uvnitř, který může uživatel změnit. Kromě toho může být tento text na střed nebo zarovnán do bloku. Úpravy na místě zahrnuje podrobnější úrovni interakce s uživatelem a proto vyžaduje odpovídající sadu vizuální upozornění pro prezentování informací o stavu pro uživatele.  
  
#### <a name="mouse-interaction"></a>Interakce myši  
  
|Vstup|Výsledek|  
|-----------|------------|  
|Klikněte na objekt nezaškrtnuté|Vybere objekt a zobrazuje na přerušovanou čáru a úchyty, pokud je objekt s možností změny velikosti.|  
|Klikněte na vybraný objekt|Aktivuje, pokud objekt podporuje úpravy na místě. Kliknutím na tlačítko mimo objekt deaktivuje režimu úprav na místě.|  
|Dvakrát klikněte na objekt|Otevře kódu objekt pro úpravy a může vložit výchozí obslužnou rutinu události, podle potřeby.|  
|Přejděte na objekt|Přesunutí kurzoru změní ukazatele. Vzhled objektu, například jeho světlost nebo barvy, může se měnit.|  
|Přejděte na úchytu|Ukazatel se změní na ukazatel změny velikosti. Pro objekty, které podporují otočení některé úchyty výběru může změnit ukazatele na otáčení kurzoru jako ukazatel myši na jinak (například přesunout dále od) s ohledem na výběr popisovač.|  
|Přetažení|I v případě, že objekt není vybrali dříve, změní kurzor na přesunutí kurzoru a přesune objekt.|  
|Editor ztratí fokus|Deaktivuje místní režimu úprav, i když objekt zachová obsah a vzhled, který měl během jeho poslední stav operace/výběr.|  
|Výběr objektu|Indikován ohraničení, tečkovaná čára nebo jiných vizuálně odlišné zacházení zvýrazněte hranice objektu.|  
|Změnit velikost vybraného objektu|Indikován úchyty výběru.<br /><br /> Objekt s možností změny velikosti má osm obslužných rutin, představující každý směr, ve kterém můžete změnit. Méně obslužné rutiny mohou být použity, pokud objekt lze nastavit pouze v určitých pokynů. Když uživatel velikostí objekt dolů kde nebude interaktivní osm obslužných rutin, může použít čtyři obslužné rutiny. Velikosti popisovač by měl být vázáno okno okraj a okraj metriky s **GetSystemMetrics** funkce rozhraní API velikost v poměru k rozlišení obrazovky.<br /><br /> ![Změnit velikost popisovače](../../extensibility/ux-guidelines/media/0713-05_resizehandles.png "0713 05_ResizeHandles")|  
|Otočit vybraný objekt|![Otočit popisovače](../../extensibility/ux-guidelines/media/0713-06_rotate.png "0713 06_Rotate")|  
  
#### <a name="keyboard-interaction"></a>Interakce klávesnice  
  
|Vstup|Výsledek|  
|-----------|------------|  
|Tabulátor|Přesouvá fokus indikátor mezi logickému uspořádání objektů v editoru. To může být zleva doprava nebo horní dolů v závislosti na **pořadové číslo prvku** (nebo ekvivalentního) hodnotu vlastnosti, pořadí vytváření objektů a celkové účel editoru. Shift + Tab obrátí směr indikátoru fokus.|  
|MEZERNÍK|Aktivuje klávesnicí režimu, a udržovat klávesu. Vstup z myši další je potřeba posouvání pozice zobrazení.|  
|Ctrl + mezerník|Aktivuje režim přiblížení a udržovat klávesu. Vstup z myši další je potřeba zvýšit nebo snížit na faktor zvětšování.|  
|Ctrl + Alt + symbol mínus|Snižuje na faktor zvětšování o jednu úroveň.|  
|Ctrl + Alt + symbol plus|Zvyšuje na faktor zvětšování o jednu úroveň.|  
|SHIFT nebo Ctrl|Přidá objekt do výběru skupiny. CTRL můžete také odstranit objekty jednotlivě ze skupiny pro výběr.|  
|Enter|K provedení příkazu výchozí pro objekt (obvykle otevřít nebo upravit).|  
|F2|Aktivuje úpravy objektu na místě.|  
|Klávesy se šipkami|Přesune vybrané objekty ve směru klávesy ŠIPKA stisknuto malých přírůstcích (například 1 pixel najednou)|  
|CTRL + klávesy se šipkami|Přesune vybrané objekty ve směru klávesy ŠIPKA stisknutí větší úseky (například 10 pixelů najednou)|  
|SHIFT + ŠIPKA klíče|Změní velikost vybrané objekty. v jednom směru, v malých přírůstcích (například 1 pixel najednou)|  
|Ctrl + Shift + klávesy se šipkami|Změní velikost vybrané objekty. v jednom směru, v přírůstcích po větší (například 10 pixelů najednou)|  
  
 Když uživatelé upravovat ovládacích prvků v místě, může mít smysl pro objekty, které se automaticky změní velikost se vstupem uživatele. Například pokud uživatel upravuje ovládací prvek popisek, pak popisek by měl dosáhnout zobrazit text, který uživatel právě zadali. Pokud to neuděláte, uživatel musí změnit velikost ovládacího prvku ručně po úpravě textu. Pokud uživatel má spoustu dalších ovládacích prvků, stane rote a neproduktivní úloh.  
  
#### <a name="graphical-containers"></a>Grafické kontejnery  
 V některých případech zadejte grafické editory kontejnery pro další grafické objekty, například ovládací prvek Windows Forms Panel nebo ovládacího prvku mřížky rozložení v Návrháři HTML. Pokud vaše editor poskytuje kontejnery pro další grafické objekty, by měl následující Výběr modelu použít pro kontejner jenom (objektů v rámci postupujte podle kontejneru, standardní model jako popsané výše):  
  
|Vstup|Výsledek|  
|-----------|------------|  
|Jedním kliknutím na kontejneru|Vybere objekt kontejneru bez přímo vyberete všechny obsažené objekty. Kontejner může přesunout nebo změně velikosti s standardní myši a klávesnice vstup (jak je popsáno výše). Obsažené objekty se přesunou ve vztahu ke kontejneru, ale nejsou obsažené objekty změnit, pokud jsou také přímo vybrané.|  
|Pozastavte ukazatel myši nad oblasti hranic kontejneru|Přesunutí kurzoru, indikující, že lze přesunout kontejneru se změní myši.|  
|Přetáhněte oblasti hranic kontejneru|Změny přesuňte kurzor myši a přesune kontejneru (a obsažené objekty v rámci). Kontejner nelze přesunout bez předchozího vybrat s jedním kliknutím.|  
|Jedním kliknutím na objekt v kontejneru|Zruší výběr kontejneru (Pokud je vybrán) a vybere pouze kliknutelnou objektu.|  
|SHIFT + klikněte na možnost nebo kombinaci kláves Ctrl + kliknutí myši na obsažený objekt nebo kontejneru|Přidá objekt kliknutelnou do existujícího výběru nebo výběr skupiny. Pokud kliknutelnou objekt je již členem skupiny výběr, odebere se ze skupiny pro výběr.|  
  
 Obsažené objekty by měl splňovat základní Výběr modelu, jak je popsáno v předchozí části. Uživatelé z testování použitelnosti Návrhář formulářů Windows, očekává bezproblémový přístup k obsažené objekty bez použité kroků (způsobené objekt omezení).  
  
#### <a name="disjoint-and-region-selections"></a>Nesouvislé a vybrané oblasti  
 Editory grafického objektu by měly podporovat nesouvislý výběr. Upozorňujeme, že tato grafika nezobrazuje vzhledu ovládacího prvku pro sadu Visual Studio. V tématu [vzhled výběr grafického objektu](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_GraphicalObjectSelectionAppearance) pro podrobné visual specifikace.  
  
 ![Nesouvislé a oblast selektory](../../extensibility/ux-guidelines/media/0713-07_disjointregionselectors.png "0713 07_DisjointRegionSelectors")  
  
 **Nesouvislý výběr**  
  
 Grafické editory musí zadat výběr oblasti indikátorem výběr výběr typu. Pokud grafický editor podporuje další typy objektů (například text), nemusí být možné v závislosti na omezení tyto typy objektů výběr oblasti.  
  
 ![Hranice výběru](../../extensibility/ux-guidelines/media/0713-08_marqueeselection.png "0713 08_MarqueeSelection")  
  
 **Hranice výběru**  
  
#### <a name="primary-and-secondary-selections"></a>Primární a sekundární výběr  
 Některé editory grafického objektu umožňuje uživateli upravit nebo zarovnat objekty ve skupinách. V takovém případě je potřeba zavést koncept primární a sekundární výběr. Primární výběr je objekt, na které reagovat všechny ostatní objekty pro skupinu operace. Objekt, který si uživatel vybere první stane primární ovládacího prvku a následné výběry přestat sekundární výběr. Primární výběr má odlišné visual zacházení ze sekundární vybrané položky k označení, který objekt je primární:  
  
 ![Primární a sekundární výběr](../../extensibility/ux-guidelines/media/0713-09_primarysecondary.png "0713 09_PrimarySecondary")  
  
 **Primární výběr dva sekundární výběr**  
  
####  <a name="BKMK_GraphicalObjectSelectionAppearance"></a> Vzhled výběr grafického objektu  
 Výběr popisovače jsou čtverce v obdélníková vzoru kolem pole ohraničující objektu. Následující graf zobrazuje příklady různé stavy, které grafické objekt může mít s popisovač, velikosti a úpravy vzhledu na místě. Velikost obslužné rutiny pro zpracování by měl být vázáno okraje okna a hraniční metriky pomocí **GetSystemMetrics** rozhraní API.  
  
|Stav|Vzhled|Podrobnosti o Visual|  
|-----------|----------------|--------------------|  
|**Nezaškrtnuté**|Výchozí|![Výchozí tlačítko stavu](../../extensibility/ux-guidelines/media/0713-10_defaultstate.png "0713 10_DefaultState")||  
|**Primární výběr**|S možností změny velikosti|![Úchyty pro změnu velikosti primární výběr](../../extensibility/ux-guidelines/media/0713-11_primaryresize.png "0713 11_PrimaryResize")|![Úchyty pro změnu velikosti primární výběr &#40;možnosti&#41;](../../extensibility/ux-guidelines/media/0713-12_primaryresizezoom.png "0713 12_PrimaryResizeZoom")|  
|**Primární výběr**|Není s možností změny velikosti|![Úchyty pro změnu velikosti primární výběr bez](../../extensibility/ux-guidelines/media/0713-13_primarynoresize.png "0713 13_PrimaryNoResize")|![Úchyty pro změnu velikosti primární výběr bez &#40;možnosti&#41;](../../extensibility/ux-guidelines/media/0713-14_primarynoresizezoom.png "0713 14_PrimaryNoResizeZoom")|  
|**Primární výběr**|Uzamčení|![Primární výběr uzamčení](../../extensibility/ux-guidelines/media/0713-15_primarylocked.png "0713 15_PrimaryLocked")|![Primární výběr uzamčení &#40;možnosti&#41;](../../extensibility/ux-guidelines/media/0713-16_primarylockedzoom.png "0713 16_PrimaryLockedZoom")|  
|**Sekundární výběr**|S možností změny velikosti|![Úchyty pro změnu velikosti sekundární výběr](../../extensibility/ux-guidelines/media/0713-17_secondaryresize.png "0713 17_SecondaryResize")|![Úchyty pro změnu velikosti sekundární výběr &#40;možnosti&#41;](../../extensibility/ux-guidelines/media/0713-18_secondaryresizezoom.png "0713 18_SecondaryResizeZoom")|  
|**Sekundární výběr**|Není s možností změny velikosti|![Úchyty pro změnu velikosti sekundární výběr bez](../../extensibility/ux-guidelines/media/0713-19_secondarynoresize.png "0713 19_SecondaryNoResize")|![Sekundární výběr bez změny velikosti &#40;možnosti&#41;](../../extensibility/ux-guidelines/media/0713-20_secondarynoresizezoom.png "0713 20_SecondaryNoResizeZoom")|  
|**Sekundární výběr**|Uzamčení|![Sekundární výběr uzamčení](../../extensibility/ux-guidelines/media/0713-21_secondarylocked.png "0713 21_SecondaryLocked")|![Sekundární výběr uzamčení &#40;možnosti&#41;](../../extensibility/ux-guidelines/media/0713-22_secondarylockedzoom.png "0713 22_SecondaryLockedZoom")|  
|**Aktivní uživatelského rozhraní**|Výchozí|![Stav uživatelského rozhraní active](../../extensibility/ux-guidelines/media/0713-23_uiactive.png "0713 23_UIActive")|![Stav uživatelského rozhraní active &#40;možnosti&#41;](../../extensibility/ux-guidelines/media/0713-24_uiactivezoom.png "0713 24_UIActiveZoom")|  
  
### <a name="view-selection-models"></a>Modely výběr zobrazení  
  
#### <a name="tree-view"></a>Zobrazení stromu  
 Zobrazí se výběr v zobrazení stromu se jednoduché zvýraznění. Pokud uživatel klikne na název uzlu nebo ikonu uzlu, bude vybrán uzlu. Trojúhelníkovou glyfů nalevo od uzlu rozbalit nebo sbalit ovládací prvek stromu ale neovlivňují výběr uživatele, s jednou výjimkou: výběr při sbalení nadřazeného uzlu po výběru na podřízeným uzlem tohoto uzlu, se přesune do nadřazené.  
  
 ![Typické stromové zobrazení v sadě Visual Studio](../../extensibility/ux-guidelines/media/0713-25_treeview.png "0713 25_TreeView")  
  
 **Typické stromové zobrazení v sadě Visual Studio**  
  
 Zobrazení stromu může podporovat vybrané souvislý a nesouvislý, i přes více úrovní ve stromové struktuře. Souvislý nebo nesouvislý více výběrů, musí být provedeny na uzly stromu viditelné. Pokud uzel sbalena, dojde ke ztrátě nesouvislý výběr a uzlu, který byl sbalené získá výběr. Tímto způsobem uživatel uvidí uzly, které ovlivní operace. Pokud jsou sbaleny uzly, stane se jasné uzlů, které může mít vliv.  
  
 Pokud je vybraná nadřazeného uzlu, operace by se měly používat na hodnotu parent, i když můžou nastat případy, kdy má smysl pro operace platí pro nadřazený a všech jeho podřízených položek. V takovém případě poskytnout další uživatelského rozhraní v průběhu operace, jako je zaškrtávací políčko nebo dialogové okno potvrzení, aby možnost "nevztahují na všechny podřízené objekty" explicitní uživatele.  
  
##### <a name="renaming"></a>Přejmenování  
 Pokud uzly ve stromu podporují přejmenování, přejmenování potřeba na místě. Operaci na místě by měl být standardní napříč všechny ovládací prvky stromů v sadě Visual Studio. Zadejte příkaz přejmenování, který se ihned aktivuje režimu úprav v místě s výběr textu pokrývající celý název uzlu připravena přijímat vstup uživatele. Pokud uzel představuje soubor, by mělo obsahovat název souboru rozšíření. Výběr zvýraznění by měla obsahovat pouze text není rozšíření a název souboru.  
  
|Vstup|Výsledek|  
|-----------|------------|  
|Enter – klávesa|Provede operaci přejmenování|  
|Klávesy ESC|Zruší operaci přejmenování|  
|Kliknutím na tlačítko mimo oblast upravit na místě|Provede operaci přejmenování|  
|vrácení zpět|Zadejte snadno zpět, chcete-li zrušit operaci přejmenování|  
  
#### <a name="selection-within-lists-and-grid-controls"></a>Výběr v seznamech a ovládací prvky mřížky  
 Klíče koncept v seznamu výběru je, že je na základě řádku, znamená to, že při výběru celý řádek je vybrán jako jednotku. Naopak mřížky můžete povolit konkrétní buněk vybrat bez ovlivnění jiných aspektů řádek. Mřížky může také obsahovat hierarchie vnořené řádků (například TreeGrid) umožňujících celý větví úrovně hierarchie k vybrané a není vybraná interakcí s nadřazenou řádky. Výběr v seznamu se zobrazí pomocí jednoduchého zvýraznění barev v celé řadě data. Zaměřuje se zobrazí ve jednopixelové desítkovém ohraničení okolo aktuálního řádku upravovat nebo buňky (řádku, pokud jsou všechny buňky jen pro čtení).  
  
> [!NOTE]
>  **Fokus** a **výběr** jsou různé koncepty. *Fokus* o tom, které uživatelského rozhraní je cílem element přijímat vstup není explicitně směrované na jiný objekt, při *výběr* odkazuje na stav objektu zahrnutí v sadě objekty, na kterých následné operace může trvat místě.  
  
 Výběr v seznamu může být souvislý, nesouvislý, nebo oblast. Když je povolené, souvislý více výběrů a nesouvislý výběr by měl být vždy podporovaný, při podporu pro výběr oblasti (pole) je volitelný. Výběr oblasti se spouští tak, že přetáhnete v mezer textu na seznamu.  
  
|Objekt|Výběr|  
|------------|---------------|  
|Seznam|Souvislý|Vždycky podporují (Pokud je povoleno více výběrů).|  
|Seznam|Nesouvislé|Vždycky podporují (Pokud je povoleno více výběrů).|  
|Seznam|Oblast|Volitelnou podporu. Inicializuje přetahování myší v mezer textu na seznamu.|  
  
 Jedním klepnutím na seznamu vyberete řádek, kde došlo k chybě a klikněte na. Pokud uživatel se stane klikněte v seznamu buňku, která podporuje úpravy v místě, je také okamžitě aktivována buňky pro úpravy na místě. Celý řádek, jinak je okamžitě vybrána a zobrazuje zvýraznění.  
  
 Přetahování v těle seznamu provádí jednu z následujících způsobů:  
  
-   Zahájí výběr oblast, pokud ji podporuje v seznamu a tlačítko myši stisknuté v prázdné znaky  
  
-   Zahájí operaci přetažením, pokud buňka seznamu nebo řádek podporuje probíhá zdroje operace přetažení  
  
-   Vybere na aktuálním řádku  
  
##### <a name="in-place-editing"></a>Úpravy na místě  
 Když je povolena úpravy v místě, existují dva základní modely: výběr řízení a vlastnost jednoduché úpravy. S ovládacím prvkem jednoduché úpravy obsahu je zvýrazněná a připravený pro uživatelský vstup také úpravy v místě je aktivována. Tam, kde se implementuje vlastnost výběr, tlačítko, které vyvolá výběr vlastnosti se zobrazí po aktivaci režimu úprav na místě a není zvýrazněná aktuální výběr. Tlačítko výběru by mělo být zarovnané vpravo v buňce. Místní úpravy příklady najdete v tématu **vlastnosti – okno** a **seznam úkolů** v sadě Visual Studio.  
  
##### <a name="keyboard-support"></a>Podpora klávesnice  
 Podpora klávesnice pro výběr v seznamech a mřížky dodržovat standardní konvence prostředí systému Windows:  
  
-   Klávesy se šipkami přejděte v seznamu výběru každý řádek buněk, jako je přesunout fokus.  
  
-   SHIFT + ŠIPKA provede souvislou ve směru klávesy se šipkami.  
  
-   CTRL + ŠIPKA následuje MEZERNÍK přepíná mezi přidávání a odebírání položek seznamu z výběru, vytváření nesouvislý výběr.  
  
-   Pro mřížky, které obsahují vnořené hierarchie šipka vpravo rozšíří nadřazeného řádku a klávesu šipka doleva sbalí jeden.  
  
-   Klávesy Tab přesouvá fokus mezi buněk na aktuálním řádku buňky se upravovat.  
  
-   Zadejte klíč k provedení příkazu výchozí položky v seznamu (často **otevřete**).  
  
-   F2 klíč aktivuje úpravy v místě pro aktuálně vybrané buňky.  
  
##  <a name="BKMK_PersistenceAndSavingSettings"></a> Trvalosti a ukládá se nastavení  
  
### <a name="overview"></a>Přehled  
 Sice obvykle zodpovědná za vlastní stavu a trvalost jednotlivých součástí softwaru v sadě Visual Studio, Visual Studio automaticky uloží nastavení v některých případech, například s okno velikosti a pozice. Následující tabulka je kombinací nastavení automaticky uloží a nastavení, které vyžadují explicitní uživatele nebo naprogramovaný tak provést akci.  
  
|Objekt|Co je potřeba uložit|Když pro uložení|Kam chcete uložit|  
|------------|------------------|------------------|-------------------|  
|Vybrat objekt (například řádek kódu)|Breakpoint – na řádek kódu<br /><br /> Zástupce uživatele přidruženého k řádku kódu|Při uložení projektu|**Možností uživatele (.suo)** soubor projektu|  
|Dialogové okno|Umístění dialogového okna, pokud byl přesunut<br /><br /> Zobrazení, které uživatel naposledy použila v dialogovém okně|Když se zavře dialogové okno<br /><br /> Při ukončení relace sady Visual Studio|V paměti<br /><br /> V registru **HKEY_Current_User**|  
|Okno|Velikost a umístění okna|Po zavření okna<br /><br /> Až se změní režim Visual Studio<br /><br /> Při ukončení relace sady Visual Studio|**Možností uživatele (.suo)** soubor projektu<br /><br /> Soubor vlastních možností pro nastavení okna|  
|Dokument|Aktuální výběr v dokumentu<br /><br /> Zobrazení dokumentu<br /><br /> Poslední několika místech uživatel navštívil|Při ukládání dokumentu|**Možností uživatele (.suo)** soubor projektu|  
|Projekt|Odkazy na soubory<br /><br /> Odkazy na adresáře na disku<br /><br /> Odkazy na ostatní software<br /><br /> Součásti<br /><br /> Stavové informace o projektu sám sebe|Při uložení projektu|Soubor projektu|  
|Řešení|Odkazy na projekty<br /><br /> Odkazy na soubory|Když je uložena na projekt nebo řešení|**Řešení (.sln)** souboru|  
|Nastavení v **nástroje > Možnosti**|Přizpůsobení klávesnice<br /><br /> Přizpůsobení panelu nástrojů<br /><br /> Barevná schémata|Když **nástroje > Možnosti** zavře dialogové okno<br /><br /> Při ukončení relace sady Visual Studio|V registru **HKEY_Current_User**|  
  
 Co uživatel provádí a když na ní dělají, určuje, zda nastavení se ukládají v paměti (během relace), které jsou uloženy na disk (v rámci relace jako nastavení registru), jako součást projekt nebo řešení soubor samostatně, v rámci **řešení Možnosti (.suo)** souboru, nebo jako vlastní nastavení souborů pouze tuto součást softwaru zná. Výše uvedené tabulce obsahuje několik události, na kterých je možné uložit nastavení. Existují však jinou dobu, ve kterých můžete chtít uložit stav:  
  
-   Když uživatel změní umístění v dialogovém okně nebo okna  
  
-   Když uživatel přenese fokus na další okno  
  
-   Když uživatel přepíná z návrhu na režim ladění  
  
-   Když se uživatel odhlásí svého účtu  
  
-   Když počítač přejde do režimu hibernace nebo vypnutí  
  
-   Když počítač nebo pevného disku se chystá naformátována a nastavit znovu  
  
### <a name="window-configurations"></a>Konfigurace oken  
 Okno konfigurace je základní prezentace vývojového prostředí – je seznam nástroj windows přítomen a způsob, ve kterém jsou uspořádány schématu. Pro systém windows spravuje integrovaného vývojového prostředí (IDE windows) je jako informace o rozvržení trvalý cena na uživatele, když uživatel spustí, IDE, rozložení okna se zobrazí, stejně jako když trvají byl ukončen Visual Studio. V souboru vlastní možnosti ve formátu XML je jako trvalý stav a pozice Windows IDE. Okna nástrojů, které jsou vytvořené pomocí balíčků načíst do rozhraní IDE zachována jeho informace o stavu v registru a může nebo nemusí být na uživatele.  
  
#### <a name="profile-specific-layouts"></a>Jednotlivé profily rozložení  
 Každý profil obsahuje nástroj rozložení oken, uspořádání pro vývojáře konkrétní osoby (Visual C++ vývojáři měli vidět **Průzkumníku řešení** na levé straně rozhraní IDE, zatímco C# vývojáři měli vidět  **Průzkumník řešení** na pravé straně). Rozložení oken jednotlivé profily se načítají, až uživatel vybere profil při spuštění. Autora balíčku měli určit rozložení okna, která je nejvhodnější pro prostředí zákazníka, zároveň budete vědět, že se změny, které uživatel provede konfiguraci okna pak natrvalo.  
  
##  <a name="BKMK_TouchInput"></a> Dotykové ovládání  
 Uživatelé stále používají vývoj produkty společnosti Microsoft na dotyková zařízení. Existují však překážky, které činit obtížné pomocí nástrojů pro vývoj na dotyková zařízení. Uživatelé se očekávají, že naše produkty a poskytuje spolehlivé a přesné touch prostředí. Účelem těchto pokynů je informovat rozhodnutí o jaké funkce dotykového ovládání, abyste zapracovali a podporovat konzistentní dotykového ovládání v sadě Visual Studio a souvisejících produktů.  
  
### <a name="levels-of-experience"></a>Úrovně prostředí  
 Následující úrovně prostředí jsou určeny k sloužit jako vodítko k pomoci týmy rozhodnout, jaké funkce dotykového ovládání nabízet podle jejich požadované úrovně investice zájem o dotykového ovládání.  
  
-   **Základní prostředí** je pro týmy, které chcete poskytnout touch možnosti proto nejsou žádné elementy end zpráv v práci.  
  
-   **Optimalizované prostředí** je pro týmy, které chcete poskytnout nejvíce touch běžné možnosti, (například ty, obvykle dostupné v internetové prohlížeče aplikace).  
  
-   **Prostředí se zvýšenými oprávněními** je pro týmy, které chcete přidat funkce takové jako gesta nebo jiné volitelné funkce, které provádět jejich aplikace touch první popisný.  
  
||Základní možnosti|Optimalizované prostředí|Zvýšené prostředí|  
|-|----------------------|--------------------------|-------------------------|  
|Umožňuje uživatelům...|Opravte kód a řešení nebo úrovni projektu čtení bez končí zpráv|Provádění úloh údržby, refactors a navigace|Pracovat v prostředí konzistentní, intuitivní a plynulá práce s jistotou|  
|Editor|Touch posouvání a výběr<br /><br /> ScrollBar touch přeskočit a stiskněte klávesu + přetažení|Roztahováním přiblížení<br /><br /> Rychlé posuvníku<br /><br /> Výběr<br /><br /> Snadné použití kontextové nabídky||  
|Hlavní panel nástrojů|Posouvání v seznamu<br /><br /> Výběr položek<br /><br /> ScrollBar touch přeskočit a stiskněte klávesu + přetažení|Snadno položky posouvání a výběr||  
|Časová okna||Změnit velikost okna<br /><br /> Rychlý přístup||  
|Dobře dokumentu||Snadné přecházení mezi otevřených souborů||  
|Gesta||Ujistěte se, že běžné gesta fungovat na všech rozhraní IDE|Na základě gesto akce<br /><br /> Podpora přetažení myší a návrhářů|  
|Další důležité informace|||Vlastní klávesnice na obrazovce|  
  
#### <a name="gestures"></a>Gesta  
 Gesta poskytují uživatelům zástupce příkazy, které mohou vyžadovat jinak složitější interakce. Viz pokyny Windows na [gesta běžné touch pro plochu aplikace](http://msdn.microsoft.com/en-us/library/windows/desktop/dd940543\(v=vs.85\).aspx)a použijte tyto pokyny pro většinu gesta, včetně jednoduchá gesta například posouvání a přibližování.