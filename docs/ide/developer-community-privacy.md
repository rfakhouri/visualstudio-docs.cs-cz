---
title: Privátní data pro sestavy problémů
ms.date: 06/21/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- developer community privacy
- privacy, developer community
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2905cd6fcf9255eb8ba76d636d908651e2254115
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2018
ms.locfileid: "36327073"
---
# <a name="developer-community-data-privacy"></a>Ochrana dat komunity vývojářů

Ve výchozím nastavení, všechny informace v problém hlásí [komunity vývojářů](https://developercommunity.visualstudio.com/), včetně všech komentáře a odpovědi, je veřejně viditelný. Toto je výhodné, protože umožňuje celé komunitě zobrazíte problémy, řešení a řešení, které jiní uživatelé nalezeny. Pokud máte obavy o ochraně osobních údajů dat nebo identity, ale máte možnosti.

## <a name="identity-privacy"></a>Osobní údaje identity

Pokud máte obavy o odhalil svoji identitu, [vytvořit nový účet Microsoft](https://signup.live.com/) nezveřejňuje všechny podrobnosti o vás. Tento účet použijte pro vytvoření sestavy.

## <a name="data-privacy"></a>Ochrana dat

Pokud máte obavy o ochrany osobních údajů, neuvádějte nic, co chcete zachovat privátní v názvu nebo obsah počáteční sestavy, který je vždycky veřejné. Místo toho vytvoří sestavu a pak Všimněte si, že budete odesílat podrobnosti soukromě v samostatných komentář. Jakmile je vytvořena sestava problém, můžete určit, kdo může zobrazit odpovědi a přílohy:

1. V sestavě, které jste vytvořili, zvolte **, přidejte komentář** vytvořit privátní popis problému.

1. V editoru odpovědět, použijte následující ovládací prvek **odeslání** a **zrušit** tlačítka k určení cílové skupiny v odpovědi. Zvolte **Viewable moderátorů a původní plakáty** omezit viditelnost zaměstnancům společnosti Microsoft a sami.

   ![Ovládací prvek ochrany osobních údajů v komunity vývojářů](media/developer-community-privacy-control.png)

   Pouze uživatelé, které zadáte můžete zobrazit komentář a všechny bitové kopie, odkazů nebo kód, který je zahrnout v ní. Všechny odpovědi v části Komentář mají stejné viditelnost jako původní komentář. To platí i v případě, že ovládací prvek ochrany osobních údajů v odpovědi nezobrazí správně stav zobrazení s omezeným přístupem.

1. Přidejte popis a žádné jiné informace, Image a potřebné pro vaše zkopírujte přiložených souborů. Vyberte **odeslání** tlačítko soukromě odesílat výše uvedené informace.

   > [!NOTE]
   > Je omezena na připojené soubory 2 GB a maximálně 10 souborů. Pokud potřebujete větší soubor nahrát, můžete odeslat novou sestavu problém nebo žádat zaměstnanec společnosti Microsoft v privátní komentář adrese URL pro odeslání.

Chcete-li zachovat ochranu vašich osobních údajů a zachovat citlivých informací mimo veřejné zobrazení, postará zachovat veškerou komunikaci se společností Microsoft k odpovědi v části Komentář viditelnost omezený. Odpovědi na jiné připomínky může vést k omylem prozrazeny citlivé informace.

## <a name="data-we-collect"></a>Data, které shromažďujeme

Pokud **nahlásit problém** je zahájeno z instalačního programu Visual Studio, shromažďujeme nejnovější protokolu instalace.

Pokud **nahlásit problém** se zahájí ze sady Visual Studio, shromažďujeme jeden nebo více z následujících typů dat:

- Programu Watson a .NET položky z protokolu událostí

- Soubor protokolu v paměti aktivity Visual Studio

- PerfWatson souborů, pokud je povolená kolekce Watson, z *VSFeedbackPerfWatsonData* složky

- LiveShare soubory protokolu, pokud existují, z *VSFeedbackVSRTCLogs* složky

- Xamarin soubory protokolu, pokud existují, z *%LOCALAPPDATA%\Xamarin\Logs*

- Soubory protokolu Nuget, pokud existují, z *%TEMP%\NuGetScratch\nuget-dg\nugetSpec.dg*

- Ladicí program protokolu souborů webové, pokud existují:

   - *%TEMP%\vscode-Chrome-Debug.txt*

   - *%TEMP%\vscode-node-debug2.txt*

   - *%TEMP%\vscode-Edge-Debug.txt*

- Snímek obrazovky, pokud zvolíte možnost ji zahrnout

- Záznam dat, pokud se rozhodnete zahrnout záznam, který zahrnuje:

   - Postup reprodukování problému

   - Trasovací soubor ETL

   - Souboru s výpisem

   > [!NOTE]
   > Můžete odstranit žádný záznam dat, která jste si jej nepřejete odeslání před odesláním sestavy.

## <a name="see-also"></a>Viz také:

- [Postup nahlásit problém pomocí sady Visual Studio](how-to-report-a-problem-with-visual-studio-2017.md)
- [Ochrana dat sestavy problém C++](/cpp/how-to-report-a-problem-with-the-visual-cpp-toolset#reports-and-privacy)