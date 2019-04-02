---
title: Aktualizace sady Visual Studio
titleSuffix: ''
description: Zjistěte, jak aktualizovat na nejnovější verzi, podrobné sady Visual Studio.
ms.date: 03/30/2019
ms.custom: seodec18
ms.topic: conceptual
ms.prod: visual-studio-windows
ms.technology: vs-installation
helpviewer_keywords:
- update [Visual Studio]
- change [Visual Studio]
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7f23ad749fc2a1d71153fd3adf2503a0c3108bf6
ms.sourcegitcommit: d4bea2867a4f0c3b044fd334a54407c0fe87f9e8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2019
ms.locfileid: "58790196"
---
# <a name="update-visual-studio-to-the-most-recent-release"></a>Aktualizace na nejnovější verzi sady Visual Studio

::: moniker range="vs-2017"

Doporučujeme vám přejít na maximum [novější verzi](/visualstudio/releasenotes/vs2017-relnotes/) sady Visual Studio 2017 tak, že vždycky získáte nejnovější funkce, opravy a vylepšení.

A pokud chcete vyzkoušet další verze, vezměte v úvahu stahování [verze Release candidate](//visualstudio/releases/2019/release-notes/) sady Visual Studio 2019 příliš.

> [!IMPORTANT]
> Musíte se přihlásit pomocí účtu, který má oprávnění správce k instalaci, aktualizaci nebo úpravy sady Visual Studio. Další informace najdete v tématu [uživatelská oprávnění a sada Visual Studio](../ide/user-permissions-and-visual-studio.md).
>
> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac, najdete v části [aktualizace sady Visual Studio pro Mac](/visualstudio/mac/update).

## <a name="update-visual-studio-2017-version-156-or-later"></a>Aktualizace sady Visual Studio 2017 verze 15.6 nebo novější

My jsme nově zjednodušili instalace a aktualizovat prostředí, aby bylo snazší pro použití přímo z integrovaného vývojového prostředí. Tady je postup k aktualizaci z verze 15.6 a novějším, která je novější verze sady Visual Studio.

### <a name="using-the-notifications-hub"></a>Pomocí centra oznámení

Při aktualizaci neexistuje odpovídající příznak oznámení v sadě Visual Studio.

1. Uložte si práci.

1. Zvolte na příznak oznámení a otevřete **oznámení** hub a klikněte na tlačítko aktualizace, ke které chcete nainstalovat.

   ![Aktualizace sady Visual Studio 2017 pomocí centra oznámení](media/vs-install-notifications-hub-15dot6.png "centru oznámení sadě Visual Studio 2017")

      > [!TIP]
      > Je kumulativní aktualizace pro edice Visual Studio 2019, takže vždy rozhodnout je nainstalovat jeden nejnovější číslo verze.

1. Když **aktualizace** dialogové okno se otevře, zvolte **aktualizovat**.

    ![Visual Studio 2017 můžete aktualizovat pomocí dialogového okna aktualizace v centru oznámení](media/vs-update-now-from-notifications-hub.png "dialogové okno aktualizace v centru oznámení v sadě Visual Studio")

     Pokud se otevře dialogové okno Řízení uživatelských účtů, zvolte **Ano**. V dalším kroku může na chvíli otevřete dialog "Čekejte prosím" a potom instalační program sady Visual Studio otevře spustíte aktualizaci.

     ![Nové prostředí instalačního programu sady Visual Studio ve verzi 15.6](media/visual-studio-15dot6-installer.png "nové prostředí instalačního programu sady Visual Studio ve verzi 15.6")

     Pokračuje v aktualizaci. Poté po dokončení restartování sady Visual Studio.

     > [!NOTE]
     > Když spustíte Visual Studio v režimu správce, musíte ručně restartovat Visual Studio po aktualizaci.

### <a name="using-the-ide"></a>Používání prostředí IDE

Můžete si vyhledejte aktualizaci a potom nainstalovat na panelu nabídek v sadě Visual Studio.

1. Uložte si práci.

1. Zvolte **pomáhají** > **vyhledávat aktualizace**.

     ![Nové nabídky Nápověda v sadě Visual Studio verze 15.6](media/vs-help-menu-check-for-updates.png "nové nabídky Nápověda v sadě Visual Studio verze 15.6")

1. Když **aktualizace** dialogové okno se otevře, zvolte **aktualizovat**.

   Aktualizace pokračuje, jak je popsáno v předchozí části a pak Visual Studio se restartuje po úspěšném dokončení aktualizace.

   > [!NOTE]
   > Když spustíte Visual Studio v režimu správce, musíte ručně restartovat Visual Studio po aktualizaci.

### <a name="using-the-visual-studio-installer"></a>Pomocí instalačního programu sady Visual Studio

Stejně jako v dřívějších verzích sady Visual Studio můžete použít instalační program sady Visual Studio pro instalaci aktualizace.

1. Uložte si práci.

1. Spusťte instalační program. Instalační program sady Visual Studio může vyžadovat aktualizaci, než budete pokračovat.

   > [!NOTE]
   > Na počítači se systémem Windows 10, najdete instalační program pod písmenem **V** jako **instalační program sady Visual Studio**, nebo pod písmenem **M** jako  **Instalační program sady Microsoft Visual Studio**.

1. Na **produktu** stránce v instalačním programu, hledejte pro edici sady Visual Studio, kterou jste nainstalovali.

1. Pokud je k dispozici aktualizace, zobrazí se **aktualizovat** tlačítko. (Může trvat několik sekund, než instalační program k určení, zda je k dispozici aktualizace.)

   Zvolte **aktualizace** tlačítko Instalovat aktualizace.

     ![Aktualizace sady Visual Studio 2017 s použitím instalačního programu sady Visual Studio](media/update-visual-studio.png "aktualizace sady Visual Studio 2017 s použitím instalačního programu sady Visual Studio")

## <a name="update-visual-studio-2017-version-155-or-earlier"></a>Aktualizace sady Visual Studio 2017 verze 15.5 nebo starší

Pokud používáte starší verzi, tady je postup, chcete-li použít aktualizace ze sady Visual Studio 2017 verze 15.0 prostřednictvím verze 15.5.

### <a name="update-by-using-the-notifications-hub"></a>Aktualizovat pomocí centra oznámení

1. Pokud jsou dostupné aktualizace, je v sadě Visual Studio odpovídající příznak oznámení.

   ![Aktualizace sady Visual Studio 2017 pomocí centra oznámení](media/notification-flag.png "aktualizace příznaku oznámení v sadě Visual Studio")

   Zvolte na příznak oznámení a otevřete **oznámení** rozbočovače.

   ![Aktualizace sady Visual Studio 2017 pomocí centra oznámení](media/notifications-hub.png "centru oznámení v sadě Visual Studio")

      > [!TIP]
      > Je kumulativní aktualizace pro edice Visual Studio 2017, takže vždy rozhodnout je nainstalovat jeden nejnovější číslo verze.

1. Zvolte **"Visual Studio Update" je k dispozici**, které se otevře **rozšíření a aktualizace** dialogové okno.

   ![Aktualizace sady Visual Studio 2017 pomocí centra oznámení](media/notifications-hub-select.png "centru oznámení v sadě Visual Studio")

1. V **rozšíření a aktualizace** dialogového okna zvolte **aktualizace** tlačítko.

   ![Aktualizace sady Visual Studio 2017 pomocí centra oznámení](media/notifications-extensions-and-updates.png "The rozšíření a aktualizace dialogového okna v sadě Visual Studio")

#### <a name="more-about-visual-studio-notifications"></a>Další informace o sadě Visual Studio oznámení

Visual Studio vás upozorní, když je aktualizace k dispozici pro samotnou sadu Visual Studio nebo pro všechny součásti a také při výskytu určitých událostí v prostředí sady Visual Studio.

* Když na příznak oznámení je žlutý, aktualizace produktu Visual Studio pro není k dispozici k instalaci.
* Po červenou na příznak oznámení je nějaký problém s vaší licencí.
* Po černou na příznak oznámení nejsou nepovinné nebo informační zprávy ke kontrole.

Vyberte příznak oznámení a otevřete **oznámení** centra a potom vyberte oznámení, které chcete zpracovat. Nebo můžete rozhodnout ignorovat nebo chcete oznámení zavřít.

 ![Volitelný nebo informační zprávu zobrazit v centru oznámení](media/notification-flag-optional.png "volitelný nebo informační zpráva příznaku oznámení v sadě Visual Studio")

Pokud vyberete možnost Ignorovat upozornění, Visual Studio zastaví, abych ho. Pokud chcete obnovit seznam ignorovaná oznámení, zvolte **nastavení** tlačítko v centru oznámení.

   ![Klikněte na tlačítko nastavení v centru oznámení zobrazíte oznámení možnosti](media/vs-notifications-hub-settings-button.png "klikněte na tlačítko nastavení v centru oznámení zobrazíte možnosti oznámení")

### <a name="update-by-using-the-visual-studio-installer"></a>Aktualizovat pomocí instalačního programu sady Visual Studio

1. Spusťte instalační program. Může být potřeba aktualizovat instalační program, než budete pokračovat. Pokud je to tento případ, budete vyzváni k tomu.

   > [!NOTE]
   > Na počítači se systémem Windows 10, najdete instalační program pod písmenem **V** jako **instalační program sady Visual Studio**, nebo pod písmenem **M** jako  **Instalační program sady Microsoft Visual Studio**.

1. Na **produktu** stránce v instalačním programu, hledejte pro edici sady Visual Studio, kterou jste nainstalovali.

1. Pokud je k dispozici aktualizace, zobrazí se **aktualizovat** tlačítko. (Může trvat několik sekund, než instalační program k určení, zda je k dispozici aktualizace.)

   Zvolte **aktualizace** tlačítko Instalovat aktualizace.

     ![Aktualizace sady Visual Studio 2017 s použitím instalačního programu sady Visual Studio](media/update-visual-studio.png "aktualizace sady Visual Studio pomocí instalačního programu sady Visual Studio")

::: moniker-end

::: moniker range="vs-2019"

Doporučujeme vám přejít na maximum [novější verzi](/visualstudio/releases/2019/release-notes/) sady Visual Studio 2019 tak, že vždycky získáte nejnovější funkce, opravy a vylepšení.

> [!IMPORTANT]
> Musíte se přihlásit pomocí účtu, který má oprávnění správce k instalaci, aktualizaci nebo úpravy sady Visual Studio. Další informace najdete v tématu [uživatelská oprávnění a sada Visual Studio](../ide/user-permissions-and-visual-studio.md).
>
> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac, najdete v části [aktualizace sady Visual Studio pro Mac](/visualstudio/mac/update).

Tady je postup, chcete-li aktualizovat vizuál&nbsp;Studio&nbsp;2019&nbsp;ve verzi Preview nebo Visual&nbsp;Studio&nbsp;2019&nbsp;RC.

## <a name="use-the-visual-studio-installer"></a>Použití instalačního programu sady Visual Studio

1. Spusťte instalační program.

     ![Spusťte instalační program sady Visual Studio](media/vs2019-visual-studio-installer.png "spusťte instalační program sady Visual Studio")

   Budete muset aktualizovat instalační program pokračovat. Pokud ano, postupujte podle pokynů.

1. V instalačním programu vyhledejte edici sady Visual Studio, který jste nainstalovali.

   Například, pokud jste dříve nainstalovali Visual&nbsp;Studio Community&nbsp;2019&nbsp;RC a zde je aktualizace pro něj a potom **k dispozici je aktualizace** v instalačním programu se zobrazí zpráva.

     ![Zvolte edici sady Visual Studio 2019, kterou chcete aktualizovat](media/vs2019-update-visual-studio-community-rc.png "zvolte edici sady Visual Studio 2019, kterou chcete aktualizovat")

1. Zvolte **aktualizace** nainstalujte aktualizace.

    ![Klikněte na tlačítko aktualizace můžete nainstalovat aktualizace](media/vs2019-choose-update-visual-studio-community-rc.png "klikněte na tlačítko aktualizace můžete nainstalovat aktualizace")

1. Po dokončení aktualizace, zvolte **spuštění** ke spuštění sady Visual Studio.

    ![Vyberte tlačítko Spustit ke spuštění sady Visual Studio](media/vs2019-choose-launch-visual-studio-community-rc.png "vyberte na spouštěcí tlačítko ke spuštění sady Visual Studio")

## <a name="use-the-ide"></a>Pomocí integrovaného vývojového prostředí

Můžete si vyhledejte aktualizaci a pak jej nainstalovat pomocí na řádku nabídek nebo vyhledávací pole v aplikaci Visual Studio 2019.

### <a name="open-visual-studio"></a>Otevřít Visual Studio

1. Z Windows **Start** nabídce zvolte **Visual Studio 2019**.

    ![Otevřít Visual Studio 2019 RC](media/vs2019-visual-studio-rc.png "otevřete Visual Studio 2019 z Windows")

1. V části **Začínáme**, zvolte možnosti otevření rozhraní IDE.

    ![Spusťte instalační program sady Visual Studio](media/vs2019-choose-option-from-get-started.png "spusťte instalační program sady Visual Studio")

    Otevře se Visual Studio. V integrovaném vývojovém prostředí **aktualizace Visual Studio 2019** se zobrazí zpráva.

    ![Zpráva 'aktualizace Visual Studio 2019' v integrovaném vývojovém prostředí](media/vs2019-update-visual-studio-ide-message.png "zpráva 'aktualizace Visual Studio 2019' v integrovaném vývojovém prostředí")

1. V **aktualizace Visual Studio 2019** zprávu, zvolte **podrobnosti**.

   ![Zvolte tlačítko Zobrazit podrobnosti o ve zprávě aktualizace Visual Studio IDE. 2019](media/vs2019-update-visual-studio-ide-view-details.png "klikněte na tlačítko Zobrazit podrobnosti zprávy aktualizace Visual Studio 2019")

1. V **aktualizovat stažený a připravený k instalaci** dialogového okna zvolte **aktualizace**.

     ![Klikněte na tlačítko aktualizace v dialogovém okně aktualizace stažené a připravené k instalaci](media/vs2019-update-visual-studio-community-rc-from-ide.png "klikněte na tlačítko aktualizace v dialogovém okně aktualizace stažené a připravené k instalaci")

   Visual Studio ukončí a potom znovu otevře.

### <a name="in-visual-studio"></a>In Visual Studio

1. Na panelu nabídek zvolte **pomáhají**a klikněte na tlačítko **vyhledávat aktualizace**.

     ![Zvolte možnost "Vyhledat aktualizace z nabídky Nápověda](media/vs-2019/vs-ide-check-updates-help-menu.png "zvolit\"Kontrola aktualizací\"z nabídky Nápověda")

    > [!NOTE]
    > Do vyhledávacího pole v integrovaném vývojovém prostředí můžete také vyhledat aktualizace. Stisknutím klávesy **Ctrl**+**Q**, zadejte "Kontrola aktualizací" a vyberte výsledek hledání, který odpovídá.

1. V **aktualizovat stažený a připravený k instalaci** dialogového okna zvolte **aktualizace**.

     ![Klikněte na tlačítko aktualizace v dialogovém okně aktualizace stažené a připravené k instalaci](media/vs2019-update-visual-studio-community-rc-from-ide.png "klikněte na tlačítko aktualizace v dialogovém okně aktualizace stažené a připravené k instalaci")

   Visual Studio ukončí a potom znovu otevře.

## <a name="use-the-notifications-hub"></a>Použití centra oznámení

1. V sadě Visual Studio uložte si práci.

1. Vyberte ikonu oznámení v pravém horním rohu IDE sady Visual Studio otevřete **oznámení** rozbočovače.

   ![Ikona oznámení v integrovaném vývojovém prostředí sady Visual Studio](media/vs-2019/notification-bar.png "ikonu oznámení v integrovaném vývojovém prostředí sady Visual Studio")

1. V **centrem oznámení**, vyberte aktualizaci, kterou chcete nainstalovat a klikněte na tlačítko **podrobnosti**.

     ![V centru oznámení v aplikaci Visual Studio 2019](media/vs-2019/notification-hub-update.png "centra oznámení v aplikaci Visual Studio 2019")

      > [!TIP]
      > Je kumulativní aktualizace pro edice Visual Studio 2019, takže vždy rozhodnout je nainstalovat jeden nejnovější číslo verze.

1. V **aktualizovat stažený a připravený k instalaci** dialogového okna zvolte **aktualizace**.

   Visual Studio aktualizuje, zavře a znovu neotevře.

::: moniker-end

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Aktualizace síťové instalace sady Visual Studio](update-a-network-installation-of-visual-studio.md)
* [Aktualizace sady Visual Studio pro Mac](/visualstudio/mac/update)
* [Úpravy sady Visual Studio](modify-visual-studio.md)
* [Odinstalace sady Visual Studio](uninstall-visual-studio.md)
