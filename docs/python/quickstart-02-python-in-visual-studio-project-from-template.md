---
title: Rychlý start - vytvořte projekt Python pomocí šablony
description: Tento rychlý start vytvoříte projekt sady Visual Studio pro jazyk Python pomocí předdefinované šablony pro základní aplikaci Flask.
ms.date: 05/07/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: quickstart
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: dca1e37a0cde89a2a531d3fceea4337bb9e348dd
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957334"
---
# <a name="quickstart-create-a-python-project-from-a-template-in-visual-studio"></a>Rychlý úvod: Vytvořte projekt Python ze šablony v sadě Visual Studio

Jakmile jste [nainstalována podpora v jazyce Python ve Visual Studio 2017](installing-python-support-in-visual-studio.md), je snadné vytvořit nový projekt Python pomocí různých šablon. V tento rychlý start vytvoříte jednoduchou aplikaci Flask pomocí šablony. Výsledný projekt je podobná projektu, můžete vytvořit ručně pomocí [rychlý start - vytvořit webovou aplikaci s Flask](../ide/quickstart-python.md).

1. Spusťte Visual Studio 2017.

1. Z panelu horní nabídce zvolte **soubor > Nový > projekt...** , potom v **nový projekt** dialogové okno hledání "prázdné flask", vyberte v seznamu střední šablonu "Prázdný webový projekt Flask", zadejte název projektu a vyberte **OK**:

    ![Vytvoření nového projektu pomocí šablony prázdný webový projekt Flask](media/quickstart-python-06-blank-flask-template.png)

1. Visual Studio vyzve vás se dialogové okno s informacemi o tom "Tento projekt vyžaduje externí balíčky." Toto dialogové okno se zobrazí, protože obsahuje šablony `requirements.txt` souboru zadáním závislost na Flask. Visual Studio můžete automaticky nainstalovat balíčky a vám dává možnost instalace je *virtuální prostředí*. Použití virtuálního prostředí se doporučuje namísto instalace do globální prostředí, takže vyberte **nainstalovat do virtuálního prostředí** pokračujte.

    ![Instalace Flask do virtuálního prostředí](media/quickstart-python-07-install-into-virtual-environment.png)

1. Visual Studio zobrazí **Přidání virtuálního prostředí** dialogové okno. Přijměte výchozí nastavení a vyberte **vytvořit**, pak souhlas žádné požadavky na zvýšení oprávnění.

    > [!Tip]
    > Abyste před zahájením projektu, ho má důrazně doporučujeme vytvoření virtuálního prostředí hned, protože většina šablony sady Visual Studio pozvat, abyste mohli provádět. Virtuální prostředí Údržba přesných požadavcích vašeho projektu v průběhu času, jak přidávat a odebírat knihovny. Potom můžete snadno generovat `requirements.txt` souboru, který použijete k přeinstalaci těchto závislostí na jiných počítačích vývoj (jako při používání zdroje ovládací prvek) a při nasazování projektu na provozním serveru. Další informace o virtuální prostředí a jejich výhody, najdete v části [pomocí virtuální prostředí](../python/selecting-a-python-environment-for-a-project.md#using-virtual-environments) a [Správa požadované balíčky s requirements.txt](../python/managing-required-packages-with-requirements-txt.md).

1. Jakmile sady Visual Studio vytvoří prostředí, podívejte se **Průzkumníku řešení** a podívejte se, že máte `app.py` souboru spolu s `requirements.txt`. Otevřete `app.py` zobrazíte, že šablona poskytl kódu, jako je například v [rychlý start - vytvořit webovou aplikaci s Flask](../ide/quickstart-python.md), se dvěma přidat části.

    Nejprve je v řádku `wsgi_app = app.wsgi_app` , může být užitečné při nasazení aplikace webového hostitele.

    Druhou je spuštění kód, který vám umožní nastavit hostitele a portu prostřednictvím proměnné prostředí místo pevně kódováno je. Takový kód vám pomůže snadno řídit konfiguraci na počítačích, vývoj a produkční beze změny kódu:

    ```python
    if __name__ == '__main__':
        import os
        HOST = os.environ.get('SERVER_HOST', 'localhost')
        try:
            PORT = int(os.environ.get('SERVER_PORT', '5555'))
        except ValueError:
            PORT = 5555
        app.run(HOST, PORT)
    ```

1. Vyberte **ladění > Spustit bez ladění** a spustit aplikaci otevřete prohlížeč na `localhost:5555`.

**Otázka: Jaký další Python šablony sady Visual Studio nabízí?**

**Odpověď**: zatížením Python, který je nainstalován, Visual Studio poskytuje řadu šablon projektu, včetně těch, které jsou pro [webového rozhraní Django, Flask a Bottle](../python/python-web-application-project-templates.md), cloudových služeb Azure, jiný strojového učení scénáře a to i šablonu pro vytváření projektů z existující strukturu složky obsahující aplikace Python. Přístup prostřednictvím **soubor > Nový > projekt...**  dialogové okno výběrem **Python** jazyk uzel a jeho podřízené uzly.

Visual Studio také poskytuje celou řadu souboru nebo *šablon položek* rychle vytvořit třídu Python, balíček Python, testování částí Python, `web.config` soubory a další. Až budete mít otevřít projekt Python, můžete přístup k šablon položek prostřednictvím **Projekt > Přidat novou položku** příkazu nabídky. Najdete v článku [šablon položek](python-item-templates.md) odkaz.

Pomocí šablon šetří důležité čas při vytváření projektu nebo vytváření souboru, a také jsou skvělý způsob, jak získat informace o různých typů aplikací a kódu struktury. Je užitečné trvat několik minut pro vytvoření projektů a položek z různých šablon se seznamte s co nabízejí.

**Otázka: Lze také použít Cookiecutter šablony?**

**Odpověď**: Ano! Ve skutečnosti Visual Studio poskytuje přímá integrace s Cookiecutter, které se dozvíte prostřednictvím [rychlý start: Vytvořte projekt ze šablony Cookiecutter](../python/quickstart-04-python-in-visual-studio-project-from-cookiecutter.md).

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Kurz: Práce s Python v sadě Visual Studio](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## <a name="see-also"></a>Viz také

- [Ručně identifikace existující překladač Pythonu](managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment).
- [Instalace podpory Python v sadě Visual Studio 2015 a starší](installing-python-support-in-visual-studio.md).
- [Umístění instalace](installing-python-support-in-visual-studio.md#install-locations).
