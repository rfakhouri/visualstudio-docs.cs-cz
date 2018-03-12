---
title: "Jak definovat vlastní příkazy pro Python projekty v sadě Visual Studio | Microsoft Docs"
description: "Demonstruje postup úpravy souborů projektu a cíle pro přidání vlastních příkazů do místní nabídky projektu Python v sadě Visual Studio. Příkazy můžete vyvolat na spustitelné programy, skripty, moduly, fragmenty kódu vloženého a pip."
ms.custom: 
ms.date: 02/02/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: ec06764bb898888657a144f682827896f52ce223
ms.sourcegitcommit: 3285243d6c0521266053340fe06505885d12178b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2018
---
# <a name="defining-custom-commands-for-python-projects"></a>Definování vlastní příkazy pro projektů v jazyce Python

Při spolupráci s projekty, Python, možná bude sami přepnutí na okno příkazového řádku pro spuštění konkrétní skripty nebo moduly, spustit příkazy pip, nebo nějaký jiný libovolný nástroj spustit. Ke zlepšení pracovní postup, můžete přidat vlastní příkazy **Python** podnabídky v místní nabídce Projekt Python. Tyto příkazy můžete spustit v okně konzoly nebo v okně výstupu sady Visual Studio. Regulární výrazy můžete použít také k sadě Visual Studio pokyn, jak analyzovat chyby a upozornění z výstup příkazu.

Ve výchozím nastavení této nabídky obsahuje jenom jeden **spustit Pylint** příkaz:

![Výchozí vzhled dílčí Python na místní nabídku projektu](media/custom-commands-default-menu.png)

Vlastní příkazy se zobrazí v této stejné kontextové nabídky. Vlastní příkazy se přidají do projektu soubor přímo, kde se vztahují k této jednotlivých projektu. Můžete také definovat vlastní příkazy v `.targets` soubor, který lze snadno importovat do více souborech projektu.

Některé šablony Python projektů v sadě Visual Studio již přidat vlastní příkazy vlastní použití jejich `.targets` souboru. Například šablony Bottle webový projekt a webový projekt Flask přidejte dva příkazy **počátečního serveru** a **spuštění ladění serveru**. Šablona webový projekt Django přidá tyto stejné příkazy a několik dalších:

![Vzhled podnabídky Python v projektu Django kontextové nabídky](media/custom-commands-django-menu.png)

Každý vlastního příkazu mohou odkazovat na soubor Python, modul Python, vloženého kódu jazyka Python, libovolný spustitelný soubor nebo příkaz pip. Můžete také zadat, jak a kde se příkaz spustí.

> [!Tip]
> Vždy, když provedete změny do souboru projektu v textovém editoru, je potřeba znovu načíst projekt v sadě Visual Studio pro tyto změny použít. Například můžete musí znovu načíst projekt po přidání vlastního příkazu definice pro tyto příkazy se objevily na místní nabídky projektu.
>
> Jak může víte, Visual Studio poskytuje prostředky ke upravit přímo soubor projektu. Nejprve klikněte pravým tlačítkem na soubor projektu a vyberte **uvolnit projekt**, pak znovu klikněte pravým tlačítkem a vyberte **upravit (název projektu)** otevřete projekt v editoru Visual Studio. Potom zkontrolujte a uložíte úpravy, ještě jednou klikněte pravým tlačítkem projekt a vyberte **znovu načíst projekt**, který také vás vyzve k potvrzení zavření souboru projektu v editoru.
>
> Při vývoji vlastního příkazu, ale tyto klikne na tlačítko se může stát zdlouhavé. Pro efektivnější pracovního postupu, načtení projektu v sadě Visual Studio a také otevřít `'.pyproj` souboru v editoru samostatné zcela (například jiné instance systému Visual Studio, Visual Studio Code, Poznámkový blok, atd.). Při uložení změn v editoru a přepnete se do sady Visual Studio, Visual Studio rozpoznává změny a zobrazí dotaz, zda chcete projekt znovu načíst ("projektu (název) byl změněn mimo prostředí."). Vyberte **opětovného načtení** a změny jsou okamžitě použity v jednom kroku.

## <a name="walkthrough-add-a-command-to-a-project-file"></a>Návod: Přidání příkaz do souboru projektu

Seznamte se s vlastní příkazy, provede v této části jednoduchý příklad, který spouští přímo pomocí python.exe souboru spuštění projektu. (Takové příkaz je efektivně stejná jako **ladění > Spustit bez ladění**.)

1. Vytvoření nového projektu s názvem "Python-CustomCommands" pomocí šablony "Aplikace Python". (Viz [rychlý start: Vytvořte projekt Python ze šablony](quickstart-02-project-from-template.md) pokyny, pokud ještě nejste obeznámeni s procesem.)

1. V `Python_CustomCommands.py`, přidejte kód `print("Hello custom commands")`.

1. Klikněte pravým tlačítkem na projekt v **Průzkumníku řešení**, vyberte **Python**a Všimněte si, že je pouze příkaz, který se zobrazí v podnabídce **spustit PyLint**. Tento stejný podnabídce zobrazeny vlastní příkazy.

1. Jako navržené v úvodu, otevřete `Python-CustomCommands.pyproj` v samostatných textovém editoru. Pak přidejte následující řádky na konci souboru pouze uvnitř ukončovací `</Project>` a soubor uložte.

    ```xml
    <PropertyGroup>
      <PythonCommands>
        $(PythonCommands);
      </PythonCommands>
    </PropertyGroup>
    ```

1. Přepněte zpět na Visual Studio a vyberte **opětovného načtení** Pokud budete vyzváni o změně souboru. Zkontrolujte **Python** nabídky zjistíte, které **spustit PyLint** je stále pouze položky zobrazené existuje, protože jste přidali pouze řádky replikovat výchozí `<PythonCommands>` obsahující PyLint skupina vlastností příkaz.

1. Přepněte do editoru do souboru projektu a přidejte následující `<Target>` definice po `<PropertyGroup>`. Jak je popsáno dále v tomto článku, to `Target` element definuje vlastní příkaz ke spuštění souboru (identifikovaný vlastnost "StartupFile") na spuštění pomocí `python.exe` v okně konzoly. Atribut `ExecuteIn="consolepause"` používá konzolu, která čeká na stisknutím klávesy před zavřením.

    ```xml
    <Target Name="Example_RunStartupFile" Label="Run startup file" Returns="@(Commands)">
      <CreatePythonCommandItem
        TargetType="script"
        Target="$(StartupFile)"
        Arguments=""
        WorkingDirectory="$(MSBuildProjectDirectory)"
        ExecuteIn="consolepause">
        <Output TaskParameter="Command" ItemName="Commands" />
      </CreatePythonCommandItem>
    </Target>
    ```

1. Přidejte hodnotu cílové složky `Name` atribut `<PythonCommands>` vlastnost skupiny přidali dříve, tak, aby element vypadá jako kód níže. Přidání název cílového do tohoto seznamu je co přidá jej do **Python** nabídky.

    ```xml
      <PythonCommands>
        $(PythonCommands);
        Example_RunStartupFile
      </PythonCommands>
    ```

    Pokud chcete, aby váš příkaz zobrazí před názvům definovaným v `$(PythonCommands)`, umístěte je před tento token.

1. Uložte soubor projektu, přepněte do sady Visual Studio a projekt po zobrazení výzvy znovu načíst. Klikněte pravým tlačítkem na projekt "Python-CustomCommands" a vyberte **Python**. Měli byste vidět **spusťte soubor spuštění** položky v nabídce. Pokud nevidíte položky nabídky, zkontrolujte, zda jste přidali název, který má `<PythonCommands>` elementu. Viz také [Poradce při potížích s](#troubleshooting) dále v tomto článku.

    ![Vlastního příkazu zobrazovaných v podnabídce kontextu Python](media/custom-commands-walkthrough-menu-item.png)

1. Vyberte **spusťte soubor spuštění** příkaz a jste měli vidět okno příkazového řádku se zobrazí s textem "Hello vlastní příkazy" a "stisknutím libovolné klávesy pokračujte. . .".  Stisknutím klávesy zavřete toto okno.

    ![Výstup vlastního příkazu v okně konzoly](media/custom-commands-walkthrough-console.png)

1. Vrátit do editoru do souboru projektu a změňte hodnotu `ExecuteIn` atribut `output`. Uložte soubor, přepněte do sady Visual Studio, projekt znovu načíst a vyvolat příkaz znovu. Tentokrát uvidíte, že program výstupu se zobrazí v sadě Visual Studio **výstup** okno:

    ![Výstup vlastního příkazu v okně výstupu](media/custom-commands-walkthrough-output-window.png)

1. Chcete-li přidat další příkazy, definovat vhodný `<Target>` element u každého příkazu, přidejte název cíle do `<PythonCommands>` skupina vlastností a znovu načíst projekt v sadě Visual Studio.

>[!Tip]
> Pokud vyvolání příkazu, že používá projektu vlastnosti, jako například `($StartupFile)`a příkaz se nezdaří, protože není definován token, Visual Studio zakáže příkaz, dokud nebude znovu načíst projekt. Provádění změn pro projekt, který by definovat vlastnosti, ale neaktualizuje stav těchto příkazů, stále je třeba znovu načíst projekt v takových případech.

## <a name="command-target-structure"></a>Příkaz cílová struktura

Obecná forma `<Target>` element je vidět v následujícím pseudo kódu:

```xml
<Target Name="Name1" Label="Display Name" Returns="@(Commands)">
    <CreatePythonCommandItem Target="filename, module name, or code"
        TargetType="executable/script/module/code/pip"
        Arguments="..."
        ExecuteIn="console/consolepause/output/repl[:Display name]/none"
        WorkingDirectory="..."
        ErrorRegex="..."
        WarningRegex="..."
        RequiredPackages="...;..."
        Environment="...">

      <!-- Output always appears in this form, with these exact attributes -->
      <Output TaskParameter="Command" ItemName="Commands" />
    </CreatePythonCommandItem>
  </Target>
```

K odkazování na vlastnosti projektu nebo proměnné prostředí v hodnoty atributu, použijte název v rámci `$()` tokenu, jako třeba `$(StartupFile)` a `$(MSBuildProjectDirectory)`. Další informace najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).

### <a name="target-attributes"></a>Cíl atributy

| Atribut | Požadováno | Popis |
| --- | --- | --- |
| Název | Ano | Identifikátor pro příkaz v rámci projektu sady Visual Studio. Tento název musí být přidán do `<PythonCommands>` vlastnost skupiny pro příkaz zobrazit v podnabídce Python. |
| Popisek | Ano | Zobrazovaný název uživatelského rozhraní, které se zobrazí v nabídce dílčí Python. |
| Vrací | Ano | Musí obsahovat `@(Commands)`, který identifikuje cíl jako příkaz. |

### <a name="createpythoncommanditem-attributes"></a>Atributy CreatePythonCommandItem

Všechny hodnoty atributů jsou velká a malá písmena.

| Atribut | Požadováno | Popis |
| --- | --- | --- |
| TargetType | Ano | Určuje, co obsahuje atribut Target a jak se používá spolu s atribut argumenty:<ul><li>**spustitelný soubor**: spuštění spustitelného souboru s názvem v cíli, připojením hodnoty v argumentech, jako kdyby zadali přímo na příkazovém řádku. Hodnota musí obsahovat jenom název program bez argumentů.</li><li>**skript**: Spusťte `python.exe` s názvem souboru v cíli, a potom s hodnotou v argumentech.</li><li>**modul**: Spusťte `python -m` následuje název modulu v cíli, a potom s hodnotou v argumentech.</li><li>**kód**: spuštění kódu vloženého obsažené v cíli. Argumenty hodnota je ignorována.</li><li>**PIP**: Spusťte `pip` pomocí příkazu na cíli, za nímž následuje argumenty; je ExecuteIn nastavena na "výstupní", ale předpokládá pip `install` příkazů a používá cíl jako název balíčku.</li></ul> |
| cíl | Ano | Název souboru, název modulu, kódu nebo příkaz pip používat, v závislosti na TargetType. |
| Arguments | Nepovinné | Určuje řetězec argumentů umožnit k cíli (pokud existuje). Upozorňujeme, že pokud je TargetType `script`, argumenty, které uvedeny k programu Python, není `python.exe`. U ignoruje `code` TargetType. |
| ExecuteIn | Ano | Určuje prostředí, ve kterém se má spustit příkaz:<ul><li>**konzole**: (výchozí) spustí, cíl a argumenty jako jejich zadání přímo na příkazovém řádku. Příkazové okno se zobrazí, když cíl běží, pak je automaticky uzavřeny.</li><li>**consolepause**: stejné konzoly, ale čeká keypress před jeho zavřením okna.</li><li>**výstup**: cíl spustí a zobrazí její výsledky v okně výstupu v sadě Visual Studio. Pokud TargetType "pip", Visual Studio Target používá jako název balíčku a připojí argumenty.</li><li>**REPL**: cíl běží v [interaktivní okno Python](interactive-repl.md); volitelný zobrazovaný název se používá pro nadpis okna.</li><li>**žádný**: se chová stejně jako konzola.</li></ul>|
| WorkingDirectory | Nepovinné | Složka, ve kterém se má spustit příkaz. |
| ErrorRegex<br>WarningRegEx | Nepovinné | Použít pouze, pokud je ExecuteIn `output`. Obě hodnoty, zadejte jako regulární výraz, pomocí kterého Visual Studio analyzuje výstupu příkazu v okně Seznam chyb zobrazit chyby a upozornění. Pokud není zadaný, neovlivňuje příkazu v okně Seznam chyb. Další informace, na jaké sadě Visual Studio očekává, najdete v části [skupiny pojmenované zachycení](#named-capture-groups-for-regular-expressions). |
| RequiredPackages | Nepovinné | Seznam požadavků balíčku pro příkaz, který používá stejný formát jako [requirements.txt](https://pip.readthedocs.io/en/1.1/requirements.html) (pip.readthedocs.io). **Spustit PyLint** příkaz, například určuje `pylint>=1.0.0`. Před spuštěním příkazu, Visual Studio kontroluje, zda jsou nainstalovány všechny balíčky v seznamu. Visual Studio použije pip nainstalovat všechny chybějící balíčky. |
| Prostředí | Nepovinné | Řetězec proměnné prostředí k definování před spuštěním příkazu. Každá proměnná se používá ve formátu název = hodnota v případě více proměnných oddělené středníky. Proměnné s více hodnotami musí být součástí jedné nebo dvojité uvozovky, jako v ' NAME = VALUE1; HODNOTA2 '. |

#### <a name="named-capture-groups-for-regular-expressions"></a>Skupiny s názvem zachycení pro regulární výrazy

Při analýze chyby a upozornění z výstupu příkazu, Visual Studio očekává regulární výrazy v `ErrorRegex` a `WarningRegex` hodnoty použijte tento příkaz s názvem skupiny:

- `(?<message>...)`: Text chyby
- `(?<code>...)`: Kód chyby
- `(?<filename>...)`: Název souboru, pro kterou chybová zpráva
- `(?<line>...)`: Číslo řádku umístění v souboru, pro který ohlásil chybu.
- `(?<column>...)`: Číslo sloupce umístění v souboru, pro který ohlásil chybu.

Například PyLint vytváří upozornění v následujícím formátu:

```output
************* Module hello
C:  1, 0: Missing module docstring (missing-docstring)
```

Umožňuje sadě Visual Studio k extrahování náležité informace, které z těchto varování a zobrazit je do **seznam chyb** okně `WarningRegex` hodnota **spustit Pylint** příkaz vypadá takto:

```regex
^(?<filename>.+?)\((?<line>\d+),(?<column>\d+)\): warning (?<msg_id>.+?): (?<message>.+?)$]]
```

(Všimněte si, že `msg_id` v hodnotě by měl být ve skutečnosti `code`, najdete v části [problém 3680](https://github.com/Microsoft/PTVS/issues/3680).)

## <a name="creating-a-targets-file-with-custom-commands"></a>Vytvoření souboru .targets pomocí vlastní příkazy

Definování vlastní příkazy v souboru projektu dává k dispozici pouze daný projektový soubor. Používat příkazy ve více souborech projektu, můžete místo toho definovat `<PythonCommands>` skupinu vlastností a všechny vaše `<Target>` elementů v `.targets` souboru. Tento soubor pak importovat do jednotlivých projektů soubory.

`.targets` Soubor je naformátován takto:

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup>
    <PythonCommands>
      $(PythonCommands);
      <!-- Additional command names -->
    </PythonCommands>
  </PropertyGroup>

  <Target Name="..." Label="..." Returns="@(Commands)">
    <!-- CreatePythonCommandItem and Output elements... -->
  </Target>

  <!-- Any number of additional Target elements-->
</Project>
```

Načíst `.targets` souboru do projektu, umístit `<Import Project="(path)">` element kdekoli v rámci `<Project>` element. Například, pokud máte soubor s názvem `CustomCommands.targets` v `targets` podsložky ve vašem projektu, použijte následující kód:

```xml
<Import Project="targets/CustomCommands.targets"/>
```

> [!Note]
> Vždy, když změníte `.targets` souboru, budete muset znovu načíst *řešení* obsahující projekt, ne jenom projektu.

## <a name="example-commands"></a>Příklady příkazů

### <a name="run-pylint-module-target"></a>Spustit PyLint (cíl modulu)

Zobrazí se následující kód v `Microsoft.PythonTools.targets` souboru:

```xml
<PropertyGroup>
  <PythonCommands>$(PythonCommands);PythonRunPyLintCommand</PythonCommands>
  <PyLintWarningRegex>
    <![CDATA[^(?<filename>.+?)\((?<line>\d+),(?<column>\d+)\): warning (?<msg_id>.+?): (?<message>.+?)$]]>
  </PyLintWarningRegex>
</PropertyGroup>

<Target Name="PythonRunPyLintCommand"
        Label="resource:Microsoft.PythonTools.Common;Microsoft.PythonTools.Common.Strings;RunPyLintLabel"
        Returns="@(Commands)">
  <CreatePythonCommandItem Target="pylint.lint"
                           TargetType="module"
                           Arguments="&quot;--msg-template={abspath}({line},{column}): warning {msg_id}: {msg} [{C}:{symbol}]&quot; -r n @(Compile, ' ')"
                           WorkingDirectory="$(MSBuildProjectDirectory)"
                           ExecuteIn="output"
                           RequiredPackages="pylint&gt;=1.0.0"
                           WarningRegex="$(PyLintWarningRegex)">
    <Output TaskParameter="Command" ItemName="Commands" />
  </CreatePythonCommandItem>
</Target>
```

### <a name="run-pip-install-with-a-specific-package-pip-target"></a>Spusťte instalaci pip s konkrétní balíček (pip cíl)

Následující příkaz spustí `pip install my-package` v okně výstupu. Můžete použít příkaz, jako když balíček vývoj a testování její instalaci. Všimněte si, že cíl obsahuje název balíčku místo `install` příkaz, který se předpokládá, že při použití `ExecuteIn="output"`.

```xml
<PropertyGroup>
  <PythonCommands>$(PythonCommands);InstallMyPackage</PythonCommands>
</PropertyGroup>

<Target Name="InstallMyPackage" Label="pip install my-package" Returns="@(Commands)">
  <CreatePythonCommandItem Target="my-package" TargetType="pip" Arguments=""
    WorkingDirectory="$(MSBuildProjectDirectory)" ExecuteIn="output">
    <Output TaskParameter="Command" ItemName="Commands" />
  </CreatePythonCommandItem>
</Target>
```

### <a name="show-outdated-pip-packages-pip-target"></a>Zobrazení zastaralých pip balíčky (pip cíl)

```xml
<PropertyGroup>
  <PythonCommands>$(PythonCommands);ShowOutdatedPackages</PythonCommands>
</PropertyGroup>

<Target Name="ShowOutdatedPackages" Label="Show outdated pip packages" Returns="@(Commands)">
  <CreatePythonCommandItem Target="list" TargetType="pip" Arguments="-o --format columns"
    WorkingDirectory="$(MSBuildProjectDirectory)" ExecuteIn="consolepause">
    <Output TaskParameter="Command" ItemName="Commands" />
  </CreatePythonCommandItem>
</Target>
```

### <a name="run-an-executable-with-consolepause"></a>Spustit spustitelný soubor s consolepause

Následující příkaz jednoduše spustí `where` zobrazíte Python souborů, začínající ve složce projektu:

```xml
<PropertyGroup>
  <PythonCommands>$(PythonCommands);ShowAllPythonFilesInProject</PythonCommands>
</PropertyGroup>

<Target Name="ShowAllPythonFilesInProject" Label="Show Python files in project" Returns="@(Commands)">
  <CreatePythonCommandItem Target="where" TargetType="executable" Arguments="/r . *.py"
    WorkingDirectory="$(MSBuildProjectDirectory)" ExecuteIn="output">
    <Output TaskParameter="Command" ItemName="Commands" />
  </CreatePythonCommandItem>
</Target>
```

### <a name="run-server-and-run-debug-server-commands"></a>Spusťte server a spusťte ladění příkazy serveru

Prozkoumat jak **počátečního serveru** a **spuštění ladění serveru** příkazy pro webové projekty jsou definovány, zkontrolujte [Microsoft.PythonTools.Web.targets](https://github.com/Microsoft/PTVS/blob/master/Python/Product/BuildTasks/Microsoft.PythonTools.Web.targets) (Githubu).

### <a name="install-package-for-development"></a>Nainstalovat balíček pro vývoj

```xml
<PropertyGroup>
  <PythonCommands>PipInstallDevCommand;$(PythonCommands);</PythonCommands>
</PropertyGroup>

<Target Name="PipInstallDevCommand" Label="Install package for development" Returns="@(Commands)">
    <CreatePythonCommandItem Target="pip" TargetType="module" Arguments="install --editable $(ProjectDir)"
        WorkingDirectory="$(WorkingDirectory)" ExecuteIn="Repl:Install package for development">
      <Output TaskParameter="Command" ItemName="Commands" />
    </CreatePythonCommandItem>
  </Target>
```

*Z [fxthomas/Example.pyproj.xml](https://gist.github.com/fxthomas/5c601e3e0c1a091bcf56aed0f2960cfa) (Githubu), použít s oprávněním.*

### <a name="generate-windows-installer"></a>Generovat Instalační služby systému Windows

```xml
<PropertyGroup>
  <PythonCommands>$(PythonCommands);BdistWinInstCommand;</PythonCommands>
</PropertyGroup>

<Target Name="BdistWinInstCommand" Label="Generate Windows Installer" Returns="@(Commands)">
    <CreatePythonCommandItem Target="$(ProjectDir)setup.py" TargetType="script"
        Arguments="bdist_wininst --user-access-control=force --title &quot;$(InstallerTitle)&quot; --dist-dir=&quot;$(DistributionOutputDir)&quot;"
        WorkingDirectory="$(WorkingDirectory)" RequiredPackages="setuptools"
        ExecuteIn="Repl:Generate Windows Installer">
      <Output TaskParameter="Command" ItemName="Commands" />
    </CreatePythonCommandItem>
  </Target>
```

*Z [fxthomas/Example.pyproj.xml](https://gist.github.com/fxthomas/5c601e3e0c1a091bcf56aed0f2960cfa) (Githubu), použít s oprávněním.*

### <a name="generate-wheel-package"></a>Generovat balíček wheel

```xml
<PropertyGroup>
  <PythonCommands>$(PythonCommands);BdistWheelCommand;</PythonCommands>
</PropertyGroup>

<Target Name="BdistWheelCommand" Label="Generate Wheel Package" Returns="@(Commands)">

  <CreatePythonCommandItem Target="$(ProjectDir)setup.py" TargetType="script"
      Arguments="bdist_wheel --dist-dir=&quot;$(DistributionOutputDir)&quot;"
      WorkingDirectory="$(WorkingDirectory)" RequiredPackages="wheel;setuptools"
      ExecuteIn="Repl:Generate Wheel Package">
    <Output TaskParameter="Command" ItemName="Commands" />
  </CreatePythonCommandItem>
</Target>
```

*Z [fxthomas/Example.pyproj.xml](https://gist.github.com/fxthomas/5c601e3e0c1a091bcf56aed0f2960cfa) (Githubu), použít s oprávněním.*

## <a name="troubleshooting"></a>Poradce při potížích

### <a name="message-the-project-file-could-not-be-loaded"></a>Zpráva: "soubor projektu, že nelze načíst

Označuje, že máte chyby syntaxe v souboru projektu. Zpráva obsahuje konkrétní chyba s číslem řádku a pozice znaku.

### <a name="console-window-closes-immediately-after-command-is-run"></a>Zavře okno konzoly okamžitě po spuštění příkazu

Použití `ExecuteIn="consolepause"` místo `ExecuteIn="console"`.

### <a name="command-does-not-appear-on-the-menu"></a>Příkaz se nezobrazí v nabídce

Zkontrolujte, zda je součástí příkaz `<PythonCommands>` skupina vlastností a odpovídají název zadaný v názvu v seznamu příkazů `<Target>` element.

Například v následující prvky název "Příklad" ve skupině vlastností neodpovídá názvu "ExampleCommand" v cílové. Visual Studio nenajde příkaz s názvem "Příklad", zobrazí se žádný příkaz. Buď použijte "ExampleCommand" v seznamu příkazů nebo změňte název cílového pouze na "Příklad".

```xml
  <PropertyGroup>
    <PythonCommands>$(PythonCommands);Example</PythonCommands>
  </PropertyGroup>
  <Target Name="ExampleCommand" Label="Example Command" Returns="@(Commands)">
    <!-- ... -->
  </Target>
```

### <a name="message-an-error-occurred-while-running-command-name-failed-to-get-command-target-name-from-project"></a>Zpráva: Došlo k chybě při spuštění (název příkazu). Nepodařilo se získat příkazu (název cílové) z projektu.

Určuje, že obsah `<Target>` nebo `<CreatePythonCommandItem>` prvky jsou nesprávné. Možné důvody patří:

- Požadované `Target` atributu je prázdný.
- Požadované `TargetType` je prázdný nebo obsahuje nerozpoznané hodnotu atributu.
- Požadované `ExecuteIn` je prázdný nebo obsahuje nerozpoznané hodnotu atributu.
- `ErrorRegex` nebo `WarningRegex` je zadán bez nastavení `ExecuteIn="output"`.
- Nerozpoznaný atributy neexistují v elementu. Například může použili jste `Argumnets` (překlepu) místo `Arguments`.

Hodnoty atributů může být prázdný, pokud jste odkazovat na vlastnost, která není definována. Například pokud použijete token `$(StartupFile)` , ale žádný spouštěcí soubor byla definována v projektu a potom token přeloží na prázdný řetězec. V takových případech můžete chtít definovat výchozí hodnotu. Například **serverem** a **spustit ladění serveru** příkazy definované v Bottle, Flask, a výchozí šablony projektů Django `manage.py` Jestliže není určeno jinak soubor spuštění serveru ve vlastnostech projektu.

### <a name="visual-studio-hangs-and-crashes-when-running-the-command"></a>Visual Studio přestane reagovat a dojde k chybě při spuštění příkazu

Jste pravděpodobně probíhá pokus o spuštění příkazu konzoly s `ExecuteIn="output"`, v takovém případě Visual Studio dojít k chybě při pokusu o provedení analýzy výstupu. Místo nich se používá `ExecuteIn="console"`. (Viz [vydání 3682](https://github.com/Microsoft/PTVS/issues/3681).)

### <a name="executable-command-is-not-recognized-as-an-internal-or-external-command-operate-program-or-batch-file"></a>Spustitelný příkazový "není názvem vnitřního ani vnějšího příkazu, fungovat programu nebo dávkového souboru"

Při použití `TargetType="executable"`, hodnota v `Target` musí být *pouze* bez argumentů, jako je například "python" nebo "python.exe" pouze název programu. Přesunout všechny argumenty k `Arguments` atribut.
