---
title: Začínáme ladění vícevláknových aplikací | Microsoft Docs
ms.custom: H1HackMay2017
ms.date: 06/02/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- multithreaded debugging, tutorial
- tutorials, multithreaded debugging
ms.assetid: 62df746b-b0f6-4df4-83cf-b1d9d2e72833
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cea34a609905ea54b00115ee6d9419eb07c58c0d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="get-started-debugging-a-multithreaded-application-in-visual-studio"></a>Začínáme ladění vícevláknové aplikace v sadě Visual Studio
Visual Studio poskytuje několik nástrojů a prvky uživatelského rozhraní pro ladění vícevláknové aplikace. Tento kurz ukazuje, jak používat značky přístup z více vláken **paralelní zásobníky** okně **paralelního sledování** oken, podmíněné zarážky a filtr zarážky. V tomto kurzu trvá jenom pár minut, ale jeho dokončení vás seznámí s funkcemi pro ladění vícevláknové aplikace.

|         |         |
|---------|---------|
|  ![film ikonu fotoaparátu pro video](../install/media/video-icon.png "přehrát video")  |    [Přehrát video,](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugging-Multi-threaded-Apps-in-Visual-Studio-2017-MoZPKMD6D_111787171) na vícevláknové ladění, který ukazuje podobným způsobem. |

Další témata obsahují další informace o použití další vícevláknové ladicí nástroje:

- Pro podobné téma, které ukazuje, jak používat **ladění umístění** panelu nástrojů a **vláken** okně najdete v části [návod: ladění vícevláknové aplikace s](../debugger/how-to-use-the-threads-window.md).

- Pro podobné téma se vzorku, který používá <xref:System.Threading.Tasks.Task> (spravovaný kód) a concurrency runtime (C++), najdete v části [návod: ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md). Obecné tipy k ladění, která platí pro nejvíce vícevláknové typy aplikací, přečtěte si toto téma a propojené tématu.
  
Zahájíte tento kurz, musíte projekt vícevláknové aplikace. Postupujte podle kroků uvedených v tomto poli k vytvoření tohoto projektu.  
  
#### <a name="to-create-the-multithreaded-app-project"></a>Chcete-li vytvořit projekt vícevláknové aplikace  
  
1.  Na **soubor** nabídce zvolte **nový** a pak klikněte na **projektu**.  
  
     **Nový projekt** zobrazí se dialogové okno.  
  
2.  V **typu projektu**s pole, klikněte na tlačítko jazyk podle vašeho výběru: **Visual C#**, **Visual C++**, nebo **jazyka Visual Basic**.  
  
3.  V **šablony** vyberte **konzolovou aplikaci**.  
  
4.  V **název** pole, zadejte název MyThreadWalkthroughApp.  
  
5.  Click **OK**.  
  
     Zobrazí se nový projekt konzoly. Po vytvoření projektu, zobrazí se zdrojový soubor. V závislosti na jazyk, který jste zvolili může být volána zdrojový soubor Program.cs, MyThreadWalkthroughApp.cpp nebo Module1.vb.  
  
6.  Odstranit kód, který se zobrazí v zdrojový soubor a nahraďte ji metodou ukázkový kód zobrazeny zde.

    ```csharp
    using System;
    using System.Threading;

    public class ServerClass
    {

        static int count = 0;
        // The method that will be called when the thread is started.
        public void InstanceMethod()
        {
            Console.WriteLine(
                "ServerClass.InstanceMethod is running on another thread.");

            int data = count++;
            // Pause for a moment to provide a delay to make
            // threads more apparent.
            Thread.Sleep(3000);
            Console.WriteLine(
                "The instance method called by the worker thread has ended.");
        }
    }

    public class Simple
    {
        public static void Main()
        {
            for (int i = 0; i < 10; i++)
            {
                CreateThreads();
            }
        }
        public static void CreateThreads()
        {
            ServerClass serverObject = new ServerClass();

            Thread InstanceCaller = new Thread(new ThreadStart(serverObject.InstanceMethod));
            // Start the thread.
            InstanceCaller.Start();

            Console.WriteLine("The Main() thread calls this after "
                + "starting the new InstanceCaller thread.");

        }
    }
    ```

    ```C++
    #include "stdafx.h"
    #include <thread>
    #include <iostream>
    #include <vector>

    int count = 0;

    void doSomeWork() {

        std::cout << "The doSomeWork function is running on another thread." << std::endl;
        int data = count++;
        // Pause for a moment to provide a delay to make
        // threads more apparent.
        std::this_thread::sleep_for(std::chrono::seconds(3));
        std::cout << "The function called by the worker thread has ended." << std::endl;
    }

    int main() {
        std::vector<std::thread> threads;

        for (int i = 0; i < 10; ++i) {

            threads.push_back(std::thread(doSomeWork));
            std::cout << "The Main() thread calls this after starting the new thread" << std::endl;
        }

        for (auto& thread : threads) {
            thread.join();
        }

        return 0;
    }
    ```

    ```VB
    Imports System.Threading

    Public Class ServerClass
        ' The method that will be called when the thread is started.
        Public count = 0
        Public Sub InstanceMethod()
            Console.WriteLine(
                    "ServerClass.InstanceMethod is running on another thread.")

            Dim data = count + 1
            ' Pause for a moment to provide a delay to make
            ' threads more apparent.
            Thread.Sleep(3000)
            Console.WriteLine(
                    "The instance method called by the worker thread has ended.")
        End Sub

    End Class

    Public Class Simple

        Public Shared Sub Main()

            Dim ts As New ThreadStarter
            For index = 1 To 10
                ts.CreateThreads()
            Next

        End Sub

    End Class
    Public Class ThreadStarter
        Public Sub CreateThreads()
            Dim serverObject As New ServerClass()

            ' Create the thread object, passing in the
            ' serverObject.InstanceMethod method using a
            ' ThreadStart delegate.
            Dim InstanceCaller As New Thread(AddressOf serverObject.InstanceMethod)

            ' Start the thread.
            InstanceCaller.Start()

            Console.WriteLine("The Main() thread calls this after " _
                        + "starting the new InstanceCaller thread.")

        End Sub
    End Class
    ```
  
7.  Na **soubor** nabídky, klikněte na tlačítko **Uložit vše**.  
  
#### <a name="to-begin-the-tutorial"></a>Chcete-li začít kurz  
  
-   V editoru kódu zdroj vyhledejte následující kód: 
  
    ```csharp  
    Thread.Sleep(3000);  
    Console.WriteLine();  
    ```  
  
    ```C++  
    Thread::Sleep(3000);  
    Console.WriteLine();  
    ```  
    ```VB
    Thread.Sleep(3000)
    Console.WriteLine()
    ```
  
#### <a name="to-start-debugging"></a>Spustit ladění  
  
1.  Klikněte v levém oddělovací mezery u `Thread.Sleep` nebo `Thread::Sleep` příkaz Vložit nový zarážky.  
  
     V oddělovací mezery na levé straně editoru zdrojového kódu zobrazí se červeném kroužku. To znamená, že v tomto umístění je teď nastavený bod přerušení. 
  
2.  Na **ladění** nabídky, klikněte na tlačítko **spustit ladění** (**F5**).  
  
     Visual Studio vytvoří řešení, se s ladicím programem připojené spustí aplikaci a poté se zastaví aplikace u zarážky.  
  
    > [!NOTE]
    > Pokud fokus přejdete do okna konzoly, klikněte na [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] okno a vrátit se k [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
4.  V editoru zdrojového kódu vyhledejte řádek, který obsahuje zarážce:  
  
    ```csharp  
    Thread.Sleep(3000);  
    ```  
  
    ```C++  
    Thread::Sleep(3000);  
    ```

    ```VB
    Thread.Sleep(3000)
    ```    
  
#### <a name="ShowThreadsInSource"></a>Ke zjištění značky přístup z více vláken  

1.  Na panelu nástrojů pro ladění, klikněte **zobrazit vláken ve zdroji** tlačítko ![zobrazit vláken ve zdroji](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker").

2. Stiskněte klávesu **F11** jednou posunut ladicí program jeden řádek kódu.
  
3.  Podívejte se na oddělovací mezery na levé straně okna. Na tomto řádku se zobrazí *vlákno značky* ikonu ![vlákno značky](../debugger/media/dbg-thread-marker.png "ThreadMarker") , která se podobá dvěma vlákny hadříkem. Vlákno značky označuje, že vlákno je zastavená v tomto umístění.

    Všimněte si, že vlákno značku může částečně zakryté podle zarážky. 
  
4.  Umístění ukazatele myši značky přístup z více vláken. Zobrazí se popis dat. Popis dat poznáte, název a vlákno identifikační číslo pro každé zastavené vlákno. V tomto případě název je pravděpodobně `<noname>`. 
  
5.  Klikněte pravým tlačítkem na vlákno značky zobrazíte možnosti dostupné v místní nabídce.
    
## <a name="ParallelStacks"></a>Zobrazení umístění vláken

V **paralelní zásobníky** okno, můžete přepnout mezi zobrazení vláken a (pro programování založené na úlohách) zobrazení úlohy a vy můžete zobrazit informace v zásobníku volání pro každé vlákno. V této aplikaci používáme zobrazení vláken.

1. Otevřete **paralelní zásobníky** okna tak, že zvolíte **ladění > Windows > paralelní zásobníky**. Měli byste vidět něco podobného jako to (přesné informace budou lišit v závislosti na aktuální umístění každé vlákno, hardwaru a programovacího jazyka).

    ![Paralelní zásobníky – okno](../debugger/media/dbg-multithreaded-parallel-stacks.png "ParallelStacksWindow")

    V tomto příkladu zleva doprava se nám získat tyto informace:
    
    - Hlavní vlákno (levé straně) byla zastavena na `Thread.Start` (okamžik zastavení je označená ikonou značky vlákno ![vlákno značky](../debugger/media/dbg-thread-marker.png "ThreadMarker")).
    - Zadali jste dvěma vlákny `ServerClass.InstanceMethod`, z nichž jeden je aktuální vlákno (žlutý šipka), zatímco jiné vlákno byla zastavena v `Thread.Sleep`.
    - Také nové vlákno (napravo) zahajuje (zastavily `ThreadHelper.ThreadStart`).

2.  Pravým tlačítkem na záznamy v **paralelní zásobníky** okna zobrazíte možnosti dostupné v místní nabídce.

    Lze provádět různé akce z těchto nabídek klikněte pravým tlačítkem, ale pro účely tohoto kurzu ukážeme další tyto podrobnosti v **paralelního sledování** okno (další části).

    > [!NOTE]
    > Pokud vás zajímá více v zobrazení seznamu zobrazit s informacemi o každé vlákno, použijte **vláken** okno místo. V tématu [návod: ladění vícevláknové aplikace s](../debugger/how-to-use-the-threads-window.md).

## <a name="set-a-watch-on-a-variable"></a>Nastavovat sledování na proměnné

1. Otevřete **paralelního sledování** okna tak, že zvolíte **ladění > Windows > paralelního sledování > paralelní sledování 1**.

2. Klikněte na buňku, kde uvidíte `<Add Watch>` text (nebo prázdná datovou buňku ve sloupci 4.), typ `data`, a stiskněte klávesu Enter.

    Hodnoty pro proměnné dat pro každé vlákno se zobrazí v okně.

3. Klikněte na tlačítko znovu v buňce, kde uvidíte `<Add Watch>` text (nebo prázdná datovou buňku ve sloupci 5.), typ `count`, a stiskněte klávesu Enter.

    Hodnoty pro počet proměnnou pro každé vlákno se zobrazí v okně. (Pokud nevidíte tuto velkého množství informací ještě, pokuste se stisknutím klávesy F11 několik vícekrát posunut provádění vlákna v ladicím programu.)

    ![Paralelní kukátko – okno](../debugger/media/dbg-multithreaded-parallel-watch.png "ParallelWatchWindow")

4. Pravým tlačítkem na jednu z jeho řádků v okně zobrazíte dostupné možnosti.

## <a name="flagging-and-unflagging-threads"></a>Označení a Unflagging vlákna  
Můžete označit příznakem vláken, které chcete udělit zvláštní pozornost. Označování vláken je vhodné můžete sledovat důležité vláken a vláken, které nechcete o ignorovat.  
  
#### <a name="to-flag-threads"></a>Chcete-li příznak vláken  

1. V **paralelního sledování** okno, podržte stisknutou klávesu SHIFT a vyberte více řádků.

2. Klikněte pravým tlačítkem a zvolte **příznak**.

    Nyní jsou označeny všechny vybrané vláken. Teď můžete filtrovat údaje a zobrazit pouze označení vlákna.
  
3.  V **paralelního sledování** okně Najít **zobrazit jenom příznakem vláken** tlačítko ![zobrazit příznakem vláken](../debugger/media/dbg-threads-show-flagged.png "ThreadMarker").  
  
4.  Klikněte **zobrazit jenom příznakem vláken** tlačítko.  
  
    Pouze označení vlákno se zobrazí v seznamu nyní.

    > [!TIP]
    > Když příznakem některé vláken, můžete klikněte pravým tlačítkem myši na řádek kódu v editoru kódu a vyberte **spustit příznakem podprocesů pro kurzor** (ujistěte se, abyste zvolili kódu, že všechny příznakem vláken dosáhnou). To se pozastaví vláken na vybraný řádek kódu, což usnadňuje řízení pořadí provádění podle [zmrazení a uvolnění vláken](#bkmk_freeze).

5.  Klikněte **zobrazit jenom příznakem vláken** tlačítko přepnete zpět do **zobrazit všechna vlákna** režimu.
    
#### <a name="to-unflag-threads"></a>K odstranění označení vlákna

K odstranění označení vlákna, kliknete pravým tlačítkem na jeden nebo více označení vláken v **paralelního sledování** okna a zvolte **Unflag**.

## <a name="bkmk_freeze"></a> Zmrazení a uvolnění provádění vlákna 

> [!TIP]
> Lze ukotvit a uvolnit (pozastavení a obnovení) vláken určit pořadí, ve kterém vláken práci. To vám může pomoct vyřešit potíže se souběžností například blokování a stavy soupeření.
  
#### <a name="to-freeze-and-unfreeze-threads"></a>Chcete-li ukotvení a uvolnění vláken  
  
1.  V **paralelního sledování** okno s všechny řádky vybraný, klikněte pravým tlačítkem a vyberte **Freeze**.

    V druhém sloupci ikonou pozastavení se teď pro každý řádek. Ikona pozastavení označuje, že vlákno nereaguje.

2.  Zrušte výběr řádky kliknutím pouze jeden řádek.

3.  Klikněte pravým tlačítkem na řádek a vyberte **odblokování**.

    Ikona pozastavení vyčkat na tomto řádku, která určuje, že vlákno je už pozastaveny.

4.  Přepněte do editoru kódu a klikněte na tlačítko **F11**. Spustí se pouze nefixované vlákno.

    Aplikace může také vytvořit instanci některé nové vláken. Všimněte si, že žádné nové podprocesy bez příznaku a nejsou pozastaveny.

## <a name="bkmk_follow_a_thread"></a> Postupujte podle jednoho vlákna pomocí podmíněné zarážky

V některých případech může být užitečné sledovat provádění z jednoho vlákna v ladicím programu. Můžete to udělat jedním ze způsobů je zmrazení vláken, která vás zajímá není, ale v některých případech můžete chtít podle jedním vláknem a bez zmrazení jiná vlákna (pro konkrétní chyb, například zkopírujte). Podle vlákno bez zmrazení jiná vlákna, se musí vyhnout rozdělení do kódu s výjimkou na vlákno, které vás zajímají. To provedete nastavením [podmíněného zarážek](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression).

Můžete nastavit zarážky v různých podmínkách, jako je název vlákna nebo ID vlákna. Další metodou, které mohou být užitečné je nastavení podmínky pro data, která víte, že je jedinečný pro každé vlákno. Toto je běžný scénář ladění, ve kterém vás zajímá více některé konkrétní datové hodnoty než v žádné konkrétní přístup z více vláken.

#### <a name="to-follow-a-single-thread"></a>Dodržet jedno vlákno

1. Klikněte pravým tlačítkem na zarážek jste dříve vytvořili a zvolte **podmínky**.

2. V **nastavení zarážek** zadejte `data == 5` podmíněného výrazu.

    ![Podmíněné zarážky](../debugger/media/dbg-multithreaded-conditional-breakpoint.png "ConditionalBreakpoint")

    > [!TIP]
    > Pokud vás zajímají další konkrétní vlákno, pak používáte názvu vlákna nebo ID vlákna pro podmínku. To uděláte v **nastavení zarážek** vyberte **filtru** místo **podmíněným výrazem**a postupujte podle pokynů tipy filtru. Můžete chtít název vaší vláken v kódu aplikace (protože vláken ID změnit při dalším spuštění ladicího programu).

3. Zavřít **nastavení zarážek** okno.

4. Klikněte na možnost restartování ![restartujte aplikace](../debugger/media/dbg-tour-restart.png "RestartApp") tlačítko Restartovat relaci ladění.

    Bude rozdělit na kód ve vlákně, pro kterou je proměnná data 5. Hledat šipku žlutý (aktuální kontextu ladicího programu) v **paralelního sledování** okno ověřit, jestli.

5. Teď můžete přes kód (F10) a kroku do kódu (F11) a postupujte podle provádění jedno vlákno.

    Dokud zarážek podmínka je jedinečné pro vlákno a ladicí program není dosáhl jiných zarážky na jiná vlákna (musíte je zakázat), můžete přes kódu a kroku do kódu, aniž by se přepnula jiná vlákna.

    > [!NOTE]
    > Při přechodu ladicí program se spustí všechna vlákna. Ladicí program však nebude rozdělit kódu na jiná vlákna Pokud jeden z dalších podprocesů dotkne zarážky. 
  
## <a name="more-about-the-multithreaded-debugging-windows"></a>Další informace o windows vícevláknové ladění 

#### <a name="to-switch-to-another-thread"></a>Chcete-li přepnout na jiné vlákno 

- Přepnutí na jiné vlákno, najdete v tématu [postupy: přepnutí na jiné vlákno během ladění](../debugger/how-to-switch-to-another-thread-while-debugging.md) 

#### <a name="to-learn-more-about-the-parallel-stack-and-parallel-watch-windows"></a>Další informace o windows paralelních zásobníků a paralelního sledování  
  
- V tématu [postupy: použití okna paralelní zásobníku](../debugger/using-the-parallel-stacks-window.md) 

- V tématu [postupy: použití okna paralelního sledování](../debugger/how-to-use-the-parallel-watch-window.md) 
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Postupy: přepnutí na jiné vlákno během ladění](../debugger/how-to-switch-to-another-thread-while-debugging.md)
