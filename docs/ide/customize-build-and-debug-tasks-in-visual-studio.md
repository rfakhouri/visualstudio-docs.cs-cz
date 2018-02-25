---
title: "Přizpůsobení sestavení a ladění úloh v sadě Visual Studio pomocí tasks.vs.json a launch.vs.json | Microsoft Docs"
ms.date: 02/21/2018
ms.technology: vs-ide-general
ms.topic: article
helpviewer_keywords:
- NMAKE [Visual Studio]
- makefiles [Visual Studio]
- customize codebases [Visual Studio]
- tasks.vs.json file [Visual Studio]
- launch.vs.json file [Visual Studio]
- vsworkspacesettings.json file [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5d40bd35d893afeb8e76e18d46185b3d63add1c5
ms.sourcegitcommit: 3abca1c733af876c8146daa43a62e829833be280
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/23/2018
---
# <a name="customize-build-and-debug-tasks-for-open-folder-development"></a>Přizpůsobení sestavení a ladění úloh pro vývoj "Otevřít složku"

Visual Studio umí spustit mnoho různých jazycích a základy kódu, ale neví, jak spustit vše. Pokud jste [otevřít složku kód](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) v sadě Visual Studio a Visual Studio umí pro spouštění vašeho kódu, můžete ji spustit hned bez jakékoli dodatečné konfigurace.

Pokud základu kódu používá vlastní sestavovací nástroje, které nerozpoznal v sadě Visual Studio, potřebujete poskytovat některé podrobnosti o konfiguraci pro spuštění a ladění kódu v sadě Visual Studio. Visual Studio pokyn jak sestavit kódu tak, že definujete *úlohy sestavení*. Můžete vytvořit jeden nebo více sestavení úloh a určete všechny položky, které jazyk potřebuje k sestavení a spuštění jeho kód. Můžete také vytvořit libovolné úlohy, které mohou provádět skoro všechny, které chcete. Například můžete vytvořit úlohy zobrazit obsah složky nebo pokud chcete přejmenovat soubor.

Přizpůsobení vašeho projektu méně základu kódu pomocí následující *.json* soubory:

|Název souboru|Účel|
|-|-|
|*tasks.vs.json*|Zadejte vlastní sestavovací příkazy a přepínače kompilátoru a libovolný (bez sestavení související) úlohy.<br>Přístupu prostřednictvím **Průzkumníku řešení** položky kontextové nabídky **nakonfigurovat úlohy**.|
|*launch.vs.json*|Zadejte argumenty příkazového řádku pro ladění.<br>Přístupu prostřednictvím **Průzkumníku řešení** položky kontextové nabídky **ladění a spusťte nastavení**.|
|*VSWorkspaceSettings.json*|Obecná nastavení, které může mít vliv na úlohy a spustit. Například definování `envVars` v *VSWorkspaceSettings.json* přidává proměnné zadané prostředí ke spuštění příkazů externě.<br>Tento soubor můžete vytvořit ručně.|

Tyto *.json* soubory jsou umístěny ve skryté složce s názvem *neodstraňujte* kořenové složky vaší základu kódu. *Tasks.vs.json* a *launch.vs.json* soubory jsou vytvořeny pomocí sady Visual Studio na podle potřeby, když zvolíte buď **nakonfigurovat úlohy** nebo **ladění a spusťte nastavení** k souboru nebo složky v **Průzkumníku řešení**. Tyto *.json* soubory jsou skryté, protože uživatelé obecně nemusíte chtít vrátit je do správy zdrojového kódu. Ale pokud chcete mít možnost ověřit jejich do správy zdrojového kódu, přetáhněte soubory do kořenové codebase, tam, kde jsou viditelné.

> [!TIP]
> Chcete-li zobrazit skryté soubory v sadě Visual Studio, vyberte **zobrazit všechny soubory** tlačítka na panelu nástrojů Průzkumníka řešení.

## <a name="define-tasks-with-tasksvsjson"></a>Define tasks with tasks.vs.json

Je možné automatizovat skripty sestavení nebo jiné externí operace se soubory, které máte v aktuálním pracovním prostoru spuštěním jako úlohy přímo v prostředí IDE. Novou úlohu můžete nakonfigurovat tak, že kliknete pravým tlačítkem na soubor nebo složku a výběr **nakonfigurovat úlohy**.

![Konfigurace nabídka úkoly](../ide/media/customize-configure-tasks-menu.png)

To vytvoří (nebo otevře) *tasks.vs.json* v soubor *neodstraňujte* složky. Můžete definovat úlohu sestavení nebo libovolný úloh v tomto souboru a pak ho pomocí názvu, dáte mu z vyvolání **Průzkumníku řešení** kontextové nabídky.

Vlastní úlohy mohou být přidány do jednotlivé soubory, nebo u všech souborů určitého typu. Například soubory balíčku NuGet lze nakonfigurovat tak, aby měl úlohu "Packages obnovení", nebo všechny zdrojové soubory lze nakonfigurovat tak, aby měl statické analýzy úlohy, jako je například linter pro všechny *.js* soubory.

### <a name="define-custom-build-tasks"></a>Definování úloh vlastní sestavení

Pokud váš kód používá vlastní sestavovací nástroje, které nerozpoznal v sadě Visual Studio, nelze spustit a ladění kódu v sadě Visual Studio, dokud nedokončíte některé kroky konfigurace. Visual Studio poskytuje *úlohy sestavení* tam, kde se dá zjistit sady Visual Studio jak vytvořit, znovu sestavit a vyčistit vašeho kódu. *Tasks.vs.json* sestavení párům souboru úloh nástroje používané vaší codebase sestavení smyčky vnitřní vývoj sady Visual Studio pro vlastní.

Vezměte v úvahu základu kódu, který se skládá z jednoho souboru C# s názvem *hello.cs*. Soubor pravidel pro takové codebase může vypadat například takto:

```makefile
build: directory hello.exe

hello.exe: hello.cs
    csc -debug hello.cs /out:bin\hello.exe

clean:
    del bin\hello.exe bin\hello.pdb

rebuild: clean build

directory: bin

bin:
    md bin
```

U takových souboru pravidel, který obsahuje sestavení, vyčistit a opětovné sestavení cíle, můžete definovat následující *tasks.vs.json* souboru. Obsahuje tři úlohami sestavení pro vytváření, znovu sestavit a čištění základu kódu, pomocí NMAKE jako nástroj pro sestavení.

```json
{
  "version": "0.2.1",
  "outDir": "\"${workspaceRoot}\\bin\"",
  "tasks": [
    {
      "taskName": "makefile-build",
      "appliesTo": "makefile",
      "type": "launch",
      "contextType": "build",
      "command": "nmake",
      "args": [ "build" ],
      "envVars": {
        "VSCMD_START_DIR": "\"${workspaceRoot}\""
      }
    },
    {
      "taskName": "makefile-clean",
      "appliesTo": "makefile",
      "type": "launch",
      "contextType": "clean",
      "command": "nmake",
      "args": [ "clean" ],
      "envVars": {
        "VSCMD_START_DIR": "\"${workspaceRoot}\""
      }
    },
    {
      "taskName": "makefile-rebuild",
      "appliesTo": "makefile",
      "type": "launch",
      "contextType": "rebuild",
      "command": "nmake",
      "args": [ "rebuild" ],
      "envVars": {
        "VSCMD_START_DIR": "\"${workspaceRoot}\""
      }
    }
  ]
}
```

Po nadefinování úlohy sestavení v *tasks.vs.json*, další kontext nabídky položky budou přidány do odpovídající soubory v **Průzkumníku řešení**. V tomto příkladu **sestavení**, **znovu sestavit**, a **Vyčistit** možnosti jsou přidány do kontextové nabídky všech *makefile* soubory.

![místní nabídky souboru pravidel se sestavením, znovu sestavit a vyčistit](media/customize-build-rebuild-clean.png)

> [!NOTE]
> Příkazy se zobrazují v místní nabídce v části **nakonfigurovat úlohy** příkaz z důvodu jejich `contextType` nastavení. "sestavení", "sestavit" a "čistou" jsou příkazy sestavení, aby se zobrazovaly v části sestavení uprostřed v místní nabídce.

Když vyberete některou z těchto možností, spustí se úloha. Zobrazí se výstup v **výstup** okno a chyby sestavení se zobrazí v **seznam chyb**.

### <a name="define-arbitrary-tasks"></a>Definování libovolný úloh

Můžete definovat libovolný úlohy v *tasks.vs.json* souboru udělat jenom o něco chcete. Například můžete definovat úlohy k zobrazení názvu aktuálně vybraného souboru v **výstup** okno, nebo seznam souborů v daném adresáři.

Následující příklad ukazuje *tasks.vs.json* soubor, který definuje jednu úlohu. Po vyvolání úlohy zobrazuje název souboru aktuálně vybrané *.js* souboru.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskName": "Echo filename",
      "appliesTo": "*.js",
      "type": "default",
      "command": "${env.COMSPEC}",
      "args": [ "echo ${file}" ]
    }
  ]
}
```

- `taskName` Určuje název, který se zobrazí v místní nabídce.
- `appliesTo` Určuje soubory, které lze provést příkaz na.
- `command` Vlastnost určuje příkaz, který má být vyvolána. V tomto příkladu `COMSPEC` proměnné prostředí se používá k identifikaci překladač příkazového řádku obvykle *cmd.exe*.
- `args` Vlastnost určuje argumenty, které mají být předány do příkazu vyvolaná.
- `${file}` Makro načte vybraného souboru v **Průzkumníku řešení**.

Po uložení *tasks.vs.json*, kliknete pravým tlačítkem na na žádném *.js* souborů ve složce a zvolte **Echo filename**. Název souboru se zobrazí v **výstup** okno.

> [!NOTE]
> Pokud vaše codebase neobsahuje *tasks.vs.json* souboru, můžete vytvořit výběrem **nakonfigurovat úlohy** v nabídce klikněte pravým tlačítkem nebo kontextu souboru v **Průzkumníku řešení**.

Další příklad definuje úlohu, která obsahuje soubory a podsložky *bin* adresáře.

```json
{
  "version": "0.2.1",
  "outDir": "\"${workspaceRoot}\\bin\"",
  "tasks": [
    {
      "taskName": "List Outputs",
      "appliesTo": "*",
      "type": "default",
      "command": "${env.COMSPEC}",
      "args": [ "dir ${outDir}" ]
    }
  ]
}
```

- `${outDir}` je definován vlastní makra, která se nejdřív před `tasks` bloku. Pak je volána `args` vlastnost.

Tato úloha se vztahuje na všechny soubory. Při otevření kontextové nabídky na všechny soubory v **Průzkumníku řešení**, název úkolu **seznamu výstupy** se zobrazuje v dolní části nabídky. Pokud vyberete **seznamu výstupy**, obsah *bin* adresáře jsou uvedeny v **výstup** oken v sadě Visual Studio.

![Libovolný úloha v místní nabídce](../ide/media/customize-arbitrary-task-menu.png)

### <a name="settings-scope"></a>Nastavení oboru

Více *tasks.vs.json* soubory může existovat v kořenové a podadresáře kódem. Tento návrh umožňuje flexibilita pro různé chování v různých podadresáře základu kódu. Visual Studio agreguje nebo přepíše nastavení v průběhu základu kódu, upřednostněním soubory v následujícím pořadí:

- Nastavení soubory v kořenové složce *neodstraňujte* adresáře.
- Adresář, kde výpočtu nastavení.
- Nadřazený adresář aktuální adresář, až kořenový adresář.
- Soubory nastavení v kořenovém adresáři.

Tato pravidla agregace platí pro *tasks.vs.json* a *VSWorkspaceSettings.json* soubory. Informace o tom, jak jsou nastavení v jiné sdílené agregován najdete v části odpovídající pro tento soubor v tomto článku.

### <a name="properties-for-tasksvsjson"></a>Properties for tasks.vs.json

Tato část popisuje některé z vlastností můžete zadat v *tasks.vs.json*.

#### <a name="appliesto"></a>appliesTo

Můžete vytvořit úlohy pro libovolný soubor nebo složku a to zadáním názvu v `appliesTo` pole, například `"appliesTo": "hello.js"`. Následující masek souboru můžete použít jako hodnoty:

|||
|-|-|
|`"*"`| Úloha je k dispozici pro všechny soubory a složky v pracovním prostoru|
|`"*/"`| Úloha je k dispozici pro všechny složky v pracovním prostoru|
|`"*.js"`| Úloha je k dispozici pro všechny soubory s příponou .js v pracovním prostoru|
|`"/*.js"`| Úloha je k dispozici pro všechny soubory s příponou .js v kořenu pracovního prostoru|
|`"src/*/"`| Úloha je k dispozici pro všechny podsložky složky "src"|
|`"makefile"`| Úloha je k dispozici pro všechny soubory souboru pravidel v pracovním prostoru|
|`"/makefile"`| Úloha je k dispozici pouze v souboru pravidel v kořenu pracovního prostoru|

#### <a name="macros-for-tasksvsjson"></a>Macros for tasks.vs.json

|||
|-|-|
|`${env.<VARIABLE>}`| Určuje všechny proměnné prostředí (například ${env. CESTA}, ${env.COMSPEC} a tak dále), je nastaven pro příkazový řádek vývojáře. Další informace najdete v tématu [příkazový řádek vývojáře pro sadu Visual Studio](/dotnet/framework/tools/developer-command-prompt-for-vs).|
|`${workspaceRoot}`| Úplná cesta ke složce prostoru (například "C:\sources\hello")|
|`${file}`| Úplná cesta k souboru nebo složky, které chcete spustit tuto úlohu (například "C:\sources\hello\src\hello.js")|
|`${relativeFile}`| Relativní cesta k souboru nebo složky (například "src\hello.js")|
|`${fileBasename}`| Název souboru bez cesty nebo rozšíření (například "hello")|
|`${fileDirname}`| Úplná cesta k souboru, s výjimkou název souboru (například "C:\sources\hello\src")|
|`${fileExtname}`| Rozšíření vybraného souboru (například ".js")|

## <a name="configure-debugging-with-launchvsjson"></a>Konfigurace ladění pomocí launch.vs.json

1. Ke konfiguraci vaší základu kódu pro ladění, v **Průzkumníku řešení** zvolte **ladění a spusťte nastavení** položky nabídky v nabídce klikněte pravým tlačítkem nebo kontextu spustitelného souboru.

   ![Ladění a spusťte nastavení kontextové nabídky](media/customize-debug-launch-menu.png)

1. V **vyberte ladicí program** dialogové okno, zvolte možnost a potom **vyberte** tlačítko.

   ![Vyberte dialogového okna ladicího programu](media/customize-select-a-debugger.png)

   Pokud *launch.vs.json* soubor již neexistuje, vytvoří se.

   ```json
   {
     "version": "0.2.1",
     "defaults": {},
     "configurations": [
       {
         "type": "default",
         "project": "bin\\hello.exe",
         "name": "hello.exe"
       }
     ]
   }
   ```

1. Pak klikněte pravým tlačítkem na spustitelný soubor ve **Průzkumníku řešení**a zvolte **nastavit jako položku při spuštění**.

   Spustitelný soubor je určený jako položku při spuštění pro vaše základu kódu a ladění **spustit** tlačítka název změní podle názvu vaší spustitelný soubor.

   ![Přizpůsobené tlačítko Start](media/customize-start-button.png)

   Pokud vyberete **F5**, ladicího programu spuštění a zastavení na všechny zarážek mohou být již nastavena. Všechny známé ladicího programu jsou dostupné a funkční.

### <a name="specify-arguments-for-debugging"></a>Zadejte argumenty pro ladění

Můžete zadat argumenty příkazového řádku předávat pro ladění v *launch.vs.json* souboru. Přidat argumentů `args` pole, jak je znázorněno v následujícím příkladu:

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "bin\\hello.exe",
      "name": "hello.exe"
    },
    {
      "type": "default",
      "project": "bin\\hello.exe",
      "name": "hello.exe a1",
      "args": [ "a1" ]
    }
  ]
}
```

Při ukládání tohoto souboru, název nové konfigurace se zobrazí v rozevíracím seznamu ladění cíl a můžete vybrat tak, aby ladicí program. Můžete vytvářet konfigurace mnoho ladění, jak se vám líbí.

![Konfigurace rozevíracím seznamu ladění](media/customize-debug-configurations.png)

> [!NOTE]
> `configurations` Pole vlastnost *launch.vs.json* je pro čtení ze dvou umístění souboru&mdash;kořenový adresář základu kódu a *neodstraňujte* adresáře. Pokud dojde ke konfliktu, přednostně na hodnotu v *.vs\launch.vs.json*.

## <a name="define-workspace-settings-in-vsworkspacesettingsjson"></a>Definujte nastavení pracovního prostoru v VSWorkspaceSettings.json

Můžete zadat Obecná nastavení, která může mít vliv na úlohy a spusťte v *VSWorkspaceSettings.json* souboru. Například pokud definujete `envVars` v *VSWorkspaceSettings.json*, Visual Studio přidává proměnné prostředí zadaný příkazy, které spouštějí externě. Pomocí tohoto souboru, musíte ji vytvořit ručně.

## <a name="additional-settings-files"></a>Soubory další nastavení

Kromě tří *.json* soubory popsaných v tomto tématu, Visual Studio také načte nastavení z některé další soubory, pokud existují ve vaší základu kódu.

### <a name="vscodesettingsjson"></a>.vscode\settings.json

Visual Studio čte omezené nastavení ze souboru s názvem *settings.json*, pokud se nachází v adresáři s názvem *.vscode*. Tato funkce slouží pouze k základy kódu, který dříve bylo vyvinuto v kódu Visual Studio. V současné době jenom nastavení číst z *.vscode\settings.json* je `files.exclude`, který filtry pro soubory vizuálně v Průzkumníku řešení a z některé nástroje pro vyhledávání.

Může mít libovolný počet *.vscode\settings.json* souborů ve vaší základu kódu. Nastavení pro čtení z tohoto souboru se vztahuje na nadřazeném adresáři *.vscode* a všech jejích podadresářů.

### <a name="gitignore"></a>.gitignore

*.gitignore* soubory se používají s oznámením Git, které soubory ignorovat; to znamená, které soubory a adresáře nechcete se změnami. *.gitignore* soubory jsou obvykle součástí codebase tak, aby nastavení můžete sdílet s všechny vývojáři základu kódu. Přečte vzory v sadě Visual Studio *.gitignore* soubory filtrování položek vizuálně a z některé hledání nástroje.

Nastavení číst z *.gitignore* souboru se použijí u nadřazeného adresáře a všechny podadresáře.

## <a name="see-also"></a>Viz také

- [Vývoj kódu bez projekty a řešení](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)
- [Otevřete složku projektů jazyka C++](/cpp/ide/non-msbuild-projects)
- [CMake projektů v jazyce C++](/cpp/ide/cmake-tools-for-visual-cpp)
- [NMAKE – odkaz](/cpp/build/nmake-reference)
- [Psaní kódu v editoru kódu a text.](../ide/writing-code-in-the-code-and-text-editor.md)