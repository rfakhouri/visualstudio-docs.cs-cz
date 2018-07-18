---
title: Ladění nebo zakázání kódu projektu v Návrháři XAML
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: ac600581-8fc8-49e3-abdf-1569a3483d74
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 4764df436a7adeb3ac65c574812c8f7d334d497b
ms.sourcegitcommit: 522ba712c0d625e51352506146b0556414681964
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/06/2018
ms.locfileid: "37890562"
---
# <a name="debug-or-disable-project-code-in-xaml-designer"></a>Ladění nebo zakázání kódu projektu v Návrháři XAML

V mnoha případech neošetřené výjimky v **XAML** Návrhář může být způsobeno kód projektu pokusu o přístup k vlastnosti nebo metody, které vracet různé hodnoty, nebo fungují jiným způsobem, při spuštění aplikace v návrháři. Můžete tyto výjimky vyřešit ladění kódu projektu v jiné instanci sady Visual Studio nebo dočasně zakázat kód projektu v Návrháři tak zabránit výjimky.

Kód projektu zahrnuje:

-   Vlastní ovládací prvky a uživatelských ovládacích prvků

-   Knihovny tříd

-   Převodníky hodnot

-   Vazby proti návrhovém generován z kódu projektu

Když kód projektu je zakázaný, sada Visual Studio zobrazí zástupné symboly. Například sada Visual Studio zobrazí název vlastnosti pro vazbu, kde data už nejsou k dispozici, nebo zástupný symbol pro ovládací prvek, který je již neběží.

![Dialogové okno neošetřené výjimky](../designers/media/xaml_unhandledexception.png)

## <a name="to-determine-if-project-code-is-causing-an-exception"></a>Chcete-li zjistit, zda kód projektu je příčinou výjimku

1.  V dialogovém okně neošetřenou výjimku, zvolte **klinutím sem zopakujete zavedení návrháře** odkaz.

2.  Na panelu nabídek zvolte **ladění** > **spustit ladění** sestavíte a spustíte aplikaci.

     Pokud se aplikace sestaví a spustí úspěšně, výjimka návrhu může být způsobeno spuštění v Návrháři projektu kódu.

## <a name="to-debug-project-code-running-in-the-designer"></a>Chcete-li ladit projekt kódu spuštěného v Návrháři

1.  V dialogovém okně neošetřenou výjimku, zvolte **kliknutím sem zakážete spuštění kódu projektu a opětovné načtení návrháře** odkaz.

2.  Vyberte ve Správci úloh Windows **ukončit úlohu** zavřete všechny instance návrháři XAML sady Visual Studio, které jsou aktuálně spuštěny.

     ![Instance návrháře XAML v Správce úloh](../designers/media/xaml_taskmanager.png)

3.  V sadě Visual Studio otevřete stránku XAML, který bude obsahovat kód nebo ovládací prvek, který chcete ladit.

4.  Otevřete novou instanci sady Visual Studio a pak otevřete druhou instanci projektu.

5.  Nastavte zarážku v kódu projektu.

6.  V nové instanci sady Visual Studio na řádku nabídek zvolte **ladění** > **připojit k procesu**.

7.  V **připojit k procesu** dialogového okna v **procesy k dispozici** klikněte na položku **XDesProc.exe**a klikněte na tlačítko **připojit** tlačítko.

     ![Proces návrháře XAML](../designers/media/xaml_attach.png)

     Jedná se o proces pro návrháře XAML v první instance sady Visual Studio.

8.  V první instanci sady Visual Studio na panelu nabídek zvolte **ladění** > **spustit ladění**.

     Nyní můžete krokovat do svého kódu, který je spuštěn v návrháři.

## <a name="to-disable-project-code-in-the-designer"></a>Chcete-li zakázat kód projektu v Návrháři

-   V dialogovém okně neošetřenou výjimku, zvolte **kliknutím sem zakážete spuštění kódu projektu a opětovné načtení návrháře** odkaz.

-   Taky můžete na panelu nástrojů **návrháře XAML**, zvolte **zakázat kód projektu** tlačítko.

     ![Tlačítko Zakázat kód projektu](../designers/media/xaml_disablecode.png)

     Můžete přepínat na tlačítko znovu pro opětovné povolení kódu projektu.

    > [!NOTE]
    > Pro projekty, které cílí ARM nebo X64 procesory, Visual Studio nelze spustit kód projektu v návrháři, proto **zakázat kód projektu** je tlačítko neaktivní v návrháři.

-   Možnost způsobí, že návrháře znovu načíst a potom zakázat veškerý kód pro přidružený projekt.

    > [!NOTE]
    > Zakázání kódu projektu může vést ke ztrátám dat doby návrhu. Alternativou je pro ladění kódu spuštěného v návrháři.

## <a name="see-also"></a>Viz také:

- [Návrh XAML v sadě Visual Studio a nástroje Blend for Visual Studio](../designers/designing-xaml-in-visual-studio.md)