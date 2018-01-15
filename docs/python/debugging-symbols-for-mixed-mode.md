---
title: "Symboly pro ladění ve smíšeném režimu Python nebo C++ v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 07/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 8ab89a3646f5fa239dee0375c3d30cfe95ebe17c
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/12/2018
---
# <a name="installing-debugging-symbols-for-python-interpreters"></a>Instalace pro Python překladače symboly pro ladění

K poskytování úplné ladění prostředí, [ladicí program Python ve smíšeném režimu](debugging-mixed-mode.md) v sadě Visual Studio musí ladění symboly pro překladač Pythonu používá analyzovat spousta interních datových strukturách. Pro python27.dll například odpovídající soubor symbol je python27.pdb; pro python36.dll je soubor symbol python36.pdb. Každá verze nástroje Překladač také poskytuje soubory symbolů pro celou řadu modulů.

S Visual Studio 2017 "Python 3" a "Anaconda 3" překladače automaticky nainstalovat jejich odpovídajících značek a Visual Studio automaticky najít tyto symboly. Pro sadu Visual Studio 2015 a starší, nebo při použití jiných překladače, budete muset stáhnout symboly samostatně a pak k nim prostřednictvím sady Visual Studio **nástroje > Možnosti** dialogové okno ve **ladění > symboly**  kartě. Tyto kroky jsou podrobně popsané v následujících částech.

Visual Studio může výzvu, když potřebuje symboly, obvykle při spouštění relace ladění ve smíšeném režimu. V takovém případě se zobrazí dialogové okno s dvě možnosti:

- **Dialogové okno Nastavení otevřete symbol** otevře **možnosti** dialogovém okně můžete **ladění > symboly** kartě.
- **Stažení symboly pro moje překladač** otevře tato přítomen stránce dokumentace, v takovém případě vyberte **nástroje > Možnosti** a přejděte do **ladění > symboly** kartě pokračujte.

    ![Smíšený režim ladicí program symboly řádku](media/mixed-mode-debugging-symbols-required.png)

## <a name="downloading-symbols"></a>Stahuje se symboly

- Python, 3.5 nebo novější: získání symboly ladění prostřednictvím Python Instalační služby. Vyberte **vlastní instalace**, vyberte **Další** zobrazíte **pokročilé možnosti**, zaškrtněte políčka pro **stáhnout symboly ladění** a **ladicí binární soubory ke stažení**:

    ![Instalační program Python 3.x včetně symboly ladění](media/mixed-mode-debugging-symbols-installer35.png)

    Soubory symbolů (`.pdb`) se pak nacházejí v kořenové složce instalace (soubory symbolů pro jednotlivé moduly jsou v `DLLs` také složku). Z toho důvodu Visual Studio je najde automaticky a nejsou potřeba žádné další kroky.

- Python 3.4.x a starší: symboly jsou k dispozici jako soubory ZIP ke stažení z [oficiální distribuce](#official-distributions) nebo [Enthought zápoje](#enthought-canopy). Po stažení, extrahujte soubory do místní složky, chcete-li pokračovat, například `Symbols` složku ve složce Python.

    > [!Important]
    > Symboly liší menší sestavení jazyka Python a mezi sestaveními 32bitové a 64bitové verze, takže chcete přesně shodovat s verzí. Chcete-li zkontrolovat překladač používá, rozbalte **prostředí Python** *uzlu* pod projekt v Průzkumníku řešení a poznamenejte si název prostředí. Potom přepnout **prostředí Python** *okno* a poznamenejte si umístění instalace. Potom otevřete okno příkazového řádku v tomto umístění a spusťte `python.exe`, který zobrazuje přesnou verzi a zda je 32bitové nebo 64bitové verze.

- Pro všechny ostatní třetích stran Python distribuci, jako například ActiveState Python: Obraťte autorům příslušné distribuci a požádejte je poskytnout symboly. WinPython, jeho části, zahrnuje standardní překladač Pythonu beze změn, takže použijte symboly z oficiálního distribučního pro příslušné číslo verze.

## <a name="pointing-visual-studio-to-the-symbols"></a>Visual Studio přejdete na symboly

Pokud jste stáhli symboly samostatně, použijte následující postup aby věděly Visual Studio. Pokud jste nainstalovali symboly prostřednictvím Python 3.5 nebo novější instalační program, Visual Studio automaticky vyhledá.

1. Vyberte **nástroje > Možnosti** nabídky a přejděte do **ladění > symboly**.
    
1. Vyberte **přidat** tlačítka na panelu nástrojů (uvedených níže), zadejte složky, kam jste rozbalili stažené symboly (což je, kdy `python.pdb` nachází, například `c:\python34\Symbols`, níže uvedené) a vyberte **OK**. 

    ![Možnosti symboly ladění ve smíšeném režimu](media/mixed-mode-debugging-symbols.png)

1. Během relace ladění Visual Studio mohou také vyžadovat zadání umístění zdrojového souboru pro překladač Pythonu. Pokud jste stáhli zdrojové soubory (z [python.org/downloads](https://www.python.org/downloads), například), pak je samozřejmě může ukazovat na je také.

> [!Note]
> Funkce ukládání do mezipaměti symbol, který je vidět v dialogovém okně se používají k vytvoření místní mezipaměti symbolů získali z online zdroje. Tyto funkce nejsou potřeba se symboly překladač Pythonu jako symboly jsou již přítomny místně. V každém případě odkazovat na [zadejte symboly a zdrojových souborů ve Visual Studio Debugger](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md) podrobnosti.

## <a name="official-distributions"></a>Oficiální distribuce

| Verze jazyka Python | Soubory ke stažení | 
| --- | --- | 
| 3.5 nebo novější | Nainstalujte symboly prostřednictvím Python Instalační služby. | 
| 3.4.4 | [32-bit](https://www.python.org/ftp/python/3.4.4/python-3.4.4-pdb.zip) - [64-bit](https://www.python.org/ftp/python/3.4.4/python-3.4.4.amd64-pdb.zip) |
| 3.4.3 | [32-bit](https://www.python.org/ftp/python/3.4.3/python-3.4.3-pdb.zip) - [64-bit](https://www.python.org/ftp/python/3.4.3/python-3.4.3.amd64-pdb.zip) |
| 3.4.2 | [32-bit](https://www.python.org/ftp/python/3.4.2/python-3.4.2-pdb.zip) - [64-bit](https://www.python.org/ftp/python/3.4.2/python-3.4.2.amd64-pdb.zip) |
| 3.4.1 | [32-bit](https://www.python.org/ftp/python/3.4.1/python-3.4.1-pdb.zip) - [64-bit](https://www.python.org/ftp/python/3.4.1/python-3.4.1.amd64-pdb.zip) |
| 3.4.0 | [32-bit](https://www.python.org/ftp/python/3.4.0/python-3.4.0-pdb.zip) - [64-bit](https://www.python.org/ftp/python/3.4.0/python-3.4.0.amd64-pdb.zip) |
| 3.3.5 | [32-bit](http://www.python.org/ftp/python/3.3.5/python-3.3.5-pdb.zip) - [64-bit](http://www.python.org/ftp/python/3.3.5/python-3.3.5.amd64-pdb.zip) |
| 3.3.4 | [32-bit](http://python.org/ftp/python/3.3.4/python-3.3.4-pdb.zip) - [64-bit](http://python.org/ftp/python/3.3.4/python-3.3.4.amd64-pdb.zip) |
| 3.3.3 | [32-bit](http://python.org/ftp/python/3.3.3/python-3.3.3-pdb.zip) - [64-bit](http://python.org/ftp/python/3.3.3/python-3.3.3.amd64-pdb.zip) |
| 3.3.2 | [32-bit](http://python.org/ftp/python/3.3.2/python-3.3.2-pdb.zip) - [64-bit](http://python.org/ftp/python/3.3.2/python-3.3.2.amd64-pdb.zip) |
| 3.3.1 | [32-bit](http://python.org/ftp/python/3.3.1/python-3.3.1-pdb.zip) - [64-bit](http://python.org/ftp/python/3.3.1/python-3.3.1.amd64-pdb.zip) |
| 3.3.0 | [32-bit](http://python.org/ftp/python/3.3.0/python-3.3.0-pdb.zip) - [64-bit](http://python.org/ftp/python/3.3.0/python-3.3.0.amd64-pdb.zip) |
| 2.7.11 | [32-bit](https://www.python.org/ftp/python/2.7.11/python-2.7.11-pdb.zip) - [64-bit](https://www.python.org/ftp/python/2.7.11/python-2.7.11.amd64-pdb.zip) |
| 2.7.10 | [32-bit](https://www.python.org/ftp/python/2.7.10/python-2.7.10-pdb.zip) - [64-bit](https://www.python.org/ftp/python/2.7.10/python-2.7.10.amd64-pdb.zip) |
| 2.7.9 | [32-bit](https://www.python.org/ftp/python/2.7.9/python-2.7.9-pdb.zip) - [64-bit](https://www.python.org/ftp/python/2.7.9/python-2.7.9.amd64-pdb.zip) |
| 2.7.8 | [32-bit](https://www.python.org/ftp/python/2.7.8/python-2.7.8-pdb.zip) - [64-bit](https://www.python.org/ftp/python/2.7.8/python-2.7.8.amd64-pdb.zip) |
| 2.7.7 | [32-bit](https://www.python.org/ftp/python/2.7.7/python-2.7.7-pdb.zip) - [64-bit](https://www.python.org/ftp/python/2.7.7/python-2.7.7.amd64-pdb.zip) |
| 2.7.6 | [32-bit](http://python.org/ftp/python/2.7.6/python-2.7.6-pdb.zip) - [64-bit](http://python.org/ftp/python/2.7.6/python-2.7.6.amd64-pdb.zip) |
| 2.7.5 | [32-bit](http://python.org/ftp/python/2.7.5/python-2.7.5-pdb.zip) - [64-bit](http://python.org/ftp/python/2.7.5/python-2.7.5.amd64-pdb.zip) |
| 2.7.4 | [32-bit](http://python.org/ftp/python/2.7.4/python-2.7.4-pdb.zip) - [64-bit](http://python.org/ftp/python/2.7.4/python-2.7.4.amd64-pdb.zip) |
| 2.7.3 | [32-bit](http://python.org/ftp/python/2.7.3/python-2.7.3-pdb.zip) - [64-bit](http://python.org/ftp/python/2.7.3/python-2.7.3.amd64-pdb.zip) |
| 2.7.2 | [32-bit](http://python.org/ftp/python/2.7.2/python-2.7.2-pdb.zip) - [64-bit](http://python.org/ftp/python/2.7.2/python-2.7.2.amd64-pdb.zip) |
| 2.7.1 | [32-bit](http://python.org/ftp/python/2.7.1/python-2.7.1-pdb.zip) - [64-bit](http://python.org/ftp/python/2.7.1/python-2.7.1.amd64-pdb.zip) |


## <a name="enthought-canopy"></a>Enthought zápoje

Enthought zápoje poskytuje symboly pro její binární soubory od verze 1.2. Jsou automaticky nainstalovány spolu s rozdělení, ale stále budete muset ručně přidat složku obsahující je symbol cestu, jak je popsáno výše. V případě typické uživatelská instalace zápoje symboly umístěné ve `%UserProfile%\AppData\Local\Enthought\Canopy\User\Scripts` pro 64bitovou verzi a `%UserProfile%\AppData\Local\Enthought\Canopy32\User\Scripts` pro 32bitová verze.

Enthought zápoje 1.1 a starší, jakož i Enthought Python distribuční (EPD), neposkytují překladač symboly a proto nejsou kompatibilní s ladění ve smíšeném režimu.