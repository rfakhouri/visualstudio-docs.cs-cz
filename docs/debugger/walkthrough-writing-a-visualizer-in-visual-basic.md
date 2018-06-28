---
title: 'Návod: Zápis Vizualizéru v jazyce Visual Basic | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- visualizers, writing
- walkthroughs [Visual Studio], visualizers
ms.assetid: c93bf5a1-3e5e-422f-894e-bd72c9bc1b57
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ba2be58b600a57fb405b55069df1c838019bfdab
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37058695"
---
# <a name="walkthrough-writing-a-visualizer-in-visual-basic"></a>Návod: Zápis vizualizéru v jazyce Visual Basic
Tento návod ukazuje, jak napsat Jednoduchý vizualizér pomocí [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]. Vizualizér, které vytvoříte v tomto návodu zobrazí obsah řetězce pomocí Windows Forms okno se zprávou. Tento jednoduchý řetězec vizualizér je základní příklad zobrazit, jak můžete vytvořit vizualizérech pro jiné datové typy hodí víc do vašich projektů.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídky, které vidíte, se může lišit od těch popsaných v nápovědě, v závislosti na aktivním nastavení nebo edici. Chcete-li změnit nastavení, přejděte na **nástroje** nabídky a zvolte **Import a Export** . Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
 Vizualizér kód musí být umístěn v knihovně DLL, která bude načten modulem ladicího programu. Prvním krokem je vytvoření projektu knihovny tříd pro knihovnu DLL.  
  
## <a name="create-and-prepare-a-class-library-project"></a>Vytvoření a přípravě projektu knihovny tříd  
  
#### <a name="to-create-a-class-library-project"></a>Vytvoření projektu knihovny tříd  
  
1.  Na **soubor** nabídce zvolte **nový** a klikněte na tlačítko **nový projekt**.  
  
2.  V **nový projekt** dialogovém **typu projektu**s, klikněte na tlačítko **jazyka Visual Basic**.  
  
3.  V **šablony** pole, klikněte na tlačítko **knihovny tříd**.  
  
4.  V **název** zadejte vhodný název pro knihovnu tříd, jako například **MyFirstVisualizer**.  
  
5.  Klikněte na tlačítko **OK**.  
  
 Po vytvoření knihovny tříd, je musí přidat odkaz na Microsoft.VisualStudio.DebuggerVisualizers.DLL, tak, aby můžete tříd definovaných existuje. Nejprve však dáváte projektu nějaký výstižný název.  
  
#### <a name="to-rename-class1vb-and-add-microsoftvisualstudiodebuggervisualizers"></a>Přejmenovat Class1.vb a přidat Microsoft.VisualStudio.DebuggerVisualizers  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **Class1.vb**a v místní nabídce klikněte na tlačítko **přejmenovat**.  
  
2.  Změňte název na něco smysluplného, například DebuggerSide.vb z Class1.vb.  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky změní deklaraci třídy v DebuggerSide.vb tak, aby odpovídaly nový název souboru.  
  
3.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **Můj první vizualizér**a v místní nabídce klikněte na tlačítko **přidat odkaz na**.  
  
4.  V **přidat odkaz na** v dialogovém **.NET** , klikněte na Microsoft.VisualStudio.DebuggerVisualizers.DLL.  
  
5.  Klikněte na tlačítko **OK**.  
  
6.  V DebuggerSide.vb, přidejte následující příkaz na `Imports` příkazy:  
  
    ```vb
    Imports Microsoft.VisualStudio.DebuggerVisualizers  
    ```  
  
## <a name="add-the-debugger-side-code"></a>Přidejte kód straně ladicí program  
 Nyní jste připraveni vytvořit kód straně ladicí program. Toto je kód, který běží v ladicím programu pro zobrazení informací, které chcete vizualizovat. Nejprve budete muset změnit deklaraci `DebuggerSide` objektu tak, aby ho dědí vlastnosti ze základní třídy `DialogDebuggerVisualizer`.  
  
#### <a name="to-inherit-from-dialogdebuggervisualizer"></a>Dědění z DialogDebuggerVisualizer  
  
1.  V DebuggerSide.vb přejděte na následující řádek kódu:  
  
    ```vb
    Public Class DebuggerSide  
    ```  
  
2.  Upravte kód tak, aby vypadá takto:  
  
    ```vb
    Public Class DebuggerSide  
    Inherits DialogDebuggerVisualizer  
    ```  
  
 `DialogDebuggerVisualizer` má jeden abstraktní metodu `Show`, který je nutné přepsat.  
  
#### <a name="to-override-the-dialogdebuggervisualizershow-method"></a>Přepsat metodu DialogDebuggerVisualizer.Show  
  
-   V `public class DebuggerSide`, přidejte následující metodu:  
  
    ```vb
    Protected Overrides Sub Show(ByVal windowService As Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService, ByVal objectProvider As Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider)  
  
        End Sub  
    ```  
  
 `Show` Metoda obsahuje kód, který skutečně vytváří dialogové okno vizualizér nebo jiných prvků uživatelského rozhraní a zobrazí informace, které byla předána vizualizér z ladicího programu. Je nutné přidat kód, který vytvoří dialogové okno a zobrazí informace. V tomto návodu jste se to provést pomocí Windows Forms okno se zprávou. Nejdřív musíte přidat odkaz a `Imports` příkaz pro <xref:System.Windows.Forms>.  
  
#### <a name="to-add-systemwindowsforms"></a>Chcete-li přidat System.Windows.Forms  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **odkazy**a v místní nabídce klikněte na tlačítko **přidat odkaz na**.  
  
2.  V **přidat odkaz na** v dialogovém **.NET** , klikněte na **System.Windows.Forms**.  
  
3.  Klikněte na tlačítko **OK**.  
  
4.  V DebuggerSide.cs, přidejte následující příkaz na `Imports` příkazy:  
  
    ```vb
    Imports System.Windows.Forms  
    ```  
  
## <a name="create-your-visualizers-user-interface"></a>Vytvoření vaší vizualizér uživatelského rozhraní  
 Nyní přidáte kód, který vytvořit a zobrazit uživatelské rozhraní pro vaše vizualizér. Protože je to vaše první vizualizér, bude zjednodušení uživatelské rozhraní a použijte okno se zprávou.  
  
#### <a name="to-show-the-visualizer-output-in-a-dialog-box"></a>Chcete-li zobrazit výstup vizualizér v dialogovém okně  
  
1.  V `Show` metoda, přidejte následující řádek kódu:  
  
    ```vb
    MessageBox.Show(objectProvider.GetObject().ToString())  
    ```  
  
     Tento příklad kódu nezahrnuje zpracování chyb. Zpracování chyb v skutečné vizualizér nebo jakýkoli jiný druh aplikace by měla obsahovat.  
  
2.  Na **sestavení** nabídky, klikněte na tlačítko **sestavení MyFirstVisualizer**. Projekt má sestavit úspěšně. Než budete pokračovat, opravte všechny chyby sestavení.  
  
## <a name="add-the-necessary-attribute"></a>Přidat atribut potřeby  
 Konec kód straně ladicí program, který je. Neexistuje jeden krok, ale: atribut, který sděluje na straně pozastaven kolekce tříd, které se skládá z vizualizér.  
  
#### <a name="to-add-the-debugee-side-code"></a>Chcete-li přidat kód debugee straně  
  
1.  Přidejte následující kód atribut DebuggerSide.vb, po `Imports` příkazy ale předtím, než `namespace MyFirstVisualizer`:  
  
    ```vb
    <Assembly: System.Diagnostics.DebuggerVisualizer(GetType(MyFirstVisualizer.DebuggerSide), GetType(VisualizerObjectSource), Target:=GetType(System.String), Description:="My First Visualizer")>  
    ```  
  
2.  Na **sestavení** nabídky, klikněte na tlačítko **sestavení MyFirstVisualizer**. Projekt má sestavit úspěšně. Než budete pokračovat, opravte všechny chyby sestavení.  
  
## <a name="create-a-test-harness"></a>Vytvořit testovací nástroje  
 V tomto okamžiku je vaší první vizualizér bylo dokončeno. Pokud jste postupovali podle kroků správně, můžete vytvořit vizualizér a nainstalovat ji do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Před instalací vizualizéru do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ale měli byste otestovat a ujistit se, že běží správně. Nyní vytvoříte test harness ke spuštění vizualizér bez instalace do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
#### <a name="to-add-a-test-method-to-show-the-visualizer"></a>Přidání metody testovací zobrazíte vizualizéru  
  
1.  Přidejte následující metodu do třídy `public DebuggerSide`:  
  
    ```vb
    Shared Public Sub TestShowVisualizer(ByVal objectToVisualize As Object)  
        Dim visualizerHost As New VisualizerDevelopmentHost(objectToVisualize, GetType(DebuggerSide))  
    visualizerHost.ShowVisualizer()  
    End Sub  
    ```  
  
2.  Na **sestavení** nabídky, klikněte na tlačítko **sestavení MyFirstVisualizer**. Projekt má sestavit úspěšně. Než budete pokračovat, opravte všechny chyby sestavení.  
  
 Dále musíte vytvořit spustitelný projekt volat vaše vizualizér knihovny DLL. Pro jednoduchost použijte projekt konzolové aplikace.  
  
#### <a name="to-add-a-console-application-project-to-the-solution"></a>Chcete-li do řešení přidat projekt konzolové aplikace  
  
1.  Na **soubor** nabídky, klikněte na tlačítko **přidat**a potom klikněte na **nový projekt**.  
  
2.  V **přidat nový projekt** dialogu **šablony** pole, klikněte na tlačítko **konzolové aplikace**.  
  
3.  V **název** zadejte nějaký výstižný název konzolové aplikace, jako například **MyTestConsole**.  
  
4.  Klikněte na tlačítko **OK**.  
  
 Nyní je nutné přidat tak MyTestConsole můžete volat MyFirstVisualizer odkazuje na nezbytné.  
  
#### <a name="to-add-necessary-references-to-mytestconsole"></a>Chcete-li přidat nezbytné odkazy na MyTestConsole  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **MyTestConsole**a v místní nabídce klikněte na tlačítko **přidat odkaz na**.  
  
2.  V **přidat odkaz na** v dialogovém **.NET** , klikněte na Microsoft.VisualStudio.DebuggerVisualizers.  
  
3.  Klikněte na tlačítko **OK**.  
  
4.  Klikněte pravým tlačítkem na **MyTestConsole**a potom klikněte na **přidat odkaz na** znovu.  
  
5.  V **přidat odkaz na** dialogové okno, klikněte na tlačítko **projekty** a pak vyberte MyFirstVisualizer.  
  
6.  Klikněte na tlačítko **OK**.  
  
## <a name="finish-your-test-harness-and-test-your-visualizer"></a>Dokončit Test Harness a testování vaší Vizualizéru  
 Nyní přidáte kód, který dokončit test harness.  
  
#### <a name="to-add-code-to-mytestconsole"></a>Přidání kódu do MyTestConsole  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **soubor Program.vb**a v místní nabídce klikněte na tlačítko **přejmenovat**.  
  
2.  Upravit název z Module1.vb něco odpovídající, jako například **TestConsole.vb**.  
  
     Všimněte si, že [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky změní deklaraci třídy v TestConsole.vb tak, aby odpovídaly nový název souboru.  
  
3.  V TestConsole. VB, přidejte následující `Imports` příkaz:  
  
    ```vb
    Imports MyFirstVisualizer  
    ```  
  
4.  V metodě `Main`, přidejte následující kód:  
  
    ```vb
    Dim myString As String = "Hello, World"  
    DebuggerSide.TestShowVisualizer(myString)  
    ```  
  
 Nyní jste připraveni k testování vaší první vizualizér.  
  
#### <a name="to-test-the-visualizer"></a>K testování vizualizéru  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **MyTestConsole**a v místní nabídce klikněte na tlačítko **nastavit jako spouštěný projekt**.  
  
2.  Na **ladění** nabídky, klikněte na tlačítko **spustit**.  
  
     Konzolové aplikace spustí. Vizualizér zobrazí se text "Hello, World."  
  
 Blahopřejeme. Máte právě vytvořené a testování vaší první vizualizér.  
  
 Pokud chcete používat vaše vizualizér v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] místo právě ho volání z test harness, je nutné ji nainstalovat. Další informace najdete v tématu [postupy: instalace Vizualizéru](../debugger/how-to-install-a-visualizer.md).  
  
## <a name="see-also"></a>Viz také  
 [Architektura vizualizéru](../debugger/visualizer-architecture.md)   
 [Postupy: instalace Vizualizéru](../debugger/how-to-install-a-visualizer.md)   
 [Vytvořit vlastní Vizualizérech](../debugger/create-custom-visualizers-of-data.md)
