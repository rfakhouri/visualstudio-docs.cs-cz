---
title: Ladění nebo zakázat kód projektu v Návrháři XAML
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ac600581-8fc8-49e3-abdf-1569a3483d74
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 536c69aa9131068397fd0a86576f473db82fbe10
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="debugging-or-disabling-project-code-in-xaml-designer"></a>Ladění nebo zakázat kód projektu v Návrháři XAML
V mnoha případech může být způsobeno neošetřených výjimek v Návrháři XAML kód projektu pokusu o přístup k vlastnosti nebo metody, které vracet různé hodnoty nebo když je aplikace spuštěna v Návrháři pracovních různými způsoby. Můžete tyto výjimky vyřešit ladění projektu kódu v jiné instanci sady Visual Studio, nebo je dočasně zakázat zakázat kód projektu v návrháři.

 Kód projektu zahrnuje:

-   Vlastní ovládací prvky a uživatelské ovládací prvky

-   Knihovny tříd

-   Převodníky hodnot

-   Vazby proti návrhu časových dat generované z projektu kódu

 Pokud je kód projektu zakázáno, Visual Studio se zobrazí zástupné symboly jako název vlastnosti pro vazbu, kde je dat již není k dispozici. nebo zástupný symbol pro ovládací prvek, který je již spuštěn.

 ![Dialogové okno neošetřené výjimky](../designers/media/xaml_unhandledexception.png "XAML_UnhandledException")

#### <a name="to-determine-if-project-code-is-causing-an-exception"></a>Chcete-li zjistit, zda kód projektu je příčinou výjimku

1.  V dialogovém okně neošetřené výjimky, vyberte **klikněte sem a znovu načíst návrháře** odkaz.

2.  V řádku nabídek zvolte **ladění**, **spustit ladění** sestavení a spuštění aplikace.

     Pokud aplikace vytvoří a spustí úspěšně, může být způsobeno spuštěna v Návrháři projektu kódu v době návrhu výjimky.

#### <a name="to-debug-project-code-running-in-the-designer"></a>Chcete-li ladit kód projektu spuštěný v Návrháři

1.  V dialogovém okně neošetřené výjimky, vyberte **kliknutí sem můžete zakázat spuštění kódu projektu a znovu načíst návrháře** odkaz.

2.  Zvolte ve Správci úloh systému Windows **ukončit úlohu** tlačítko zavřete všechny instance návrháři XAML pro Visual Studio, které jsou aktuálně spuštěny.

     ![Instance návrháře XAML v Správce úloh](../designers/media/xaml_taskmanager.png "XAML_TaskManager")

3.  V sadě Visual Studio otevřete stránku XAML, který bude obsahovat kód nebo ovládací prvek, který chcete ladit.

4.  Otevření nové instance sady Visual Studio a pak otevřete druhou instanci projektu.

5.  Nastavte zarážky v kódu projektu.

6.  V nové instanci sady Visual Studio na řádku nabídek zvolte **ladění**, **připojit k procesu**.

7.  V **připojit k procesu** dialogové okno, v **procesy k dispozici** vyberte **XDesProc.exe**a potom vyberte **Attach** tlačítko.

     ![Proces návrháře XAML](../designers/media/xaml_attach.png "XAML_Attach")

     Toto je proces pro Návrhář XAML v sadě Visual Studio na první instanci.

8.  V první instanci sady Visual Studio na řádku nabídek zvolte **ladění**, **spustit ladění**.

     Můžete teď krok do vašeho kódu, který je spuštěn v návrháři.

#### <a name="to-disable-project-code-in-the-designer"></a>Chcete-li zakázat kód projektu v Návrháři

-   V dialogovém okně neošetřené výjimky, vyberte **kliknutí sem můžete zakázat spuštění kódu projektu a znovu načíst návrháře** odkaz.

-   Nebo na panelu nástrojů v Návrháři XAML, zvolte **zakázat kód projektu** tlačítko.

     ![Tlačítko Zakázat kód projektu](../designers/media/xaml_disablecode.png "XAML_DisableCode")

     Můžete přepínat na tlačítko znovu a znovu povolte kód projektu.

    > [!NOTE]
    >  Pro projekty, které používají ARM nebo X64 procesory, Visual Studio nelze spustit projekt kódu v návrháři, proto **zakázat kód projektu** tlačítko k dispozici v návrháři.

-   Buď možnost způsobí, že návrháře znovu načíst a pak vypne všechny kód pro přidružené projektu.

    > [!NOTE]
    >  Zakázat kód projektu může vést ke ztrátám dat čase návrhu. Alternativou je ladit kód spuštěný v návrháři.

## <a name="see-also"></a>Viz také

- [Navrhování XAML v sadě Visual Studio a nástroj Blend for Visual Studio](../designers/designing-xaml-in-visual-studio.md)