---
title: Instalace v pomalé nebo nespolehlivé síti prostředí | Dokumentace Microsoftu
description: Další informace o použití instalačního programu sady Visual Studio nespolehlivé síti nebo máte malou šířkou pásma, a způsob použití příkazového řádku se stáhnout instalační soubory.
ms.date: 01/17/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- installing Visual Studio
- no internet connection
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4517984b5da3c6d8e650ec4148c085c2a42aa392
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634417"
---
# <a name="install-visual-studio-2017-on-low-bandwidth-or-unreliable-network-environments"></a>Instalace sady Visual Studio 2017 v pomalé nebo nespolehlivé síti prostředí

Doporučujeme vám, že zkusíte webovou Instalační službu sady Visual Studio&mdash;myslíme, že budete pro vás vhodné prostředí pro většinu situací.

 > [!div class="button"]
 > [Stažení sady Visual Studio 2017](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)
<br/>

Pokud připojení k Internetu je nedostupné nebo nespolehlivé, můžete vytvořit místní mezipaměti soubory, které potřebujete k dokončení offline instalace můžete použít příkazový řádek. Tady je způsob.

> [!NOTE]
> Pokud jste správce organizace, který chce provést nasazení sady Visual Studio 2017 k síti klientských pracovních stanic, které jsou aplikována brána firewall z Internetu, najdete v našich [vytvoření síťové instalace sady Visual Studio 2017](../install/create-a-network-installation-of-visual-studio.md) a [Instalaci certifikátů vyžadovaných pro offline instalace sady Visual Studio](../install/install-certificates-for-visual-studio-offline.md) stránky.

## <a name="step-1---download-the-visual-studio-bootstrapper"></a>Krok 1 – stažení zaváděcího nástroje Visual Studio

Začněte tím, že stažení zaváděcího nástroje Visual Studio pro vaši zvolenou edici sady Visual Studio.

Váš soubor&mdash;nebo na konkrétnější, soubor zaváděcí nástroj&mdash;bude odpovídat nebo se podobně jako na jednu z následujících akcí.

| Edice                    | Soubor                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Visual Studio Community    | [vs_community.exe](https://aka.ms/vs/15/release/vs_community.exe)       |
| Visual Studio Professional | [vs_professional.exe](https://aka.ms/vs/15/release/vs_professional.exe) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://aka.ms/vs/15/release/vs_enterprise.exe)     |

## <a name="step-2---create-a-local-install-cache"></a>Krok 2: vytvoření mezipaměti místní instalace

Musíte mít internetové připojení k dokončení tohoto kroku. Chcete-li vytvořit místní rozložení, otevřete příkazový řádek a použijte jeden z příkazů z následujících příkladů. Příklady v tomto článku se předpokládá, že používáte komunitní edice sady Visual Studio; Upravte příkaz v závislosti na edici.

- Vývoj desktopových aplikací .NET a webové rozhraní .NET spusťte:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

- Vývoj pro Office a .NET desktop spusťte:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.Office --includeOptional --lang en-US```

- Vývoje desktopových aplikací C++ pro spuštění:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.NativeDesktop --includeRecommended --lang en-US```

- Vytvoření kompletní místní rozložení se všemi funkcemi (bude to trvat dlouho&mdash;máme _velké_ funkcí!), spusťte:

   ```vs_community.exe --layout c:\vs2017layout --lang en-US```

Pokud chcete nainstalovat jiný jazyk než angličtinu, změňte `en-US` národní prostředí v seznamu v dolní části této stránky. Použijte tento [seznamu komponent a úlohy, které jsou k dispozici](workload-and-component-ids.md) můžete dále přizpůsobit vaše mezipaměť instalace podle potřeby.

> [!IMPORTANT]
> Úplné rozložení sady Visual Studio 2017 vyžaduje minimálně 35 GB místa na disku a může trvat nějakou dobu ke stažení. Zobrazit [použitím parametrů příkazového řádku instalace sady Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md) informace o tom, jak vytvořit rozložení s pouze ty součásti, kterou chcete nainstalovat.

## <a name="step-3---install-visual-studio-from-the-local-cache"></a>Krok 3: instalace sady Visual Studio z místní mezipaměti

> [!TIP]
> Při spuštění z mezipaměti místní instalace instalační program používal místní verze každý z těchto souborů. Ale pokud vyberete součásti během instalace, které nejsou v mezipaměti, jsme provést při stahování z Internetu.

Pokud chcete mít jistotu, že nainstalujete jenom soubory, které jste stáhli, použijte stejné možnosti příkazového řádku, které jste použili k vytvoření mezipaměti rozložení. Například, pokud jste vytvořili mezipaměť rozložení pomocí následujícího příkazu:

```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

Jak spustit instalaci, použijte tento příkaz:

```c:\vs2017layout\vs_community.exe --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional```

> [!NOTE]
> Pokud dojde k chybě, podpis je neplatný, je nutné nainstalovat aktualizace certifikátů. Otevřete složku pro certifikáty v offline mezipaměti. Klikněte dvakrát na každém ze souborů certifikátu a klikněte na Průvodce správce certifikátů. Pokud budete vyzváni k zadání hesla, ponechte prázdné.

## <a name="list-of-language-locales"></a>Seznam národních prostředí jazyka

| **Jazyk národního prostředí** | **Jazyk** |
| ----------------------- | --------------- |
| cs-CZ | Čeština |
| de-DE | Němčina |
| en US | Angličtina |
| es-ES | Španělština |
| fr-FR | Francouzština |
| IT-IT | Italština |
| ja-JP | Japonština |
| ko-KR | Korejština |
| pl-PL | Polština |
| pt-BR | Portugalština – Brazílie |
| ru-RU | Ruština |
| tr-TR | Turečtina |
| zh-CN | Čínština (zjednodušená) |
| zh-TW | Čínština (tradiční) |

## <a name="get-support"></a>Získat podporu

V některých případech může něco selže. Pokud se nezdaří instalace aplikace Visual Studio, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud žádný z kroků pro řešení potíží, kontaktujte nás podle živý chat pro pomoc s instalací (jenom v angličtině). Podrobnosti najdete v tématu [stránku podpory sady Visual Studio](https://visualstudio.microsoft.com/vs/support/#talktous).

Tady je několik dalších možností podpory:

* Může probíhat hlášení problémů s produktem nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu sady Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémů s produktem a najít odpovědi v [komunity vývojářů v aplikaci Visual Studio](https://developercommunity.visualstudio.com/).
* Můžete také Spolupracujte s námi a jinými vývojáři Visual Studio prostřednictvím [konverzace sady Visual Studio v komunitě Gitteru](https://gitter.im/Microsoft/VisualStudio). (Tato možnost vyžaduje [Githubu](https://github.com/) účet.)

## <a name="see-also"></a>Viz také:

* [Instalace sady Visual Studio](install-visual-studio.md)
* [Příručka pro správce aplikace Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
* [ID pracovního vytížení a komponenta Visual Studio 2017](workload-and-component-ids.md)
