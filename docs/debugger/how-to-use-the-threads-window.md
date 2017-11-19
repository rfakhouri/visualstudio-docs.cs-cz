---
title: "Ladění vícevláknové aplikace s použití okna vláken | Microsoft Docs"
ms.custom: H1HackMay2017
ms.date: 05/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- multithreaded debugging, tutorial
- tutorials, multithreaded debugging
ms.assetid: adfbe002-3d7b-42a9-b42a-5ac0903dfc25
caps.latest.revision: "38"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4469f2f70bececca258fe4ea1a98d753f8349f87
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-debug-a-multithreaded-application-in-visual-studio-using-the-threads-window"></a>Návod: Ladění vícevláknové aplikace v sadě Visual Studio pomocí okna vláken
Visual Studio poskytuje **vláken** prvky můžete ladění vícevláknových aplikací rozhraní okna a jiný uživatel. Tento kurz ukazuje, jak používat **vláken** okno a **ladění umístění** panelu nástrojů. Informace o dalších nástrojů najdete v tématu [Začínáme ladění vícevláknové aplikace](../debugger/get-started-debugging-multithreaded-apps.md). V tomto kurzu trvá jenom pár minut, ale jeho dokončení vás seznámí s funkcemi pro ladění vícevláknové aplikace.   
  
Zahájíte tento kurz, musíte projekt vícevláknové aplikace. Postupujte podle kroků uvedených v tomto poli k vytvoření tohoto projektu.  
  
#### <a name="to-create-the-multithreaded-app-project"></a>Chcete-li vytvořit projekt vícevláknové aplikace  
  
1.  Na **soubor** nabídce zvolte **nový** a pak klikněte na **projektu**.  
  
     **Nový projekt** zobrazí se dialogové okno.  
  
2.  V **typu projektu**s pole, klikněte na tlačítko jazyk podle vašeho výběru: **jazyka Visual Basic**, **Visual C#**, nebo **Visual C++**.  
  
3.  V **šablony** vyberte **konzolovou aplikaci**.  
  
4.  V **název** pole, zadejte název MyThreadWalkthroughApp.  
  
5.  Click **OK**.  
  
     Zobrazí se nový projekt konzoly. Po vytvoření projektu, zobrazí se zdrojový soubor. V závislosti na jazyk, který jste zvolili může být například zdrojového souboru Module1.vb, Program.cs nebo MyThreadWalkthroughApp.cpp  
  
6.  Odstranit kód, který se zobrazí v zdrojový soubor a nahraďte ji metodou ukázkový kód, který se zobrazí v části "Vytvoření vlákna" tématu [vytváření vláken a předávání dat na čas spuštění](/dotnet/standard/threading/creating-threads-and-passing-data-at-start-time).  
  
7.  Na **soubor** nabídky, klikněte na tlačítko **Uložit vše**.  
  
#### <a name="to-begin-the-tutorial"></a>Chcete-li začít kurz  
  
-   V editoru kódu zdroj vyhledejte následující kód:  
  
    ```VB  
    Thread.Sleep(3000)   
    Console.WriteLine(  
    ```  
  
    ```CSharp  
    Thread.Sleep(3000);  
    Console.WriteLine();  
    ```  
  
    ```C++  
    Thread::Sleep(3000);  
    Console.WriteLine();  
    ```  
  
#### <a name="to-start-debugging"></a>Spustit ladění  
  
1.  Klikněte v levém oddělovací mezery u `Console.WriteLine` příkaz Vložit nový zarážky.  
  
     V oddělovací mezery na levé straně editoru zdrojového kódu zobrazí se červeném kroužku. To znamená, že v tomto umístění je teď nastavený bod přerušení.  
  
2.  Na **ladění** nabídky, klikněte na tlačítko **spustit ladění** (**F5**).  
  
     Ladění spustí, vaše aplikace spuštění konzoly ke spuštění a pak zastaví u zarážky.  
  
3.  V okně konzoly aplikace v tomto okamžiku má fokus, klikněte na [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] okno a vrátit se k [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
4.  V editoru zdrojového kódu vyhledejte řádek, který obsahuje následující kód:  
  
    ```VB  
    Thread.Sleep(5000)   
    ```  
  
    ```CSharp  
    Thread.Sleep(3000);  
    ```  
  
    ```C++  
    Thread::Sleep(3000);  
    ```
  
#### <a name="to-discover-the-thread-marker"></a>Ke zjištění značky přístup z více vláken  

1.  Na panelu nástrojů pro ladění, klikněte **zobrazit vláken ve zdroji** tlačítko ![zobrazit vláken ve zdroji](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker"). 
  
2.  Podívejte se na oddělovací mezery na levé straně okna. Na tomto řádku se zobrazí *vlákno značky* ikonu ![vlákno značky](../debugger/media/dbg-thread-marker.png "ThreadMarker") , která se podobá dvěma vlákny hadříkem. Vlákno značky označuje, že vlákno je zastavená v tomto umístění.  
  
3.  Umístění ukazatele myši značky přístup z více vláken. Zobrazí se popis dat. Popis dat poznáte, název a vlákno identifikační číslo pro každé zastavené vlákno. V takovém případě je pouze jedno vlákno, jejíž název je pravděpodobně `<noname>`.  

    > [!TIP]
    > Vám může být užitečné k identifikaci nameless vláken je přejmenováním. V okně vláken zvolte **přejmenovat** po pravým tlačítkem myši na **název** sloupec v řádku přístup z více vláken.
  
4.  Klikněte pravým tlačítkem na vlákno značky zobrazíte možnosti dostupné v místní nabídce. 
    
  
## <a name="flagging-and-unflagging-threads"></a>Označení a Unflagging vlákna  
Můžete označit příznakem vláken, které chcete udělit zvláštní pozornost. Označování vláken je vhodné můžete sledovat důležité vláken a vláken, které nechcete o ignorovat.  
  
#### <a name="to-flag-threads"></a>Chcete-li příznak vláken   

1.  Na **zobrazení** nabídky, přejděte na příkaz **panely nástrojů**.  
  
    Ujistěte se, že **ladění umístění** je vybrán panel nástrojů.

2.  Přejděte na **ladění umístění** panelu nástrojů a klikněte na tlačítko **vláken** seznamu.  
  
    > [!NOTE]
    >  Tento panel nástrojů poznáte tři hlavní seznamy: **proces**, **vláken**, a **rámce zásobníku**.  
  
3.  Všimněte si, kolik vláken zobrazí v seznamu.  
  
4.  Přejděte zpět do editoru zdrojového kódu a klikněte pravým tlačítkem na vlákno značky ![vlákno značky](../debugger/media/dbg-thread-marker.png "ThreadMarker") znovu.  
  
5.  V místní nabídce přejděte na **příznak**a potom klikněte na název přístup z více vláken a identifikační číslo.  
  
6.  Přejděte zpět na **ladění umístění** panelu nástrojů a najít **zobrazit jenom příznakem vláken** ikonu ![zobrazit příznakem vláken](../debugger/media/dbg-threads-show-flagged.png "ThreadMarker") do napravo od **vláken** seznamu.  
  
    Ikona příznaky na tlačítko byla neaktivní před. Nyní je aktivní tlačítko.  
  
7.  Klikněte **zobrazit jenom příznakem vláken** ikonu.  
  
    Pouze označení vlákno se zobrazí v seznamu nyní. (Můžete kliknutím na tlačítko jeden příznak přepněte zpět na **zobrazit všechna vlákna** režimu.)

8. Otevřete okno vláken výběrem **ladění > Windows > vláken**.

    ![Vláken okno](../debugger/media/dbg-threads-window.png "ThreadsWindow")  
  
    V **vláken** okně označení vlákna má ikonu viditelného červený příznak k němu připojen.

    > [!TIP]
    > Když příznakem některé vláken, můžete klikněte pravým tlačítkem myši na řádek kódu v editoru kódu a vyberte **spustit příznakem podprocesů pro kurzor** (ujistěte se, abyste zvolili kódu, že všechny příznakem vláken dosáhnou). To se pozastaví vláken na vybraný řádek kódu, takže je snazší řízení pořadí provádění podle [zmrazení a uvolnění vláken](#bkmk_freeze).
  
11. V editoru kódu zdroj znovu klikněte pravým tlačítkem značky přístup z více vláken.  
  
     Všimněte si, jaké možnosti jsou nyní k dispozici v místní nabídce. Místo **příznak**, teď najdete **Unflag**. Neklikejte na **Unflag**.  

     Chcete-li zjistit, jak k odstranění označení vlákna, přejděte k dalšímu postupu.  
  
#### <a name="to-unflag-threads"></a>K odstranění označení vlákna  
  
1.  V **vláken** okna, klikněte pravým tlačítkem myši na řádku odpovídající označení vlákna.  
  
     Zobrazí se místní nabídky. Obsahuje možnosti pro **Unflag** a **odstranění označení všechna vlákna**.  
  
2.  Chcete-li odstranění označení vlákna, klikněte na tlačítko **Unflag**.  

    Podívejte se na **ladění umístění** znovu panelu nástrojů. **Zobrazit jenom příznakem vláken** tlačítko znovu aktivní. Můžete unflagged pouze označení vlákna. Protože nejsou k dispozici nejsou žádná označení vlákna, panelu nástrojů přešel zpět do **zobrazit všechna vlákna** režimu. Klikněte **vláken** seznamu a ověřte, zda se zobrazí všechna vlákna.  
  
5.  Přejděte zpět **vláken** okno a zkontrolujte informace sloupce.  
  
    V první sloupec si všimnete ikonou vlajky obrysu v jednotlivých řádcích seznamu přístup z více vláken. (Obrys znamená, že vlákno se bez příznaku.)  
  
6.  Kliknutím na ikony outline příznak pro dvě vláken, druhý a třetí v dolní části seznamu. 

    Ikony příznak stát plný červený místo dutý jsou podrobněji popsány dále.  
  
7.  Klikněte na tlačítko v horní části sloupce Příznak.  
  
    Pořadí seznamu vláken změnit, pokud jste klikli na tlačítko. Seznam vláken je nyní řazená označení vlákna nahoře.  
  
8.  Znovu klikněte na tlačítko v horní části sloupce Příznak.  
  
    Pořadí řazení změnit znovu.  
  
## <a name="more-about-the-threads-window"></a>Další informace o okna vláken  
  
#### <a name="to-learn-more-about-the-threads-window"></a>Další informace o okna vláken  
  
1.  V **vláken** okně zkontrolujte třetí sloupec vlevo. Tlačítka v horní části Tento sloupec uvádí **ID**.  
  
2.  Klikněte na tlačítko **ID**.  
  
     Seznam vláken je nyní seřazené podle číslo ID vlákna.  
  
3.  Klikněte pravým tlačítkem na libovolného vlákna v seznamu. V místní nabídce klikněte na tlačítko **hexadecimální zobrazení**.  
  
     Formát čísla ID vlákna se změní.  
  
4.  Podržte ukazatel myši nad **umístění** u libovolného vlákna v seznamu ve sloupci.  
  
     Po aktuálně zpoždění zobrazí se datového tipu. Zobrazuje zásobníku částečné volání pro vlákno.

     > [!TIP]
     > Grafické zobrazení zásobníky volání pro vlákna, otevřete [paralelní zásobníky](../debugger/using-the-parallel-stacks-window.md) okno (při ladění, zvolte **ladění / Windows / paralelní zásobníky**).  
  
5.  Podívejte se na čtvrtém sloupci zleva, který je označený **kategorie**. Do kategorie klasifikace vláken.  
  
     První vlákno vytvořené v proces se označuje jako hlavní vlákno. Najděte v seznamu přístup z více vláken.  
  
6.  Klikněte pravým tlačítkem na hlavní vlákno a pak klikněte na **přepnout na vlákno**.  
  
     A **rozdělit režimu** se zobrazí v okně. Zde zjistíte, že ladicí program není aktuálně provádění kód, který můžete zobrazit, (protože je hlavní vlákno).   
  
7.  Podívejte se na **zásobníkem volání.** okno a **ladění umístění** panelu nástrojů.  
  
     Obsah **zásobníkem volání** okno změnily. 

## <a name="bkmk_freeze"></a>Zmrazení a uvolnění provádění vlákna 

Lze ukotvit a uvolnit (pozastavení a obnovení) vláken určit pořadí, ve kterém vláken práci. To vám může pomoct vyřešit potíže se souběžností například blokování a stavy soupeření.

> [!TIP]
> Pokud chcete, postupujte podle jedním vláknem a bez zmrazení jiná vlákna (také běžný ladění scénář), najdete v článku [Začínáme ladění vícevláknové aplikace](../debugger/get-started-debugging-multithreaded-apps.md#bkmk_follow_a_thread).
  
#### <a name="to-freeze-and-unfreeze-threads"></a>Chcete-li ukotvení a uvolnění vláken  
  
1.  V **vláken** okna, klikněte pravým tlačítkem na libovolného vlákna a pak klikněte na **Freeze**.  
  
2.  Podívejte se na druhý sloupec (aktuální vlákno sloupec). Ikona pozastavení se teď zobrazí existuje. Tato ikona pozastavení označuje, že vlákno nereaguje.  
  
3.  Zobrazit **pozastaveno počet** sloupec tak, že ho vyberete **sloupce** seznamu.

    Počet pozastavit pro vlákno je nyní 1.  
  
4.  Klikněte pravým tlačítkem na ukotvené vlákno a pak klikněte na **odblokování**.  
  
     Aktuální vlákno sloupec a **pozastaveno počet** změnit sloupec. 
  
## <a name="switching-the-to-another-thread"></a>Přepnutí jiné vlákno 
  
#### <a name="to-switch-threads"></a>Chcete-li přepnout vláken  
  
1.  V **vláken** okně zkontrolujte druhý sloupec zleva (aktuální vlákno sloupec). Tlačítka v horní části v tomto sloupci nemá žádný text nebo ikonu.
  
2.  Podívejte se na aktuální vlákno sloupec a Všimněte si, že má jedno vlákno žlutý šipku. Žlutá šipka označuje, že tento přístup z více vláken je aktuální vlákno (Toto je aktuální umístění ukazatele spuštění).
  
    Poznamenejte si číslo ID vlákna kde uvidíte ikonu aktuální vlákno. Ikonu aktuální vlákno se přesune na jiné vlákno, ale je nutné pro něj znovu po dokončení. 
  
3.  Klikněte pravým tlačítkem na jiné vlákno a pak klikněte na **přepnout na vlákno**.  
  
4.  Podívejte se na **zásobníkem volání** okno v editoru zdrojového kódu. Obsah se změnil.  
  
5.  Podívejte se na **ladění umístění** panelu nástrojů. Ikonu aktuální vlákno došlo ke změně došlo, příliš.  
  
6.  Přejděte na **ladění umístění** panelu nástrojů. Vyberte jiné vlákno z **vlákno** seznamu.  
  
7.  Podívejte se na **vláken** okno. Došlo ke změně ikonu aktuální vlákno.  
  
8. V editoru kódu zdroj klikněte pravým tlačítkem na značku přístup z více vláken. V místní nabídce přejděte na **přepnout na vlákno** a klikněte na název nebo ID číslo přístup z více vláken.  
  
     Nyní jste viděli tři způsoby změny ikonu aktuální vlákno na jiné vlákno: pomocí **vláken** okně **přístup z více vláken** v seznamu **ladění umístění** nástrojů a vlákno značky v editoru zdrojového kódu.  
  
     Pomocí hodnoty přístup z více vláken můžete přepnout pouze vláken, které jsou zastaveny v tomto konkrétní umístění. Pomocí **vláken** okno a **ladění umístění** nástrojů můžete přepnout do libovolného vlákna.   
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Postupy: přepnutí na jiné vlákno během ladění](../debugger/how-to-switch-to-another-thread-while-debugging.md)