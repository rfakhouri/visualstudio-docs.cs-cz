---
title: 'Návod: Zápis Vizualizéru v jazyce C# | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
helpviewer_keywords:
- visualizers, writing
- walkthroughs [Visual Studio], visualizers
ms.assetid: 53467461-8e0f-45ee-9bc4-374bbaeaf00f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 490c2c2b15eff701cee751b57bbf55024910beab
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31479835"
---
# <a name="walkthrough-writing-a-visualizer-in-c"></a>Návod: Zápis vizualizéru v jazyce C# #
Tento návod ukazuje, jak napsat Jednoduchý vizualizér pomocí jazyka C#. Vizualizér, které vytvoříte v tomto návodu zobrazí obsah řetězce pomocí systému Windows forms se zprávou. Tento jednoduchý řetězec vizualizér není obzvláště užitečná sám o sobě, ale zobrazí základní kroky, které je potřeba provést k vytvoření užitečnější vizualizérech pro jiné datové typy.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídky, které vidíte, se může lišit od těch popsaných v nápovědě, v závislosti na aktivním nastavení nebo edici. Chcete-li změnit nastavení, přejděte na **nástroje** nabídky a zvolte **nastavení importu a exportu**. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
 Vizualizér kód musí být umístěn v knihovně DLL, která bude načten modulem ladicího programu. Proto prvním krokem je vytvoření projektu knihovny tříd pro knihovnu DLL.  

## <a name="create-a-visualizer-manually"></a>Ruční vytvoření vizualizéru

Postupujte podle níže vytvořit vizualizéru úlohy.
  
#### <a name="to-create-a-class-library-project"></a>Vytvoření projektu knihovny tříd  
  
1.  Na **soubor** nabídce zvolte **nový > projekt**.  
  
2.  V **nový projekt** dialogovém **Visual C#**, vyberte **.NET Standard**.  
  
3.  V prostředním podokně vyberte **knihovny tříd**.  
  
4.  V **název** zadejte vhodný název pro knihovnu tříd, jako je například MyFirstVisualizer.  
  
5.  Click **OK**.  
  
 Po vytvoření knihovny tříd, musíte přidat odkaz na Microsoft.VisualStudio.DebuggerVisualizers.DLL, tak, aby můžete tříd definovaných existuje. Než přidáte odkaz, ale je třeba přejmenovat některé třídy tak, aby měla smysluplný název.  
  
#### <a name="to-rename-class1cs-and-add-microsoftvisualstudiodebuggervisualizers"></a>Přejmenovat Class1.cs a přidat Microsoft.VisualStudio.DebuggerVisualizers  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na Class1.cs a zvolte **přejmenovat** v místní nabídce.  
  
2.  Změňte název na něco smysluplného, například DebuggerSide.cs z Class1.cs.  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky změní deklaraci třídy v DebuggerSide.cs tak, aby odpovídaly nový název souboru.  
  
3.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **odkazy** a zvolte **přidat odkaz na** v místní nabídce.  
  
4.  V **přidat odkaz na** v dialogovém **.NET** , zvolte Microsoft.VisualStudio.DebuggerVisualizers.DLL.  
  
5.  Click **OK**.  
  
6.  V DebuggerSide.cs, přidejte následující příkaz na `using` příkazy:  
  
    ```csharp  
    using Microsoft.VisualStudio.DebuggerVisualizers;  
    ```  
  
 Nyní jste připraveni vytvořit kód straně ladicí program. Toto je kód, který běží v ladicím programu pro zobrazení informací, které chcete vizualizovat. Nejprve budete muset změnit deklaraci `DebuggerSide` objektu, který dědí vlastnosti ze základní třídy `DialogDebuggerVisualizer`.  
  
#### <a name="to-inherit-from-dialogdebuggervisualizer"></a>Dědění z DialogDebuggerVisualizer  
  
1.  V DebuggerSide.cs přejděte na následující řádek kódu:  
  
    ```csharp  
    public class DebuggerSide  
    ```  
  
2.  Změňte kód, který:  
  
    ```csharp  
    public class DebuggerSide : DialogDebuggerVisualizer  
    ```  
  
 `DialogDebuggerVisualizer` má jeden abstraktní metodu (`Show`), je nutné přepsat.  
  
#### <a name="to-override-the-dialogdebuggervisualizershow-method"></a>Přepsat metodu DialogDebuggerVisualizer.Show  
  
-   V `public class DebuggerSide`, přidejte následující **metoda:**  
  
    ```csharp  
    protected override void Show(IDialogVisualizerService windowService, IVisualizerObjectProvider objectProvider)  
    {  
    }  
    ```  
  
 `Show` Metoda obsahuje kód, který skutečně vytváří dialogové okno vizualizér nebo jiných prvků uživatelského rozhraní a zobrazí se informace, které byla předána vizualizér z ladicího programu. Je nutné přidat kód, který vytvoří dialogové okno a zobrazí informace. V tomto návodu jste se to provést pomocí systému Windows forms se zprávou. Nejdřív musíte přidat odkaz a `using` příkaz pro System.Windows.Forms.  
  
#### <a name="to-add-systemwindowsforms"></a>Chcete-li přidat System.Windows.Forms  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **odkazy** a zvolte **přidat odkaz na** v místní nabídce.  
  
2.  V **přidat odkaz na** v dialogovém **.NET** , zvolte System.Windows.Forms.DLL.  
  
3.  Click **OK**.  
  
4.  V DebuggerSide.cs, přidejte následující příkaz na `using` příkazy:  
  
    ```csharp  
    using System.Windows.Forms;  
    ```  
  
 Nyní přidáte kód, který vytvořit a zobrazit uživatelské rozhraní pro vaše vizualizér. Protože je to vaše první vizualizér, jsme se zjednodušení uživatelské rozhraní a použijte okno se zprávou.  
  
#### <a name="to-show-the-visualizer-output-in-a-dialog-box"></a>Chcete-li zobrazit výstup vizualizér v dialogovém okně  
  
1.  V `Show` metoda, přidejte následující řádek kódu:  
  
    ```csharp  
    MessageBox.Show(objectProvider.GetObject().ToString());  
    ```  
  
     Tento příklad kódu nezahrnuje zpracování chyb. Zpracování chyb v skutečné vizualizér nebo jakýkoli jiný druh aplikace by měla obsahovat.  
  
2.  Na **sestavení** nabídky, zvolte **sestavení MyFirstVisualizer**. Projekt má sestavit úspěšně. Než budete pokračovat, opravte všechny chyby sestavení.  
  
 Konec kód straně ladicí program, který je. Neexistuje jeden krok, ale; atribut, který sděluje na straně pozastaven kolekce tříd, které se skládá z vizualizér.  
  
#### <a name="to-add-the-debuggee-side-code"></a>Chcete-li přidat kód pozastaven straně  
  
1.  Přidejte následující kód atribut DebuggerSide.cs, po `using` příkazy ale předtím, než `namespace MyFirstVisualizer`:  
  
    ```csharp  
    [assembly:System.Diagnostics.DebuggerVisualizer(  
    typeof(MyFirstVisualizer.DebuggerSide),  
    typeof(VisualizerObjectSource),  
    Target = typeof(System.String),  
    Description = "My First Visualizer")]  
    ```  
  
2.  Na **sestavení** nabídky, zvolte **sestavení MyFirstVisualizer**. Projekt má sestavit úspěšně. Než budete pokračovat, opravte všechny chyby sestavení.  
  
 V tomto okamžiku je vaší první vizualizér bylo dokončeno. Pokud jste postupovali podle kroků správně, můžete vytvořit vizualizér a nainstalovat ji do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Před instalací vizualizéru do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ale měli byste otestovat a ujistit se, že běží správně. Nyní vytvoříte test harness ke spuštění vizualizér bez instalace do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
#### <a name="to-add-a-test-method-to-show-the-visualizer"></a>Přidání metody testovací zobrazíte vizualizéru  
  
1.  Přidejte následující metodu do třídy `public DebuggerSide`:  
  
    ```csharp  
    public static void TestShowVisualizer(object objectToVisualize)  
    {  
       VisualizerDevelopmentHost visualizerHost = new VisualizerDevelopmentHost(objectToVisualize, typeof(DebuggerSide));  
       visualizerHost.ShowVisualizer();  
    }  
    ```  
  
2.  Na **sestavení** nabídky, zvolte **sestavení MyFirstVisualizer**. Projekt má sestavit úspěšně. Než budete pokračovat, opravte všechny chyby sestavení.  
  
 Dále musíte vytvořit spustitelný projekt volat vaše vizualizér knihovny DLL. Pro jednoduchost použijeme projektu konzolové aplikace.  
  
#### <a name="to-add-a-console-application-project-to-the-solution"></a>Chcete-li do řešení přidat projekt konzolové aplikace  
  
1.  Na **soubor** nabídce zvolte **přidat** a pak klikněte na **nový projekt**.  
  
2.  V **přidat nový projekt** dialogu **šablony** vyberte **konzolové aplikace**.  
  
3.  V **název** zadejte nějaký výstižný název konzolové aplikace, jako například `MyTestConsole`.  
  
4.  Click **OK**.  
  
 Nyní je nutné přidat tak MyTestConsole můžete volat MyFirstVisualizer odkazuje na nezbytné.  
  
#### <a name="to-add-necessary-references-to-mytestconsole"></a>Chcete-li přidat nezbytné odkazy na MyTestConsole  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **MyTestConsole** a zvolte **přidat odkaz na** v místní nabídce.  
  
2.  V **přidat odkaz na** dialogové okno, **.NET** , zvolte Microsoft.VisualStudio.DebuggerVisualizers.DLL.  
  
3.  Click **OK**.  
  
4.  Klikněte pravým tlačítkem na **MyTestConsole** a zvolte **přidat odkaz na** znovu.  
  
5.  V **přidat odkaz na** dialogové okno, klikněte na tlačítko **projekty** kartě a pak klikněte na tlačítko MyFirstVisualizer.  
  
6.  Click **OK**.  
  
 Nyní přidáte kód, který dokončit test harness.  
  
#### <a name="to-add-code-to-mytestconsole"></a>Přidání kódu do MyTestConsole  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na Program.cs a zvolte **přejmenovat** v místní nabídce.  
  
2.  Upravte název ze souboru Program.cs požadavků uživatele, jako je například TestConsole.cs.  
  
     **Poznámka:** [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky změní deklaraci třídy v TestConsole.cs tak, aby odpovídaly nový název souboru.  
  
3.  V TestConsole.cs, přidejte následující kód, který `using` příkazy:  
  
    ```csharp  
    using MyFirstVisualizer;  
    ```  
  
4.  V metodě `Main`, přidejte následující kód:  
  
    ```csharp  
    String myString = "Hello, World";  
    DebuggerSide.TestShowVisualizer(myString);  
    ```  
  
 Nyní jste připraveni k testování vaší první vizualizér.  
  
#### <a name="to-test-the-visualizer"></a>K testování vizualizéru  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **MyTestConsole** a zvolte **nastavit jako spouštěný projekt** v místní nabídce.  
  
2.  Na **ladění** nabídce zvolte **spustit**.  
  
     Spustí konzolové aplikace a vizualizér zobrazí se text "Hello, World".  
  
 Blahopřejeme. Máte právě vytvořené a testování vaší první vizualizér.  
  
 Pokud chcete používat vaše vizualizér v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] místo právě ho volání z test harness, je nutné ji nainstalovat. Další informace najdete v tématu [postupy: instalace Vizualizéru](../debugger/how-to-install-a-visualizer.md).  
  
## <a name="create-a-visualizer-using-the-visualizer-item-template"></a>Vytvořit pomocí šablony položky vizualizér vizualizéru  
 Pokud Tento názorný postup uvádí, jak vytvořit vizualizéru ručně. K tomu bylo potřeba jako cvičení učení. Teď, když víte, jak jednoduché vizualizéru funguje, je snadný způsob, jak vytvořit: pomocí šablony položky vizualizér.  
  
 Nejprve budete muset vytvořit nový projekt knihovny tříd.  
  
#### <a name="to-create-a-new-class-library"></a>Chcete-li vytvořit nové knihovny tříd  
  
1.  Na **soubor** nabídce zvolte **nový > projekt**.  
  
2.  V **nový projekt** dialogovém **Visual C#**, vyberte **.NET Standard**.  
  
3.  V prostředním podokně vyberte **knihovny tříd**.   
  
4.  V **název** zadejte vhodný název pro knihovnu tříd, jako je například MySecondVisualizer.  
  
5.  Click **OK**.  
  
 Teď můžete do něj může přidat položku vizualizér:  
  
#### <a name="to-add-a-visualizer-item"></a>Přidat položku vizualizéru  
  
1.  V **Průzkumníku**, klikněte pravým tlačítkem na MySecondVisualizer.  
  
2.  V místní nabídce vyberte **přidat** a pak klikněte na **novou položku**.  
  
3.  V **přidat novou položku** dialogovém **Visual C# položky**, vyberte **vizualizér**.  
  
4.  V **název** zadejte vhodný název, jako je například SecondVisualizer.cs.  
  
5.  Klikněte na tlačítko **přidat**.  
  
 Který je všechny je k němu. Zkontrolujte soubor SecondVisualizer.cs a zobrazit kód, který šablony přidat za vás. Pokračujte a Experimentujte s kódem. Nyní když znáte základy, jste si k vytvoření složitých a užitečné vizualizérech vlastní.  
  
## <a name="see-also"></a>Viz také  
 [Architektura vizualizéru](../debugger/visualizer-architecture.md)   
 [Postupy: instalace Vizualizéru](../debugger/how-to-install-a-visualizer.md)   
 [Vytvořit vlastní Vizualizérech](../debugger/create-custom-visualizers-of-data.md)
