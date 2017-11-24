---
title: "Nastavit výchozí hodnoty pro nasazení v podnicích sady Visual Studio | Microsoft Docs"
description: "Zásady domény a další konfigurace operace pro podnikové nasazení sady Visual Studio."
ms.date: 05/05/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- gpo
- policy
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 9B7B4608-7A3F-4FF4-BDCE-42D9F7CE6DBA
author: heaths
ms.author: heaths
manager: ghogen
ms.openlocfilehash: ff6cc33a9bd7e5feddf83f770ef008ff6c33e4a9
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2017
---
# <a name="set-defaults-for-enterprise-deployments-of-visual-studio"></a>Výchozí nastavení pro nasazení v podnicích sady Visual Studio

Můžete nastavit zásady registru, které ovlivňují nasazení sady Visual Studio. Tyto zásady jsou globální pro nového instalačního programu a vliv:

- Kde jsou nainstalovány některé balíčky sdílet s jinými verzemi nebo instancí
- Kde balíčky v mezipaměti
- Zda jsou všechny balíčky v mezipaměti

Můžete nastavit některé z těchto zásad [možnosti příkazového řádku](use-command-line-parameters-to-install-visual-studio.md), nastavte hodnoty registru na počítači nebo i distribuovat pomocí zásad skupiny v rámci celé organizace.

## <a name="registry-keys"></a>Klíče registru

Existuje několik umístění, kde můžete nastavit výchozí hodnoty enterprise, chcete-li povolit ovládacího prvku pomocí zásad skupiny nebo přímo v registru. Visual Studio vypadá postupně Pokud chcete zobrazit, pokud byly nastaveny žádné zásady organizace; Jakmile je hodnota zásad rozpozná v níže uvedeném pořadí, zbývající klíče se ignorují.

1. `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\Setup`
2. `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\Setup`
3. `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\VisualStudio\Setup`(na 64bitové operační systémy)

> [!IMPORTANT]
> Pokud není nastaveno `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\Setup` klíče a místo toho nastavte jednu z jiných klíčů, byste měli nastavit i jiné klíče na 64bitové operační systémy. Tento problém je vyřešen v budoucí aktualizace.

Některé hodnoty registru jsou automaticky nastavit poprvé, budou se používá není-li již nastaven. Tento postup zajistí, že následné instaluje použít stejné hodnoty. Tyto hodnoty se uloží v klíči registru druhý `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\Setup`.

Můžete nastavit následující hodnoty registru:

| **Jméno** | **Typ** | **Výchozí** | **Popis** |
| -------- | -------- | ----------- | --------------- |
| `CachePath` | `REG_SZ`nebo`REG_EXPAND_SZ` | %ProgramData%\Microsoft\VisualStudio\Packages | Jsou uložené adresáři, kde balíček manifesty a volitelně datové části. Najdete v návodu k [zakázat nebo přesunout do mezipaměti balíček](disable-or-move-the-package-cache.md) Další informace. |
| `KeepDownloadedPayloads` | `REG_DWORD` | 1 | Datové části balíčku zachovat i po jejich instalaci. Hodnota můžete kdykoli změnit. Zakázání zásady odebere všechny uložené v mezipaměti balíček datových částí pro instanci opravit nebo změnit. Najdete v návodu k [zakázat nebo přesunout do mezipaměti balíček](disable-or-move-the-package-cache.md) Další informace. |
| `SharedInstallationPath` | `REG_SZ`nebo`REG_EXPAND_SZ` | % ProgramFiles (x86) %\Microsoft Visual Studio\Shared | Adresář, kde jsou nainstalovány některé balíčky sdílené mezi verzemi instancí sady Visual Studio. Hodnota dají kdykoli měnit, ale mají vliv jenom budoucí nainstaluje. Všechny produkty již nainstalována do původního umístění nesmí být přesunuta, nebo se nemusí správně fungovat. |

> [!IMPORTANT]
> Pokud změníte `CachePath` registru zásad po všech instaluje, je nutné přesunout do stávajícího balíčku mezipaměti do nového umístění a ujistěte se, zda je zabezpečená, aby `SYSTEM` a `Administrators` mít úplnou kontrolu a `Everyone` má přístup pro čtení.
> Nepodařilo se přesunout existující mezipaměti nebo jeho zajištění může způsobit problémy s budoucí nainstaluje.

## <a name="get-support"></a>Získat podporu
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:
* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi.
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio).  (Tato možnost vyžaduje [Githubu](https://github.com/) účtu).

## <a name="see-also"></a>Viz také

 * [Instalaci sady Visual Studio](install-visual-studio.md)
 * [Zakažte nebo přesunout do mezipaměti balíčku](disable-or-move-the-package-cache.md)
 * [Používání parametrů příkazového řádku pro instalaci sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
