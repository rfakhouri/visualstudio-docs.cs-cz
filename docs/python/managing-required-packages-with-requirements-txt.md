---
title: Použití soubor requirements.txt, který ke správě požadavků balíčku
description: Soubor requirements.txt, který můžete použít ke správě závislostí projektu. Pokud se zobrazí projekt obsahující soubor requirements.txt, můžete snadno nainstalovat tyto závislosti v jednom kroku.
ms.date: 06/27/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: efefda9fb5eb863550684511a5c0834f5d43f7fd
ms.sourcegitcommit: 40b6438b5acd7e59337a382c39ec711b9e99cc8a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/11/2018
ms.locfileid: "49100910"
---
# <a name="manage-required-packages-with-requirementstxt"></a>Správa požadované balíčky pomocí souboru requirements.txt

Pokud sdílíte projekt s ostatními, použití sestavovacího systému nebo v plánu nasadit na jakékoli jiné umístění, které je potřeba obnovit prostředí, budete muset zadat externí balíčky, které projekt vyžaduje. Doporučuje se použít [soubor requirements.txt](http://pip.readthedocs.org/en/latest/user_guide.html#requirements-files) (readthedocs.org), který obsahuje seznam příkazů pro pip, který instaluje požadované verze závislé balíčky.

Technicky vzato některý název souboru může sloužit ke sledování požadavků (s použitím `-r <full path to file>` při instalaci balíčku), ale Visual Studio poskytuje specifické podpoře pro *souboru requirements.txt*:

- Pokud jste načetli projekt, který obsahuje *souboru requirements.txt* a chcete nainstalovat všechny balíčky uvedené v tomto souboru, rozbalte **prostředí Pythonu** uzel v **Průzkumníka řešení**, klikněte pravým tlačítkem na uzel prostředí a vyberte **instalovat z requirements.txt**:

    ![Instalovat z requirements.txt](media/environments-requirements-txt-install.png)

- Pokud už máte všechny potřebné balíčky nainstalované ve prostředí, můžete kliknout pravým tlačítkem v daném prostředí **Průzkumníka řešení** a vyberte **generovat soubor requirements.txt** k vytvoření potřebných soubor. Pokud soubor již existuje, se zobrazí výzva pro jak ji aktualizovat:

    ![Možnosti aktualizace souboru requirements.txt](media/environments-requirements-txt-replace.png)

  - **Nahradí celý soubor** odebere všechny položky, poznámky a možnosti, které existují.
  - **Aktualizovat existující položky** zjistí požadavků balíčku a aktualizuje specifikátory verze tak, aby odpovídaly aktuálně nainstalovanou verzi.
  - **Aktualizace a přidání položky** aktualizuje všechny požadavky, které se nacházejí a přidá všechny ostatní balíčky na konec souboru.

Protože *souboru requirements.txt* soubory jsou určeny k zablokování požadavky prostředí, všechny nainstalované balíčky jsou vytvářeny s použitím přesné verze. Pomocí přesné verze zajistí, že můžete snadno reprodukovat svoje prostředí na jiném počítači. Balíčky jsou zahrnuty i v případě, že byly nainstalovány s rozsah verzí, jako závislost jinému balíčku, nebo instalační program než pip.

Pokud balíček nejde nainstalovat pomocí pip a zobrazí se v *souboru requirements.txt* celou instalaci souboru, se nezdaří. V takovém případě ruční úpravy souboru a vylučte tento balíček nebo pomocí [pip na možnosti](https://pip.readthedocs.org/en/latest/reference/pip_install.html#requirements-file-format) k odkazování na instalovatelnou verzi balíčku. Například můžete chtít použít [ `pip wheel` ](https://pip.readthedocs.org/en/latest/reference/pip_wheel.html) závislost zkompilujete a přidat `--find-links <path>` umožňuje vaší *souboru requirements.txt*:

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

### <a name="see-also"></a>Viz také:

- [Správa prostředí Pythonu v sadě Visual Studio](managing-python-environments-in-visual-studio.md)
- [Výběr interpretu pro projekt](selecting-a-python-environment-for-a-project.md)
- [Cesty pro hledání](search-paths.md)
- [Odkaz na okno prostředí Pythonu](python-environments-window-tab-reference.md)
