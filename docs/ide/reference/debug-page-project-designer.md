---
title: Stránka Ladění, návrhář projektu
ms.date: 06/27/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesDebug
helpviewer_keywords:
- Project Designer, Debug page
- Debug page in Project Designer
ms.assetid: ef11eae9-df96-4e20-aabd-2678ba317140
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c7b79b5aa5054781813d561089dab204bd1763bf
ms.sourcegitcommit: 935e341a02dba1c2aa3b6e89469388aa6e626f7f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/20/2018
ms.locfileid: "53684755"
---
# <a name="debug-page-project-designer"></a>Stránka Ladění, návrhář projektu

Použití **ladění** stránku **Návrháře projektu** můžete nastavit vlastnosti pro ladění chování v projektu jazyka Visual Basic nebo C#.

Pro přístup **ladění** stránky, vyberte uzel projektu v **Průzkumníka řešení**. Na **projektu** nabídce zvolte  **\<název projektu > vlastnosti**. Když **Návrháře projektu** se zobrazí, klikněte na tlačítko **ladění** kartu.

> [!NOTE]
> Toto téma se nevztahuje na aplikacích pro UPW. Zobrazit [spustíte relaci ladění (VB, C#, C++ a XAML)](../../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md) pro aplikace pro UPW.

## <a name="configuration-and-platform"></a>Konfigurace a platforma

Tyto možnosti umožňují vybrat konfigurace a platformy k zobrazení a úpravě.

**Konfigurace**

Určuje které nastavení konfigurace má být zobrazeno nebo upraveno. Toto nastavení může být **ladění** (výchozí), **vydání**, nebo **všechny konfigurace**.

**Platforma**

Určuje které nastavení platformy má být zobrazeno nebo upraveno. Může zahrnovat volby **jakýkoli procesor** (výchozí), **x64**, a **x86**.

## <a name="start-action"></a>Spustit akci

**Zahájení** označuje položku, která se spustí při ladění aplikace: projekt, vlastní program, adresu URL nebo žádnou akci. Ve výchozím nastavení je tato možnost nastavená na **spustit projekt**. **Spustit akci** nastavení **ladění** stránky určuje hodnotu `StartAction` vlastnost.

**Spustit projekt**

Tato možnost slouží k určení, že spustitelný soubor (pro projekty aplikací pro Windows a Konzolová aplikace) by měl být spuštěn při ladění aplikace. Ve výchozím nastavení je vybraná tato možnost.

**spustit externí program**

Tato možnost slouží k určení, že konkrétní program má být spuštěn při ladění aplikace.

**Spustit prohlížeč s adresou URL**

Tato možnost slouží k určení, že určité adresy URL by měl mít přístup při ladění aplikace.

## <a name="start-options"></a>Možnosti spuštění

**Argumenty příkazového řádku**

Do tohoto textového pole zadejte argumenty příkazového řádku pro ladění.

**Pracovní adresář**

Do tohoto textového pole zadejte adresář, ze které bude projekt spustit. Nebo klikněte na tlačítko Procházet (**...** ) Chcete-li vybrat adresář.

**Použití vzdáleného počítače**

Chcete-li ladit aplikaci ze vzdáleného počítače, zaškrtněte toto políčko a zadejte cestu ke vzdálenému počítači v textovém poli.

## <a name="debugger-engines"></a>Ladicím modulem.

**Povolit ladění nativního kódu**

Tato možnost určuje, zda je podporováno ladění nativního kódu. Toto políčko zaškrtněte, pokud jsou objekty COM volání nebo spustit vlastní program napsány v nativním kódu, která volá váš projekt a musí ladění nativního kódu. Zrušte zaškrtnutí tohoto políčka Zakázat ladění nespravovaného kódu. Toto políčko je ve výchozím nastavení zaškrtnuté.

**Povolit ladění SQL serveru**

Zaškrtněte nebo zrušte zaškrtnutí políčka Povolit nebo zakázat ladění procedur SQL z aplikace Visual Basic. Toto políčko je ve výchozím nastavení zaškrtnuté.

## <a name="see-also"></a>Viz také:

- [Ladění v sadě Visual Studio](../../debugger/debugger-feature-tour.md)
- [Nastavení projektu pro konfiguraci ladění jazyka C#](../../debugger/project-settings-for-csharp-debug-configurations.md)
- [Nastavení projektu pro konfiguraci ladění jazyka Visual Basic](../../debugger/project-settings-for-a-visual-basic-debug-configuration.md)
- [Postupy: Ladění aplikace ClickOnce s omezenými oprávněními](../../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)
- [Postupy: Vytvoření a úprava konfigurací](../../ide/how-to-create-and-edit-configurations.md)