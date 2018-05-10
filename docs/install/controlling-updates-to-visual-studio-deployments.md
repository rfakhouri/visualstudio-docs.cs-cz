---
title: Ovládací prvek aktualizací pro nasazení v sadě Visual Studio
description: Zjistěte, jak chcete-li změnit umístění, kde Visual Studio hledá aktualizace při instalaci ze sítě.
ms.date: 08/14/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 35C7AB05-07D5-4B38-BCAC-AB88444E7368
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 24a8f49c036ed28693d92b162a417114f2c93e89
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="control-updates-to-network-based-visual-studio-deployments"></a>Ovládací prvek aktualizací pro nasazení založené na síti Visual Studio

Podnikoví správci často vytvořit rozložení a uloží v síťové sdílené složky pro nasazení pro své koncové uživatele.

## <a name="controlling-where-visual-studio-looks-for-updates"></a>Řízení, kde vyhledá aktualizace Visual Studio

Ve výchozím nastavení Visual Studio nadále vypadat online aktualizace i v případě instalace byla nasazena v síťové sdílené složce. Pokud je k dispozici aktualizace, můžete ho nainstalovat uživatele. Všechny aktualizovaném obsahu, který nebyl nalezen v offline rozložení je stáhnout z webu.

Pokud chcete přímou kontrolu nad kde vyhledá aktualizace Visual Studio, můžete upravit umístění, kde bude vypadat. Můžete také určit, které vaši uživatelé jsou aktualizovány na verzi. Chcete-li to provést, postupujte takto:

 1. Vytvořte offline rozložení:
    ```cmd
    vs_enterprise.exe --layout C:\vs2017offline --lang en-US
    ```
 2. Zkopírujte jej do sdílené složky, kam chcete ji hostovat:
    ```cmd
    xcopy /e C:\vs2017offline \\server\share\VS2017
    ```
 3. Upravte soubor response.json v rozložení a změna `channelUri` hodnotu tak, aby odkazoval na kopii channelManifest.json, kterými se řídí správce.

  Ujistěte se, abyste se vyhnuli zpětná lomítka v hodnotě, jako v následujícím příkladu:

  ```json
    "channelUri":"\\\\server\\share\\VS2017\\ChannelManifest.json"
  ```

 Koncoví uživatelé nyní můžete spustit instalační program z této sdílené složce pro instalaci sady Visual Studio.
    ```cmd
    \\server\share\VS2017\vs_enterprise.exe
    ```

Když správce podnikové sítě zjistí, je čas pro své uživatele aktualizovat na novější verzi sady Visual Studio, mohou [aktualizovat umístění rozložení](update-a-network-installation-of-visual-studio.md) začlenit aktualizované soubory, následujícím způsobem.

 1. Použijte příkaz, který je podobná následující příkaz:
    ```cmd
    vs_enterprise.exe --layout \\server\share\VS2017 --lang en-US
    ```
 2. Zkontrolujte, zda soubor response.json v aktualizované rozložení stále obsahuje vaše vlastní nastavení, konkrétně channelUri úpravy, následujícím způsobem:
    ```json
    "channelUri":"\\\\server\\share\\VS2017\\ChannelManifest.json"
    ```
 Existující sady Visual Studio nainstaluje z tento vzhled rozložení aktualizace v `\\server\share\VS2017\ChannelManifest.json`. Pokud channelManifest.json je novější než co uživatel nainstaloval, Visual Studio upozorní uživatele, že je k dispozici aktualizace.

 Aktualizovaná verze sady Visual Studio nový nainstaluje automaticky instalovat přímo z rozložení.

## <a name="controlling-notifications-in-the-visual-studio-ide"></a>Řízení oznámení v prostředí Visual Studio IDE

Jak je popsáno výše, Visual Studio kontroluje umístění, ze kterého je nainstalován, například sdílené síťové složky nebo Internetu, zda jsou k dispozici žádné aktualizace. Pokud je k dispozici aktualizace, Visual Studio upozorní uživatele s příznak oznámení v pravém horním rohu okna.

 ![Příznak oznámení aktualizací](media/notification-flag.png)

Oznámení můžete zakázat, pokud nechcete, aby koncoví uživatelé mají být informování aktualizací. (Například můžete chtít zakázat oznámení, pokud poskytování aktualizací prostřednictvím mechanismus distribuce softwaru centrální.)

Protože Visual Studio 2017 [ukládá položky registru v privátní registru](tools-for-managing-visual-studio-instances.md#editing-the-registry-for-a-visual-studio-instance), nelze upravovat přímo registru typické způsobem. Ale obsahuje sady Visual Studio `vsregedit.exe` nástroj, který můžete použít, chcete-li změnit nastavení v sadě Visual Studio. Můžete vypnout oznámení pomocí následujícího příkazu:

```cmd
vsregedit.exe set "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" HKCU ExtensionManager AutomaticallyCheckForUpdates2Override dword 0
```

(Nezapomeňte nahradit adresář tak, aby odpovídaly nainstalovanou instanci, kterou chcete upravit.)

> [!TIP]
> Použití [vswhere.exe](tools-for-managing-visual-studio-instances.md#detecting-existing-visual-studio-instances) najít konkrétní instanci sady Visual Studio na pracovní stanici klienta.

## <a name="get-support"></a>Získat podporu

V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:

* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu a najít v odpovědi [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/).
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio). (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také

* [Instalace sady Visual Studio](install-visual-studio.md)
* [Příručka správce Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
* [Nástroje pro správu instancí sady Visual Studio](tools-for-managing-visual-studio-instances.md)
