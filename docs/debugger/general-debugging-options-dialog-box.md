---
title: "Obecné, ladění, dialogové okno Možnosti | Microsoft Docs"
ms.custom: 
ms.date: 05/23/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.options.General
- VS.ToolsOptionsPages.Debugger.General
- VS.ToolsOptionsPages.Debugger.ENC
- vs.debug.options.ENC
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords: Options dialog box, debugging
ms.assetid: b33aee0b-43c3-4c26-8ed4-bc673f491503
caps.latest.revision: "46"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bf693d7a5339e57edeaed82c25ed552901e1ea51
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/04/2018
---
# <a name="general-debugging-options-dialog-box"></a>Obecné, ladění, dialogové okno Možnosti
**Nástroje > Možnosti > ladění > Obecné** stránce můžete nastavit následující možnosti:  
  
**Dotázat se před odstraněním všechny zarážky**  
Vyžaduje potvrzení před dokončením **odstranit všechny zarážky** příkaz.  
  
**Přerušení všech procesů, když jeden proces dělí**  
Současně dělí všech procesů, ke kterým je připojen ladicí program, když dojde k zalomení.  
  
**Pozastavení při výjimky mezi hranice spravované/nativní nebo domény aplikace**  
Ve spravované nebo ve smíšeném režimu ladění, můžete modul common language runtime zachytávat výjimky, které zasahují hranice spravované/nativní nebo hranic domény aplikace, pokud jsou splněny následující podmínky:  
  
1\) při nativní kód zavolá spravovaného kódu pomocí zprostředkovatele komunikace s objekty COM a spravovaného kódu vyvolá výjimku. V tématu [Úvod zprostředkovatele komunikace s objekty COM](/dotnet/articles/visual-basic/programming-guide/com-interop/introduction-to-com-interop).  
  
2\) při spravovaný kód spuštěný v doméně aplikace 1 volá spravovaného kódu v doméně aplikace 2 a kód domény aplikace 2 vyvolá výjimku. V tématu [programování s doménami aplikací](/dotnet/articles/framework/app-domains/index).  

3\) při kód zavolá funkci pomocí reflexe a funkce vyvolá výjimku. V tématu [reflexe](/dotnet/framework/reflection-and-codedom/reflection).  
  
V podmínce 2 a 3, výjimka někdy zachycena spravovaným kódem v `mscorlib` místo modul common language runtime. Tato možnost nemá vliv na nejnovější na výjimky zachytila `mscorlib`.  
  
**Povolit ladění na úrovni adresa**  
 Povoluje rozšířené funkce pro ladění na úrovni adres ( **zpětný překlad** okně **zaregistruje** okno a adresu zarážky).  
  
- **Zobrazit zpětný překlad Pokud zdroj není k dispozici**  
    Automaticky zobrazí **zpětný překlad** okno při pokusu o ladění kódu pro zdroj, který je k dispozici.  
  
**Povolit filtry zarážek**  
Umožňuje nastavit filtry na zarážky tak, aby se ovlivní pouze konkrétní procesy, vláken nebo počítače.  
 
**Použití nového pomocníka výjimka**  
Umožňuje pomocníka výjimka (Visual Studio 2017), který nahrazuje Pomocníka pro výjimky.
  
> [!NOTE]
> Pro spravovaný kód, tato možnost označovaly jako **Povolit Pomocníka pro výjimky** . 
  
**Povolit pouze můj kód**  
Ladicí program zobrazí a kroky do uživatele (kód "Moje"), bez ohledu na kód systémové a jiný kód, který je optimalizovaná nebo která symboly ladění nemá.

- **Upozornit, pokud žádný kód uživatele při spuštění (pouze spravované)**  
    Při spuštění s ladění pouze můj kód povolena, tato možnost upozorní, pokud neexistuje žádný kód uživatele ("vlastní kód"). 

**Povolení rozhraní .NET Framework zdroje krokování s**  
Umožňuje ladicí program na krok do zdroje rozhraní .NET Framework. Pouze můj kód rozhraní .NET Framework symboly bude stažen do umístění mezipaměti automaticky povolením této možnosti zakáže. Můžete změnit umístění mezipaměti v **možnosti** dialogové okno, **ladění** kategorie, **symboly** stránky.  
  
**Krok přes vlastnosti a operátory (pouze spravované)**  
Ladicí program zabrání zanoříte se do vlastnosti a operátory ve spravovaném kódu.  
  
**Povolit vyhodnocení vlastnosti a další funkce implicitní volání**  
Zapne automatické vyhodnocení vlastnosti a funkce implicitní volá ve windows proměnné a **QuickWatch** dialogové okno.  
  
- **Volání funkce Převod řetězce na objekty ve windows proměnné (C# a JavaScript pouze)**  
    Provede volání na řetězec implicitní převod při vyhodnocování objekty ve windows proměnné. Proto že výsledek je zobrazen jako řetězec místo názvu typu. Vztahuje se pouze při ladění v kódu jazyka C#. Toto nastavení může být přepsána debuggerdisplay – atribut (viz [používání atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)).  
  
**Povolit podporu zdrojového serveru**  
Informuje ladicího programu sady Visual Studio získat zdrojové soubory ze zdrojových serverů, které implementují SrcSrv (`srcsrv.dll`) protokolu. Team Foundation Server a ladění nástrojů pro Windows jsou dva servery zdroje, které implementují protokol. Další informace o nastavení SrcSrv najdete v tématu [SrcSrv](hhttps://msdn.microsoft.com/en-us/library/windows/hardware/ff558791(v=vs.85).aspx) dokumentaci. Kromě toho najdete v části [zadejte symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
> [!IMPORTANT]
>  Protože čtení soubory PDB můžete spustit libovolný kód v souborech, ujistěte se, že důvěřujete serveru.  
  
- **Tisk zdrojový server diagnostické zprávy v okně Výstup**  
    Pokud je povolená podpora zdrojového serveru, toto nastavení zapne diagnostiky zobrazení.  
  
- **Povolit zdrojového serveru pro částečnou důvěryhodností sestavení (pouze spravované)**  
    Pokud je povolená podpora zdrojového serveru, toto nastavení přepisuje výchozí chování není načítají se zdroje pro sestavení s částečnou důvěryhodností.  

- **Povolit podporu odkaz zdroje**  
    Informuje ladicího programu sady Visual Studio ke stažení zdrojových souborů pro soubory PDB, které obsahují informace o propojení zdroje. Další informace o odkaz na zdroj, najdete v článku [zadání odkazu zdroje](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/source_link.md).

    > [!IMPORTANT]
    >  Vzhledem k tomu, že odkaz na zdroj bude stáhnout soubory pomocí protokolu http nebo https, ujistěte se, že důvěřujete na soubor .pdb.  
  
**Zvýrazněte celý řádek pro zarážky a aktuální příkaz (pouze C++)**  
Když ladicího programu označuje bod přerušení nebo aktuální příkaz, označuje celý řádek.  
  
**Vyžadovat zdrojové soubory tak, aby přesně odpovídaly původní verze**  
Informuje ladicí program na zkontrolujte, zda zdrojový soubor odpovídá verzi zdrojový kód, který je použit k vytvoření spustitelného souboru, kterou ladíte. Pokud verze neodpovídá, budete vyzváni k vyhledání odpovídající zdroj. Pokud není nalezen odpovídající zdroj, zdrojový kód se nezobrazí během ladění. 
  
**Přesměrovat všechny text okno výstupu na příkazové podokno**  
Odešle všechny ladicího programu zprávy, které by obvykle se zobrazí v **výstup** okna **Immediate** okno místo.  
  
**Zobrazit nezpracované struktura objektů ve windows proměnné**  
Veškerá přizpůsobení zobrazení objektu struktura vypne. Další informace o možnostech přizpůsobení zobrazení najdete v tématu [vytvářet vlastní zobrazení objektů .managed](../debugger/create-custom-views-of-dot-managed-objects.md).  
  
**Potlačit optimalizaci JIT pro načtení modulu (pouze spravované)**  
Zakáže optimalizaci JIT spravovaného kódu, když je načten modul a je zkompilovat JIT, je připojen ladicí program. Zakázat optimalizace může usnadnit práci k ladění některé problémy, i když za cenu výkonu. Pokud používáte pouze můj kód, potlačení JIT optimalizace může způsobit bez uživatelského kódu, než se objeví jako uživatel (kód "Moje").

**Povolit ladění jazyka JavaScript pro technologii ASP.NET (Chrome a IE)** umožňuje nástroj script debugger pro aplikace ASP.NET. Při prvním použití v prohlížeči Chrome musíte se přihlásit do prohlížeče při prvním použití povolení rozšíření Chrome, které jste nainstalovali. Tuto možnost zakažte vrátit se do starší verze chování.    

**Načíst Export knihovny dll**  
Načte tabulky export knihovny dll. Symbol informace z tabulek export knihoven dll může být užitečné, pokud pracujete s zpráv systému Windows, Windows postupy (WindowProcs), objekty modelu COM nebo zařazování nebo všechny knihovny dll, pro které nemáte symboly. Načítání knihovny dll exportovat informace zahrnuje některé režijní náklady. Proto tato možnost je ve výchozím nastavení vypnuta.  
  
Pokud chcete zobrazit, jaké symboly jsou k dispozici v tabulce export knihovny DLL, použijte `dumpbin /exports`. Symboly jsou k dispozici pro všechny 32bitové verzi systému dll. Načtením `dumpbin /exports` výstupu se zobrazí název funkce stejné, včetně jiných než alfanumerických znaků. To je užitečné pro nastavení zarážky na funkci. Názvy funkcí z knihovny dll export tabulek, může se objevit zkrácený jinde v ladicím programu. Volání jsou uvedena v pořadí volání s aktuální funkcí (nejhlouběji vnořených) nahoře. Další informace najdete v tématu [/EXPORTS dumpbin](/cpp/build/reference/dash-exports).  
  
**Zobrazit paralelní zásobníky diagram zdola nahoru**  
Určuje směr, ve kterém jsou zobrazeny zásobníky v **paralelní zásobníky** okno.  
  
**Pokud data zapsaná nebyla změňte hodnotu Ignorovat výjimky přístupu paměti grafického procesoru**  
Ignoruje časování, které byly zjištěny během ladění Pokud data nebyla změnit. Další informace najdete v tématu [ladění kódu GPU](../debugger/debugging-gpu-code.md).  
  
**Použití spravovaných kompatibility režimu**  
Nahradí výchozí ladění modul starší verzí povolit tyto scénáře:  
  
- Použití jiného jazyka než C#, VB a F #, která poskytuje vlastní vyhodnocovací filtr výrazů rozhraní .NET Framework (to zahrnuje C + +/ CLI).  
  
- Chcete povolit upravit a pokračovat pro projekty C++ při ladění ve smíšeném režimu.  
  
Všimněte si, že výběr spravovaných kompatibility režimu zakáže některé funkce, které jsou implementovány pouze ve výchozí ladění modulu. 

**Pomocí starší verze vyhodnocovače výrazů jazyka C# a VB**  
Ladicí program bude používat vyhodnocovače výrazů Visual Studio 2013 C# / VB. místo vyhodnocovače založené na Visual Studio 2015 Roslyn výrazů.    
  
**Upozornit při použití vlastní ladicí program vizualizérech proti potenciálně nebezpečného procesy (pouze spravované)**  
Visual Studio vás upozorní, když používáte vlastní vizualizér, který běží v procesu pozastaven kódu, protože může být spuštěna nezabezpečený kód.  
  
**Povolit přidělení haldy ladění Windows (pouze Native)**  
Umožňuje haldy ladění windows ke zlepšení haldy diagnostiky. Povolením této možnosti bude mít dopad na výkon ladění.  
  
**Povolit uživatelského rozhraní nástroje pro ladění pro jazyk XAML**  
Dynamickém vizuálním stromu a windows Live prozkoumat vlastnosti se zobrazí při spuštění ladění (F5) typu podporované projektu. Další informace najdete v tématu [vlastnosti zkontrolujte XAML při ladění](../debugger/inspect-xaml-properties-while-debugging.md).  
  
- **Náhled vybrané elementy v dynamickém vizuálním stromu**  
    Element jazyka XAML, jehož kontext je vybrána, vybere se také v **dynamickém vizuálním stromu** okno.  
  
- **Zobrazit nástroje pro modul runtime v aplikaci**  
    Ukazuje **dynamickém vizuálním stromu** příkazy v panelu nástrojů v hlavním okně aplikace XAML, který je právě laděn. Tato možnost byla zavedena v sadě Visual Studio 2015 Update 2. 

- **Povolit XAML upravit a pokračovat** umožňuje použití operace upravit a pokračovat funkcí pro kód XAML. 
  
**Povolení diagnostických nástrojů při ladění**  
**Diagnostické nástroje** při ladění, zobrazí se okno.
  
**Zobrazit uplynulý čas PerfTip při ladění**  
V okně kód zobrazí uplynulý čas dané metody volání při ladění.  
  
**Povolit upravit a pokračovat**  
Můžete použít upravit a pokračovat funkce při ladění.  
  
- **Povolit nativní upravit a pokračovat**  
    Můžete použít upravit a pokračovat funkce při ladění nativního kódu C++. Další informace najdete v tématu [upravit a pokračovat (Visual C++)](../debugger/edit-and-continue-visual-cpp.md).  
  
- **Změny na pokračovat (pouze Native)**  
    Visual Studio automaticky zkompiluje a platí všechny zbývající kód změny, které jste provedli při pokračování procesu ze stavu pozastavení. Pokud není vybrána, můžete použít změny pomocí "Použít změny kódu" položky v nabídce ladění.  
  
- **Upozornění na starý kód (jenom Native)**  
    Získáte upozornění na starý kód.    

**Zobrazit spusťte kliknutím na tlačítko v editoru při ladění** Pokud je vybraná tato možnost, [spustit kliknutím](debugger-feature-tour.md#run-to-a-point-in-your-code-quickly-using-the-mouse) tlačítko se zobrazí při ladění.

## <a name="options-supported-in-older-versions-of-visual-studio"></a>Možnosti podporované v starší verze sady Visual Studio

Pokud používáte starší verze sady Visual Studio, mohou být některé další možnosti přítomny.

**Povolit Pomocníka pro výjimky**  
Pro spravovaný kód Povolit Pomocníka pro výjimky. V aplikaci Visual Studio 2017 pomocníka výjimka nahrazuje Pomocníka pro výjimky.

**Unwind zásobníku volání na neošetřených výjimek**  
Způsobí, že **zásobníkem volání** okno vrácení zásobníku volání do bodu předtím, než došlo k neošetřené výjimce. 

**Upozornit, pokud žádné symboly při spuštění (pouze native)**  
Zobrazí dialogové okno upozornění při pokusu o ladění programu, pro kterou má ladicí program bez informací o symbolu. 

**Upozornit, pokud je při spuštění zakázáno ladění skriptů**  
Zobrazí dialogové okno upozornění při spuštění ladicího programu s ladění skriptů zakázáno.

**Použijte režim nativní kompatibility**  
Pokud je vybraná tato možnost, ladicího programu místo nové nativní ladicí program používá nativní ladicí program Visual Studio 2010.  
  
Tato možnost by měla použít při ladění kódu .NET C++, protože nové ladění modulu nepodporuje vyhodnocování výrazů .NET C++. Povolení nativního režimu kompatibility, ale zakáže řadu funkcí, které závisí na aktuální implementace ladicí program k provozu. Například modul starší verze chybí mnoho vizualizérech pro vestavěné typy `std::string` v projektech Visual Studio 2015.   Pro optimální zkušenosti s laděním v těchto případech použijte projektů Visual Studio 2013.
  
## <a name="see-also"></a>Viz také  
 [Ladění v sadě Visual Studio](../debugger/index.md)  
 [Prohlídka funkce ladicí program](../debugger/debugger-feature-tour.md)