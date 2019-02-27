---
title: Rychlý start – vytvoření projektu Pythonu pomocí Cookiecutter
description: V tomto rychlém startu vytvoříte projekt sady Visual Studio pro Python s pomocí šablon Cookiecutter.
ms.date: 02/25/2019
ms.topic: quickstart
author: kraigb
ms.author: kraigb
manager: jillfra
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: 5c5a3170a2fa66a68fd010b616afcd24e8661776
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56843101"
---
# <a name="quickstart-create-a-project-from-a-cookiecutter-template"></a>Rychlý start: Vytvoření projektu ze šablony Cookiecutter

Jakmile [nainstalována podpora Pythonu v sadě Visual Studio 2017](installing-python-support-in-visual-studio.md), je snadné vytvořit nový projekt ze šablony Cookiecutter, včetně množství, které se publikují do Githubu. [Cookiecutter](https://cookiecutter.readthedocs.io/en/latest/) poskytuje grafické uživatelské rozhraní pro zjišťování šablony, zadejte možnosti šablony a vytváření projektů a souborů. Je součástí sady Visual Studio 2017 a je možné nainstalovat odděleně v dřívějších verzích sady Visual Studio.

1. Pro účely tohoto rychlého startu nejprve nainstalujte distribuční Anaconda3 Python, který obsahuje potřebné balíčky Pythonu pro šablony Cookiecutter je vidět tady. Spusťte instalační program sady Visual Studio, vyberte **změnit**, rozbalte možnosti pro **vývoj v jazyce Python** na pravé straně a vyberte **Anaconda3** (32bitová nebo 64bitová verze). Všimněte si, že instalace může trvat delší dobu v závislosti na rychlosti Internetu, ale toto je nejjednodušší způsob, jak nainstalovat potřebné balíčky.

1. Spusťte sadu Visual Studio.

1. Vyberte **souboru** > **nové** > **z Cookiecutter**. Tento příkaz otevře okno v sadě Visual Studio, kde můžou Procházet šablony.

    ![Nový projekt ze šablony Cookiecutter](media/projects-from-cookiecutter1.png)

1. Vybrané **Microsoft/python-skriptu sklearn třídění cookiecutter** šablony, pak vyberte **Další**. (Proces se může trvat několik minut při prvním použití konkrétní šablonu, protože Visual Studio nainstaluje požadované balíčky Pythonu.)

1. V dalším kroku, nastavit umístění nového projektu v **vytvořit do** pole a pak vyberte **vytvořit a otevřít projekt**.

    ![Druhý krok pomocí Cookiecutter, nastavení vlastností projektu](media/projects-from-cookiecutter2.png)

1. Po dokončení procesu se zobrazí zpráva **úspěšně vytvoření souborů pomocí šablony...** . Otevření projektu v Průzkumníku řešení automaticky.

1. Stisknutím klávesy **Ctrl**+**F5** nebo vyberte **ladění** > **spustit bez ladění** ke spuštění programu.

    ![Výstup projektu šablony python skriptu sklearn třídění cookiecutter](media/projects-from-cookiecutter4.png)

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Kurz: Práce s využitím Pythonu v sadě Visual Studio](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## <a name="see-also"></a>Viz také:

- [Použití rozšíření Cookiecutter](using-python-cookiecutter-templates.md)
- [Ručně identifikovat existující interpret Pythonu](managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment)
- [Instalace podpory Pythonu v sadě Visual Studio 2015 a starší](installing-python-support-in-visual-studio.md)
- [Umístění instalace](installing-python-support-in-visual-studio.md#install-locations)
