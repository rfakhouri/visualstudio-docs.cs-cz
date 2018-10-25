---
title: Další informace k ladění vícevláknových aplikací
description: Ladění pomocí okna paralelní zásobníky a paralelní sledování v sadě Visual Studio
ms.custom: H1HackMay2017
ms.date: 08/01/2018
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
ms.assetid: 62df746b-b0f6-4df4-83cf-b1d9d2e72833
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 66239362e454d5ab333214c444aeee3fa54b1b8a
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49936852"
---
# <a name="get-started-debugging-multithreaded-applications-in-visual-studio"></a>Začínáme s laděním vícevláknových aplikací v sadě Visual Studio
Visual Studio poskytuje několik nástrojů a prvky uživatelského rozhraní si můžete usnadnit ladění aplikací s více vlákny. Tento kurz ukazuje, jak používat značky vlákna **paralelní zásobníky** okně **paralelní sledování** oken, podmíněné zarážky a filtr zarážek. Tento kurz trvá jenom několik minut, ale jeho dokončení se můžete seznámit s funkcemi pro ladění aplikací s více vlákny.

| | |
|---------|---------|
| ![Ikona filmové kamery pro video](../install/media/video-icon.png "Sledovat video") | [Podívejte se na video](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugging-Multi-threaded-Apps-in-Visual-Studio-2017-MoZPKMD6D_111787171) vícevláknové ladění zobrazující podobný postup. |

Další témata poskytují další informace o použití jiných vícevláknové ladění nástrojů:

- Podobně jako tématu, který ukazuje, jak používat **umístění ladění** nástrojů a **vlákna** okna, naleznete v tématu [návod: ladění aplikace s více vlákny](../debugger/how-to-use-the-threads-window.md).

- Podobně jako tématu pomocí ukázky, která používá <xref:System.Threading.Tasks.Task> (spravovaný kód) a modulu runtime souběžnosti (C++), najdete v článku [návod: ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md). Obecné tipy pro ladění, které se týkají nejvíce s více vlákny typy aplikací, přečtěte si toto téma a propojené tématu.
  
Pokud chcete začít tento kurz, potřebujete projekt aplikace s více vlákny. Postupujte podle kroků uvedených zde k vytvoření tohoto projektu.  
  
#### <a name="to-create-the-multithreaded-app-project"></a>Chcete-li vytvořit projekt aplikace s více vlákny  
  
1.  Na **souboru** nabídce zvolte **nový** a potom klikněte na tlačítko **projektu**.  
  
     **Nový projekt** zobrazí se dialogové okno.  
  
2.  Klepněte na jazyk podle svého výběru: **Visual C#**, **Visual C++**, nebo **jazyka Visual Basic**.  
  
3.  V části **Windows Desktop**, zvolte **konzolovou aplikaci**.  
  
4.  V **název** pole, zadejte název MyThreadWalkthroughApp.  
  
5.  Klikněte na tlačítko **OK**.  
  
     Zobrazí se nový projekt konzoly. Po vytvoření projektu se zobrazí zdrojový soubor. V závislosti na jazyku, kterou jste zvolili může volat zdrojového souboru Program.cs, MyThreadWalkthroughApp.cpp nebo Module1.vb.  
  
6.  Odstranit kód, který se zobrazí ve zdrojovém souboru a nahraďte ji metodou ukázkový kód je vidět tady.

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

    using namespace;

    int count = 0;

    void doSomeWork() {

        cout << "The doSomeWork function is running on another thread." << endl;
        int data = count++;
        // Pause for a moment to provide a delay to make
        // threads more apparent.
        this_thread::sleep_for(chrono::seconds(3));
        cout << "The function called by the worker thread has ended." << endl;
    }

    int main() {
        vector<thread> threads;

        for (int i = 0; i < 10; ++i) {

            threads.push_back(thread(doSomeWork));
            cout << "The Main() thread calls this after starting the new thread" << endl;
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
  
7.  Na **souboru** nabídky, klikněte na tlačítko **Uložit vše**.  
  
#### <a name="to-begin-the-tutorial"></a>Chcete-li začít kurz  
  
-   V editoru zdrojového kódu vyhledejte následující kód: 
  
    ```csharp  
    Thread.Sleep(3000);  
    Console.WriteLine();  
    ```  
  
    ```C++  
    this_thread::sleep_for(chrono::seconds(3));
    cout << "The function called by the worker thread has ended." << endl; 
    ```  

    ```VB
    Thread.Sleep(3000)
    Console.WriteLine()
    ```
  
#### <a name="to-start-debugging"></a>Pro spuštění ladění  
  
1. Klikněte v levém hřbetu z `Thread.Sleep` nebo `this_thread::sleep_for` příkazu k vložení novou zarážku.  
  
    Na levé straně editoru zdrojového kódu na ovládací prvek zobrazí se červený kruh. To znamená, že na tomto místě je nyní nastaveno zarážku. 
  
2. Na **ladění** nabídky, klikněte na tlačítko **spustit ladění** (**F5**).  
  
    Visual Studio vytvoří řešení, aplikace spustí s připojeným ladícím nástrojem a poté se aplikace zastaví u zarážky.  
  
   > [!NOTE]
   > Je-li přepnout fokus do okna konzoly, klikněte na tlačítko v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] okno a vraťte se na [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
3. V editoru zdrojového kódu vyhledejte řádek, který obsahuje zarážku:  
  
   ```csharp  
   Thread.Sleep(3000);  
   ```  
  
   ```C++  
   this_thread::sleep_for(chrono::seconds(3)); 
   ```

   ```VB
   Thread.Sleep(3000)
   ```    
  
#### <a name="ShowThreadsInSource"></a>Ke zjištění značky vlákna  

1.  Na panelu nástrojů pro ladění, klikněte na tlačítko **zobrazit vlákna ve zdroji** tlačítko ![zobrazit vlákna ve zdroji](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker").

2. Stisknutím klávesy **F11** jednou pro přechod na ladicí program jeden řádek kódu.
  
3.  Podívejte se na ovládací prvek na levé straně okna. Na tomto řádku se zobrazí *značky vlákna* ikonu ![značky vlákna](../debugger/media/dbg-thread-marker.png "ThreadMarker") , který se podobá dvěma vlákny látky. Značky vlákna označuje, že je vlákno zastavené v tomto umístění.

    Všimněte si, že značky vlákna mohou být částečně zakryty podle zarážku. 
  
4.  Ukazatel myši značky vlákna. Zobrazí se DataTip. DataTip zjistíte číslo ID názvu a vlákna pro každé vlákno zastavené. V tomto případě název je pravděpodobně `<noname>`. 
  
5.  Klikněte pravým tlačítkem na značky vlákna zobrazíte dostupné možnosti v místní nabídce.
    
## <a name="ParallelStacks"></a>Zobrazení umístění vlákna

V **paralelní zásobníky** okně můžete přepínat mezi zobrazení vláken a (pro programování založené na úlohách) zobrazení úloh kde můžete zobrazit informace v zásobníku volání pro každé vlákno. V této aplikaci používáme zobrazení vláken.

1. Otevřít **paralelní zásobníky** okno výběrem **ladit > Windows > paralelní zásobníky**. By měl vypadat nějak takto (přesné informace budou lišit v závislosti na aktuální umístění každé vlákno, hardwaru a svůj oblíbený programovací jazyk).

    ![Paralelních zásobníků okno](../debugger/media/dbg-multithreaded-parallel-stacks.png "ParallelStacksWindow")

    V tomto příkladu zleva doprava jsme získat tyto informace pro spravovaný kód:
    
    - Hlavní vlákno (levá strana) se zastavila na `Thread.Start` (okamžik zastavení je označená ikonou značky vlákna ![značky vlákna](../debugger/media/dbg-thread-marker.png "ThreadMarker")).
    - Zadaná dvě vlákna `ServerClass.InstanceMethod`, z nichž jeden je aktuální vlákno (žlutá šipka), zatímco jiné vlákno se zastavila v `Thread.Sleep`.
    - Spouští se také nové vlákno (napravo) (zastavena `ThreadHelper.ThreadStart`).

2.  Klikněte pravým tlačítkem na položky v **paralelní zásobníky** okno zobrazte dostupné možnosti v místní nabídce.

    Můžete provádět různé akce z těchto nabídek klikněte pravým tlačítkem, ale pro účely tohoto kurzu vám ukážeme některé tyto podrobnosti v **paralelní sledování** okno (další oddíly).

    > [!NOTE]
    > Pokud vás zajímá více v zobrazení seznamu zobrazit informace na každé vlákno, použijte **vlákna** okno místo. Zobrazit [návod: ladění aplikace s více vlákny](../debugger/how-to-use-the-threads-window.md).

## <a name="set-a-watch-on-a-variable"></a>Nastavení sledování u proměnné

1. Otevřít **paralelní sledování** okno výběrem **ladit > Windows > paralelní sledování > paralelního kukátka 1**.

2. Klikněte na buňku, kde se zobrazují `<Add Watch>` text (nebo prázdný hlavičkové buňky ve sloupci 4), typ `data`, a stiskněte klávesu Enter.

    V okně se zobrazí hodnoty pro proměnné data pro každé vlákno.

3. Klikněte znovu na buňku, kde se zobrazují `<Add Watch>` text (nebo prázdnou buňku v 5. sloupec), typ `count`, a stiskněte klávesu Enter.

    V okně se zobrazí hodnoty pro proměnné count pro každé vlákno. (Pokud se nezobrazí ještě takovém množství informací, pokuste se stisknutím klávesy F11 ještě několikrát k přechodu provádění vláken v ladicím programu.)

    ![Paralelního kukátka](../debugger/media/dbg-multithreaded-parallel-watch.png "ParallelWatchWindow")

4. Klikněte pravým tlačítkem na jeden z řádků v okně zobrazíte dostupné možnosti.

## <a name="flagging-and-unflagging-threads"></a>Označení a Unflagging vlákna  
Můžete označit příznakem vlákna, která chcete věnovat zvláštní pozornost. Příznakem vlákna je dobrým způsobem ke sledování důležité vláken a pro ignorování vlákna, které vás nezajímají.  
  
#### <a name="to-flag-threads"></a>Označit vlákna  

1. V **paralelní sledování** okno, podržte stisknutou klávesu SHIFT a vyberte více řádků.

2. Klikněte pravým tlačítkem a zvolte **příznak**.

    Nyní se označí všechna vybraná vlákna. Teď můžete filtrovat, chcete-li zobrazit pouze vlákna s příznakem.
  
3.  V **paralelní sledování** okně Najít **zobrazit pouze s příznakem vlákna** tlačítko ![zobrazit vlákna s příznakem](../debugger/media/dbg-threads-show-flagged.png "ThreadMarker").  
  
4.  Klikněte na tlačítko **zobrazit pouze s příznakem vlákna** tlačítko.  
  
    Pouze vlákno s příznakem se zobrazí v seznamu nyní.

    > [!TIP]
    > Pokud máte některá vlákna označená příznakem, můžete klikněte pravým tlačítkem na řádek kódu v editoru kódu a zvolte **spustit vlákna s příznakem do pozice kurzoru** (ujistěte se, že zvolíte dosáhne kódu, že všechny příznakem vlákna). To se pozastaví, vláken na vybraný řádek kódu, které usnadňují určit pořadí provedení [zmrazení a uvolnění vláken](#bkmk_freeze).

5.  Klikněte na tlačítko **zobrazit pouze s příznakem vlákna** tlačítko přepnete zpět do **zobrazit všechna vlákna** režimu.
    
#### <a name="to-unflag-threads"></a>K odstranění označení vlákna

K odstranění označení vlákna, kliknete pravým tlačítkem na jeden nebo více vlákna s příznakem v **paralelní sledování** okno a zvolte **Unflag**.

## <a name="bkmk_freeze"></a> Zmrazení a uvolnění provádění vlákna 

> [!TIP]
> Můžete zablokovat a odblokovat (pozastavení a obnovení) určit pořadí, ve kterém provádění vlákna pracovních vláken. To může pomoct vyřešit potíže se souběžností například zablokování a konflikty časování.
  
#### <a name="to-freeze-and-unfreeze-threads"></a>Ukotvit a uvolnit vlákna  
  
1.  V **paralelní sledování** okna se všechny řádky vybraný, klikněte pravým tlačítkem a vyberte **ukotvit**.

    V druhém sloupci zobrazí ikona pozastavení teď pro každý řádek. Ikona pozastavení označuje, že vlákno je zmrazen.

2.  Zrušte výběr řádků kliknutím pouze jeden řádek.

3.  Klikněte pravým tlačítkem na řádek a vyberte **uvolnit**.

    Ikona pozastavení zanikne na tento řádek, která udává, že vlákno je již zmrazen.

4.  Přejděte do editoru kódu a klikněte na tlačítko **F11**. Spouští pouze nezmrazený vlákno.

    Aplikace může také vytvořit instanci některá nová vlákna. Všimněte si, že všechny nová vlákna bez příznaku a nejsou zmrazen.

## <a name="bkmk_follow_a_thread"></a> Postupujte podle jednoho vlákna s použitím podmíněné zarážky

V některých případech může být užitečné sledovat provádění jedním vláknem v ladicím programu. Můžete to udělat jedním ze způsobů je zmrazení vlákna, které vás nezajímají, ale v některých scénářích možná budete chtít postupujte podle jednoho vlákna bez zmrazení ostatní vlákna (pro reprodukci chyb konkrétní, třeba). Sledovat vlákna bez zmrazení ostatní vlákna, je třeba se vyvarovat rozdělení do kódu s výjimkou ve vlákně, které vás zajímají. Můžete to provést tak, že nastavíte [podmíněné zarážky](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression).

Můžete nastavit zarážky v různých podmínkách, jako je například název vlákna nebo ID vlákna. Další metodou, mohou být užitečné je nastavení podmínky pro data, o kterém víte, že bude jedinečný pro každé vlákno. Toto je běžný scénář ladění, ve které vás zajímají další některé konkrétní hodnoty dat než v žádné konkrétní vlákno.

#### <a name="to-follow-a-single-thread"></a>Chcete-li postupujte podle jednoho vlákna

1. Klikněte pravým tlačítkem na zarážku, kterou jste vytvořili dřív a zvolte **podmínky**.

2. V **nastavení zarážek** okno, zadejte `data == 5` podmíněného výrazu.

    ![Podmíněné zarážky](../debugger/media/dbg-multithreaded-conditional-breakpoint.png "ConditionalBreakpoint")

    > [!TIP]
    > Pokud vás zajímají další konkrétním vlákně, použijte název vlákna nebo ID vlákna pro podmínku. K tomu **nastavení zarážek** okně **filtr** místo **podmíněný výraz**a postupujte podle filtru tipy. Můžete chtít název vlákna v kódu vaší aplikace (protože vlákna ID změnit při restartování ladicího programu).

3. Zavřít **nastavení zarážek** okna.

4. Klikněte na tlačítko Restart ![restartovat aplikaci](../debugger/media/dbg-tour-restart.png "RestartApp") tlačítko Restartovat ladicí relaci.

    Bude rozdělte do kódu ve vlákně, pro který datová proměnná je 5. Hledat žlutá šipka (aktuální kontext ladicího programu) v **paralelní sledování** okna pro ověření, že.

5. Teď můžete krokovat přes kód (F10) a můžete krokovat s vnořením (F11) kód a postupujte podle provádění jedno vlákno.

    Podmínka zarážky jsou jedinečné pro vlákno, a pokud ladicí program nebude přístupů žádné zarážky na jiných vláknech (budete muset zakázat), můžete krokovat přes kódu a s vnořením do kódu bez přepnutí ostatní vlákna.

    > [!NOTE]
    > Při přechodu ladicí program se spustí všechna vlákna. Ladicí program však nebude proniknout do kódu v jiných vláknech, pokud jeden z jiných vláken narazí na zarážku. 
  
## <a name="more-about-the-multithreaded-debugging-windows"></a>Další informace o vícevláknové ladění systému windows 

#### <a name="to-switch-to-another-thread"></a>Chcete-li přepnout do jiného vlákna 

- Chcete-li přepnout do jiného vlákna, naleznete v tématu [postupy: přepnutí na jiné vlákno během ladění](../debugger/how-to-switch-to-another-thread-while-debugging.md) 

#### <a name="to-learn-more-about-the-parallel-stack-and-parallel-watch-windows"></a>Další informace o windows paralelní zásobníku a paralelního sledování  
  
- Zobrazit [postupy: použití okna paralelní zásobníku](../debugger/using-the-parallel-stacks-window.md) 

- Zobrazit [postupy: použití okna paralelního sledování](../debugger/how-to-use-the-parallel-watch-window.md) 
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Postupy: Přepnutí na jiné vlákno během ladění](../debugger/how-to-switch-to-another-thread-while-debugging.md)
