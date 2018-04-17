---
title: Rychlý start - vytvořte projekt Python pomocí Cookiecutter
description: Tento rychlý start vytvoříte projekt sady Visual Studio pro jazyk Python pomocí šablony Cookiecutter.
ms.custom: mvc
ms.date: 09/22/2017
ms.technology:
- devlang-python
dev_langs:
- python
ms.topic: quickstart
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: ff5079247c0fb9e2ae4e1efbde40bc14d93c4908
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="quickstart-create-a-project-from-a-cookiecutter-template"></a>Rychlý úvod: Vytvořte projekt ze šablony Cookiecutter

Jakmile jste [nainstalována podpora v jazyce Python ve Visual Studio 2017](installing-python-support-in-visual-studio.md), je snadné vytvořit nový projekt ze šablony Cookiecutter, včetně mnoha z těch, které jsou publikovány na Githubu. [Cookiecutter](https://cookiecutter.readthedocs.io/en/latest/) poskytuje grafické uživatelské rozhraní k zjištění šablony, zadejte možnosti šablony a vytváření projektů a soubory. To je součástí Visual Studio 2017 a je možné nainstalovat odděleně v dřívějších verzích sady Visual Studio.

1. Tento rychlý start nejprve nainstalujte distribuční Anaconda3 Python, včetně nezbytných balíčků Python pro šablonu Cookiecutter zobrazeny zde. Spusťte instalační program sady Visual Studio, vyberte **upravit**, rozbalte položku Možnosti **vývoj Python** na pravé straně a vyberte možnost "Anaconda3" (32bitová nebo 64bitová verze). Všimněte si, že instalace může trvat delší dobu v závislosti na rychlosti sítě Internet, ale toto je nejjednodušší způsob, jak nainstalovat potřebné balíčky.

1. Spusťte sadu Visual Studio.

1. Vyberte **soubor > Nový > z Cookiecutter...** . Tento příkaz otevře okno v sadě Visual Studio, kde je možné procházet šablony. 

    ![Nový projekt ze šablony Cookiecutter](media/projects-from-cookiecutter1.png)

1. Vybraná šablona "Microsoft nebo python-sklearn třídění cookiecutter" a pak vyberte **Další**. (Tento proces může trvat několik minut při prvním použití Cookiecutter.)

1. V dalším kroku, nastavit umístění pro nový projekt v **vytvořit na** pole a pak vyberte **vytvořit**.

    ![Druhý krok pomocí Cookiecutter, nastavení vlastností projektu](media/projects-from-cookiecutter2.png)

1. Po dokončení procesu se zobrazí zpráva "Soubory vytvořen úspěšně." Vyberte příkaz **otevřete v Průzkumníku řešení** otevřít projekt.

1. Stiskněte klávesy Ctrl + F5 nebo vyberte **ladění > Spustit bez ladění** ke spuštění programu. 

    ![Výstup šablony python sklearn třídění cookiecutter projektu](media/projects-from-cookiecutter4.png)

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Kurz: Práce s Python v sadě Visual Studio](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## <a name="see-also"></a>Viz také

- [Použití rozšíření Cookiecutter](using-python-cookiecutter-templates.md)
- [Ručně identifikace existující překladač Pythonu](managing-python-environments-in-visual-studio.md#manually-identifying-an-existing-environment).
- [Instalace podpory Python v sadě Visual Studio 2015 a starší](installing-python-support-in-visual-studio.md).
- [Umístění instalace](installing-python-support-in-visual-studio.md#install-locations).
