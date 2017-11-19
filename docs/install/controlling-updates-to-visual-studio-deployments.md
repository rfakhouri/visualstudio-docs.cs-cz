---
title: "Řízení aktualizací pro nasazení v sadě Visual Studio | Microsoft Docs"
description: "{{ZÁSTUPNÝ SYMBOL}}"
ms.date: 08/14/2017
ms.reviewer: tims
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 35C7AB05-07D5-4B38-BCAC-AB88444E7368
author: timsneath
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 72e217f8543b6b150cc0587c36fac692e150179d
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="control-updates-to-network-based-visual-studio-deployments"></a>Ovládací prvek aktualizací pro nasazení založené na síti Visual Studio

Podnikoví správci často vytvořit rozložení a uloží v síťové sdílené složky pro nasazení pro své koncové uživatele.

## <a name="controlling-where-visual-studio-looks-for-updates"></a>Řízení, kde vyhledá aktualizace Visual Studio
Ve výchozím nastavení Visual Studio nadále vypadat online aktualizace i v případě instalace byla nasazena v síťové sdílené složce. Pokud je k dispozici aktualizace, můžete ho nainstalovat uživatele. Všechny aktualizovaném obsahu, který nebyl nalezen v offline rozložení je stáhnout z webu.

Pokud chcete přímou kontrolu nad kde vyhledá aktualizace Visual Studio, můžete upravit umístění, kde bude vypadat. Můžete také určit, které vaši uživatelé jsou aktualizovány na verzi. Chcete-li to provést, postupujte takto:

 1. Vytvořte offline rozložení:
    ```
    vs_enterprise.exe --layout C:\vs2017offline --lang en-US
    ```
 2. Zkopírujte jej do sdílené složky, kam chcete ji hostovat:
    ```
    xcopy /e C:\vs2017offline \\server\share\VS2017
    ```
 3. Upravte soubor response.json v rozložení a změna `channelUri` hodnotu tak, aby odkazoval na kopii channelManifest.json, kterými se řídí správce.

  Ujistěte se, abyste se vyhnuli zpětná lomítka v hodnotě, jako v následujícím příkladu:

  ```json
    "channelUri":"\\\\server\\share\\VS2017\\ChannelManifest.json"
  ```

 Koncoví uživatelé nyní můžete spustit instalační program z této sdílené složce pro instalaci sady Visual Studio.
    ```
    \\server\share\VS2017\vs_enterprise.exe
    ```

Když správce podnikové sítě zjistí, je čas pro své uživatele aktualizovat na novější verzi sady Visual Studio, mohou [aktualizovat umístění rozložení](update-a-network-installation-of-visual-studio.md) začlenit aktualizované soubory, následujícím způsobem.

 1. Použijte příkaz, který je podobná následující příkaz:
    ```
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
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránku Tipy pro odstraňování potíží. Taky můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj v prostředí Visual Studio IDE nebo ke sdílení návrh s nám na [UserVoice](https://visualstudio.uservoice.com/forums/121579). Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi. Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio) (vyžaduje [Githubu](https://github.com/) účtu).

## <a name="see-also"></a>Viz také
* [Instalaci sady Visual Studio](install-visual-studio.md)
* [Příručka správce Visual Studio](visual-studio-administrator-guide.md)
* [Používání parametrů příkazového řádku pro instalaci sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
* [Nástroje pro správu instancí sady Visual Studio](tools-for-managing-visual-studio-instances.md)
