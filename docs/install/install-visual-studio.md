---
title: Instalace sady Visual Studio
titleSuffix: ''
description: Zjistěte, jak nainstalovat sadu Visual Studio, krok za krokem.
ms.date: 03/30/2019
ms.custom: seodec18
ms.topic: conceptual
f1_keywords:
- vs.about
helpviewer_keywords:
- install Visual Studio
- dev15
- set up Visual Studio
- Visual Studio setup
- Visual Studio installer
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: c76f7f151d10de791a8bcd0c50418d8775f51737
ms.sourcegitcommit: d4bea2867a4f0c3b044fd334a54407c0fe87f9e8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2019
ms.locfileid: "58790716"
---
# <a name="install-visual-studio"></a>Instalace sady Visual Studio

::: moniker range="vs-2019"

Vítá vás Visual Studio 2019! V této verzi je snadno vybrat a instalace jen těch funkcí, které potřebujete. A z důvodu jeho nižší minimální nároky na místo, nainstaluje rychle a s menšími dopady na systém.

::: moniker-end

::: moniker range="vs-2017"

Vítá vás nový způsob, jak nainstalovat sadu Visual Studio! V této verzi jsme jsme usnadnili si můžete vybrat a instalace jen těch funkcí, které potřebujete. Také jsme jste snížení nároků sady Visual Studio tak, aby nainstaloval rychleji a s menšími dopady na systém, než kdy dřív.

::: moniker-end

> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac, najdete v části [instalace sady Visual Studio pro Mac](/visualstudio/mac/installation/).

::: moniker range="vs-2019"

Chcete vědět více o tom, co je nového v této verzi? Najdete v našich [poznámky k verzi](/visualstudio/releases/2019/release-notes/).

::: moniker-end

::: moniker range="vs-2017"

Chcete vědět více o tom, co je nového v této verzi? Najdete v našich [poznámky k verzi](/visualstudio/releasenotes/vs2017-relnotes).

::: moniker-end

Připraveno k instalaci? Provedeme vás přes něj krok za krokem.

## <a name="step-1---make-sure-your-computer-is-ready-for-visual-studio"></a>Krok 1: Ujistěte se, že váš počítač připravený pro sadu Visual Studio

Před zahájením instalace sady Visual Studio:

::: moniker range="vs-2017"

1. Zkontrolujte, [požadavky na systém](/visualstudio/productinfo/vs2017-system-requirements-vs). Tyto požadavky vám pomohli určit, jestli počítač podporuje Visual Studio 2017.

1. Použijte nejnovější aktualizace Windows. Tyto aktualizace zkontrolujte, zda má počítač nejnovější aktualizace zabezpečení a požadované systémové komponenty pro sadu Visual Studio.

1. Restartování počítače. Restartování zajistí, že instalaci sady Visual Studio nebudou bránit probíhající instalace nebo aktualizace.

1. Uvolněte místo. Odeberte nepotřebné soubory a aplikace z % SystemDrive %, například spuštěním aplikace Vyčištění disku.

::: moniker-end

::: moniker range="vs-2019"

1. Zkontrolujte, [požadavky na systém](/visualstudio/releases/2019/system-requirements). Tyto požadavky vám pomohli určit, jestli počítač podporuje Visual Studio 2019.

1. Použijte nejnovější aktualizace Windows. Tyto aktualizace zkontrolujte, zda má počítač nejnovější aktualizace zabezpečení a požadované systémové komponenty pro sadu Visual Studio.

1. Restartování počítače. Restartování zajistí, že instalaci sady Visual Studio nebudou bránit probíhající instalace nebo aktualizace.

1. Uvolněte místo. Odeberte nepotřebné soubory a aplikace z % SystemDrive %, například spuštěním aplikace Vyčištění disku. 

::: moniker-end

::: moniker range="vs-2017"

Dotazy týkající se spouštění předchozích verzí sady Visual Studio souběžně se sadou Visual Studio 2017, najdete v článku [informace o kompatibilitě sady Visual Studio](/visualstudio/productinfo/vs2017-compatibility-vs#compatibility-with-previous-releases/).

::: moniker-end

::: moniker range="vs-2019"

Dotazy týkající se spouštění předchozích verzí sady Visual Studio souběžně s Visual Studio 2019, najdete v článku [Visual Studio. 2019 cílení na platformy a Kompatibilita](/visualstudio/releases/2019/compatibility/) stránky.

::: moniker-end

## <a name="step-2---download-visual-studio"></a>Krok 2: stažení sady Visual Studio

Dále si stáhněte soubor zaváděcího nástroje sady Visual Studio. Uděláte to tak, klikněte na následující tlačítko, zvolte edici sady Visual Studio, které chcete, zvolte **Uložit**a klikněte na tlačítko **otevřít složku**.

::: moniker range="vs-2017"

 > [!div class="button"]
 > [Stáhněte si Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

::: moniker-end

::: moniker range="vs-2019"

 > [!div class="button"]
 > [Stáhněte si Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019+rc)

::: moniker-end

## <a name="step-3---install-the-visual-studio-installer"></a>Krok 3: instalace instalační program sady Visual Studio

Spusťte soubor zaváděcí nástroj k instalaci instalačního programu sady Visual Studio. Tohoto nového zjednodušeného instalačního programu obsahuje všechno, co je potřeba nainstalovat i přizpůsobení sady Visual Studio.

1. Z vaší **stáhne** složky, dvakrát klikněte na panel zaváděcí nástroj, který odpovídá nebo se podobá následující soubory:

   * **vs_community.exe** pro Visual Studio Community
   * **vs_professional.exe** for Visual Studio Professional
   * **vs_enterprise.exe** pro Visual Studio Enterprise

   Pokud se zobrazí oznámení o řízení uživatelských účtů, zvolte **Ano**.

2. Požádáme vás potvrďte Microsoft [licenční podmínky](https://visualstudio.microsoft.com/license-terms/) a Microsoft [prohlášení o zásadách](https://privacy.microsoft.com/privacystatement). Zvolte **pokračovat**.

   ![Licenční podmínky a prohlášení o zásadách](media/privacy-and-license-terms.png "licenční podmínky společnosti Microsoft a prohlášení o ochraně osobních údajů")

## <a name="step-4---choose-workloads"></a>Krok 4 – volba úlohy

Po dokončení instalace instalační program vám pomůže ho svou instalaci přizpůsobit výběrem sady funkcí, nebo úlohy –, který chcete. Tady je způsob.

 ::: moniker range="vs-2017"

1. Najít úlohu, kterou chcete v **instalaci sady Visual Studio** obrazovky.

   ![Visual Studio 2017: Nainstalujte úlohu](../install/media/vs-installer-installing-workloads.png)

     Například zvolte úlohu "Vývoj desktopových aplikací .NET". Obsahuje výchozí základní editor, který obsahuje základní podporu pro více než 20 jazycích, schopnost otevírat a upravovat kód z libovolné složky bez nutnosti vytvářet projekt, editaci kódu a integrované správy zdrojového kódu.

1. Až zvolíte, workload(s) chcete, zvolte **nainstalovat**.

    V dalším kroku stav obrazovek, které zobrazí průběh instalace sady Visual Studio.

 ::: moniker-end

::: moniker range="vs-2019"

1. Po instalaci nové úlohy a komponenty, zvolte **spuštění**.

   ![Visual Studio 2019: Nainstalujte úlohu](../install/media/vs-2019/vs-installer-workloads.png)

     Například zvolte úlohu "vývoj aplikací ASP.NET a web". Obsahuje výchozí základní editor, který obsahuje základní podporu pro více než 20 jazycích, schopnost otevírat a upravovat kód z libovolné složky bez nutnosti vytvářet projekt, editaci kódu a integrované správy zdrojového kódu.

1. Až zvolíte, workload(s) chcete, zvolte **nainstalovat**.

    V dalším kroku stav obrazovek, které zobrazí průběh instalace sady Visual Studio.

 ::: moniker-end

> [!TIP]
> Kdykoli po instalaci můžete nainstalovat úlohy nebo komponenty, které nenainstaloval původně. Pokud máte Visual Studio otevřete, přejděte na **nástroje** > **získat nástroje a funkce...**  tím se otevře instalačního programu sady Visual Studio. Nebo otevřete **instalační program sady Visual Studio** z nabídky Start. Odtud můžete vybrat úlohy nebo komponenty, které chcete nainstalovat. Potom kliknutím na možnost **změnit**.

## <a name="step-5---choose-individual-components-optional"></a>Krok 5: zvolit jednotlivé součásti (volitelné)

Pokud nechcete použít funkci úlohy k přizpůsobení instalace sady Visual Studio nebo které chcete přidat další komponenty, než úloha nainstaluje, lze provést instalaci nebo přidáním jednotlivé komponenty z **jednotlivé komponenty** kartu. Zvolte, co chcete a pak postupujte podle pokynů.

::: moniker range="vs-2017"

  ![Visual Studio 2017 – instalace jednotlivých součástí](media/vs-installer-installing-components.png "jednotlivých součástí instalace sady Visual Studio")

::: moniker-end

::: moniker range="vs-2019"

  ![Visual Studio 2019 – instalace jednotlivých součástí](media/vs-2019/vs-installer-individual-components.png "jednotlivých součástí instalace sady Visual Studio")

::: moniker-end


## <a name="step-6---install-language-packs-optional"></a>Krok 6 – instalace jazykových sad (volitelné)

Ve výchozím nastavení instalační program pokusí tak, aby odpovídala jazyku operačního systému při prvním spuštění. Chcete-li nainstalovat Visual Studio v jazyce podle vašeho výběru, zvolte **jazykových sad** kartu z instalačního programu sady Visual Studio a pak postupujte podle pokynů.

::: moniker range="vs-2017"

  ![Visual Studio 2017 – instalace jazykových sad](media/vs-installer-installing-language-packs.png "jazykové sady Nainstalujte Visual Studio")

::: moniker-end

::: moniker range="vs-2019"

  ![Visual Studio 2019 – instalace jazykových sad](media/vs-2019/vs-installer-language-packs.png "jazykové sady Nainstalujte Visual Studio")

::: moniker-end

### <a name="change-the-installer-language-from-the-command-line"></a>Změnit jazyk instalačního programu z příkazového řádku

Dalším způsobem, že můžete změnit výchozí jazyk je spuštění instalačního programu z příkazového řádku. Například můžete vynutit instalační program pro spuštění v anglickém jazyce pomocí následujícího příkazu: `vs_installer.exe --locale en-US`. Instalační program bude mějte na paměti Toto nastavení při příštím spuštění. Instalační program podporuje následující klíčová slova jazyka: zh-cn, zh-tw, cs-cz, en-us, es-es, fr-fr, de-de, it-it, ja-jp, ko-kr, pl-pl, pt-br, ru-ru a tr-tr.

## <a name="step-7---change-the-installation-location-optional"></a>Krok 7: Změna umístění instalace (volitelné)

::: moniker range="vs-2017"

**Nové ve verzi 15.7**: Nyní můžete snížit nároky na instalaci sady Visual Studio na systémovou jednotku. Můžete se rozhodnout, zda budou přesunuty mezipaměť pro stahování, sdílených komponent, sady SDK a nástrojů na jiné jednotky a sady Visual Studio na disku, na kterém běží nejrychlejší.

  ![Visual Studio 2017 – Změna umístění instalací](media/installation-options-by-location.png "Změna umístění instalace")

::: moniker-end

::: moniker range="vs-2019"

Můžete snížit nároky na instalaci sady Visual Studio na systémovou jednotku. Můžete se rozhodnout, zda budou přesunuty mezipaměť pro stahování, sdílených komponent, sady SDK a nástrojů na jiné jednotky a sady Visual Studio na disku, na kterém běží nejrychlejší.

  ![Visual Studio 2019 - Změna umístění instalací](media/vs-2019/vs-installer-installation-locations.png "Změna umístění instalace")

::: moniker-end

> [!IMPORTANT]
> Pouze při první instalaci sady Visual Studio, můžete vybrat jinou jednotku. Pokud jste již nainstalovali a chcete změnit jednotky, je nutné odinstalovat Visual Studio a pak ho znovu nainstalujte.

Další informace najdete v tématu [vybrat umístění instalace](change-installation-locations.md) stránky.

## <a name="step-8---start-developing"></a>Krok 8: začít s vývojem

::: moniker range="vs-2017"

1. Po dokončení instalace sady Visual Studio, zvolte **spuštění** tlačítko, abyste mohli začít vyvíjet pomocí sady Visual Studio.

2. Zvolte **souboru**a klikněte na tlačítko **nový projekt**.

3. Vyberte typ projektu.

   Například [sestavení aplikace v jazyce C++](../ide/getting-started-with-cpp-in-visual-studio.md), zvolte **nainstalováno**, rozbalte **Visual C++** a pak zvolte typ projektu jazyka C++, který má být sestaveno.

   K [sestavení C# aplikace](../get-started/csharp/tutorial-console.md), zvolte **nainstalováno**, rozbalte **Visual C#** a klikněte na tlačítko C# typ, který chcete sestavit projekt.

::: moniker-end

::: moniker range="vs-2019"

1. Po dokončení instalace sady Visual Studio, zvolte **spuštění** tlačítko, abyste mohli začít vyvíjet pomocí sady Visual Studio.

1. V okně start zvolte **vytvořte nový projekt**.

1. Do vyhledávacího pole zadejte aplikace, kterou chcete vytvořit zobrazíte seznam dostupných šablon. Seznam šablon závisí na workload(s), kterou jste zvolili během instalace. Chcete-li zobrazit různé šablony služby, zvolte různé úlohy.

   Můžete také filtrovat hledání pro konkrétní programovací jazyk s využitím **jazyk** rozevíracího seznamu. Můžete filtrovat pomocí **platformy** seznamu a **typ projektu** příliš seznamu. 

1. Visual Studio otevře nový projekt a jste připraveni kód!

::: moniker-end

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Aktualizace sady Visual Studio](update-visual-studio.md)
* [Úpravy sady Visual Studio](modify-visual-studio.md)
* [Odinstalace sady Visual Studio](uninstall-visual-studio.md)
* [Vytvoření offline instalace sady Visual Studio](create-an-offline-installation-of-visual-studio.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
* [Instalace sady Visual Studio pro Mac](/visualstudio/mac/installation)