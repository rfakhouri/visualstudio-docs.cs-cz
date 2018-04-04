---
title: Nástroje pro zjišťování a správu instancí sady Visual Studio | Microsoft Docs
description: '{{ZÁSTUPNÝ SYMBOL}}'
ms.date: 08/14/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 85686707-14C0-4860-9B7A-66485D43D241
author: tglee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2e2c0f6d6884590cfb793aa522984ed7f008c37f
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/03/2018
---
# <a name="tools-for-detecting-and-managing-visual-studio-instances"></a>Nástroje pro zjišťování a správu instancí sady Visual Studio

## <a name="detecting-existing-visual-studio-instances"></a>Zjišťování existující instance Visual Studio
Provedli jsme k dispozici několik nástrojů, které vám pomohou zjistit a spravovat nainstalované sady Visual Studio instancí na klientské počítače:

* [VSWhere](https://github.com/microsoft/vswhere): spustitelný soubor integrovaný do sady Visual Studio nebo k dispozici pro samostatné distribuci, která vám pomůže vyhledat umístění všech instancí sady Visual Studio na konkrétní počítač.
* [VSSetup.PowerShell](https://github.com/microsoft/vssetup.powershell): skripty prostředí PowerShell, které používají rozhraní API konfigurace instalace k identifikaci nainstalovaných instancí sady Visual Studio.
* [VS-instalace-Samples](https://github.com/microsoft/vs-setup-samples): C# a C++ vzorků, které ukazují, jak používat rozhraní API konfigurace instalace k dotazování existující instalaci.

Kromě toho [API pro konfiguraci nastavení](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.setup.configuration.aspx) poskytuje rozhraní pro vývojáře, kteří chtějí vytvářet své vlastní nástroje pro dotazem instance Visual Studio.

## <a name="using-vswhereexe"></a>Pomocí vswhere.exe
`vswhere.exe` je automaticky zahrnuty v aplikaci Visual Studio 2017 verze 15.2 nebo vyšší, nebo můžete ho stáhnout z [stránce vydání](https://github.com/Microsoft/vswhere/releases). Použití `vswhere -?` získat pomoc informace o nástroji. Jako příklad tento příkaz zobrazí všechny verze sady Visual Studio, včetně starší verze produktu a předběžné a výsledky ve formátu JSON:

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Installer> vswhere.exe -legacy -prerelease -format json
```

>[!TIP]
>Další informace o instalaci Visual Studio 2017 najdete v tématu [stavu Chmiela blog články](https://blogs.msdn.microsoft.com/heaths/tag/vs2017/).


## <a name="editing-the-registry-for-a-visual-studio-instance"></a>Úprava registru pro instanci sady Visual Studio
Ve Visual Studio 2017 nastavení registru jsou uloženy v privátní umístění, což umožňuje víc instancí vedle sebe na stejném počítači stejné verze sady Visual Studio.

Protože tyto položky nejsou uložené v registru globální, existují zvláštní pokyny pro pomocí Editoru registru provést změny nastavení registru:

1. Pokud máte otevřené instance Visual Studio 2017, zavřete ji.
2. Spustit `regedit.exe`.
3. Vyberte `HKEY_LOCAL_MACHINE` uzlu.
4. Vyberte z hlavní nabídky Regedit **souboru -> Načíst podregistr...**  a pak vyberte příslušný soubor privátní registru, který je uložen v **AppData\Local** složky. Příklad:
   ```
   %localappdata%\Microsoft\VisualStudio\<config>\privateregistry.bin
   ```

> [!NOTE]
> `<config>` odpovídá instanci Visual Studia, která chcete procházet.

Zobrazí se výzva k zadání názvu hive, který se stane název vaší izolované hive. Po tak učiníte, mělo být možné procházet registru pod izolované hive, kterou jste vytvořili.

> [!IMPORTANT]
> Před opětovným spuštěním sady Visual Studio musí uvolnit izolované hive, kterou jste vytvořili. Chcete-li to provést, vyberte soubor -> Uvolnit podregistr z hlavní nabídky Regedit. (Pokud to neprovedete, pak soubor zůstane uzamčen a Visual Studio nebude možné spustit.)

## <a name="get-support"></a>Získat podporu
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:
* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi.
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio).  (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také
* [Příručka správce sady Visual Studio](visual-studio-administrator-guide.md)
