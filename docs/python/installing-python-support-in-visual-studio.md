---
title: Instalace podpory Python
description: Postup instalace nástroje Python Tools pro Visual Studio (PTVS) v aplikaci Visual Studio 2017, 2015, 2013, 2012 a 2010, včetně možnosti a umístění instalace.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: ae4dd83f5618ed908dee666f04c580f8c3161cbf
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37058682"
---
# <a name="how-to-install-python-support-in-visual-studio-on-windows"></a>Jak nainstalovat podporu jazyka Python v sadě Visual Studio v systému Windows

Chcete-li nainstalovat podporu jazyka Python pro Visual Studio (také označované jako Python Tools pro Visual Studio nebo PTVS), postupujte podle pokynů v oddílu, který se shoduje s vaší verzí sady Visual Studio:

- [Visual Studio 2017](#visual-studio-2017)
- [Visual Studio 2015](#visual-studio-2015)
- [Visual Studio 2013 a starší](#visual-studio-2013-and-earlier)

Pro Visual Studio 2015 a starší budete také muset samostatně [nainstalovat překladač Pythonu](installing-python-interpreters.md) podle vašeho výběru (Python 3.5 a starší; 3.6 není podporována a vygeneruje zpráva "Python Nepodporovaná verze 3.6"). Stejné stránce také obsahuje pokyny pro přidání existující překladač Python pro Visual Studio 2017.

Chcete-li rychle otestování podpory Python po provedení kroků instalace, otevřete okno Python interaktivní stisknutím klávesy Alt-I a zadáním `2+2`. Pokud nevidíte výstup `4`, znovu zkontrolovat vaše kroky.

> [!Tip]
> Zatížení Python zahrnuje užitečné Cookiecutter rozšíření, která poskytuje grafické uživatelské rozhraní k zjištění šablony, zadejte možnosti šablony a vytváření projektů a soubory. Podrobnosti najdete v tématu [pomocí Cookiecutter](using-python-cookiecutter-templates.md).

> [!Note]
> Podpora v jazyce Python není v současné době k dispozici v sadě Visual Studio pro Mac, ale je k dispozici na Mac a Linux pomocí Visual Studio Code. V tématu [otázky a odpovědi](overview-of-python-tools-for-visual-studio.md#questions-and-answers).

## <a name="visual-studio-2017"></a>Visual Studio 2017

1. Stáhněte a spusťte nejnovější verzi instalačního programu Visual Studio 2017. Pokud máte už nainstalovanou sadu Visual Studio, spusťte instalační program Visual Studio, vyberte **upravit** možnost (najdete v části [upravit Visual Studio](../install/modify-visual-studio.md)) a přejděte ke kroku 2.

    > [!div class="nextstepaction"]
    > <a target="frameTarget" href="https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&rel=15&rid=34347&utm_source=docs&utm_medium=clickbutton&utm_campaign=python_install">Nainstalovat Visual Studio 2017 Community</a>

    >[!Tip]
    > Community edition je pro jednotlivé vývojáři, učebny learning, academic výzkum a vývoj s otevřeným zdrojem. Pro jiné účely, nainstalujte <a target="frameTarget" href="https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Professional&rel=15&rid=34347&utm_source=docs&utm_medium=clickbutton&utm_campaign=python_install">Visual Studio 2017 Professional</a> nebo <a target="frameTarget" href="https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Enterprise&rel=15&rid=34347&utm_source=docs&utm_medium=clickbutton&utm_campaign=python_install">Visual Studio 2017 Enterprise</a>.

1. Instalační program nabídne seznam úloh, které jsou skupiny související možnosti jsou pro vývoj pro konkrétní oblasti. Pro jazyk Python, vyberte **vývoj Python** zatížení.

    ![Python vývoj zatížení v instalačním programu sady Visual Studio](media/installation-python-workload.png)

    Volitelné: Pokud pracujete s vědecké zpracování dat, zvažte také **vědecké zpracování dat a analytických aplikací** zatížení. Tato úloha zahrnuje podporu pro Python, jakož i jazyk R a F #. Další informace najdete v tématu [vědecké zpracování dat a aplikací pro uchovávání zatížení](../rtvs/data-science-and-analytical-applications-workload.md).

    > [!Note]
    > Python a vědecké zpracování dat úlohy jsou k dispozici pouze s verzí aplikace Visual Studio 2017 15.2 a novějším.

1. Na pravé straně instalačního programu vyberte v případě potřeby další možnosti. Přeskočte tento krok přijměte výchozí možnosti.

    ![Python vývoj možnosti v instalačním programu sady Visual Studio](media/installation-python-options.png)

    | Možnost | Popis |
    | --- | --- |
    | Distribuce Python | Vyberte libovolnou kombinaci variant 32bitové a 64bitové verze Python 2, Python 3, Anaconda2 a Anaconda3 distribuce, které chcete pracovat. Každý obsahuje překladač distribuci, modulu runtime a knihovny. Anaconda, konkrétně je platforma vědecké účely open data, která obsahuje řadu různých předem nainstalované balíčky. (Můžete vrátit na instalační program sady Visual Studio kdykoli přidat nebo odebrat distribuce.)  **Poznámka:**: Pokud jste nainstalovali distribuční mimo instalační program sady Visual Studio, je potřeba zkontrolovat ekvivalentní možnost. Visual Studio automaticky rozpozná existující instalace Python. V tématu [prostředí Python](managing-python-environments-in-visual-studio.md). |
    | Podpora Cookiecutter šablony | Nainstaluje Cookiecutter grafické uživatelské rozhraní k zjištění šablony, zadejte možnosti šablony a vytváření projektů a soubory. V tématu [pomocí rozšíření Cookiecutter](using-python-cookiecutter-templates.md). |
    | Podpora webového Python | Nainstaluje nástroje pro vývoj webů, včetně HTML, CSS a JavaScript úpravy podporu, společně s šablon pro projekty pomocí rozhraní Bottle, Flask a Django. V tématu [Python webové šablony projektů](python-web-application-project-templates.md). |
    | Podpora Python IoT | Podporuje vývoj jádro IoT Windows používá Python. |
    | Nástroje pro nativní vývoj Python | Nainstaluje kompilátoru C++ a další komponenty potřebné k vývoji nativní rozšíření pro jazyk Python. V tématu [vytváření rozšíření pro C++ pro jazyk Python](working-with-c-cpp-python-in-visual-studio.md). Taky nainstalovat **vývoj aplikací s jazykem C++** zatížení pro plnou podporu C++. |
    | Základní nástroje Azure Cloud Services | Poskytuje další podporu pro vývojáře Azure Cloud Services v Pythonu. V tématu [Azure cloud service projekty](python-azure-cloud-service-project-template.md). |

1. Po instalaci instalační program poskytuje možnosti změnit, spusťte, opravit nebo odinstalovat Visual Studio. **Upravit** tlačítko se změní na **aktualizace** když jsou k dispozici pro všechny nainstalované součásti aktualizace Visual Studio. (Možnost upravit je pak k dispozici v rozevírací nabídce.) Visual Studio a instalační program z nabídky Start systému Windows můžete také spustit a to vyhledáním "Visual Studio".

    ![Spuštění, úprava, úprava nebo odinstalace z instalačního programu sady Visual Studio](media/installation-vs-launch.png)

|   |   |
|---|---|
| ![Ikona filmové kamery pro video](../install/media/video-icon.png "Sledovat video") | [Podívejte se na video (Microsoft Virtual Academy)](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Installing-Visual-Studio-Python-Support-go1id3LWE_1705918567) k instalaci podpory jazyka Python v sadě Visual Studio.|

### <a name="troubleshooting"></a>Poradce při potížích

Pokud narazíte na potíže instalaci nebo spuštění Python v sadě Visual Studio, zkuste následující postup:

- Určení, zda dochází ke stejné chybě pomocí rozhraní příkazového řádku jazyka Python, který je, spuštěná `python.exe` z příkazového řádku.
- Použití [opravit možnosti v instalačním programu sady Visual Studio](../install/repair-visual-studio.md).
- Opravit nebo znovu nainstalovat Python prostřednictvím **Nastavení > aplikace a funkce** v systému Windows.

**Příklad chyba**: Nepodařilo se spustit proces interaktivní: System.ComponentModel.Win32Exception (0x80004005): Neznámá chyba (0xc0000135) na Microsoft.PythonTools.Repl.PythonInteractiveEvaluator.d__43.MoveNext().

## <a name="visual-studio-2015"></a>Visual Studio 2015

1. Spusťte instalační program sady Visual Studio **ovládací panely > programy a funkce**, vyberete **Microsoft Visual Studio 2015** a potom **změnu**.

1. V instalačním programu vyberte **upravit**.

1. Vyberte **programovací jazyky > Python Tools pro Visual Studio** a potom **Další**:

    ![Možnost PTVS v instalační program sady Visual Studio 2015](media/installation-vs2015.png)

1. Po dokončení instalačního programu sady Visual Studio [nainstalovat překladač Pythonu zvoleného](installing-python-interpreters.md). Pokud již máte překladač nainstalován a Visual Studio nebude automaticky rozpoznat najdete v tématu [ručně identifikovat stávajícího prostředí](managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment).

## <a name="visual-studio-2013-and-earlier"></a>Visual Studio 2013 a starší

1. Nainstalujte příslušnou verzi nástroje Python Tools pro sadu Visual Studio pro vaši verzi sady Visual Studio:

    - Visual Studio 2013: [PTVS 2.2 pro Visual Studio 2013](https://github.com/Microsoft/PTVS/releases/v2.2). **Soubor > Nový projekt** dialogové okno v sadě Visual Studio 2013 vám zástupce pro tento proces.
    - Visual Studio 2012: [PTVS 2.1 pro sadu Visual Studio 2012](https://pytools.codeplex.com/downloads/get/920478)
    - Visual Studio 2010: [PTVS 2.1 pro Visual Studio 2010](https://pytools.codeplex.com/downloads/get/920479)

1. [Nainstalujte překladač Pythonu zvoleného](installing-python-interpreters.md). Pokud již máte překladač nainstalován a Visual Studio nebude automaticky rozpoznat najdete v tématu [ručně identifikovat stávajícího prostředí](managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment).

## <a name="install-locations"></a>Umístění instalace

Ve výchozím nastavení pro všechny uživatele v počítači je nainstalována podpora v jazyce Python.

Pro Visual Studio 2017 zatížení Python je nainstalována v `%ProgramFiles(x86)%\Microsoft Visual Studio\2017\<VS_edition>Common7\IDE\Extensions\Microsoft\Python` kde &lt;VS_edition&gt; Community, Professional nebo Enterprise.

Pro Visual Studio 2015 a starší cesty instalace jsou následující:

- 32bitová verze:
  - Cesta: `%Program Files(x86)%\Microsoft Visual Studio <VS_ver>\Common7\IDE\Extensions\Microsoft\Python Tools for Visual Studio\<PTVS_ver>`
  - Umístění v registru cesty: `HKEY_LOCAL_MACHINE\Software\Microsoft\PythonTools\<VS_ver>\InstallDir`
- 64bitová verze:
  - Cesta: `%Program Files%\Microsoft Visual Studio <VS_ver>\Common7\IDE\Extensions\Microsoft\Python Tools for Visual Studio\<PTVS_ver>`
  - Umístění v registru cesty: `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\PythonTools\<VS_ver>\InstallDir`

kde:

- &lt;VS_ver&gt; je:
  - 14.0 pro Visual Studio 2015
  - 12.0 pro Visual Studio 2013
  - 11.0 pro sadu Visual Studio 2012
  - 10.0 pro Visual Studio 2010
- &lt;PTVS_ver&gt; číslo verze, jako je například 2.2, 2.1, 2.0, 1.5, 1.1 a 1.0.

### <a name="user-specific-installations-15-and-earlier"></a>Uživatelská instalace (1,5 a starší)

Python Tools pro Visual Studio 1.5 a starší povolena instalace pro aktuálního uživatele, v takovém případě cesta instalace je `%LocalAppData%\Microsoft\VisualStudio\<VS_ver>\Extensions\Microsoft\Python Tools for Visual Studio\<PTVS_ver>` kde &lt;VS_ver&gt; a &lt;PTVS_ver&gt; jsou stejné, jak je popsáno výše.

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
