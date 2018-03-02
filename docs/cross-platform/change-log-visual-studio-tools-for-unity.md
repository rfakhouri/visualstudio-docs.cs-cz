---
title: "Změnit protokolu (Visual Studio Tools for Unity) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-unity-tools
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea490b7e-fc0d-44b1-858a-a725ce20e396
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: c408473207075f1c20935b3bbd985012230dc094
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="change-log-visual-studio-tools-for-unity"></a>Protokol změn (Visual Studio Tools for Unity)
Visual Studio Tools for Unity změnit protokolu.

## <a name="3503"></a>3.5.0.3
 Vydaná 2018-01-09

### <a name="bug-fixes"></a>Opravy chyb  

-   **Integrace:**  

    -   Opravené automatické pdb do mdb ladění symbol převodu.

## <a name="3502"></a>3.5.0.2
 Vydaná 2017-12-04

### <a name="new-features"></a>Nové funkce

-   **Integrace:**

    -   Projekty Unity se teď při přidání nebo odebrání skriptu z Unity automaticky znovu načítají v sadě Visual Studio.

-   **Ladicí program:**

    -   Přidat možnost k použití Mono ladicí program sdílí Xamarin a Visual Studio pro Mac k ladění editoru Unity.

    -   Byla přidána podpora pro soubory symbolů přenosné ladění.

### <a name="bug-fixes"></a>Opravy chyb

-   **Integrace:**

    -   Opravit potíže s instalací závislosti.

    -   Opravené Unity API nápovědy nabídky se nezobrazují.

-   **Generování projektu:**

    -   Generování projektu pevné player při práci na UWP hry s 4.6 IL2CPP/.NET back-end.

    -   Pevné navíc .dll rozšíření neoprávněně přidat k názvu souboru sestavení.

    -   Opravené využití konkrétní projektu rozhraní API úroveň kompatibility místo globální jeden.

    -   Nevynucovat příznak AllowAttachedDebuggingOfEditor Unity jako výchozí hodnota je nyní "true".

## <a name="3402"></a>3.4.0.2
 Vydaná 2017-09-19

### <a name="new-features"></a>Nové funkce

-   **Generování projektu:**

    -   Přidaná podpora pro assembly.json kompilačních jednotek.

    -   Zastavit kopírování Unity sestavení do složky projektu.

-   **Ladicí program:**

    -   Byla přidána podpora pro nastavení další příkaz s nový modul runtime Unity.

    -   Byla přidána podpora pro typ Decimal s nový modul runtime Unity.

    -   Přidaná podpora pro implicitní nebo explicitní převody.

### <a name="bug-fixes"></a>Opravy chyb

-   **Vyhodnocení:**

    -   Vytváření dlouhodobého pole s velikostí implicitní.

    -   Opravené kompilátoru vygenerované položky s místní hodnoty.

-   **Generování projektu:**

    -   Pevný odkaz na Microsoft.CSharp 4.6 úrovně rozhraní API.

## <a name="3302"></a>3.3.0.2
 Vydaná 2017-08-15

### <a name="bug-fixes"></a>Opravy chyb

-   **Generování projektu:**

    -   Pevné generování řešení sady Visual Studio Unity 5.5 a předchozí verze.

## <a name="3300"></a>3.3.0.0
 Vydaná 2017-08-14

### <a name="new-features"></a>Nové funkce

-   **Vyhodnocení:**

    -   Byla přidána podpora pro vytváření struktur s nový modul runtime Unity.

    -   Přidaná podpora minimalist pro ukazatele.

### <a name="bug-fixes"></a>Opravy chyb

-   **Vyhodnocení:**

    -   Volání metody pevné primitiv.

    -   Pole pevné vyhodnocení s typy, které jsou označené jako BeforeFieldInit.

    -   Opravené nepodporovaný volání s binárními operátory (odečíst).

    -   Opravené problémy při přidávání položek pro Visual Studio sledovat.

-   **Generování projektu:**

    -   Pevné odkazy název sestavení s mcs.rsp soubory.

    -   Opravené definuje úrovně rozhraní API.

## <a name="3200"></a>3.2.0.0
 Vydaná 2017-05-10

### <a name="new-features"></a>Nové funkce

-   **Instalační program:**

    -   Přidaná podpora pro čištění mezipaměť MEF.

### <a name="bug-fixes"></a>Opravy chyb

-   **Editor kódu:**

    -   Opravené klasifikace nebo dokončení s vlastní atributy.

    -   Pevné blikání s Unity zprávy.

## <a name="3100"></a>3.1.0.0
 Vydaná 2017-04-07

### <a name="new-features"></a>Nové funkce

-   **Ladicí program:**

    -   Přidaná podpora pro nový modul runtime Unity (s .NET 4.6 / kompatibilita C# 6).

-   **Generování projektu:**

    -   Byla přidána podpora pro profil .NET 4.6.

    -   Byla přidána podpora pro mcs.rsp soubory.

    -   Při použití Unity 5.6 vždy povolte nezabezpečený kompilace přepínače.

    -   Přidaná podpora pro generování projektu "Player" při použití Windows Store platformy a il2cpp back-end.

### <a name="bug-fixes"></a>Opravy chyb

-   **Editor kódu:**

    -   Opravené vsuvka pozice po vložení metoda s automatickým dokončováním.

-   **Generování projektu:**

    -   Po zpracování verze odebrané sestavení.

## <a name="3001"></a>3.0.0.1
 Vydaná 2017-03-07

### <a name="this-version-includes-all-new-features-and-bug-fixes-introduced-with-28x-series"></a>Tato verze obsahuje všechny nové funkce a opravy chyb zavedené 2.8.x řady.

## <a name="2820---30-preview-3"></a>2.8.2.0 - 3.0 preview 3
 Vydaná 2017-01-25

### <a name="bug-fixes"></a>Opravy chyb

-   **Generování projektu:**

    -   Pevné regrese, kde modulů plug-in projekty tam, kde je odkazováno dvakrát, nejprve jako binární knihovny DLL pak jako projekt odkazovat.

## <a name="2810---30-preview-2"></a>2.8.1.0 - 3.0 preview 2
 Vydaná 2017-01-23

### <a name="bug-fixes"></a>Opravy chyb

-   **Editor kódu:**

    -   Vyřešili selhání při spouštění deklarace atributu bez závorek dokončení.

-   **Ladicí program:**

    -   Fixed – funkce zarážky coroutines pod nový Unity kompilátoru nebo modul runtime.

    -   Přidání upozornění v případě unbindable bod přerušení (Pokud je nalezen žádný odpovídající umístění zdroje).

-   **Generování projektu:**

    -   Opravené csproj generace s lokalizovaným nebo speciální znaky.

    -   Pevné odkazy mimo prostředky, jako je Library (jako je Facebook SDK).

-   **Různé:**

    -   Přidání zkontrolujte Unity zabrání spuštění při instalaci nebo odinstalaci.

    -   Přepnout do https do cíle vzdálené dokumentace Unity.

## <a name="2800---30-preview"></a>2.8.0.0 - 3.0 preview
 Vydaná 2016-11-17

### <a name="new-features"></a>Nové funkce

-   **Obecné:**

    -   Byla přidána podpora pro Visual Studio 2017 Instalační služby.

    -   Byla přidána podpora pro Visual Studio 2017 rozšíření.

    -   Podpora přidání lokalizace.

-   **Editor kódu:**

    -   Přidaný C# IntelliSense pro Unity zprávy.

    -   Přidaný C# kódu zabarvení pro Unity zprávy.

-   **Ladicí program:**

    -   Přidání podpory pro `is`, `as`, přímé cast `default`, `new` výrazy.

    -   Byla přidána podpora pro řetězec concat výrazy.

    -   Přidaná podpora pro šestnáctkové zobrazení celočíselné hodnoty.

    -   Byla přidána podpora pro vytvoření nové proměnné dočasného (příkazů).

    -   Přidaná podpora pro implicitní převody primitivní.

    -   Když je očekávané nebo nebyl nalezen typ přidat lépe chybové zprávy.

-   **Generování projektu:**

    -   Odebrat příponu CSharp z názvy projektů.

    -   Odebrán odkaz na soubor systému široké msbuild cíle.

-   **Průvodci:**

    -   Byla přidána podpora pro Unity zprávy v jiných chování typy jako Editor nebo EditorWindow.

    -   Přepnout do Roslyn k vložení a formátování zprávy Unity.

### <a name="bug-fixes"></a>Opravy chyb

-   **Ladicí program:**

    -   Opravit chyby chybám Unity při vyhodnocování obecné typy.

    -   Opravené zpracování typů s povolenou hodnotou Null.

    -   Opravené zpracování výčty.

    -   Opravené zpracování typy vnořených členů.

    -   Opravené kolekce indexer přístup.

    -   Opravené podpora ladění iterátorů rámce s novou kompilátor jazyka C#.

-   **Generování projektu:**

    -   Opravené chyby, která zabránila kompilace, pokud je cílem Unity Web player.

    -   Opravené chyby, která zabránila kompilace při kompilování skriptu s webové kódovaný název souboru.

## <a name="2300"></a>2.3.0.0
 Vydaná 2016-07-14

### <a name="new-features"></a>Nové funkce

-   **Obecné:**

    -   Přidat možnost zakázat Unity konzoly protokoly v sadě Visual Studio seznam chyb.

    -   Přidat k povolení vlastnosti generovaného projektu má být změněn.

-   **Ladicí program:**

    -   Přidání textu, XML, HTML a JSON řetězec vizualizérech.

-   **Průvodci:**

    -   Přidat chybí MonoBehaviors.

### <a name="bug-fixes"></a>Opravy chyb

-   **Obecné:**

    -   Vyřešili konflikt s ReSharper, která zabránila ovládacích prvků v sadě Visual Studio nastavení zobrazení.

    -   Vyřešili konflikt s Xamarinem, která zabránila v některých případech ladění.

-   **Ladicí program:**

    -   Byl opraven problém, která způsobila, že chcete ukotvit při ladění Visual Studio.

    -   Oprava problému s zarážky funkce v sadě Visual Studio 2015.

    -   Vyřešili několik výraz vyhodnocení problémů.

## <a name="2200"></a>2.2.0.0
 Vydaná 2016-02-04

### <a name="new-features"></a>Nové funkce

-   **Průvodci:**

    -   Přidání inteligentní vyhledávání v **MonoBehavior implementace** průvodce.

    -   Kontext učiněna průvodců vědět; například NetworkBehavior zprávy jsou k dispozici pouze při práci se službou NetworkBehavior.

    -   Byla přidána podpora pro NetworkBehavior zprávy v průvodci.

-   **UI:**

    -   Přidat konfiguraci zobrazení zprávy MonoBehavior možnost.

    -   Odebrat stránky vlastností sady Visual Studio, které nejsou požadovanou do projektů Unity.

### <a name="bug-fixes"></a>Opravy chyb

-   **Generování projektu:**

    -   Pevné odkazy na UnityEngine a UnityEditor na Unity 4.6.

    -   Opravené generování souborů projektu, když Unity běží na OSX.

    -   Opravené zpracování projektu názvy obsahující znaky hashmark (#).

    -   Vygenerovaný projekty omezena na 4 C#.

-   **Ladicí program:**

    -   Oprava problému s vyhodnocení výrazu při ladění uvnitř Unity coroutine.

    -   Byl opraven problém, která způsobila, že chcete ukotvit při ladění Visual Studio.

-   **UI:**

    -   Pevné nekompatibility s [karty Studio](https://tabsstudio.com/) rozšíření sady Visual Studio.

-   **Instalační program:**

    -   Tím, že vytvoříte položky registru HKLM podporují instalaci celého systému VSTU (instalace pro všechny uživatele).

    -   Opravené problémy s odinstalace VSTU po instalaci stejnou verzi nástroje VSTU několik různých verzí sady Visual Studio. Například když VSTU **2015** 2.1.0.0 a VSTU **2013** 2.1.0.0 byly oba nainstalovány.

## <a name="2100"></a>2.1.0.0
 Vydaná 2015-09-08

### <a name="new-features"></a>Nové funkce

-   Podpora pro Unity 5.2

### <a name="bug-fixes"></a>Opravy chyb

-   Zobrazení položek nabídky v Unity < 4.2

-   Když Visual Studio zamkne soubory XML intellisense, se už zobrazí chybová zpráva.

-   Zpracování <\<při Změnit >> podmíněné zarážky při podmíněného argument není logická hodnota.

-   Pevné odkazy na sestavení UnityEngine a UnityEditor pro aplikace Windows Store.

-   Pevné chyby při krokování v ladicím programu: nelze krok obecné výjimce.

-   Pevný počet vstupů do zarážky ve Visual Studiu 2015.

## <a name="2000"></a>2.0.0.0
 Vydaná 2015-07-20

### <a name="bug-fixes"></a>Opravy chyb

-   **Integrace Unity:**

    -   Pevné převodu symboly ladění vytvořené pomocí sady Visual Studio 2015, při importu knihovny DLL a jeho symboly ladění (PDB).

    -   Vždy Vygenerujte soubory MDB při importu knihovny DLL a jeho symboly ladění (PDB), s výjimkou případů, kdy se soubor MDB také poskytuje.

    -   Opravené znečištění adresáře projektu Unity s adresářem obj.

    -   Pevné odkazy na System.Xml.Link a System.Runtime.Serialization generování.

    -   Přidaná podpora pro více odběrateli na generování souboru projektu rozhraní API moduly přiřazení.

    -   I když jeden ze souborů má být vygenerován uzamčeno generování souboru vždy dokončení projektu.

    -   Přidání podpory pro * zástupné znaky v rozšíření filtrovat při zadávání soubory mají být zahrnuty do projektu C#.

-   **Integrace aplikace Visual Studio:**

    -   Opravit potíže s kompatibilitou s nástroji Power produktivitu.

    -   Pevné generování MonoBehaviors kolem deklarace události a delegáti.

-   **Ladicí program:**

    -   Pevné potenciální zablokování při ladění.

    -   Byl opraven problém s místní hodnoty by níž se má zobrazit v určitých rámce zásobníku.

    -   Pevné zkontrolujete prázdné pole.

## <a name="1990---20-preview-2"></a>1.9.9.0 - 2.0 preview 2
 Vydaná 2015-04-02

### <a name="new-features"></a>Nové funkce

-   **Unity Project Exploreru:**

    -   Při přejmenování souboru v prohlížeči projektu Unity automaticky přejmenovat – třída (viz **možnosti** dialogové okno).

    -   Automaticky vyberte nově vytvořenou skripty v prohlížeči projektu Unity.

    -   Sledování aktivních skriptů v prohlížeči projektu Unity (viz **možnosti** dialogové okno).

    -   Dual synchronizovat Průzkumníku řešení Visual Studio (viz **možnosti** dialogové okno).

    -   Přijmout sady Visual Studio ikony v prohlížeči projektu Unity.

-   **Ladicí program:**

    -   Vyberte cíl aktivní ladicí ze seznamu cíle ladění uloženém nebo nedávno použité (viz **možnosti** dialogové okno).

    -   Vytvoření funkce zarážky na MonoBehavior metody a použít je několik tříd MonoBehavior.

    -   V ladicím programu podporovat Zkontrolujte ID objektu.

    -   Podpora počet v ladicím programu volání zarážek.

    -   Podpora přerušení na výjimka v ladicím programu (experimentální. V tématu **možnosti** dialogové okno).

    -   Při vyhodnocování výrazy v ladicím programu, podporují vytvoření objekty a pole.

    -   Podpora porovnání null při vyhodnocení výrazy v ladicím programu.

    -   Zastaralé členy v ladicího programu Sledování vyfiltrujte.

-   **Instalační program:**

    -   Optimalizované Visual Studio Tools for Unity rozšíření registrace.

    -   Nainstalujte Visual Studio Tools pro Unity balíček pro Unity 5.

-   **Dokumentace:** zvýšit výkon při generování dokumentace.

-   **Průvodci:** podpora nových metod MonoBehavior Unity 4.6 a Unity 5.

-   **Unity:** unsafe příznaky vyhledávání a vlastní definuje v soubory .rsp během generování souboru projektu.

-   **Uživatelské rozhraní:** přidat Visual Studio Tools for Unity **možnosti** dialogové okno v sadě Visual Studio.

### <a name="bug-fixes"></a>Opravy chyb

-   **Unity Project Exploreru:**

    -   Po soubory jsou přesunut nebo přejmenován ze Průzkumníku řešení Visual Studio, obnovte Prohlížeč projektu Unity.

    -   Zachovejte výběr při přejmenování souborů v prohlížeči projektu Unity.

    -   Zakázat automatické rozbalení a sbalení při soubory jsou dvojité kliknutí na v prohlížeči projektu Unity.

    -   Zajistěte, aby nově vybrané soubory jsou viditelné v prohlížeči projektu Unity.

-   **Ladicí program:**

    -   Zabránit možného freeze – při vyhodnocování výrazy v ladicím programu sady Visual Studio.

    -   Ujistěte se, že volání metod dojít ve správné doméně v ladicím programu.

-   **Unity:**

    -   Opravte umístění UnityVS.OpenFile s Unity 5.

    -   Opravte umístění pdb2mdb s Unity 5.

    -   Zabránit možnou výjimkou během generování souboru projektu.

    -   Při spuštění Unity na OSX, zabránit možné zablokování.

    -   Zpracování vnitřní výjimky.

    -   Protokoly konzoly Unity poslat seznam chyb VS.

-   **Dokumentace:** opravte generování dokumentace pro novou dokumentaci unity.

-   **Projekt:** přesunout a přejmenujte soubory .meta Unity v případě potřeby i ve složkách.

-   **Průvodci:** opravte pořadí parametrů metody MonoBehavior při generování kódu.

-   **Uživatelské rozhraní:** motivy podpora Visual Studio pro místní nabídky a ikony.

## <a name="1980---20-preview"></a>1.9.8.0 - 2.0 preview
 Vydaná 2014-11-12

### <a name="new-features"></a>Nové funkce

-   Podpora pro Visual Studio 2015.

-   Kód zabarvení pro Unity shadery ve Visual Studiu 2015.

-   Lepší vizualizaci hodnoty při ladění:

    -   Lepší vizualizaci ArrayLists, seznamy, zatřiďovacích tabulkách a slovník.

    -   Zobrazit členy jiné veřejné a statické členy jako kategorie v místní zobrazení a sledovat.

    -   Vylepšené zobrazení na Unity SerializedProperty pouze vyhodnotit pole hodnota platná pro vlastnost.

    -   DebuggerDisplayAttribute podpora třídy a struktury.

    -   Debuggertypeproxyattribute – podpora.

-   Ujistěte se, vkládání MonoBehaviour metody pomocí našich průvodců dodržovat konvence kódování uživatele.

-   V projektech UnityVS generované implementovat podporu pro kompilaci čas textové šablony.

-   Implementovat podporu pro ResX prostředky v projektech UnityVS vygenerovat.

-   Podpora otevírání shadery v sadě Visual Studio z Unity.

### <a name="bug-fixes"></a>Opravy chyb

-   Vyčistit sockets před počínaje hra Unity po připojit a Play byla spuštěna v sadě Visual Studio. To při používání připojit a Play opravuje některé problémy s stabilitu připojení mezi Unity a VS.

-   Vyhněte se volání metody v Unity je skriptovací stroj ladicího programu rozhraní, které jsou náchylné k zmrazení Unity. To opravy zablokování Unity při připojení ladicího programu.

-   Opravte zobrazení z callstacks, když jsou k dispozici žádné symboly.

-   Pokud ale nemáme pro Neregistrovat zpětné volání protokolu.

## <a name="1920"></a>1.9.2.0
 Vydaná 2014-10-09

### <a name="new-features"></a>Nové funkce

-   Zlepšení detekce přehrávače Unity.

-   Pokud používáte naše otevírající soubor, ujistěte se, Unity předat číslo řádku, jakož i název souboru.

-   Výchozí v online dokumentaci Unity, pokud neexistuje žádná místní dokumentace.

### <a name="bug-fixes"></a>Opravy chyb

-   Opravte potenciální havárií Unity při stiskne boru přerušení po domény znovu načíst.

-   Opravte výjimky uvedené v konzole Unity při zavření naše konfigurace nebo o systému windows, doména znovu načíst.

-   Opravte detekce 64bitový Unity spuštěn místně.

-   Opravte filtrování MonoBehaviours za verzi Unity v průvodci.

-   Opravte chyby, kde byly všechny prostředky zahrnuté v souborech projektu, pokud filtr rozšíření byla prázdná.

## <a name="1910"></a>1.9.1.0
 Vydaná 2014-09-22

### <a name="new-features"></a>Nové funkce

-   Optimalizujte zarážek vazby do zdrojového umístění.

-   Podpora pro přetížené metody při vyhodnocení výrazu ladicího programu.

-   Podpora pro primitiva zabalení a typy hodnot při vyhodnocení výrazu ladicího programu.

-   Podpora při ladění anonymní metody znovu vytvořit místní proměnné prostředí C#.

-   Odstranění a přejmenování souborů .meta při odstranění nebo přejmenování souborů ze sady Visual Studio.

### <a name="bug-fixes"></a>Opravy chyb

-   Opravte zpracování sady Visual Studio motivů. Dříve, může zobrazit dialogová okna na černé motivy prázdný (připojit problémy [#932637](https://connect.microsoft.com/VisualStudio/feedbackdetail/view/932637/) a [#936439](https://connect.microsoft.com/VisualStudio/feedbackdetail/view/936439/)).

-   Oprava Unity zmrazení při připojování ladicí program, když je rekompilace Unity (připojit problémy [#947119](https://connect.microsoft.com/VisualStudio/feedbackdetail/view/947119/) a [#969211](https://connect.microsoft.com/VisualStudio/feedbackdetail/view/969211/)).

-   Opravte zarážky při ladění vzdáleného editory nebo přehrávače zkompilovány v jiném systému.

-   Opravte možné havárií Visual Studio, když je dosaženo zarážky.

-   Oprava zarážky vazby předejdete zarážky zobrazuje jako odpojeno.

-   Opravte zpracování obor proměnné v ladicím programu, aby se zabránilo za provozu proměnné, které se zobrazují mimo rozsah.

-   Při vyhodnocení výrazu ladicího programu opravte vyhledávání statické členy (připojit problém [#953379](https://connect.microsoft.com/VisualStudio/feedbackdetail/view/953379/)).

-   Opravte zobrazení typů při vyhodnocení výrazu ladicího programu pro zobrazení statických polí a vlastností.

-   Opravte generování řešení, pokud názvy projektů Unity obsahuje speciální znaky, Visual Studio zakazuje (připojit problém #948666).

-   Opravte Visual Studio Tools Unity balíček, který chcete okamžitě zastavit odesílání událostí konzole po nezaškrtnuté (připojit problém #933357) možnost.

-   Opravte detekce odkazy na správně obnovit odkazy na nových rozhraní API jako UnityEngine.UI v projektech UnityVS vygenerovat.

-   Opravte instalační program vyžadovat, že Visual Studio je uzavřena před instalací, aby se zabránilo poškozená instalace.

-   Opravte instalační program nainstalovat jako součást správné samostatné, sdílena mezi všechny verze VSTU Unity referenční sestavení.

-   Opravte otevírání skripty v 64bitová verze verzích Unity s VSTU.

## <a name="1900"></a>1.9.0.0
 Vydaná 2014-07-29

### <a name="new-features"></a>Nové funkce

-   V okně připojit ladicí program Unity přidáte schopnost zadejte vlastní IP a portu k ladění.

-   Přidejte konfigurační možnost pro nastavení Unity ke spuštění na pozadí, nebo ne.

-   Přidejte konfigurační možnost pro generování soubory řešení a projektu nebo pouze soubory projektu.

-   Spuštění cílového: připojit Unity nebo připojit Unity a Play.

-   Zobrazení vícerozměrných polí v ladicím programu.

-   Zpracujte nové Unity Player ladění porty.

-   Zpracování odkazy na nové sestavení Unity stejně jako na Unity 4.6 grafickým uživatelským rozhraním sestavení.

-   Deconstructs uzavření pro správné zobrazení místní proměnné při ladění.

-   Deconstructs generovaného iterátory proměnné do argumenty při ladění.

-   Zachování stavu Unity Project Exploreru po znovu načíst projekt.

-   Přidejte příkaz, který chcete synchronizovat Project Exploreru Unity s aktuálním dokumentu.

### <a name="bug-fixes"></a>Opravy chyb

-   Opravte podmíněné zarážky, jejichž podmínky jsou nastavené před zahájením ladicího programu.

-   Opravte odkazy na UnityEngine, aby se zabránilo upozornění.

-   Opravte analýzy verze pro Unity beta.

-   Vyřešte problém, kde proměnné nezobrazilo v okně místní proměnné při stiskne zarážku nebo krokování s.

-   Opravte proměnné popisů tlačítek v sadě Visual Studio 2013.

-   Opravte generování dokumentace technologie IntelliSense pro Unity 4.5.

-   Opravte Unity nebo Visual Studio komunikace po domény znovu načíst (play/stop v Unity).

-   Opravte zpracování částí sady Visual Studio motivů.

> [!IMPORTANT]
>  C# se převládá jazyk v ekosystému Unity - nové ukázkové prostředky jsou v jazyce C#, použije výchozí Unity dokumentace jazyka C# – jsme odebrali naše základní podpora UnityScript a poč lepší zaměřit se na uživatelské prostředí C#. V důsledku toho VSTU řešení jsou teď C# pouze a je mnohem rychlejší načíst.

## <a name="1820"></a>1.8.2.0
 Vydaná 2014-01-07

### <a name="new-features"></a>Nové funkce

-   Obejít problém v síťové vrstvy pro Unity skriptovací stroj na Mavericks pro vzdálené zjišťování editory.

-   Zpracujte nové porty ke zjištění vzdáleného přehrávače Unity.

-   Odkaz sestavení UnityEngine konkrétní na aktuální vytvořit cíl.

-   Přidáte nastavení filtru soubory pro zahrnutí do vygenerované projekty.

-   Přidejte nastavení zakázat odesílání protokoly konzoly k sadě Visual Studio seznam chyb. To je užitečné, pokud používáte PlayMaker nebo konzoly Pro jako může být pouze jeden zpětné volání registrací v Unity přijímat protokoly konzoly.

-   Přidáte nastavení pro zakažte generování mdb ladicími symboly. To je užitečné, pokud jste mdb generování sami.

### <a name="bug-fixes"></a>Opravy chyb

-   Opravit to regrese při soubory otevřít v sadě VS z Unity > = 4.2 by dojít ke ztrátě IntelliSense.

-   Opravte naše VS dialogová okna pro zpracování vlastní motivy.

-   Opravte zavření v kontextové nabídce UPE.

-   Zabránit havárie v Unity generování konkrétní verze sestavení Pokud synchronizován.

## <a name="1810"></a>1.8.1.0
 Vydané 11 – 21 2013

### <a name="new-features"></a>Nové funkce

-   Upraví průvodců MonoBehaviour s rozhraními API 4.3 Unity.

-   Průvodci MonoBehaviour jsou filtrování Unity rozhraní API v závislosti na verzi, kterou používáte.

-   K projektům přidat odkaz na System.Xml.Linq pro Unity > 4.1.

-   Prettify naše volání Debug.Log tak, aby neobsahoval začátku stacktrace ve zprávě.

### <a name="bug-fixes"></a>Opravy chyb

-   Opravit chyby, kde by jsme konfliktu s výchozí zpracování souborů JavaScript v sadě Visual Studio.

-   Pevné bílé pixelů zobrazovaných v sadě VS skutečných této doby.

-   Opravené odstranění UnityVS.VersionSpecific sestavení, pokud je určen jen pro čtení pomocí SCM.

-   Při vytváření sockets v balíčku UnityVS pevné výjimky.

-   Při načítání uložené bitové kopie ze sestavení sady Visual Studio, pevné havárie v sadě Visual Studio.

-   Pevné chyby při generování UnityVS.VersionSpecific pro zdroj buildů Unity.

-   Při otevírání soket v balíčku Unity, pevné možné zablokování.

-   Vyřešilo se zpracování Unity projektu s pomlčkou (-) v názvu.

-   Otevírání skripty vyřešili z Unity není zaměnit pořadí ALT + TAB pro Unity 4.2 a vyšší.

## <a name="1800"></a>1.8.0.0
 Vydaná 2013-09-24

### <a name="new-features"></a>Nové funkce

-   Rychlost připojení výrazně Vylepšená ladicí program.

-   Automaticky zpracujte navigace k souboru a řádku pro Unity 4.2 a vyšší.

-   Podmíněné zarážky.

-   Generátor souborů projektu teď zpracovává šablon T4.

-   Aktualizujte MonBehavior průvodců pomocí nových rozhraní API.

-   Dokumentace IntelliSense v jazyce C# pro typy Unity.

-   Vyhodnocení aritmetické a logických výrazů.

-   Lepší zjišťování vzdálené editory pro vzdálené ladění preview.

### <a name="bug-fixes"></a>Opravy chyb

-   Pevné chyby kde jsme by úniku vlákna v sadě VS po odpojení ladicího programu.

-   Pevné bílé pixelů, které jsou uvedeny v sadě VS.

-   Vyřešilo se zpracování kliknutí na ikonu stavu panelu.

-   Dlouhodobý generování odkazů se sestavení ve složkách modulů plug-in.

-   Opravené vytváření soketů z balíčku UnityVS v případě výjimky.

-   Detekce nové verze UnityVS vyřešený.

-   Pevné řádku správce licencí, pokud vypršela platnost licence.

-   Opravit chyby, která může vykreslit seznamu proces prázdný v ladicím programu připojit k procesu okno VS.

-   Opravené změna hodnoty logických výrazů v místní zobrazení.

## <a name="1220"></a>1.2.2.0
 Vydaná 2013-07-09

### <a name="bug-fixes"></a>Opravy chyb

-   Zpracování plně kvalifikované názvy v vyhodnocovací filtr výrazů.

-   Kde Unity skriptovací stroj je odeslání nám nesprávné stackframe dat pevné zablokování, související s výjimek.

-   Pevné procesu sestavení pro Web cíle.

-   Opravit chybu, která může nastat, pokud byla spuštěna sada Visual Studio a který byl odstraněný soubor v seznamu souborů, které se otevře při spuštění.

-   Opravené UnityVS.OpenFile zpracovat soubory bez skriptu, jako je kompilovat, shadery.

-   Jsme teď referenční Boo.Lang a UnityScript.Lang ze všech C# projektů.

-   Opravené generování odkazů v projektech, pokud projekt obsahuje speciální znaky.

-   Alternativní řešení VS problém, kde volání metod k uvolnění projekty by aktivovat více MessageBox výjimky NullReferenceException.

-   Opravené zpracování Unity 4.2 Beta sestavení.

## <a name="1210"></a>1.2.1.0
 Vydaná 2013-04-09

### <a name="bug-fixes"></a>Opravy chyb

-   Pevné místní nasazení Unity sestavení pro doplňování kódu, pokud dojde k chybě vstupně-výstupní operace (jako jsou například soubory jen pro čtení, nebo soubory uzamčený Visual Studio).

-   Opravit to regrese, kde otevření skriptu z Unity nebude zaměřit soubor pokud již byl otevřen v sadě Visual Studio.

-   Vyřešený problém výkonu nové zpracování výjimky.

-   Opravené vazba zarážky v některé externí knihovny DLL.

## <a name="1200"></a>1.2.0.0
 Vydaná 2013-03-25

### <a name="new-features"></a>Nové funkce

-   Rychlost připojení výrazně Vylepšená ladicí program.

-   Optimalizované Project Exploreru Unity pro větší projekty.

-   Nastavení sady Visual Studio pro přerušení (nebo ne) respektovat zpracovat a neošetřené výjimky.

-   Respektovat nastavení sady Visual Studio volat ToString lokální proměnné.

-   Přidat nové nabídky Ladění -> Unity připojit ladicí program, který můžete použít k ladění přehrávače Unity.

-   Zachovejte vlastní projekty, které jsou přidány k řešení UnityVS při generování souboru řešení.

-   Přidat nové klávesové zkratky CTRL + ALT + M -> CTRL + H zobrazíte Unity dokumentace pro funkce Unity nebo člen na pozici pomocí kurzoru.

-   Při kompilování ze sady Visual Studio, vezměte v úvahu soubory odezvy kompilátoru (konfigurace).

-   Deconstruct kompilátoru generované typy zobrazíte proměnné při ladění generátor metody.

-   Zjednodušení vzdálené ladění odebráním potřeba nakonfigurovat sdílenou složku a Unity. Teď právě musíte mít přístup k projektu Unity ze systému Windows.

-   Vlastní profil Unity nainstalujte jako standardní profil cílového rozhraní .net. To opraví všechny falešně pozitivních zjištění, které může zobrazit ReSharper.

-   Práce mimo Unity, skriptování modul chyb, tak nebudou porušovat ladicí program na jiný správně zaregistrován vláken.

-   Přepracování otevírající soubor tak, aby se zabránilo časování v sadě VS, kde se vydával za moct otevřít soubory, při selhání na soubor otevřený.

-   UnityVS je nyní požádá o aktualizaci sestavení při VS je sestavení projektu a už není v souboru uložte.

### <a name="bug-fixes"></a>Opravy chyb

-   Pevné naše vlastní profil .net

-   Pevná integrace motivů, to opravuje naše potíže s VS 2012 tmavým motivem.

-   Opravené rychlé chování zástupce v VS 2012.

-   Pevná taktování problém, který může nastat při ladění a jiný hlavní vlákno by dosáhl zarážky.

-   Opravené UnityScript a poč dokončení aliasy typu, jako je například int.

-   Opravené výjimky při zápisu nového UnityScript nebo poč řetězce.

-   Opravené výjimky v nabídkách Unity při řešení nebyla načtena.

-   Opravené chyby UVS 48: zadáním double uvozovky někdy vytvořit chyba a rozdělit všechny funkce (doplňování kódu, zvýraznění syntaxe atd).

-   Opravené chyby UVS 46: Duplicitní souboru otevřenou skriptu (UnityScript), když kliknete na seznamu Visual Studio chyby.

-   Opravené chyby UVS 42: Unity připojení logo ve stavovém řádku nemůže pracovat s událostí myši v VS 2012.

-   Opravené chyby UVS 44: kombinace kláves CTRL + SHIFT + Q není k dispozici v VS 2012 pro rychlé MonoBehaviours.

-   Opravené chyby UVS-40: Pokud je v VS2012 "tmavý" motiv neaktivní okno se nečitelná vybrané položky v prohlížeči projektu Unity.

-   Opravené chyby UVS 39: tokenizaci problém uvozené řetězce.

-   Opravené chyby UVS 35: vyvolání ToString na objekty při kontrole proměnné.

-   Opravené chyby UVS 27: nekonzistence okno Goto Symbol s "tmavý" motiv VS2012.

-   Opravené chyby UVS 11: místní hodnoty v coroutines.

## <a name="1100---beta-release"></a>1.1.0.0 - beta verze
 Vydaná 2014-10-09

## <a name="10130"></a>1.0.13.0
 Vydaná 2013-01-21

### <a name="bug-fixes"></a>Opravy chyb

-   Pevné Zamknutí sady Visual Studio, který může nastat, pokud cíl ladění odesílá události neplatný vlákno. Které by obvykle mohlo dojít při ladění vzdáleného Unity na OSX.

-   Pevné Zamknutí sady Visual Studio, který může nastat, pokud dojde k výjimce ladicího programu.

-   Pevné naše MonoBehavior Pomocníci po MonoBehavior C# v oboru názvů.

-   Popisy tlačítek pevné ladicí program pro UnityScript v sadě Visual Studio 2012.

-   Pevné generování projektu, kdy jsou pouze konstanty ladění se změnil z Unity.

-   Opravené klávesnice navigace v prohlížeči projektu Unity.

-   Opravené UnityScript zabarvení pro uvozovacími znaky řetězce.

-   Pevné naše otevírající soubor tak snadno uhodnout lepší název projektu při použití mimo Unity. Které je potřeba, pokud uživatel používá třetí otevírající soubor část v Unity Delegující na UnityVS.

-   Opravené zpracování dlouho zpráv odeslaných z Unity UnityVS. Před dlouhou zprávy mohlo způsobit chybu naše zasílání zpráv součástí UnityVS. V důsledku toho někdy UnityVS nebude otevřete soubor z Unity.

## <a name="10120"></a>1.0.12.0
 Vydaná 2013-01-03

### <a name="bug-fixes"></a>Opravy chyb

-   Opravené Zamknutí sady Visual Studio, může dojít v případě sady Visual Studio odstraňoval zarážky.

-   Opravit chyby, kde některé by být zarážky po Unity překompilovat herní skripty.

-   Pevné ladicí program na správně upozornit Visual Studio, pokud nevázaný zarážky.

-   Vyřešený problém registrace, které by mohlo ohrozit ladicího programu sady Visual Studio k ladění nativního programy.

-   Pevné výjimku, která může dojít při vyhodnocování UnityScript a rezervace výrazy.

-   Opravit to regrese, kde by změna úrovně rozhraní API .net v Unity aktivovat aktualizaci souborů projektu.

-   Pevné chybě rozhraní API, kde nelze uživatelského kódu účastnit obslužná rutina zpětného volání protokolu.

## <a name="10110"></a>1.0.11.0
 Vydaná 2012-11-28

### <a name="new-features"></a>Nové funkce

-   Oficiální podporu Unity 4.

-   Manipulace s skriptů z Project Exploreru Unity.

-   Integrace v sadě Visual Studio přejděte do okna.

-   Analýza informací zprávu konzoly, tak, aby kliknutím na položku v seznamu chyb můžete přejít na první stackframe se symboly.

-   Přidat [rozhraní API](../cross-platform/customize-project-files-created-by-vstu.md) aby mohl uživatel účastnit generování projektu.

-   Přidat [rozhraní API](../cross-platform/share-the-unity-log-callback-with-vstu.md) aby mohl uživatel účastnit LogCallback.

### <a name="bug-fixes"></a>Opravy chyb

-   Opravené regrese na pozadí Project Exploreru Unity v sadě Visual Studio 2012.

-   Generování pevné projektu pro uživatele úplné profilu .net.

-   Generování pevné projektu pro uživatele webové cíle.

-   Generování pevné projektu zahrnout ladění, trasování kompilace symboly jako Unity nemá.

-   Opravené havárie, při použití speciálních znaků v okně naše Goto Symbol.

-   Opravit chyby, pokud nelze vložíme naše ikony v sadě Visual Studio stavový řádek.

## <a name="10100"></a>1.0.10.0
 Vydaná 2012-10-09

### <a name="bug-fixes"></a>Opravy chyb

-   Pevné pozadí Project Exploreru Unity v sadě Visual Studio 2010.

-   Pevné zablokování Visual Studio, který může nastat, pokud UnityVS se pokusil připojit ladicí program pro Unity, jehož rozhraní ladicího programu dříve došlo k chybě.

-   Pevné zablokování Visual Studio, který může dojít v případě, že byl nastavený bod přerušení a načtěte AppDomain by tomu bylo.

-   Opravit, jak jsou načítány sestavení z Unity chcete zabránit zamykání souborů a matou procesu sestavení Unity.

## <a name="1090"></a>1.0.9.0
 Vydaná 2012-10-03

### <a name="bug-fixes"></a>Opravy chyb

-   Když projekt Unity zahrnuje skutečné prostředky JavaScript generování pevné projektu.

-   Opravené chyby zpracování při vyhodnocení výrazu.

-   Opravit, nastavení nové hodnoty pro pole typů hodnot.

-   Opravené možné vedlejší efekty při ukazatele myši na výrazy z editoru kódu.

-   Opravit, jak jsou typy prohledávány v načíst sestavení pro vyhodnocení výrazu.

-   Opravené chyby UVS – 21: vyhodnocení přiřazení na objekty Unity nemá žádný vliv.

-   Opravené chyby UVS – 21: neplatný ukazatel při vyhodnocování volání metody Unity matematické API.

## <a name="1080"></a>1.0.8.0
 Vydaná 2012-09-26

### <a name="bug-fixes"></a>Opravy chyb

-   Opravené způsob, jak naše skriptu otevírající získat cestu k projekt, který má být Opravdu to je možné otevřít v sadě Visual Studio a skripty.

-   Opravené chyby se zarážkami vytvořit relaci ladění byl spuštěn, který by mohl způsobit zamčení sady Visual Studio.

-   Opravit, jak je UnityVS zaregistrovaná na Visual Studio 2010.

## <a name="1070"></a>1.0.7.0
 Vydaná 2012-09-14

### <a name="new-features"></a>Nové funkce

-   Podpora Visual Studio 2012.

### <a name="bug-fixes"></a>Opravy chyb

-   Opravené generování souborů projektu editoru a moduly plug-in tak, aby odpovídaly chování pro Unity.

-   Pevné překlad PDB symbolů Unity 4.

> [!IMPORTANT]
>  Kvůli podpoře Visual Studio 2012 jsme museli přejmenování několik souborů a některé další pohyb. UnityVS balíček, který chcete importovat Unity teď jmenuje UnityVS 2010 nebo UnityVS 2012, v uvedeném pořadí Visual Studio 2010 a Visual Studio 2012. Tato verze také vyžaduje, aby se soubory projektu UnityVS obnovovaly.

## <a name="1060---internal-build"></a>1.0.6.0 - interní sestavení
 Vydaná 2012-09-12

## <a name="1050"></a>1.0.5.0
 Vydaná 2012-09-10

### <a name="bug-fixes"></a>Opravy chyb

-   Opravené generování souborů projektu při skripty nebo shadery měl znakem neplatný kód xml.

-   Opravené zjišťování instancí Unity při Unity byl připojen k serveru Asset. Tento stav aktivován selhání otevírat soubory z Unity a automatické připojení ladicího programu sady Visual Studio.

## <a name="1040"></a>1.0.4.0
 Vydaná 2012-09-05

### <a name="new-features"></a>Nové funkce

-   Automatický převod ladicími symboly v Unity.

     Pokud máte ve složce Asset o sestavení .dll .NET s jeho přidružené pdb, jednoduše znovu importujte sestavení a UnityVS převede PDB do souboru symboly ladění rozumí skriptovací stroj pro Unity, a budete moci na krok do vaší sestavení .NET z UnityVS.

### <a name="bug-fixes"></a>Opravy chyb

-   Pevné UnityVS havárie, při ladění způsobené výjimky vyvolané metody nebo vlastnosti uvnitř Unity.

## <a name="1030"></a>1.0.3.0
 Vydaná 2012-09-04

### <a name="new-features"></a>Nové funkce

-   Nová možnost konfigurace zakázat použití UnityVS otevírat soubory z Unity.

### <a name="bug-fixes"></a>Opravy chyb

-   Opravené generace odkazy na UnityEditor pro projekty jiný editor.

-   Opravené definice symbolu UNITY_EDITOR pro projekty jiný editor.

-   Opravené náhodných VS chyby způsobené naše vlastní stavový řádek.

## <a name="1020"></a>1.0.2.0
 Vydaná 2012-08-30

### <a name="bug-fixes"></a>Opravy chyb

-   Opravené konflikt s ladicím programem PythonTools.

-   Pevné odkazy na Mono.Cecil.

-   Opravené chyby v tom, jak skriptování sestavení byly získány ze Unity s b7 Unity 4.

## <a name="1010"></a>1.0.1.0
 Vydaná 2012-08-28

### <a name="new-features"></a>Nové funkce

-   Zobrazte náhled podporu Unity 4.0 Beta.

### <a name="bug-fixes"></a>Opravy chyb

-   Pevné kontroly vlastností vyvolávání výjimek.

-   Pevné sestupném do základní objektů při kontrole objekty.

-   Opravené prázdné rozevíracího seznamu pro kurzor v Průvodci MonoBehavior.

-   Opravené dokončení pro knihovnu dll ve složce Asset UnityScript a poč.

## <a name="1000---initial-release"></a>1.0.0.0 – počáteční verze
 Vydaná 2012-08-22
