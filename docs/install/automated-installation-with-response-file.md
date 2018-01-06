---
title: "Automatizovat instalaci sady Visual Studio se souborem odpovědí | Microsoft Docs"
description: "Naučte se vytvořit soubor odpovědi JSON, která pomáhá automatizovat instalaci sady Visual Studio"
ms.date: 08/14/2017
ms.reviewer: tims
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- response file
- automate
- installation
- command-line
author: timsneath
ms.author: tglee
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8bb0cfca6efe913b38a94daf0ed846699f0266cd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-settings-in-a-response-file"></a>Jak definovat nastavení v souboru odpovědí
Správci, kteří nasazují Visual Studio můžete zadat soubor odezvy pomocí `--in` parametru, jako v následujícím příkladu:

```
vs_enterprise.exe --in customInstall.json
```

Soubory odezvy jsou [JSON](http://json-schema.org/) soubory, jejichž obsah zrcadlení argumenty příkazového řádku.  Obecně platí, že pokud parametr příkazového řádku nezadávaly žádné argumenty (například `--quiet`, `--passive`atd), hodnota v souboru odpovědí musí být true nebo false.  Pokud se používá argument (například `--installPath <dir>`), hodnota v souboru odpovědí, by měl být řetězec.  Pokud má argument a může vyskytovat více než jednou na příkazovém řádku (například `--add <id>`), musí být pole řetězců.

Parametry, které jsou určené v nastavení příkazového řádku přepsání ze souboru odpovědí, s výjimkou při provádění více vstupů parametry (například `--add`). Pokud máte více vstupů, vstupy zadány na příkazovém řádku jsou sloučeny s nastavení ze souboru odpovědí.

# <a name="setting-a-default-configuration-for-visual-studio"></a>Nastavení výchozí konfiguraci pro sadu Visual Studio

Pokud jste vytvořili mezipaměť rozložení sítě `--layout`, počáteční `response.json` soubor je vytvořen v rozložení. Pokud vytvoříte částečné rozložení, tento soubor odpovědí obsahuje úlohy a jazyky, které byly zahrnuté v rozložení.  Spuštěním instalačního programu z této rozložení automaticky používá tento soubor response.json, který vybere úlohy a součásti, které jsou součástí zobrazení.  Uživatelé mohou stále zaškrtněte nebo zrušte všechny úlohy v nastavení uživatelského rozhraní před instalací sady Visual Studio.

Správci, kteří vytvářejí rozložení můžete upravit `response.json` souboru v rozložení řídit výchozí nastavení, že jejich uživatelé uvidí, když se z rozložení instalaci sady Visual Studio.  Například pokud správce chce, aby se určité úlohy a součásti nainstalované ve výchozím nastavení, mohou nakonfigurovat `response.json` souboru je přidat.

Při spuštění instalačního programu sady Visual Studio ze složky rozložení, ho _automaticky_ používá soubor odpovědí ve složce rozložení.  Nemusíte používat `--in` možnost.

Můžete aktualizovat `response.json` souboru, který se vytvoří ve složce aplikace offline rozložení definovat výchozí nastavení pro uživatele, kteří instalaci z tohoto rozložení.

> [!WARNING]
> Je důležité, že necháte existující vlastnosti, které byly definovány při vytváření rozložení.

Základní `response.json` soubor v rozložení by měl vypadat podobně jako v následujícím příkladu, s tím rozdílem, že se bude zahrnovat hodnota produktu a kanál, který chcete nainstalovat:

```json
{
  "installChannelUri": ".\\ChannelManifest.json",
  "channelUri": "https://aka.ms/vs/15/release/channel",
  "installCatalogUri": ".\\Catalog.json",
  "channelId": "VisualStudio.15.Release",
  "productId": "Microsoft.VisualStudio.Product.Enterprise"
}
```
Při vytváření nebo aktualizaci rozložení, vytvoří se také response.template.json soubor.  Tento soubor obsahuje všechny úlohy, součásti a jazyk ID, které lze použít.  Tento soubor je k dispozici jako šablonu pro jaké všechna může být součástí vlastní instalace.  Správci můžou používat tento soubor jako výchozí bod pro soubor vlastní odezvy.  Právě odeberte ID pro akcí, které nechcete instalovat a uložit ho v souboru odpovědí.  Neupravovat soubor response.template.json nebo změny budou ztraceny při každé aktualizaci rozložení.

## <a name="example-layout-response-file-content"></a>Obsah souboru odpovědí příklad rozložení
Následující příklad nainstaluje Visual Studio Enterprise se šesti běžné úlohy a komponenty a s jazyky angličtinu a francouzštinu uživatelského rozhraní. V tomto příkladu můžete použít jako šablonu; jenom na ty, které chcete nainstalovat změňte úlohy a součásti:

```json
{
  "installChannelUri": ".\\ChannelManifest.json",
  "channelUri": "https://aka.ms/vs/15/release/channel",
  "installCatalogUri": ".\\Catalog.json",
  "channelId": "VisualStudio.15.Release",
  "productId": "Microsoft.VisualStudio.Product.Enterprise",

  "installPath": "C:\\VS2017",
  "quiet": false,
  "passive": false,
  "includeRecommended": true,
  "norestart": false,

  "addProductLang": [
    "en-US",
    "fr-FR"
    ],

    "add": [
        "Microsoft.VisualStudio.Workload.ManagedDesktop",
        "Microsoft.VisualStudio.Workload.Data",
        "Microsoft.VisualStudio.Workload.NativeDesktop",
        "Microsoft.VisualStudio.Workload.NetWeb",
        "Microsoft.VisualStudio.Workload.Office",
        "Microsoft.VisualStudio.Workload.Universal",
        "Component.GitHub.VisualStudio"
    ]
}
```

## <a name="get-support"></a>Získat podporu
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:
* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi.
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio).  (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také
* [Visual Studio 2017 pracovního vytížení a součást ID](workload-and-component-ids.md)
