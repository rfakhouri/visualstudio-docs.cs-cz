---
title: Stránka Ladění, návrhář projektu
ms.date: 06/27/2018
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesDebug
helpviewer_keywords:
- Project Designer, Debug page
- Debug page in Project Designer
ms.assetid: ef11eae9-df96-4e20-aabd-2678ba317140
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a1f54485a4dd47b0aec4401f6cdfb39072e9f8cf
ms.sourcegitcommit: 85d66dc9fea3fa49018263064876b15aeb6f9584
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2019
ms.locfileid: "68461410"
---
# <a name="debug-page-project-designer"></a>Stránka Ladění, návrhář projektu

Pomocí stránky **ladění** v **Návrháři projektu** můžete nastavit vlastnosti pro chování ladění v Visual Basic nebo C# projektu.

Chcete-li získat přístup ke stránce **ladění** , vyberte uzel projektu v **Průzkumník řešení**. V nabídce **projekt** vyberte  **\<ProjectName > vlastnosti**. Když se zobrazí **Návrhář projektu** , klikněte na kartu **ladění** .

> [!NOTE]
> Toto téma se nevztahuje na aplikacích pro UPW. Viz [zahájit ladicí relaci (VB, C# C++ a XAML)](../../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md) pro aplikace pro UWP.

## <a name="configuration-and-platform"></a>Konfigurace a platforma

Následující možnosti umožňují vybrat konfiguraci a platformu pro zobrazení nebo úpravu.

**Konfigurace**

Určuje, která nastavení konfigurace se mají zobrazit nebo upravit. Nastavení lze **ladit** (výchozí), vydávat nebo **všechny konfigurace**.

**Platformy**

Určuje, která nastavení platformy se mají zobrazit nebo upravit. Volby můžou zahrnovat **jakýkoli procesor** (výchozí), **x64**a **x86**.

## <a name="start-action"></a>Spustit akci

**Akce spustit** označuje položku, která se má spustit při ladění aplikace: projekt, vlastní program, adresa URL nebo nic. Ve výchozím nastavení je tato možnost nastavena na hodnotu **spustit projekt**. Hodnota vlastnosti určuje nastavení **Akce zahájit** na stránce **ladění.** `StartAction`

**Spustit projekt**

Tuto možnost zvolte, chcete-li určit, zda má být spuštěn spustitelný soubor (pro projekty aplikace systému Windows a Konzolová aplikace) při ladění aplikace. Tato možnost je vybrána ve výchozím nastavení.

**Spustit externí program**

Tuto možnost vyberte, pokud chcete určit, že se má při ladění aplikace spustit konkrétní program.

**Spustit prohlížeč s adresou URL**

Tuto možnost vyberte, pokud chcete určit, že při ladění aplikace má být k určité adrese URL přistupovaná konkrétní adresa URL.

## <a name="start-options"></a>Možnosti spuštění

**Argumenty příkazového řádku**

Do tohoto textového pole zadejte argumenty příkazového řádku, které chcete použít pro ladění.

**Pracovní adresář**

Do tohoto textového pole zadejte adresář, ze kterého se projekt spustí. Nebo klikněte na tlačítko pro procházení ( **...** ) a vyberte adresář.

**Použít vzdálený počítač**

Chcete-li ladit aplikaci ze vzdáleného počítače, zaškrtněte toto políčko a do textového pole zadejte cestu ke vzdálenému počítači.

## <a name="debugger-engines"></a>Moduly ladicího programu

**Povolit ladění nativního kódu**

Tato možnost určuje, zda je podporováno ladění nativního kódu. Zaškrtněte toto políčko, pokud provádíte volání objektů COM nebo pokud spustíte vlastní program napsaný v nativním kódu, který volá váš projekt, a musíte ladit nativní kód. Zrušením zaškrtnutí tohoto políčka zakážete ladění nespravovaného kódu. Toto políčko je ve výchozím nastavení zaškrtnuté.

**Povolit ladění SQL Server**

Zaškrtnutím nebo zrušením zaškrtnutí tohoto políčka povolíte nebo zakážete ladění procedur SQL z aplikace Visual Basic. Toto políčko je ve výchozím nastavení zaškrtnuté.

## <a name="see-also"></a>Viz také:

- [První seznámení s ladicím programem](../../debugger/debugger-feature-tour.md)
- [Nastavení projektu pro konfiguraci ladění jazyka C#](../../debugger/project-settings-for-csharp-debug-configurations.md)
- [Nastavení projektu pro konfiguraci ladění jazyka Visual Basic](../../debugger/project-settings-for-a-visual-basic-debug-configuration.md)
- [Postupy: Ladění aplikace ClickOnce s omezenými oprávněními](../../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)
- [Postupy: Vytvoření a úprava konfigurací](../../ide/how-to-create-and-edit-configurations.md)