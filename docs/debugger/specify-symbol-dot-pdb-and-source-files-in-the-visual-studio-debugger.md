---
title: Zadejte symbolu (.pdb) a zdrojových souborů v ladicím programu | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 04/05/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Debugger.Native
- VS.ToolsOptionsPages.Debugger.Symbols
- vs.debug.options.Native
- vs.debug.nosymbols
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- source code
- .dbg files
- source code, managing
- symbols, managing
- .pdb files
- dbg files
- pdb files
- debugger
ms.assetid: 1105e169-5272-4e7c-b3e7-cda1b7798a6b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7e2549cfe71ef05d611251bbc8a017bd4891df3e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="specify-symbol-pdb-and-source-files-in-the-visual-studio-debugger"></a>Zadejte symbolu (.pdb) a zdrojových souborů v ladicím programu sady Visual Studio
Soubor databáze (.pdb) programu, také nazývaný soubor symbol, mapuje identifikátorů, které vytvoříte ve zdrojovém kódu pro tříd, metod a jiný kód na identifikátory, které se používají v kompilovaném spustitelné soubory projektu. Soubor PDB také mapuje příkazy ve zdrojovém kódu k provozním pokynům ve spustitelných souborech. Ladicí program používá tyto informace k určení dvě důležité informace:

* Název souboru a řádku číslo zdrojového mají být zobrazeny v prostředí Visual Studio IDE
* Umístění ve spustitelném souboru kdykoli zastavit při nastavení zarážky

Soubor symbolů obsahuje také původní umístění zdrojových souborů, případně umístění zdrojového serveru, ze kterého lze načíst zdrojové soubory.
  
> [!TIP]
> Pokud chcete ladit kód mimo vašeho projektu zdrojového kódu, například Windows kód nebo kód třetí strany vašeho projektu volání, je nutné zadat umístění pdb (a volitelně zdrojové soubory externího kódu) a tyto soubory musí přesně odpovídat sestavení t zadá spustitelné soubory.  
 
##  <a name="BKMK_Find_symbol___pdb__files"></a> Kde ladicí program hledat pro soubory symbolů? 
  
1.  Umístění, které je zadáno uvnitř knihovny DLL nebo spustitelného souboru.  
  
     (Ve výchozím nastavení, pokud máte vytvořenou knihovnu DLL nebo spustitelný soubor ve vašem počítači, linker umístí úplnou cestu a název souboru přidruženého souboru PDB do knihovny DLL nebo spustitelného souboru. Ladicí program nejprve zkontroluje, zda existuje soubor se symboly v umístění, které je zadáno v knihovně DLL nebo spustitelném souboru. To je užitečné, protože budete mít vždy symboly, které jsou k dispozici pro kód, který jste zkompilovali v počítači.)  
  
2.  soubory PDB, které se nacházejí ve stejné složce jako knihovny DLL nebo spustitelný soubor.

3. Žádná umístění [zadaná v možnostech ladicí program](#BKMK_Specify_symbol_locations_and_loading_behavior) pro soubory symbolů. 
  
    * Všechny složky mezipaměti místního symbolu.  
  
    * Žádné sítě, Internetu, nebo místní symbol servery a umístění, která jsou určena, jako je Microsoft symbol server (Pokud je povoleno). 

> [!NOTE]
> Před sady Visual Studio 2012 při ladění spravovaného kódu na vzdáleném zařízení je potřeba pro symbol soubory na vzdáleném počítači. Od verze sady Visual Studio 2012, všechny soubory symbolů musí být umístěna v místním počítači nebo v umístění [zadaná v možnostech ladicí program](#BKMK_Specify_symbol_locations_and_loading_behavior).  
  
##  <a name="BKMK_Why_do_symbol_files_need_to_exactly_match_the_executable_files_"></a> Proč se mají soubory symbolů tak, aby přesně odpovídaly spustitelné soubory?  
Ladicí program načte pouze soubor PDB pro spustitelný soubor, který přesně odpovídá souboru .pdb vytvořeném, když byl sestaven spustitelný soubor (to znamená, že PDB musí být originál nebo kopie původního souboru .pdb). Vzhledem k tomu, že kompilátor je optimalizován pro rychlost kompilace, kromě svého hlavního úkolu vytvoření správného a efektivního kódu, se může změnit rozložení skutečného spustitelného souboru i v případě, že nedošlo ke změně samotného kódu. Další informace najdete v části [proč Visual Studio vyžaduje ladicí program symbol soubory tak, aby přesně shodu binární soubory, které byly vytvořeny ve?](https://blogs.msdn.microsoft.com/jimgries/2007/07/06/why-does-visual-studio-require-debugger-symbol-files-to-exactly-match-the-binary-files-that-they-were-built-with/)
  
##  <a name="BKMK_Specify_symbol_locations_and_loading_behavior"></a> Konfigurace, kde ladicí program vyhledá soubory symbolů a načítání chování – symbol
 Při ladění projektu v prostředí Visual Studio IDE, ladicí program automaticky načte soubory symbolů, které se nacházejí v adresáři projektu. Můžete zadat alternativní vyhledávání cesty a symbolů servery pro Microsoft Windows a komponenty jiných výrobců v **nástroje > Možnosti > ladění > symboly**. Můžete také zadat konkrétní moduly, které mají automaticky načíst symboly pro ladicí program. A můžete potom změnit tato nastavení ručně při aktivním ladění.  
  
1.  V sadě Visual Studio, otevřete **nástroje > Možnosti > ladění > symboly** stránky.  
  
     ![Nástroje pro &#45; možnosti &#45; ladění &#45; symboly stránky](../debugger/media/dbg_tools_options_symbols.gif "DBG_Tools_Options_Symbols")  
  
2.  Vyberte složku, ![nástroje&#47; možnosti&#47; ladění&#47;ikonou složky symboly](../debugger/media/dbg_tools_options_foldersicon.png "DBG_Tools_Options_FoldersIcon") ikonu. Upravovat text se zobrazí v **symbolů umístění souborů (.pdb)** pole.  
  
3.  Zadejte adresu URL nebo cestu k adresáři serveru symbolů nebo umístění symbolu. Doplňování výrazů vám pomůže najít správný formát.

    Můžete použít **kombinaci kláves Ctrl + až** a **kombinaci kláves Ctrl + nižší** Chcete-li změnit pořadí načítání pro umístění symbolu. Stiskněte klávesu **F2** upravit adresu URL nebo cestu k adresáři.
  
4.  Pro zlepšení symbol načítání výkonu zadejte cestu k místnímu adresáři, kam lze zkopírovat symboly symbol servery v **mezipaměti symboly v tomto adresáři** pole místní adresář, který lze zkopírovat symboly.  
  
    > [!NOTE]
    >  Neumísťujte mezipaměť symbolu do chráněné složky (například C:\Windows nebo některé z jejích podsložek). Místo toho použijte složku pro čtení i zápis.  
  
### <a name="specify-symbol-loading-behavior"></a>Zadejte chování načítání symbolu 
  
Můžete zadat soubory, které mají být načteny automaticky z **symbolů umístění souborů (.pdb)** zadejte umístění při spuštění ladění. Soubory se symboly v adresáři projektu jsou vždy načteny.  
  
1.  Zvolte **všechny moduly, není-li vyloučit** načíst všechny symboly pro všechny moduly kromě těch, které určíte při výběru **zadejte vyloučené moduly** odkaz.  
  
2.  Vyberte **pouze zadané moduly** možnost a potom zvolte **zadejte moduly** seznam modulů, můžete soubory, které chcete automaticky načíst symbolů. Soubory symbolů pro ostatní moduly jsou ignorovány.  
  
### <a name="specify-additional-symbol-options"></a>Určit další možnosti symbolu. 
  
Můžete také nastavit následující možnosti v **nástroje > Možnosti > ladění > Obecné** stránky:  
  
**Načíst Export knihovny DLL (pouze native)**  
  
Při výběru načte exportní tabulky knihovny DLL. Symbolické informace z tabulky exportu knihovny DLL mohou být užitečné, pokud pracujete se zprávami systému Windows, postupy systému Windows (WindowProcs), objekty COM nebo zařazování nebo libovolnou knihovnou DLL pro kterou nemáte symboly. Informace o exportu knihovny DLL pro čtení zahrnují nadměrné zatížení. Proto tato možnost je ve výchozím nastavení vypnuta.  
  
Pokud chcete zobrazit, jaké symboly jsou k dispozici v tabulce export knihovny DLL, použijte `dumpbin /exports`. Symboly jsou k dispozici pro všechny 32bitové systémové knihovny DLL. Načtením `dumpbin /exports` výstupu se zobrazí název funkce stejné, včetně jiných než alfanumerických znaků. To je užitečné pro nastavení zarážky na funkci. Názvy funkcí z tabulky exportu knihovny DLL se mohou jinde v ladícím programu zobrazit ořezané. Volání jsou uvedena v pořadí volání s aktuální funkcí (nejhlouběji vnořených) nahoře. Další informace najdete v tématu [/EXPORTS dumpbin](/cpp/build/reference/dash-exports).  
  
###  <a name="BKMK_Use_symbol_servers_to_find_symbol_files_not_on_your_local_machine"></a> Servery symbolů použít k vyhledání symbol souborů není na místním počítači  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] můžete stáhnout souborů ze serverů symbolu, které implementují protokol symsrv. [Visual Studio Team Foundation Server](http://msdn.microsoft.com/Library/bd6977ca-e30a-491a-a153-671d81222ce6) a [ladicích nástrojů pro systém Windows](http://msdn.microsoft.com/library/windows/hardware/ff551063\(v=VS.85\).aspx) dvou nástrojů, které můžete implementovat servery symbolů. Zadejte servery symbol pro použití v VS **možnosti** dialogové okno.  
  
 Mezi servery se symboly, které můžete použít, patří:  
  
 **Servery Microsoft veřejné symbolů**  
  
 Pokud chcete ladit selhání, ke kterému dojde během volání systémové knihovny DLL nebo knihovny třetí strany, budete často potřebovat systémové soubory .pdb, které obsahují symboly pro soubory DLL, EXE a ovladače zařízení v systému Windows. Tyto symboly můžete získat na veřejných serverech symbolů společnosti Microsoft. Servery Microsoft veřejné symbolů poskytují symboly pro operační systémy Windows, kromě rozhraní MDAC, IIS, ISA a [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
 Chcete-li používat servery Microsoft symbolů, zvolte **možnosti a nastavení** na **ladění** nabídky a potom zvolte **symboly**. Vyberte **servery Microsoft symbolů**.  
  
 **Servery symbolů v interní síti nebo na místním počítači**  
  
 Váš tým nebo společnost může vytvořit servery symbolů pro vaše vlastní produkty jako mezipaměť pro symboly z externích zdrojů. Symbolový server můžete mít na vlastním počítači. Umístění symbolu servery jako adresu URL nebo cestu můžete zadat na **ladění**/**symboly** stránky VS **dialogové okno Možnosti**.  
  
 **Servery symbolů třetích stran**  
  
 Jiní zprostředkovatelé aplikací a knihoven systému Windows mohou poskytovat přístup k symbolovému serveru na internetu. Můžete také zadat adresu URL tyto servery symbolů **ladění**/**symboly** stránky,  
  
> [!NOTE]
>  Pokud používáte symbolový server jiný než veřejné symbolové servery společnosti Microsoft, přesvědčte se, zda symbolový server a jeho cesty jsou důvěryhodné. Vzhledem k tomu, že soubory se symboly mohou obsahovat libovolný spustitelný kód, můžete se vystavit bezpečnostním hrozbám.  
  
###  <a name="BKMK_Find_and_load_symbols_while_debugging"></a> Najít a načíst symboly při ladění  
 V každém okamžiku, kdy je ladicí program v režimu pozastavení, můžete načíst symboly pro modul, který byl dříve vyloučen možnostmi ladicího programu nebo které kompilátor nemůže najít. Symboly můžete načíst z místních nabídek oken Zásobník volání, Moduly, Lokální, Automatické a Všechna kukátka. Pokud ladicí program se přeruší v kódu, který nemá symbol nebo zdrojové soubory k dispozici, zobrazí se okno dokumentu. Zde naleznete informace o chybějících souborech a provedení akcí k jejich vyhledání a načtení.
  
 **Najít symboly se stránkami dokumentu načteny žádné symboly**  
  
 Existuje několik způsobů jak může ladicí program proniknout do kódu, který nemá k dispozici symboly ladicího programu:  
  
1.  Krokování kódu.  
  
2.  Rozdělení do kódu od zarážky nebo výjimky.  
  
3.  Přepnutí do jiného podprocesu.  
  
4.  Změna zásobníku dvojitým kliknutím na snímek v okně Zásobník volání.  
  
 Když dojde k jedné z těchto událostí, ladicí program zobrazí **načteny žádné symboly** stránce vám pomůžou najít a načíst nezbytné symboly.  
  
 ![Žádná stránka načíst symboly](../debugger/media/dbg_nosymbolsloaded.png "DBG_NoSymbolsLoaded")  
  
-   Chcete-li změnit cesty hledání, zvolte cestu nezaškrtnuté nebo zvolte **nový** a zadejte novou cestu. Zvolte **načíst** a hledat cesty znovu načíst soubor symbol, pokud je nalezena.  
  
-   Zvolte **Procházet a najít***název spustitelného souboru***...**  potlačení žádné možnosti symbol a opakujte cesty pro hledání. Pokud je nalezen soubor symbolů, bude načten, nebo se zobrazí Průzkumník souborů, kde můžete soubor symbolu vybrat ručně.  
  
-   Zvolte **změnit Symbol nastavení...**  zobrazíte **ladění** > **symboly** dialogovém okně Možnosti VS.  
  
-   Zvolte **zobrazit zpětný překlad** zobrazíte zpětný překlad v novém okně jednou.  
  
-   Vždy zobrazovat zpětný překlad, když nejsou nalezeny soubory zdroj nebo symbol, zvolte **dialogovém okně Možnosti** propojit a vyberte **povolit ladění na úrovni adresu** a **zobrazit zpětný překlad Pokud zdroj není k dispozici**.  
  
     ![Možnosti &#47; ladění &#47; zpětný překlad Obecné možnosti](../debugger/media/dbg_options_general_disassembly_checkbox.png "DBG_Options_General_disassembly_checkbox")  
  
 **Změnit symbol možnosti z místní nabídky**  
  
 Při práci v režimu pozastavení můžete najít a načíst symboly pro položky, které jsou zobrazeny v oknech Zásobník volání, Moduly, Lokální, Automatické a všech oknech Kukátka. V okně vyberte položku, otevřete místní nabídku a zvolte jednu z následujících možností:  
  
|Možnost|Popis|  
|------------|-----------------|  
|**Načtení symbolů**|Pokusí se načíst symboly ze zadaných v umístění **ladění**/**symboly** stránka **možnosti** dialogové okno. Pokud nelze najít soubor symbolů, spustí se Průzkumník souborů, takže můžete určit nové umístění pro hledání.|  
|**Načíst informace o symbolu**|Představuje informace, které vykazují umístění načteného souboru se symbolem nebo prohledávána umístění, pokud ladicí program nemůže najít soubor.|  
|**Symbol nastavení...**|Otevře se **ladění**/**symboly** stránky VS **možnosti** dialogové okno.|  
|**Vždy automaticky načíst.**|Přidá soubor symbolů do seznamu souborů, které jsou automaticky načteny pomocí ladicího programu.|  
  
###  <a name="BKMK_Set_compiler_options_for_symbol_files"></a> Nastavení možností kompilátoru pro soubory symbolů  
 Při sestavení projektu v prostředí IDE VS a použijte standardní **ladění** konfigurace sestavení C++ a spravované kompilátory vytvoříte soubory odpovídající symboly pro váš kód. Můžete také nastavit možnosti kompilátoru na příkazovém řádku k vytvoření souborů symbolů.  
  
 **C++ – možnosti**  
  
 Soubor databáze programu (PDB) uchovává informace o ladění a stavu projektu, které umožňují přírůstkové propojení konfigurace ladění programu. Soubor .pdb se vytvoří při sestavování s [/ZI nebo /Zi](/cpp/build/reference/z7-zi-zi-debug-information-format) (pro C/C++).  
  
 V [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)], [/Fd](/cpp/build/reference/fd-program-database-file-name) možnost názvy na soubor .pdb vytvořené kompilátoru. Když vytvoříte projekt v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pomocí průvodců **/Fd** je možnost nastavena na soubor .pdb s názvem *projektu*pdb.  
  
 Pokud vytváříte aplikace C/C++ pomocí souboru pravidel a zadáte **/ZI** nebo **/Zi** bez **/Fd**, v níž se dva soubory PDB:  
  
-   VC*x*pdb, kde *x* představuje verzi Visual C++, například VC11.pdb. Tento soubor obsahuje všechny informace o ladění pro jednotlivé soubory OBJ a je umístěn ve stejném adresáři jako soubor pravidel projektu.  
  
-   Project.pdb tento soubor obsahuje všechny informace o ladění the.exe souboru. Pro jazyk C/C++ je umístěn v podadresáři \debug.  
  
 Pokaždé, když se vytvoří soubor OBJ, kompilátor C/C++ sloučí informace o ladění do VC*x*pdb. Vložené informace obsahují informace o typu, ale neobsahují informace o symbolu, jako jsou definice funkce. Ano, i když každý zdrojový soubor obsahuje společné soubory hlaviček, jako \<odkazující na Windows >, definice TypeDef z těchto hlavičky místo používán každý soubor OBJ ukládají pouze jednou.  
  
 Linker vytvoří project.pdb, který obsahuje informace o ladění souboru EXE v projektu. Soubor project.pdb obsahuje informace o úplné ladění, včetně prototypy funkcí, ne jenom informace typu nalézt v VC*x*pdb. Oba soubory PDB umožňují přírůstkové aktualizace. Linker také vloží cestu k souboru .pdb ve vytvořeném souboru .exe nebo .dll.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Ladicí program používá cestu k souboru PDB v souboru EXE nebo DLL najít soubor project.pdb. Pokud ladicí program nemůže najít soubor .pdb v tomto umístění nebo pokud cesta je neplatná (například pokud projekt byl přesunut do jiného počítače), ladicí program vyhledá cestu obsahující EXE, cesty symbol zadat **možnosti** Dialogové okno (**ladění** složky, **symboly** uzlu). Ladicí program nenačte soubor .pdb, který neodpovídá laděnému spustitelnému souboru. Pokud ladicí program nemůže najít soubor .pdb **najít symboly** se zobrazí dialogové okno, které umožňuje hledat symboly nebo je přidat do cesta hledání.  
  
 **Možnosti rozhraní .NET framework**  
  
 Soubor databáze programu (PDB) uchovává informace o ladění a stavu projektu, které umožňují přírůstkové propojení konfigurace ladění programu. Soubor .pdb se vytvoří při sestavování s **/debug**. Mohou vytvářet aplikace s **/debug:full** nebo **/debug:pdbonly**. Sestavování s použitím **/debug:full** generuje debuggable kód. Sestavování s použitím **/debug:pdbonly** generuje soubory PDB ale negeneruje `DebuggableAttribute` které sděluje kompilátoru za běhu, zda je k dispozici informace o ladění. Použití **/debug:pdbonly** Pokud chcete generovat soubory PDB pro sestavení pro vydání, které nechcete být debuggable. Další informace najdete v tématu [/Debug (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/debug-compiler-option) nebo [/Debug (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/debug).  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Ladicí program používá cestu k souboru PDB v souboru EXE nebo DLL najít soubor project.pdb. Pokud ladicí program nemůže najít soubor .pdb v tomto umístění, nebo pokud cesta je neplatná, ladicí program vyhledá cestu obsahující EXE se a potom zadat cesty symbol v **možnosti** dialogové okno. Obvykle je tato cesta **ladění** složky v **symboly** uzlu. Ladicí program nenačte soubor .pdb, který neodpovídá laděnému spustitelnému souboru. Pokud ladicí program nemůže najít soubor .pdb **najít symboly** se zobrazí dialogové okno, které umožňuje hledat symboly nebo je přidat do cesta hledání.  
  
 **webové aplikace**  
  
 Konfigurační soubor aplikace (Web.config) musí být nastaven na režim ladění. Režim ladění způsobí, že technologie ASP.NET generuje dynamicky generované soubory a umožňuje ladicímu program připojit k aplikaci technologie ASP.NET. Visual Studio to nastaví automaticky při spuštění ladění, pokud jste vytvořili projekt ze šablony webové projekty.  
  
##  <a name="BKMK_Find_source_files"></a> Najít zdrojové soubory  
  
###  <a name="BKMK_Where_the_debugger_searches_for_source_files"></a> Kde ladicí program hledá zdrojové soubory  
 Ladicí program vyhledá zdrojové soubory v následujících umístěních:  
  
1.  Soubory, které jsou otevřeny v integrovaném vývojovém prostředí Visual Studio instance, které spustilo ladicí program.  
  
2.  Soubory v řešení, které je otevřít v sadě Visual Studio instance.  
  
3.  Adresáře, které jsou určené v **společných vlastností**/**zdrojové soubory ladění** stránky ve vlastnostech řešení. (V **Průzkumníku řešení**, vyberte uzel řešení, klikněte pravým tlačítkem a vyberte **vlastnosti**. )  
  
4.  Zdrojové informace o souboru .pdb modulu. To může být umístění zdrojového souboru, když modul byl vytvořen, nebo to může být příkaz na zdrojový server.  
  
###  <a name="BKMK_Find_and_load_source_files_with_the_No_Source___No_Symbols_Loaded_pages"></a> Najít a načíst zdrojových souborů s stránky načíst ne Source/No symboly  
 Když ladicí program dělí provádění v umístění, kde zdrojového souboru není k dispozici, se zobrazí **žádný zdroj načíst** nebo **načteny žádné symboly** stránky, které vám mohou pomoci najít zdrojový soubor. **Načteny žádné symboly** se zobrazí, když ladicí program nemůže najít soubor symbolu (.pdb) pro spustitelný soubor na dokončení jeho vyhledávání. Stránka Žádné symboly poskytuje možnosti pro vyhledání souboru. Pokud je soubor PDB nalezen po spuštění jedné z možností a ladicí program může načíst zdrojový soubor pomocí informací v souboru symbolů, zobrazí se zdroj. V opačném **žádný zdroj načíst** se zobrazí stránka s popisem příslušného problému. Na stránce se zobrazí odkazy s možnostmi, které umožňují provádět akce, které mohou problém vyřešit.  
  
###  <a name="BKMK_Add_source_file_search_paths_to_a_solution"></a> Přidání cesty pro hledání zdrojových souborů do řešení  
 Můžete určit síť nebo místní adresáře pro hledání zdrojových souborů.  
  
1.  Vyberte v Průzkumníku řešení a potom zvolte **vlastnosti** z místní nabídky.  
  
2.  V části **společných vlastností** uzlu, zvolte **zdrojové soubory ladění**.  
  
3.  Klikněte na složku ![nástroje&#47; možnosti&#47; ladění&#47;ikonou složky symboly](../debugger/media/dbg_tools_options_foldersicon.png "DBG_Tools_Options_FoldersIcon") ikonu. Upravovat text se zobrazí v **adresáře, který obsahuje zdrojový kód** seznamu.  
  
4.  Přidejte cestu, kterou chcete prohledat.  
  
 Všimněte si, že je prohledán pouze zadaný adresář. Je nutné přidat položky pro všechny podadresáře, které chcete prohledávat.  
  
###  <a name="BKMK_Use_source_servers"></a> Použití zdrojových serverů  
 Pokud neexistuje žádný zdrojový kód v místním počítači nebo soubor PDB neodpovídá zdrojovému kódu, můžete použít zdrojový server k ladění aplikace. Zdrojový server přijímá požadavky na soubory a vrací skutečné soubory. Zdrojový server je spuštěn pomocí souboru knihovny DLL s názvem srcsrv.dll. Zdrojový Server přečte soubor PDB aplikace, který obsahuje odkazy na úložiště zdrojového kódu, jakož i příkazy pro načtení zdrojového kódu z úložiště. Můžete omezit, jaké příkazy mohou být provedeny ze souboru .pdb aplikace uvedením seznamu povolených příkazů v souboru s názvem srcsrv.ini, který musí být umístěn ve stejném adresáři jako soubory srcsrv.dll a devenv.exe.  
  
> [!IMPORTANT]
>  Libovolné příkazy lze vložit do souboru v souboru pdb aplikace, takže zkontrolujte, zda umístíte pouze ty, které chcete provést do souboru srcsrv.ini. Pokus o provedení příkazu mimo soubor srcsvr.ini způsobí zobrazení dialogového okna s potvrzením. Další informace najdete v tématu [upozornění zabezpečení: ladicí program musí spustit nedůvěryhodný příkaz](../debugger/security-warning-debugger-must-execute-untrusted-command.md). Parametry příkazu nejsou ověřovány, proto buďte s důvěryhodnými příkazy opatrní. Například pokud důvěřujete souboru cmd.exe, uživateli se zlými úmysly může zadat parametry, které by z příkazu mohly udělat hrozbu.  
  
 **Chcete-li povolit použití zdrojového serveru**  
  
1.  Ujistěte se, že jsou dodrženy bezpečnostní opatření popsané v předchozí části.  
  
2.  Na **nástroje** nabídky, zvolte **možnosti**.  
  
     **Možnosti** zobrazí se dialogové okno.  
  
3.  V **ladění** uzlu, zvolte **Obecné**.  
  
4.  Vyberte **podporu zdrojový server** zaškrtávací políčko.  
  
     ![Povolení možnosti zdrojového serveru](../debugger/media/dbg_options_general_enablesrcsrvr_checkbox.png "DBG_Options_General_EnableSrcSrvr_checkbox")  
  
5.  (Volitelné) Zvolte požadované podřízené možnosti.  
  
     Všimněte si, že oba **povolit zdrojového serveru pro částečnou důvěryhodností sestavení (pouze spravované)** a **vždy spouští příkazy serveru nedůvěryhodného zdroje bez zobrazení výzvy** může zvýšit rizika zabezpečení, které jsou popsané výše.  
  
## <a name="see-also"></a>Viz také  
[Seznámení s Visual Studio Symbol nastavení a soubory symbolů](https://blogs.msdn.microsoft.com/visualstudioalm/2015/01/05/understanding-symbol-files-and-visual-studios-symbol-settings/)

[Rozhraní .NET vzdálené Symbol načítání změny v sadě Visual Studio 2012 a 2013](http://blogs.msdn.com/b/visualstudioalm/archive/2013/10/16/net-remote-symbol-loading-changes-in-visual-studio-2012-and-2013.aspx)