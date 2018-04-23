---
title: 'Návod: Ladění paralelní aplikace | Microsoft Docs'
ms.custom: H1HackMay2017
ms.date: 03/22/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, parallel tasks walkthrough
- parallel stacks toolwindow
- parallel tasks toolwindow
- parallel applications, debugging [C++]
- debugging, parallel applications
- parallel applications, debugging [Visual Basic]
- parallel applications, debugging [C#]
ms.assetid: 2820ac4c-c893-4d87-8c62-83981d561493
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aceeb00f81bb858b1cebe19168b7366f08562745
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="walkthrough-debugging-a-parallel-application-in-visual-studio"></a>Návod: Ladění paralelní aplikace v sadě Visual Studio
Tento návod ukazuje, jak používat **paralelních úloh** a **paralelní zásobníky** windows k ladění paralelní aplikace. Tyto windows vám pomůžou pochopit a ověřit modul runtime chování kód, který používá [Task Parallel Library (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl) nebo [Concurrency Runtime](/cpp/parallel/concrt/concurrency-runtime). Tento názorný postup obsahuje ukázkový kód, který má integrovanou zarážky. Po kód dělí, Průvodce ukazuje způsob použití **paralelních úloh** a **paralelní zásobníky** windows a zkontrolujte ji.  
  
 Tento názorný postup se dozvíte, jaké tyto úlohy:  
  
-   Postup zobrazení zásobníky volání všechny vláken v jednom zobrazení.  
  
-   Postup zobrazení seznamu `System.Threading.Tasks.Task` instancí, které jsou vytvořeny ve vaší aplikaci.  
  
-   Jak zobrazit skutečné volání zásobníky úloh místo vláken.  
  
-   Jak se orientovat na kód z **paralelních úloh** a **paralelní zásobníky** systému windows.  
  
-   Jak windows zvládnout s měřítkem prostřednictvím seskupení, přibližování a jiné související funkce.  
  
## <a name="prerequisites"></a>Požadavky  
 Tento návod předpokládá, že **pouze můj kód** je povoleno (je povolená ve výchozím nastavení v novějších verzích sady Visual Studio). Na **nástroje** nabídky, klikněte na tlačítko **možnosti**, rozbalte **ladění** uzlu, vyberte **Obecné**a potom vyberte **povolit Pouze můj kód (pouze spravované)**. Pokud tato funkce není nastavena, když můžete nadále používat Tento názorný postup, ale výsledky mohou lišit od obrázky.  
  
## <a name="c-sample"></a>Ukázka C#  
 Pokud používáte ukázku C#, tento návod také předpokládá, že externí kód skryt. Určí, zda je zobrazen kód externí, klikněte pravým tlačítkem **název** záhlaví tabulky **zásobníkem volání** okno a pak vyberte nebo zrušte **zobrazit externí kód**. Pokud tato funkce není nastavena, když můžete nadále používat Tento názorný postup, ale výsledky mohou lišit od obrázky.  
  
## <a name="c-sample"></a>Ukázka C++  
 Pokud používáte ukázku C++, můžete ignorovat odkazy na externí kód v tomto tématu. Externí kódu se vztahuje pouze na ukázky C#.  
  
## <a name="illustrations"></a>Obrázky  
 Obrázky v tomto tématu zjištěných na počítači čtyřjádrový ukázky C#. I když k dokončení tohoto průvodce můžete použít další konfigurace, tyto ilustrace mohou lišit od co se zobrazí ve vašem počítači.  
  
## <a name="creating-the-sample-project"></a>Vytvoření ukázkového projektu  
 Ukázkový kód v tomto návodu je pro aplikaci, která se nic nestane. Cílem je právě pochopit, jak pomocí nástroje systému windows k ladění paralelní aplikace.  
  
#### <a name="to-create-the-sample-project"></a>K vytvoření ukázkového projektu  
  
1.  V sadě Visual Studio na **soubor** nabídky, přejděte na příkaz **nový** a pak klikněte na **projektu**.  
  
2.  V **nainstalovaných šablonách** podokně, vyberte buď Visual C#, Visual Basic, Visual C++. Pro spravované jazyky, zajistěte, aby [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] se zobrazí v poli framework.  
  
3.  Vyberte **konzolové aplikace** a pak klikněte na **OK**. Zůstanou v konfiguraci ladění, což je výchozí hodnota.  
  
4.  Otevřete soubor sada, cs nebo VB kódu v projektu. Odstraňte její obsah, když chcete vytvořit soubor prázdný kód.  
  
5.  Vložte následující kód pro zvoleného jazyka do souboru prázdný kód.  
  
 [!code-csharp[Debugger#1](../debugger/codesnippet/CSharp/walkthrough-debugging-a-parallel-application_1.cs)]
 [!code-cpp[Debugger#1](../debugger/codesnippet/CPP/walkthrough-debugging-a-parallel-application_1.cpp)]
 [!code-vb[Debugger#1](../debugger/codesnippet/VisualBasic/walkthrough-debugging-a-parallel-application_1.vb)]  
  
1.  Na **soubor** nabídky, klikněte na tlačítko **Uložit vše**.  
  
2.  Na **sestavení** nabídky, klikněte na tlačítko **znovu sestavit řešení**.  
  
     Všimněte si, že existují čtyři volání `Debugger.Break` (`DebugBreak` v C++ ukázce) proto není nutné vložit zarážky; právě spuštěnou aplikací způsobí, že pro přerušení v ladicím programu až čtyřikrát.  
  
## <a name="using-the-parallel-stacks-window-threads-view"></a>Pomocí paralelní balíků okno: zobrazení vláken  
 Na **ladění** nabídky, klikněte na tlačítko **spustit ladění**. Počkejte, než pro první zarážky být narazí.  
  
#### <a name="to-view-the-call-stack-of-a-single-thread"></a>Chcete-li zobrazit zásobníku volání z jednoho vlákna  
  
1.  Na **ladění** nabídky, přejděte na příkaz **Windows** a pak klikněte na **vláken**. Ukotvení **vláken** okna v dolní části sady Visual Studio.  
  
2.  Na **ladění** nabídky, přejděte na příkaz **Windows** a pak klikněte na **zásobníkem volání**. Ukotvení **zásobníkem volání** okno dole v sadě Visual Studio.  
  
3.  Klikněte dvakrát na vlákno v **vláken** okno aktuální. Aktuální vláken obsahovat žlutou šipku. Když změníte aktuální vlákno, jeho zásobník volání se zobrazí v **zásobníkem volání** okno.  
  
#### <a name="to-examine-the-parallel-stacks-window"></a>K prozkoumání okna paralelní zásobníky  
  
1.  Na **ladění** nabídky, přejděte **Windows** a pak klikněte na **paralelní zásobníky**. Ujistěte se, že **vláken** je vybrán v okně na levém horním rohu.  
  
     Pomocí **paralelní zásobníky** můžete zobrazit více zásobníky volání současně v jednom zobrazení. Následující obrázek ukazuje **paralelní zásobníky** okno výše **zásobníkem volání** okno.  
  
     ![Zobrazení v okně paralelní zásobníky vláken](../debugger/media/pdb_walkthrough_1.png "PDB_Walkthrough_1")  
  
     Zásobník volání hlavní vlákno, zobrazí se v jedné a zásobníky volání pro jiné čtyři vlákna jsou seskupené v jiné pole. Čtyři vláken jsou seskupeny dohromady, protože jejich rámce zásobníku sdílet stejnou metodu kontexty; To znamená, že jsou ve stejné metody: `A`, `B`, a `C`. K zobrazení ID vlákna a názvy vláken, které sdílejí stejné pole, najeďte myší do tohoto pole hlavičky (**4 vláken**). Aktuální vlákno je zobrazená tučným písmem.  
  
     ![Popisek, který ukazuje názvy a ID vlákna](../debugger/media/pdb_walkthrough_1a.png "PDB_Walkthrough_1A")  
  
     Žlutá šipka označuje active zásobníku aktuálního vlákna.
  
     Můžete nastavit, kolik podrobností o zobrazíte pro rámce zásobníku (**názvy modulů**, **typy parametrů**, **názvy parametrů**, **hodnoty parametrů**, **Čísla řádků** a **posun bajtů**) kliknutím pravým tlačítkem myši v **zásobníkem volání** okno.  
  
     Modré zvýraznění kolem pole označuje, že aktuální vlákno je součástí dané pole. Aktuální vlákno je také indikován tučné zásobníku v popisu tlačítka. Pokud dvakrát kliknete na hlavní vlákno v okně vláken, můžete sledovat, modré zvýraznění v **paralelní zásobníky** okno přesune odpovídajícím způsobem.  
  
     ![Zvýrazněná hlavní vlákno v okna paralelní zásobníky](../debugger/media/pdb_walkthrough_1c.png "PDB_Walkthrough_1C")  
  
#### <a name="to-resume-execution-until-the-second-breakpoint"></a>Chcete-li pokračovat v provádění až druhý zarážek  
  
1.  Chcete-li pokračovat v provádění dokud druhý zarážek přístupů, na **ladění** nabídky, klikněte na tlačítko **pokračovat**. Následující obrázek znázorňuje stromu vlákno u druhé zarážky.  
  
     ![Paralelní zásobníky okno, které ukazuje mnoho větví](../debugger/media/pdb_walkthrough_2.png "PDB_Walkthrough_2")  
  
     U první zarážky všechny čtyři vláken se z adresu S.A k S.B na S.C metody. Zda jsou informace stále viditelné v **paralelní zásobníky** mají další zvýšily okno, ale čtyři vláken. Jeden z nich nadále S.D a pak S.E. Jiné dál S.F, S.G a S.H. Dvěma dalšími dál S.I a S.J a z zde jeden z nich byl přesunut do S.K a dalších dál externí kód jiný uživatel.  
  
     Můžete ukazatel myši přesunete pole záhlaví, například **1 vlákno** nebo **2 vláknech**, zobrazíte vlákno ID vláken. Pozastavte ukazatel myši nad rámec zásobníku zobrazíte vlákno ID plus další podrobnosti rámce. Modré zvýraznění označuje aktuální vlákno a žlutá šipka označuje active zásobníku aktuálního vlákna.  
  
     Ikona hadřík vláken (interweaved řádky) znamenat rámce zásobníku active fixní vláken. V **zásobníkem volání** okna, klikněte dvakrát na S.B přepnout rámce. **Paralelní zásobníky** okno označuje aktuální rámec zásobníku aktuálního vlákna pomocí ikony zelenou zakřivenou šipkou.  
  
     V **vláken** okně přepínat mezi vláken a všimněte zobrazení v **paralelní zásobníky** okno se aktualizuje.  
  
     Pomocí místní nabídky v můžete přepnout na jiné vlákno nebo na jiný rámec jiné vlákno **paralelní zásobníky** okno. Například klikněte pravým tlačítkem na S.J, přejděte na **přepínače do rámečku**a potom klikněte na příkaz.  
  
     ![Paralelní zásobníky – cesta spuštění](../debugger/media/pdb_walkthrough_2b.png "PDB_Walkthrough_2B")  
  
     Klikněte pravým tlačítkem na S.C a přejděte na **přepínače do rámečku**. Jeden z příkazů má zaškrtnutí označující rámce zásobníku aktuálního vlákna. Můžete přepnout do tohoto rámečku stejném vlákně, v (jenom na zelenou šipku přesune) nebo můžete přepnout na další vlákno (modré zvýraznění bude také přesunout). Následující obrázek znázorňuje podnabídky.  
  
     ![Zásobníky nabídky 2 možnosti na C při aktuální J](../debugger/media/pdb_walkthrough_3.png "PDB_Walkthrough_3")  
  
     Když metoda kontextu je přidružen pouze jeden zásobníku, zobrazí pole hlavičky **1 vlákno** a můžete přepnout do ní dvojitým kliknutím na soubor. Pokud dvakrát kliknete na metoda kontext, který má přidruženo více než 1 rámečkem, pak v nabídce automaticky objeví. Když najedete kontexty metoda, Všimněte si černý trojúhelník vpravo. Kliknutím na tento trojúhelník také zobrazí v místní nabídce.  
  
     Pro velké aplikace, které mají velký počet vláken můžete se zaměřit na pouze podmnožinu vláken. **Paralelní zásobníky** okno může zobrazit zásobníky volání pouze pro označení vlákna. Chcete-li příznak vláken, použijte místní nabídky nebo první buňky vlákna. 

     Na panelu nástrojů klikněte **zobrazit jenom příznakem** tlačítko vedle pole se seznamem.  

     ![Paralelní zásobníky okno a popis tlačítka](../debugger/media/pdb_walkthrough_3a.png "PDB_Walkthrough_3A")  

     Pouze s příznakem vlákno se zobrazí v **paralelní zásobníky** okno.
  
#### <a name="to-resume-execution-until-the-third-breakpoint"></a>Chcete-li pokračovat v provádění až třetí zarážek  
  
1.  Chcete-li pokračovat v provádění dokud třetí zarážek přístupů, na **ladění** nabídky, klikněte na tlačítko **pokračovat**.  
  
     Více vláken jsou ve stejné metody, ale metoda nebyla na začátku zásobníku volání, zobrazí se v různých polí metodu. Je například u aktuální zarážky S.L, který se nachází tři vlákna a zobrazí se tří polí. Klikněte dvakrát na j.  
  
     ![Cesta spuštění v okně paralelní zásobníky](../debugger/media/pdb_walkthrough_3b.png "PDB_Walkthrough_3B")  
  
     Všimněte si, že je S.L tučné do dalších polí, aby mohli zobrazit, kde jinak se zobrazí. Pokud chcete zobrazit rámce, který volání do S.L a které rámců, se volání, klikněte **přepnout metoda zobrazení** tlačítka na panelu nástrojů. Následující obrázek znázorňuje metoda zobrazení **paralelní zásobníky** okno.  
  
     ![Zobrazení metody v okně paralelní zásobníky](../debugger/media/pdb_walkthrough_4.png "PDW_Walkthrough_4")  
  
     Všimněte si, jak diagram seskupit na vybrané metodě a umístěný v jeho vlastní pole uprostřed zobrazení. Se zobrazí v horní a dolní volané a volající. Klikněte na tlačítko **přepnout metoda zobrazení** tlačítko nechte tento režim.  
  
     V místní nabídce **paralelní zásobníky** okno má také následující další položky.  
  
    -   **Hexadecimální zobrazení** přepíná čísla v popisech mezi desetinných míst a šestnáctkové číslo.  
  
    -   **Symbolů nastavení** otevřete příslušných dialogových oken.  
  
    -   **Zobrazit vláken ve zdroji** Přepíná zobrazení značek přístup z více vláken ve zdrojovém kódu, který ukazuje umístění vláken ve zdrojovém kódu.
  
    -   **Zobrazit externí kód** zobrazí všechny snímky, i když nejsou v uživatelského kódu. Vyzkoušejte podívejte se na diagram rozšířit, aby odpovídala další snímky (které může být neaktivní, protože nemáte symboly pro ně).  

2.  V **paralelní zásobníky** okna, ujistěte se, že **automaticky přejít na aktuální rámec zásobníku** na panelu nástrojů zobrazí tlačítko je na.  

     Pokud máte velké diagramy a krok na další zarážku, může být vhodné zobrazení tak, aby automaticky posuňte active zásobníku aktuální vlákno; To znamená, vlákno, které nejprve průchodu zarážkou.
  
3.  Než budete pokračovat, v **paralelní zásobníky** okno, posuňte všechny způsobem, jak levé straně a úplně dolů.  
  
#### <a name="to-resume-execution-until-the-fourth-breakpoint"></a>Chcete-li pokračovat v provádění dokud čtvrtý zarážek  
  
1.  Chcete-li pokračovat v provádění dokud čtvrtý zarážek přístupů, na **ladění** nabídky, klikněte na tlačítko **pokračovat**.  
  
     Všimněte si jak autoscrolled zobrazení na místě. Přepínač vláken v **vláken** Přijaté rámce zásobníku okno nebo přepínač **zásobníkem volání** okno a Všimněte si, jak zobrazení vždy autoscrolls na správný snímek. Vypnout **automaticky přejít na aktuální snímek nástroj** možnost a zobrazit rozdíl.  
  
     **Pohled z ptačí perspektivy** také pomáhá s velkých diagramů v **paralelní zásobníky** okno. Ve výchozím nastavení **pohled z ptačí perspektivy** zapnutý. Ale můžete přepnout ho kliknutím na tlačítko mezi posuvníky v pravém dolním rohu okna, jak je znázorněno na následujícím obrázku.  
  
     ![Ptačí perspektivy na&#45;oční zobrazení v okně paralelní zásobníky](../debugger/media/pdb_walkthrough_5.png "PDB_Walkthrough_5")  
  
     V pohled z ptačí perspektivy je možné přesunout rámeček k rychlému posouvání zobrazení diagramu.  
  
     Klikněte na prázdnou oblast diagramu a přetáhněte ji na požadované místo je jiný způsob, jak přesunout diagram vede libovolným směrem.  
  
     Chcete-li oddálit diagramu, stiskněte a podržte klávesu CTRL a přesunout kolečko myši. Případně klikněte na tlačítko přiblížení na panelu nástrojů a pak použít nástroj Lupa.  
  
     Můžete také zobrazit zásobníky shora dolů směrem místo zdola nahoru, kliknutím **nástroje** nabídce kliknete na **možnosti**a potom vyberte nebo zrušte zaškrtnutí políčka v části **ladění** uzlu.  
  
2.  Než budete pokračovat, na **ladění** nabídky, klikněte na tlačítko **Zastavte ladění** k provádění end.  
  
## <a name="using-the-parallel-tasks-window-and-the-tasks-view-of-the-parallel-stacks-window"></a>Použití okna paralelní úlohy a úlohy zobrazení okna paralelní zásobníky  
 Doporučujeme dokončit postupy starší, než budete pokračovat.  
  
#### <a name="to-restart-the-application-until-the-first-breakpoint-is-hit"></a>Znovu spustit, dokud první zarážky průchodu  
  
1.  Na **ladění** nabídky, klikněte na tlačítko **spustit ladění** a počkat na první zarážky být narazí.  
  
2.  Na **ladění** nabídky, přejděte na příkaz **Windows** a pak klikněte na **vláken**. Ukotvení **vláken** okna v dolní části sady Visual Studio.  
  
3.  Na **ladění** nabídky, přejděte **Windows** a klikněte na tlačítko **zásobníkem volání**. Ukotvení **zásobníkem volání** okno dole v sadě Visual Studio.  
  
4.  Klikněte dvakrát na vlákno v **vláken** okna je aktuální. Aktuální vláken obsahovat žlutou šipku. Když změníte aktuální vlákno, jsou aktualizovány jiných systému windows. V dalším kroku vyzkoušíme úlohy.  
  
5.  Na **ladění** nabídky, přejděte na příkaz **Windows**a potom klikněte na **úlohy**. Následující obrázek ukazuje **úlohy** okno.  
  
     ![Čtyři spuštění úloh v okně úlohy](../debugger/media/pdb_walkthrough_6.png "PDW_Walkthrough_6")  
  
     Pro každý úkol spuštěný si můžete přečíst jeho ID, která je vrácena vlastnost se stejným názvem, ID a název vlákno, které spouští, jeho umístění (ukazatele myši na tento zobrazí popisek, který má zásobníku volání celou). Také v části **úloh** sloupce, zobrazí se metoda, která byla předána do úlohy; jinými slovy, výchozím bodem.  
  
     Žádný sloupec lze seřadit. Všimněte si, řazení glyf, který označuje sloupec pro řazení a směr. Můžete také změnit pořadí sloupců tak, že je přetáhnete doleva nebo doprava.  
  
     Žlutá šipka označuje aktuální úlohy. Úlohy můžete přepnout dvojitým kliknutím na úlohu nebo pomocí místní nabídky. Po přepnutí úlohy základní vlákno se změní na aktuální a další okna se aktualizují.  
  
     Přepnete ručně od jednoho do jiného, přesune šipku žlutý, ale bílé šipku dál ukazuje úkol, který způsobil ladicí program na přerušení.  
  
#### <a name="to-resume-execution-until-the-second-breakpoint"></a>Chcete-li pokračovat v provádění až druhý zarážek  
  
1.  Chcete-li pokračovat v provádění dokud druhý zarážek přístupů, na **ladění** nabídky, klikněte na tlačítko **pokračovat**.  
  
     Dříve **stav** sloupec vám ukázal všechny úlohy, jako aktivní, ale teď dvě úlohy jsou zablokované. Úlohy mohou být blokovány mnoha různých důvodů. V **stav** sloupce, při přechodu na úlohu čekání na další informace, proč je blokovaný. Na následujícím obrázku je například úloha 3 čekání na úloha 4.  
  
     ![Dvě čekání úlohy v okně úlohy](../debugger/media/pdb_walkthrough_7.png "PDB_Walkthrough_7")  
  
     Úloha 4, pak čeká na monitorování vlastníkem vlákno přiřazen k úloze 2. (Klikněte pravým tlačítkem myši na záhlaví a zvolte **sloupce** > **vlákno přiřazení** zobrazíte hodnotu přiřazení vlákno pro úloha 2).
  
     ![Čeká se na úlohy a popisu tlačítka v okně úlohy](../debugger/media/pdb_walkthrough_7a.png "PDB_Walkthrough_7A")
  
     Úlohu můžete označit příznakem, kliknete na příznak v první sloupec **úlohy** okno.  
  
     Nastavením příznaku můžete použít ke sledování úloh mezi různé zarážky ve stejné relaci ladění nebo vyfiltrujete pro úlohy, jejichž zásobníky volání se zobrazují v **paralelní zásobníky** okno.  
  
     Pokud jste použili **paralelní zásobníky** okno dříve, můžete zobrazit vláken aplikace. Zobrazení **paralelní zásobníky** znovu okno, ale tentokrát zobrazit úlohy aplikace. To provedete zaškrtnutím **úlohy** do pole v levé horní části. Následující obrázek znázorňuje zobrazení úloh.  
  
     ![Úlohy zobrazení v okně paralelní zásobníky](../debugger/media/pdb_walkthrough_8.png "PDB_Walkthrough_8")  
  
     Vláken, která nejsou aktuálně provádění úlohy nejsou zobrazeny v zobrazení úlohy **paralelní zásobníky** okno. Navíc pro vlákna, které se spouští úlohy, některé rámce zásobníku, které nejsou relevantní pro úlohy jsou filtrovány z horní a dolní části zásobníku.  
  
     Zobrazení **úlohy** znovu okno. Klikněte pravým tlačítkem na libovolné záhlaví sloupce zobrazíte místní nabídku pro sloupec.  
  
     Místní nabídky můžete přidat nebo odebrat sloupce. Například není vybraný sloupec AppDomain; Proto se nezobrazí v seznamu. Klikněte na tlačítko **nadřazené**. **Nadřazené** bez hodnot pro všechny čtyři úlohy, zobrazí se sloupec.  
  
#### <a name="to-resume-execution-until-the-third-breakpoint"></a>Chcete-li pokračovat v provádění až třetí zarážek  
  
1.  Chcete-li pokračovat v provádění dokud třetí zarážek přístupů, na **ladění** nabídky, klikněte na tlačítko **pokračovat**.  
  
     Nový úkol, úloha 5, je nyní spuštěna a nyní čeká úloha 4. Uvidíte, proč podržením ukazatele nad čekání úlohy v **stav** okno. V **nadřazené** sloupce, Všimněte si, že úloha 4 je nadřazená úloha 5.  
  
     Pro lepší vizualizaci relaci nadřazený podřízený, klikněte pravým tlačítkem myši na záhlaví sloupce a potom klikněte na **nadřazeného a podřízeného prvku**. Měli byste vidět na následujícím obrázku.  
  
     ![Nadřazené&#45;podřízené zobrazení v okně úlohy](../debugger/media/pdb_walkthrough_9.png "PDB_Walkthrough_9")  
  
     Všimněte si, že úloha 4 a 5 úloha běží ve stejném vlákně (Zobrazit **vlákno přiřazení** sloupce, pokud je skrytý). Tyto informace se nezobrazí v **vláken** období; zobrazuje, zde je Další výhodou **úlohy** okno. Chcete-li to ověřit, podívejte se **paralelní zásobníky** okno. Ujistěte se, že jsou zobrazeny **úlohy**. Vyhledejte úlohy 4 a 5 poklepáním na tyto v **úlohy** okno. Když to uděláte, modré zvýraznění **paralelní zásobníky** okno se aktualizuje. Můžete také vyhledat úlohy 4 a 5 naskenováním popisky tlačítek na **paralelní zásobníky** okno.  
  
     ![Úlohy zobrazení v okně paralelní zásobníky](../debugger/media/pdb_walkthrough_9a.png "PDB_Walkthrough_9A")  
  
     V **paralelní zásobníky** oken, klikněte pravým tlačítkem na S.P a pak klikněte na tlačítko **přejděte do vláken**. Okno přepne do zobrazení vláken a odpovídající snímek je v zobrazení. Ve stejném vlákně, uvidíte obě úlohy.  
  
     ![Zvýrazněná vlákna v zobrazení vláken](../debugger/media/pdb_walkthrough_9b.png "PDB_Walkthrough_9B")  
  
     To je Další výhodou zobrazení úkolů na **paralelní zásobníky** okna, ve srovnání s **vláken** okno.  
  
#### <a name="to-resume-execution-until-the-fourth-breakpoint"></a>Chcete-li pokračovat v provádění dokud čtvrtý zarážek  
  
1.  Chcete-li pokračovat v provádění dokud třetí zarážek přístupů, na **ladění** nabídky, klikněte na tlačítko **pokračovat**. Klikněte **ID** záhlaví sloupce seřadíte podle ID. Měli byste vidět na následujícím obrázku.  
  
     ![Čtyři úkolů stavů v okna paralelní zásobníky](../debugger/media/pdb_walkthrough_10.png "PDB_Walkthrough_10")  
  
     Protože dokončení úlohy 5, je již zobrazen. Pokud se nejedná o tento případ ve vašem počítači a k zablokování není zobrazený, krok jednou stisknutím **F11**.  
  
     Úloha 3 a 4 úloh jsou nyní čeká na sobě navzájem a jsou zablokované. Existují také 5 nové úlohy, které jsou podřízené úloha 2 a je nyní naplánováno. Naplánované úlohy jsou úlohy, které byly spuštěny v kódu, ale ještě nebyl spuštěn. Proto jejich **umístění** a **vláken přiřazení** sloupce jsou prázdné.  
  
     Zobrazení **paralelní zásobníky** znovu okno. Hlavička každé pole obsahuje popis, který ukazuje názvy a ID vlákna. Umožňuje přepnout do zobrazení úlohy v **paralelní zásobníky** okno. Pozastavte ukazatel myši nad hlavičku zobrazíte ID úkolu a název a stav úlohy, jak je znázorněno na následujícím obrázku.  
  
     ![Záhlaví popisu tlačítka v okně paralelní zásobníky](../debugger/media/pdb_walkthrough_11.png "PDB_Walkthrough_11")  
  
     Úlohy můžete seskupovat podle sloupce. V **úlohy** okna, klikněte pravým tlačítkem myši **stav** záhlaví sloupce a pak klikněte na tlačítko **seskupení podle stavu**. Následující obrázek ukazuje **úlohy** okno seskupené podle stavu.  
  
     ![Seskupené úlohy v okně úlohy](../debugger/media/pdb_walkthrough_12.png "PDB_Walkthrough_12")  
  
     Můžete taky Seskupit podle jiné sloupce. Seskupování úlohami můžete se zaměřit na podmnožinu úlohy. Každá skupina sbalitelné obsahuje počet položek, které jsou seskupeny dohromady.
  
     Poslední funkci **úlohy** okno prozkoumat je místní nabídky, která se zobrazí, když kliknete pravým tlačítkem na úlohu.  
  
     Místní nabídky zobrazí jiné příkazy, v závislosti na stavu úlohy. Příkazy může zahrnovat **kopie**, **Vybrat vše**, **hexadecimální zobrazení**, **přepnout úloh**, **Freeze – přiřazené Přístup z více vláken**, **Freeze všechna vlákna, to ale**, a **odblokování přiřazené vlákno**, a **příznak**.  
  
     Lze ukotvit základní vlákno úlohy nebo úlohy, nebo můžete zmrazení všechna vlákna s výjimkou toho, přiřazené. Ukotvené vlákno je reprezentována v **úlohy** je okno jak **vláken** okno podle modrá *pozastavit* ikonu.  
  
## <a name="summary"></a>Souhrn  
 Tento názorný postup ukázáno **paralelních úloh** a **paralelní zásobníky** ladicího programu systému windows. Pomocí těchto systému windows na skutečné projektů, které využívají vícevláknové kódu. Můžete zkontrolovat paralelní kód napsaný v C++, C# nebo Visual Basic.  
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/walkthrough-debugging-a-parallel-application.md)   
 [Základy ladicího programu](../debugger/debugger-basics.md)   
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [Paralelní programování](/dotnet/standard/parallel-programming/index)   
 [Concurrency Runtime](/cpp/parallel/concrt/concurrency-runtime)   
 [Použití okna paralelní zásobníky](../debugger/using-the-parallel-stacks-window.md)   
 [Používání okna úloh](../debugger/using-the-tasks-window.md)