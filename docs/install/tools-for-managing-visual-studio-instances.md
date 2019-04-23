---
title: Nástroje pro zjišťování a správu instancí sady Visual Studio
titleSuffix: ''
description: Další informace o nástrojích, které můžete použít ke zjišťování a správa instalací sady Visual Studio na klientských počítačích.
ms.date: 08/14/2017
ms.custom: seodec18
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 85686707-14C0-4860-9B7A-66485D43D241
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 006a3fa3d41799a87449b8f9e111ca341a698bf5
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60041644"
---
# <a name="tools-for-detecting-and-managing-visual-studio-instances"></a>Nástroje pro zjišťování a správu instancí sady Visual Studio

Existuje několik nástrojů, které můžete použít k detekci instalace sady Visual Studio na klientských počítačích a ke správě zařízení, příliš.

## <a name="detecting-existing-visual-studio-instances"></a>Zjišťování existující instance sady Visual Studio

Vylepšili jsme k dispozici několik nástrojů, které vám pomohou zjistit a spravovat nainstalované instance sady Visual Studio na klientských počítačích:

* [vswhere](https://github.com/microsoft/vswhere): spustitelný soubor sestavení do sady Visual Studio nebo k dispozici pro samostatné distribuci, která vám pomůže najít umístění pro všechny instance sady Visual Studio na daném počítači.
* [VSSetup.PowerShell](https://github.com/microsoft/vssetup.powershell): Skripty prostředí PowerShell, které používají rozhraní API pro konfiguraci nastavení pro identifikaci nainstalované instance sady Visual Studio.
* [Ukázky nastavení VS](https://github.com/microsoft/vs-setup-samples): C#a C++ – ukázky, které ukazují, jak použít rozhraní API pro konfiguraci nastavení k dotazování existující instalaci.

Kromě toho [rozhraní API pro konfiguraci nastavení](<xref:Microsoft.VisualStudio.Setup.Configuration>) poskytuje rozhraní pro vývojáře, kteří chtějí vytvářet své vlastní nástroje pro dotazem instancí sady Visual Studio.

## <a name="using-vswhereexe"></a>Pomocí vswhere.exe

`vswhere.exe` automaticky je součástí sady Visual Studio (od verze Visual Studio 2017 verze 15.2 a novějších verzí), nebo můžete sadu stáhnout z [stránky vydaných verzí vswhere](https://github.com/Microsoft/vswhere/releases). Použití `vswhere -?` zobrazíte informace nápovědy o tomto nástroji. Jako příklad tento příkaz zobrazí všechny verze sady Visual Studio, včetně starších verzí produktů a verzí a výsledky ve formátu JSON:

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Installer> vswhere.exe -legacy -prerelease -format json
```

::: moniker range="vs-2017"

> [!TIP]
> Další informace o instalaci sady Visual Studio 2017 najdete v tématu [archivy instalační program Visual Studio](https://devblogs.microsoft.com/setup/tag/vs2017/).

::: moniker-end

## <a name="editing-the-registry-for-a-visual-studio-instance"></a>Úprava registr pro instanci aplikace Visual Studio

V sadě Visual Studio nastavení registru jsou uložené v privátním umístění, která umožňuje více instancí vedle sebe k verzi sady Visual Studio na stejném počítači.

Protože tyto položky nejsou uložené v registru globální, existují zvláštní pokyny pro použití Editoru registru provádět změny nastavení registru:

1. Pokud máte otevřené instance sady Visual Studio, zavřete ho.

1. Spustit `regedit.exe`.

1. Vyberte `HKEY_LOCAL_MACHINE` uzlu.

1. V hlavní nabídce Regedit vyberte **souboru** > **načíst Hive...**  a potom vyberte soubor privátního registru, který je uložený v **AppData\Local** složky. Příklad:

   ```
   %localappdata%\Microsoft\VisualStudio\<config>\privateregistry.bin
   ```

   > [!NOTE]
   > `<config>` odpovídá instanci sady Visual Studio, která chcete procházet.

Zobrazí se výzva k zadání názvu hive, který se stane názvem izolované hive. Když tak učiníte, byste měli přejít registru v izolované hive, který jste vytvořili.

> [!IMPORTANT]
> Předtím, než znovu spustíte Visual Studio, musí uvolnit izolované hive, který jste vytvořili. Chcete-li to provést, vyberte **souboru** > **Uvolnit podregistr** v hlavní nabídce Regedit. (Pokud to neprovedete, pak soubor zůstane uzamčen a sady Visual Studio nebude možné spustit.)

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Příručka správce sady Visual Studio](visual-studio-administrator-guide.md)
