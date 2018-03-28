---
title: Nainstalovat Visual Studio 2017 | Microsoft Docs
description: Informace o instalaci sady Visual Studio, krok za krokem.
ms.custom: ''
ms.date: 12/04/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
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
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ee1291e2ca304ed770eeee28c4996f68d2d07adb
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/28/2018
---
# <a name="install-visual-studio-2017"></a>Nainstalovat Visual Studio 2017
Vítá vás nový způsob instalaci sady Visual Studio! V našem nejnovější verzi jsme provedli jsme je snazší pro vás k výběru a instalaci součástí, které potřebujete. Také jsme jste snížení nároků sady Visual Studio tak, aby nainstaloval rychleji a s menšími dopady na systém než kdy dřív.

Chcete se dozvědět více o tom, co je nového v této verzi? V tématu naše [poznámky k verzi](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes).

Připraveno k instalaci? Provedeme vás přes něj krok za krokem.

## <a name="step-1---make-sure-your-computer-is-ready-for-visual-studio"></a>Krok 1 – Ujistěte se, že je počítač připraven pro sadu Visual Studio

Před zahájením instalace sady Visual Studio:

1. Zkontrolujte [požadavky na systém](https://www.visualstudio.com/productinfo/vs2017-system-requirements-vs). Tyto požadavky můžete vědět, jestli počítač podporuje Visual Studio 2017.
2. Použít nejnovější aktualizace systému Windows. Tyto aktualizace zkontrolujte, zda má počítač nejnovější aktualizace zabezpečení a požadované systémové součásti pro sadu Visual Studio.
3. Restartování počítače. Restartování zajistí, že všechny čekající instalace nebo aktualizace není bránit instalaci sady Visual Studio.
4. Uvolněte místo. Odebrání nepotřebných souborů a aplikací % SystemDrive %, například spuštění aplikace Vyčištění disku.

Dotazy týkající se staršími verzemi sady Visual Studio vedle sebe s Visual Studio 2017, najdete v článku [informace o kompatibilitě sady Visual Studio](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs#compatibility-with-previous-releases).

## <a name="step-2---download-visual-studio"></a>Krok 2 – stažení sady Visual Studio

Další stáhněte si soubor zaváděcího nástroje Visual Studio. Uděláte to tak, klikněte na následující tlačítko, vyberte edici Visual Studio 2017, který chcete, klikněte na tlačítko **Uložit**a potom klikněte na **otevřít složku**.

 > [!div class="button"]
 > [Stažení sady Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
<br/>

|         |         |
|---------|---------|
|  ![film ikonu fotoaparátu pro video](media/video-icon.png "přehrát video")  |    [Přehrát video,](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Download-the-Visual-Studio-Installer-GgrESHD6D_3311787171) na stažení souboru zaváděcího nástroje sady Visual Studio a vyberte edice Visual Studia, která je pro vás nejvhodnější. |

## <a name="step-3---install-the-visual-studio-installer"></a>Krok 3 – instalace instalační program sady Visual Studio

Potom spusťte soubor zaváděcího nástroje nainstalovat Instalační program Visual Studio. Tato nového zjednodušeného instalačního programu obsahuje všechno, co je potřeba nainstalovat i přizpůsobení Visual Studio 2017.

1.  Z vaší **stáhne** složku, klikněte dvakrát na zavaděč, který odpovídá nebo podobný jedné z následujících souborů:

  * **vs_enterprise.exe** for Visual Studio Enterprise
  * **vs_professional.exe** for Visual Studio Professional
  * **vs_community.exe** for Visual Studio Community  <br><br>

  Pokud se zobrazí oznámení o řízení uživatelských účtů, klikněte na tlačítko **Ano**.

2.  Požádáme vás potvrdit Microsoft [licenční podmínky](https://www.visualstudio.com/license-terms/) a Microsoft [prohlášení o ochraně osobních údajů](https://go.microsoft.com/fwlink/?LinkID=824704). Klikněte na tlačítko **pokračovat**.  

   ![Licenční podmínky a prohlášení o ochraně osobních údajů](media/vs2017-privacy-and-license-terms.PNG "licenční podmínky společnosti Microsoft a prohlášení o ochraně osobních údajů")

## <a name="step-4---select-workloads"></a>Krok 4 – vyberte úlohy

Po instalaci instalační program vám pomůže ho svou instalaci přizpůsobit výběrem sady funkcí – nebo úlohy, který chcete. Tady je způsob.

1.  Najít úlohu, kterou chcete v **instalaci sady Visual Studio** obrazovky.

 ![Vyberte zatížení z tohoto dialogového okna nastavení Visual Studio 2017](../install/media/install-visual-studio-enterprise.png)

     Vyberte například zatížení "Vývoj aplikací .NET". Se dodává s výchozí editor jádra, která obsahuje základní kódu úpravy podporu pro více než 20 jazycích, schopnost otevírat a upravovat kód z libovolné složky bez nutnosti vytvářet projekt a integrované správy zdrojového kódu.  

2.  Po výběru workload(s) má, klikněte na tlačítko **nainstalovat**.

    Potom zobrazit stav obrazovky zobrazující průběh instalace Visual Studia.

3.  Po instalaci nové úlohy a součásti, klikněte na tlačítko **spusťte**.  

> [!TIP]
>  Kdykoli po instalaci můžete nainstalovat úlohy nebo součásti, které jste původně nenainstalovali. Pokud máte Visual Studio otevřete, přejděte na **nástroje** > **funkcí a nástrojů pro získání...**  otevře se instalační program Visual Studio. Můžete také otevřít **instalační program Visual Studio** z nabídky Start. Odtud můžete vybrat úlohy nebo součásti, které chcete nainstalovat a pak klikněte na **upravit**.  

|         |         |
|---------|---------|
|  ![film ikonu fotoaparátu pro video](media/video-icon.png "přehrát video")  |    [Přehrát video,](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Install-Workloads-in-Visual-Studio-2017-jHE19HD6D_1611787171) o tom, jak nainstalovat Instalační program Visual Studio a nainstalujte zatížení. |

## <a name="step-5---select-individual-components-optional"></a>Krok 5 – vyberte jednotlivé součásti (volitelné)

Pokud nechcete použít funkci úlohy k přizpůsobení instalace Visual Studia, můžete tak učinit nainstalováním jednotlivých součástí. Chcete-li vybrat jednotlivé komponenty, klikněte na tlačítko **jednotlivých součástí** z instalačního programu Visual Studio, vyberte co chcete a potom postupujte podle pokynů.

  ![Visual Studio 2017 – instalace jednotlivých součástí](media/vs2017-components.PNG "jednotlivých součástí instalace sady Visual Studio")

  |         |         |
  |---------|---------|
  |  ![film ikonu fotoaparátu pro video](media/video-icon.png "přehrát video")  |   [Přehrát video,](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Install-Components-in-Visual-Studio-2017-ZMfaVID6D_7411787171) o postupu instalace jednotlivých součástí s použitím instalační program Visual Studio. |

## <a name="step-6---install-language-packs-optional"></a>Krok 6: instalace jazykové sady (volitelné)

Ve výchozím nastavení instalační program pokusí podle jazyka operačního systému, když je poprvé spuštěna. Nainstalovat Visual Studio 2017 v jazyce dle vlastního výběru, klikněte na **jazykové sady** možnost z instalačního programu Visual Studio a postupujte podle pokynů.

  ![Visual Studio 2017 – instalace jazykové sady](media/vs2017-languages.PNG "jazykové sady nainstalovat Visual Studio")

  |         |         |
  |---------|---------|
  |  ![film ikonu fotoaparátu pro video](media/video-icon.png "přehrát video")  |   [Přehrát video,](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Install-Language-Packs-in-Visual-Studio-2017-ByT7yID6D_9011787171) o tom, jak nainstalovat jazykovou sadu pomocí Instalační program Visual Studio. |

### <a name="change-the-installer-language-from-the-command-line"></a>Změnit jazyk instalační program z příkazového řádku

Dalším způsobem, že můžete změnit výchozí jazyk je tak, že spustíte instalační program z příkazového řádku. Například můžete vynutit pomocí následujícího příkazu spustíte v angličtině instalačního programu: `vs_installer.exe --locale en-US`. Instalační program bude mějte na paměti Toto nastavení, při příštím spuštění. Instalační program podporuje následující klíčová slova jazyka: zh-cn, zh-tw, cs-cz, en-us, es-es, fr-fr, de-de, it-it, ja-jp, ko-kr, pl-pl, pt-br, ru-ru a tr-tr.


## <a name="step-7---start-developing"></a>Krok 7 – začít vyvíjet
1. Po dokončení instalace sady Visual Studio klikněte **spusťte** tlačítko pro [začít s vývojem pomocí sady Visual Studio](../ide/get-started-developing-with-visual-studio.md).

2. Klikněte na tlačítko **soubor**a potom klikněte na **nový projekt**.

3. Vyberte typ projektu. <br><br>
   Například pro [sestavení aplikace C++](../ide/getting-started-with-cpp-in-visual-studio.md), klikněte na tlačítko **nainstalovaná**, rozbalte položku **Visual C++**a pak vyberte typ projektu C++, který chcete vytvořit. <br><br>
   K [sestavení aplikace C#](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md), klikněte na tlačítko **nainstalovaná**, rozbalte položku **Visual C#**a pak vyberte typ projektu C#, který chcete vytvořit.

## <a name="get-support"></a>Získat podporu
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:
* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi.
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio).  (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také
* [Update Visual Studio 2017](update-visual-studio.md)
* [Upravit Visual Studio 2017](modify-visual-studio.md)
* [Odinstalace Visual Studio 2017](uninstall-visual-studio.md)
* [Vytvoření offline instalace Visual Studio 2017](create-an-offline-installation-of-visual-studio.md)
* [Visual Studio Příručka pro správce 2017](visual-studio-administrator-guide.md)
  * [Nainstalujte Visual Studio 2017 pomocí parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
* [Instalace Build Tools do kontejneru](build-tools-container.md)
