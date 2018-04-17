---
title: Použití souboru requirements.txt ke správě požadavků balíčku
description: Soubor requirements.txt můžete použít ke správě závislosti projektu. Pokud se zobrazí projekt, který obsahuje soubor requirements.txt, můžete snadno nainstalovat těchto závislostí v jednom kroku.
ms.custom: ''
ms.date: 02/20/2018
ms.technology:
- devlang-python
ms.devlang: python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: dfc5525bdb59e54ded2eddfd622b29d455719b77
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="managing-required-packages-with-requirementstxt"></a>Správa požadované balíčky s requirements.txt

Pokud jste sdílení projektu s ostatními, použití systému sestavení nebo plánujete [publikování do služby Microsoft Azure](python-azure-cloud-service-project-template.md), je třeba zadat externí balíčky, které vyžaduje projekt. Doporučuje se používat [soubor requirements.txt](http://pip.readthedocs.org/en/latest/user_guide.html#requirements-files) (readthedocs.org) obsahující seznam příkazů pro pip, který nainstaluje požadované verze závislé balíčky.

Technicky libovolný název souboru může sloužit k sledování požadavků (pomocí `-r <full path to file>` při instalaci balíčku), ale Visual Studio poskytuje konkrétní podporu pro `requirements.txt`:

- Pokud jste načíst projekt, který obsahuje `requirements.txt` a chcete instalovat všechny balíčky uvedené v tomto souboru, rozbalte **prostředí Python** uzlu v **Průzkumníku řešení**, klikněte pravým tlačítkem uzel prostředí a vyberte možnost **nainstalovat z requirements.txt**:

    ![Nainstalovat z requirements.txt](media/environments-requirements-txt-install.png)

- Pokud již máte všechny potřebné balíčky nainstalované v prostředí, můžete prostředí v Průzkumníku řešení klikněte pravým tlačítkem a vyberte **generovat soubor requirements.txt** k vytvoření souboru nezbytné. Pokud soubor již existuje, jak se zobrazí výzva k její aktualizaci:

    ![Možnosti requirements.txt aktualizace](media/environments-requirements-txt-replace.png)

  - **Nahradí celý soubor** odebere všechny položky, komentáře a možnosti, které existují.
  - **Aktualizovat existující položky** zjistí požadavků balíčku a aktualizuje verze specifikátory tak, aby odpovídaly aktuálně nainstalovanou verzi.
  - **Aktualizace a přidání položky** aktualizuje všechny požadavky, které se nacházejí a přidá všechny ostatní balíčky na konec souboru.

Protože `requirements.txt` soubory jsou určeny k freeze – požadavky na prostředí, všechny nainstalované balíčky jsou zapsány s přesné verze. Použití přesné verze zajišťuje, že budete moci snadno opakovat prostředí na jiném počítači. Balíčky jsou zahrnuty i v případě, že byly instalovány s rozsahem verze jako závislost jiný balíček, nebo instalační program než pip.

Pokud balíček nelze nainstalovat systém PIP a zobrazí se v `requirements.txt` souboru celý instalace se nezdaří. V takovém případě ruční úpravy souboru vyloučit tohoto balíčku, nebo chcete použít [pip na možnosti](http://pip.readthedocs.org/en/latest/reference/pip_install.html#requirements-file-format) k odkazování na instalovat verzi balíčku. Například může byste radši chtěli použít [ `pip wheel` ](http://pip.readthedocs.org/en/latest/reference/pip_wheel.html) závislost zkompilujete a přidat `--find-links <path>` možnost na váš `requirements.txt`:

```output
C:\Project>pip wheel azure
Downloading/unpacking azure
    Running setup.py (path:C:\Project\env\build\azure\setup.py) egg_info for package azure

Building wheels for collected packages: azure
    Running setup.py bdist_wheel for azure
    Destination directory: c:\project\wheelhouse
Successfully built azure
Cleaning up...

C:\Project>type requirements.txt
--find-links wheelhouse
--no-index
azure==0.8.0

C:\Project>pip install -r requirements.txt -v
Downloading/unpacking azure==0.8.0 (from -r requirements.txt (line 3))
    Local files found: C:/Project/wheelhouse/azure-0.8.0-py3-none-any.whl
Installing collected packages: azure
Successfully installed azure
Cleaning up...
    Removing temporary dir C:\Project\env\build...
```

## <a name="see-also"></a>Viz také

- [Správa prostředí Python v sadě Visual Studio](managing-python-environments-in-visual-studio.md)
- [Výběr interpretu pro projekt](selecting-a-python-environment-for-a-project.md)
- [Cesty pro hledání](search-paths.md)
- [Odkaz na okno prostředí Python](python-environments-window-tab-reference.md)