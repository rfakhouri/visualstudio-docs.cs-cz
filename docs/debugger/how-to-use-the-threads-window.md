---
title: Ladění vícevláknových aplikací
description: Ladění pomocí okna vláken a panelu nástrojů umístění ladění v sadě Visual Studio
ms.custom: ''
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- multithreaded debugging, tutorial
- tutorials, multithreaded debugging
ms.assetid: adfbe002-3d7b-42a9-b42a-5ac0903dfc25
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bcd3a3f47af8251f6f4bfa1b5b5f08da7a1f3e3e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49933557"
---
# <a name="walkthrough-debug-a-multithreaded-application-in-visual-studio-using-the-threads-window"></a>Návod: Ladění vícevláknové aplikace v sadě Visual Studio pomocí okna vlákna
Visual Studio poskytuje **vlákna** prvky si můžete usnadnit ladění aplikací s více vlákny rozhraní okna a jinými uživateli. Tento kurz ukazuje způsob použití **vlákna** okno a **umístění ladění** nástrojů. Informace o dalších nástrojů, naleznete v tématu [Začínáme s laděním vícevláknových aplikací](../debugger/get-started-debugging-multithreaded-apps.md). Tento kurz trvá jenom několik minut, ale jeho dokončení se můžete seznámit s funkcemi pro ladění aplikací s více vlákny.   
  
Pokud chcete začít tento kurz, potřebujete projekt aplikace s více vlákny. Postupujte podle kroků uvedených zde k vytvoření tohoto projektu.  
  
#### <a name="to-create-the-multithreaded-app-project"></a>Chcete-li vytvořit projekt aplikace s více vlákny  
  
1.  Na **souboru** nabídce zvolte **nový** a potom klikněte na tlačítko **projektu**.  
  
     **Nový projekt** zobrazí se dialogové okno.  
  
2.  V **typu projektu**s poli, klikněte na jazyk podle vašeho výběru: **jazyka Visual Basic**, **Visual C#**, nebo **Visual C++**.  
  
3.  V části **Windows Desktop**, zvolte **konzolovou aplikaci**.  
  
4.  V **název** pole, zadejte název MyThreadWalkthroughApp.  
  
5.  Klikněte na tlačítko **OK**.  
  
     Zobrazí se nový projekt konzoly. Po vytvoření projektu se zobrazí zdrojový soubor. V závislosti na jazyku, kterou jste zvolili může volat zdrojový soubor Module1.vb, Program.cs nebo MyThreadWalkthroughApp.cpp  
  
6.  Odstranit kód, který se zobrazí ve zdrojovém souboru a nahraďte ji metodou ukázkový kód, který se zobrazí v části "Vytvoření vlákna" v tématu [vytváření vláken a předávání dat v době spuštění](/dotnet/standard/threading/creating-threads-and-passing-data-at-start-time).  
  
7.  Na **souboru** nabídky, klikněte na tlačítko **Uložit vše**.  
  
#### <a name="to-begin-the-tutorial"></a>Chcete-li začít kurz  
  
-   V editoru zdrojového kódu vyhledejte následující kód:  
  
    ```VB  
    Thread.Sleep(3000)   
    Console.WriteLine()
    ```  
  
    ```csharp  
    Thread.Sleep(3000);  
    Console.WriteLine();  
    ```  
  
    ```C++  
    Thread::Sleep(3000);  
    Console.WriteLine();  
    ```  
  
#### <a name="to-start-debugging"></a>Pro spuštění ladění  
  
1. Klikněte v levém hřbetu z `Console.WriteLine` příkazu k vložení novou zarážku.  
  
    Na levé straně editoru zdrojového kódu na ovládací prvek zobrazí se červený kruh. To znamená, že na tomto místě je nyní nastaveno zarážku.  
  
2. Na **ladění** nabídky, klikněte na tlačítko **spustit ladění** (**F5**).  
  
    Zahájením ladění, vaše aplikace spustí konzolu ke spuštění a pak zastaví na zarážce.  
  
3. Okno aplikace konzoly v tomto okamžiku má fokus, klikněte na tlačítko v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] okno a vraťte se na [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
4. V editoru zdrojového kódu vyhledejte řádek, který obsahuje následující kód:  
  
   ```VB  
   Thread.Sleep(5000)   
   ```  
  
   ```csharp  
   Thread.Sleep(3000);  
   ```  
  
   ```C++  
   Thread::Sleep(3000);  
   ```
  
#### <a name="to-discover-the-thread-marker"></a>Ke zjištění značky vlákna  

1.  Na panelu nástrojů pro ladění, klikněte na tlačítko **zobrazit vlákna ve zdroji** tlačítko ![zobrazit vlákna ve zdroji](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker"). 
  
2.  Podívejte se na ovládací prvek na levé straně okna. Na tomto řádku se zobrazí *značky vlákna* ikonu ![značky vlákna](../debugger/media/dbg-thread-marker.png "ThreadMarker") , který se podobá dvěma vlákny látky. Značky vlákna označuje, že je vlákno zastavené v tomto umístění.  
  
3.  Ukazatel myši značky vlákna. Zobrazí se DataTip. DataTip zjistíte číslo ID názvu a vlákna pro každé vlákno zastavené. V tomto případě existuje pouze jedno vlákno, jehož název je pravděpodobně `<noname>`.  

    > [!TIP]
    > Vám může být užitečné pro identifikaci nameless vlákna podle nich. V okně vlákna zvolte **přejmenovat** po klepnutí pravým tlačítkem na **název** sloupce v řádku vlákna.
  
4.  Klikněte pravým tlačítkem na značky vlákna zobrazíte dostupné možnosti v místní nabídce. 
    
  
## <a name="flagging-and-unflagging-threads"></a>Označení a Unflagging vlákna  
Můžete označit příznakem vlákna, která chcete věnovat zvláštní pozornost. Příznakem vlákna je dobrým způsobem ke sledování důležité vláken a pro ignorování vlákna, které vás nezajímají.  
  
#### <a name="to-flag-threads"></a>Označit vlákna   

1.  Na **zobrazení** nabídky, přejděte k **panely nástrojů**.  
  
    Ujistěte se, že **umístění ladění** vybrán panel nástrojů.

2.  Přejděte **umístění ladění** nástrojů a klikněte na tlačítko **vlákna** seznamu.  
  
    > [!NOTE]
    >  Tento panel nástrojů můžete rozpoznat podle tři viditelného seznamy: **procesu**, **vlákna**, a **rámec zásobníku**.  
  
3.  Všimněte si, kolik vlákna se zobrazují v seznamu.  
  
4.  Přejděte zpět na editor zdrojového kódu a klikněte pravým tlačítkem na značky vlákna ![značky vlákna](../debugger/media/dbg-thread-marker.png "ThreadMarker") znovu.  
  
5.  V místní nabídce, přejděte na **příznak**a potom klikněte na název vlákna a identifikační číslo.  
  
6.  Přejděte zpět na **umístění ladění** nástrojů a Hledat **zobrazit pouze s příznakem vlákna** ikonu ![zobrazit vlákna s příznakem](../debugger/media/dbg-threads-show-flagged.png "ThreadMarker") k vpravo **vlákna** seznamu.  
  
    Příznaky ikony na tlačítku byla aktivní před. Nyní je aktivní tlačítko.  
  
7.  Klikněte na tlačítko **zobrazit pouze s příznakem vlákna** ikonu.  
  
    Pouze vlákno s příznakem se zobrazí v seznamu nyní. (Můžete kliknout na tlačítko jeden příznak přepnete zpět do **zobrazit všechna vlákna** režimu.)

8. Otevřete okno vláken výběrem **ladit > Windows > vlákna**.

    ![Vlákna okna](../debugger/media/dbg-threads-window.png "ThreadsWindow")  
  
    V **vlákna** okně vlákna s příznakem má ikonu viditelného rvená vlaječka k němu připojená.

    > [!TIP]
    > Pokud máte některá vlákna označená příznakem, můžete klikněte pravým tlačítkem na řádek kódu v editoru kódu a zvolte **spustit vlákna s příznakem do pozice kurzoru** (ujistěte se, že zvolíte dosáhne kódu, že všechny příznakem vlákna). To se pozastaví, vláken na vybraný řádek kódu, díky tomu je snadněji řídit pořadí provádění podle [zmrazení a uvolnění vláken](#bkmk_freeze).
  
11. V editoru zdrojového kódu klikněte pravým tlačítkem na značky vlákna znovu.  
  
     Všimněte si, jaké možnosti jsou teď dostupné v místní nabídce. Místo **příznak**, teď se vám **Unflag**. Neklikejte na **Unflag**.  

     Chcete-li zjistit, jak odstranění označení vlákna, přejděte k dalšímu postupu.  
  
#### <a name="to-unflag-threads"></a>K odstranění označení vlákna  
  
1.  V **vlákna** okna, klikněte pravým tlačítkem na řádek odpovídající vlákno s příznakem.  
  
     Zobrazí se místní nabídka. Obsahuje možnosti pro **Unflag** a **odznačit všechna vlákna**.  
  
2.  Odznačit vlákno, klikněte na tlačítko **Unflag**.  

    Podívejte se na **umístění ladění** nástrojů znovu. **Zobrazit pouze s příznakem vlákna** tlačítko znovu zobrazené šedě. Je odebrán příznak pouze vlákno s příznakem. Vzhledem k tomu, že neexistují žádná vlákna s příznakem, panelu nástrojů náramků RFID zpět do **zobrazit všechna vlákna** režimu. Klikněte na tlačítko **vlákna** seznam a ověřte, zda se zobrazí všechna vlákna.  
  
5.  Přejděte zpět **vlákna** okno a zkontrolovat informace o sloupci.  
  
    V prvním sloupci můžete si všimnout ikonou vlajky obrysu v jednotlivých řádcích seznamu vláken. (Obrys znamená, že je vlákna bez příznaku.)  
  
6.  Kliknutím na ikony osnovy příznak pro dvě vlákna, druhý a třetí v dolní části seznamu. 

    Ikony příznaků stát solid červené, namísto prázdný jsou podrobněji popsány dále.  
  
7.  Klikněte na tlačítko v horní části sloupce Příznak.  
  
    Pořadí seznamu vláken změnit, pokud jste klikli na tlačítko. Seznam vláken je teď seřazené s příznakem vlákna v horní části.  
  
8.  Znovu klikněte na tlačítko v horní části sloupce Příznak.  
  
    Pořadí řazení změnit znovu.  
  
## <a name="more-about-the-threads-window"></a>Další informace o okna vláken  
  
#### <a name="to-learn-more-about-the-threads-window"></a>Další informace o okna vláken  
  
1.  V **vlákna** okna, zkontrolujte třetí sloupec z levé strany. V horní části tohoto sloupce na tlačítku zobrazeno **ID**.  
  
2.  Klikněte na tlačítko **ID**.  
  
     Seznam vláken je teď seřazené podle číslo ID vlákna.  
  
3.  Klikněte pravým tlačítkem na jakékoli vlákno v seznamu. V místní nabídce klikněte na tlačítko **hexadecimální zobrazení**.  
  
     Formát čísla ID vlákna je změnit.  
  
4.  Najeďte myší na ukazatel myši **umístění** sloupec pro jakékoli vlákno v seznamu.  
  
     Momentální zpožděním zobrazí se DataTip. Zobrazuje částečné volání zásobníku pro vlákno.

     > [!TIP]
     > Grafické zobrazení zásobníky volání pro vlákna, otevřete [paralelní zásobníky](../debugger/using-the-parallel-stacks-window.md) okno (při ladění, zvolte **ladění / Windows / paralelní zásobníky**).  
  
5.  Podívejte se na čtvrtém sloupci zleva, který je označen **kategorie**. Vlákna jsou rozdělit do kategorií.  
  
     První vlákno v procesu vytvoří se označuje jako hlavní vlákno. Vyhledejte ho v seznamu vláken.  
  
6.  Klikněte pravým tlačítkem na hlavním vlákně a pak klikněte na tlačítko **přepnout na vlákno**.  
  
     A **režim přerušení** zobrazí se okno. Zjistíte, že ladicí program není aktuálně spuštěním jakéhokoli kódu, který může zobrazit (protože je hlavní vlákno).   
  
7.  Podívejte se na **zásobník volání** okno a **umístění ladění** nástrojů.  
  
     Obsah **zásobník volání** okno změnily. 

## <a name="bkmk_freeze"></a> Zmrazení a uvolnění provádění vlákna 

Můžete zablokovat a odblokovat (pozastavení a obnovení) určit pořadí, ve kterém provádění vlákna pracovních vláken. To může pomoct vyřešit potíže se souběžností například zablokování a konflikty časování.

> [!TIP]
> Pokud chcete postupovat podle jednoho vlákna bez zmrazení ostatní vlákna (také běžný ladicí scénář), přečtěte si téma [Začínáme s laděním vícevláknových aplikací](../debugger/get-started-debugging-multithreaded-apps.md#bkmk_follow_a_thread).
  
#### <a name="to-freeze-and-unfreeze-threads"></a>Ukotvit a uvolnit vlákna  
  
1.  V **vlákna** okna, klikněte pravým tlačítkem na libovolného vlákna a pak klikněte na **ukotvit**.  
  
2.  Podívejte se na druhý sloupec (aktuální vlákno sloupce). Ikona pozastavení se teď zobrazí existuje. Tyto pozastavení ikona značí, že vlákno je zmrazen.  
  
3.  Zobrazit **pozastavený počet** sloupec tak, že ho vyberete **sloupce** seznamu.

    Počet pozastavení pro vlákno je nyní 1.  
  
4.  Klikněte pravým tlačítkem na zmrazené vlákno a potom klikněte na tlačítko **uvolnit**.  
  
     Aktuální vlákno sloupce a **pozastavený počet** změny sloupců. 
  
## <a name="switching-the-to-another-thread"></a>Přepnutí jiné vlákno 
  
#### <a name="to-switch-threads"></a>Chcete-li přepnout vlákna  
  
1.  V **vlákna** okna, zkontrolujte druhý sloupec doleva (aktuální vlákno sloupce). Tlačítko v horní části v tomto sloupci nemá žádný text nebo ikonu.
  
2.  Podívejte se na aktuální vlákno sloupce a Všimněte si, že má jedno vlákno žlutá šipka. Žlutá šipka označuje, že toto vlákno je aktuální vlákno (Toto je aktuální umístění spuštění ukazatele).
  
    Si poznamenejte číslo ID vlákna kde uvidíte ikonu aktuální vlákno. Aktuální vlákno ikony se přesune do jiného vlákna, ale budete muset vložit ho po dokončení obnovení. 
  
3.  Klikněte pravým tlačítkem na jiné vlákno a poté klikněte na tlačítko **přepnout na vlákno**.  
  
4.  Podívejte se na **zásobník volání** okna v editoru zdrojového kódu. Obsah se změnil.  
  
5.  Podívejte se na **umístění ladění** nástrojů. Aktuální vlákno ikony se změnila, příliš.  
  
6.  Přejděte **umístění ladění** nástrojů. Vyberte jiném podprocesu než **vlákno** seznamu.  
  
7.  Podívejte se na **vlákna** okna. Aktuální vlákno ikony se změnila.  
  
8. V editoru zdrojového kódu klikněte pravým tlačítkem na značky vlákna. V místní nabídce, přejděte na **přepnout na vlákno** a klikněte na číslo název nebo ID vlákna.  
  
     Nyní jste viděli změna aktuální ikony vlákna do jiného vlákna třemi způsoby: pomocí **vlákna** okno, **vlákno** seznamu v **umístění ladění** nástrojů a značky vlákna v editoru zdrojového kódu.  
  
     Pomocí značky vlákna můžete přepnout pouze do vlákna, která se zastaví v tomto konkrétním umístění. S použitím **vlákna** okno a **umístění ladění** nástrojů, můžete přepnout na libovolného vlákna.   
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Postupy: Přepnutí na jiné vlákno během ladění](../debugger/how-to-switch-to-another-thread-while-debugging.md)
