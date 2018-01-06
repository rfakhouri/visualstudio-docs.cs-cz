---
title: "Vývoj kódu v sadě Visual Studio bez projekty a řešení | Microsoft Docs"
ms.custom: 
ms.date: 02/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.texteditor
dev_langs:
- JScript
- VB
- CSharp
helpviewer_keywords:
- code, editing
- code editor, syntax coloring
- code editor [Visual Studio]
- brace matching
- code editor, line numbers
- code editor, brace matching
- line numbers
- syntax coloring
- code editor
- code files
- code
ms.assetid: cb53bb9b-5b76-4759-b9b8-7bf32298bcbb
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 78b59ff3d8d6c54465ce29334c1dbe041b7a71be
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="develop-code-in-visual-studio-without-projects-or-solutions"></a>Vývoj kódu v sadě Visual Studio bez projekty a řešení  
V 2017 Visual Studio můžete do sady Visual Studio bez nutnosti soubor řešení nebo produktu project otevřete kód z téměř jakéhokoli typu na základě adresáře projektu. To znamená, že můžete, například najít projekt kódu na Git, klonovat a pak otevřete přímo do sady Visual Studio a začít, aniž by bylo nutné vytvořit projekt nebo řešení pro vývoj.  

Nejenže můžete můžete upravit kód a sestavte jej v sadě Visual Studio, můžete také přejít pomocí kódu (například pomocí přejděte na příkaz). Kód zobrazí s zabarvení syntaxe a v mnoha případech zahrnují základní dokončování a ladění, dokončete s zarážky. Některé jazyky bude obsahovat i další funkce. V tématu [vytvořit přenosné, vlastní editor nastavení](create-portable-custom-editor-options.md) Další informace.  

## <a name="open-code-anywhere"></a>Otevřete kód kdekoli  
Kód v sadě Visual Studio můžete otevřít následujícími způsoby:  

- Na panelu nabídek Visual Studio zvolte **soubor**, **otevřete**, **složky**, pak přejděte do umístění v kódu.  

- V nabídce kontextu (klikněte pravým tlačítkem) do složky obsahující kód zvolte **otevřete v sadě Visual Studio** příkaz.  

- Vyberte **otevřít složku** odkaz na Visual Studio – úvodní stránka.  

- Otevřete kód klonovat z úložiště GitHub.  

### <a name="to-open-code-from-a-cloned-github-repo"></a>Chcete-li spustit kód z klonovaného úložiště GitHub  
Následující příklad ukazuje, jak klonovat úložiště GitHub a pak otevřete jeho kód v sadě Visual Studio. Pomocí tohoto postupu, musí mít účet GitHub a Git pro Windows v systému nainstalována. V tématu [zaregistrujete nový účet GitHub](https://help.github.com/articles/signing-up-for-a-new-github-account/) a [Git pro Windows](https://git-for-windows.github.io/) Další informace.  

1. Přejděte na úložišti, které chcete klonovat na Githubu.  

1. Vyberte **klonovat nebo stáhnout** tlačítko a potom zvolte **kopírovat do schránky** tlačítko v rozevírací nabídce zkopírovat zabezpečená adresa URL pro úložiště GitHub.  

  ![Tlačítko klonování Githubu](./media/VSIDE_Code_Clone.png)

    > [!NOTE]
    >  Když máte také možnost Otevřít projekt na ploše nebo stažení souboru ZIP projektu, tento příklad ukazuje, jak naklonujte úložiště pomocí zabezpečené metody adresy URL.

1. Ve Visual Studiu zvolte **Team Explorer** otevřete Průzkumník týmových projektů.  

1. V nástroji Team Explorer pod **místní úložiště Git** zvolte **klon** příkaz a vložte adresu URL stránky Githubu do textového pole.  

  ![Klonování projektu](./media/VSIDE_Code_Clone2.png)

1. Vyberte **klon** tlačítko klonovat soubory projektu do místního úložiště Git. V závislosti na velikosti úložiště tento proces může trvat několik minut.  

1. Po úložišti má klonování k vašemu systému, v nástroji Team Explorer klikněte **otevřete** příkazu v nabídce kontextu (klikněte pravým tlačítkem) nově naklonovaný úložišti.  

  ![Klonovaný úložišti](./media/VSIDE_Code_Clone3.png)

1. Vyberte **zobrazit zobrazení složky** příkaz k prohlížení souborů v Průzkumníku řešení  

  ![Nastaví zobrazení složky](./media/VSIDE_Code_Clone3_show.png)

  Teď můžete procházet složky a soubory v klonovaném úložišti a zobrazení a hledání kód v sadě Visual Studio editoru kódu kompletní s zabarvení syntaxe a další funkce.

    ![Hledání kódu klonovaný projektu](./media/VSIDE_Code_Clone4.png)  

|         |         |
|---------|---------|
|  ![film ikonu fotoaparátu pro video](../install/media/video-icon.png "přehrát video")  |    [Přehrát video,](https://mva.microsoft.com/en-us/training-courses/getting-started-with-visual-studio-2017-17798?l=lp3TOKD6D_6711787171) o tom, jak klonovat a otevřete kód z úložiště GitHub v sadě Visual Studio. |

## <a name="debug-your-code"></a>Ladění kódu  
Můžete ladit kód v sadě Visual Studio bez projekt nebo řešení. K ladění některé jazyky, možná budete muset zadat platný *spuštění souboru* v projektu kódu, jako je skript, spustitelný soubor nebo projektu. Visual Studio tento zadaný kód spustí nejprve při ladění kódu.  

Pole se seznamem rozevíracího seznamu vedle tlačítka Start na panelu nástrojů zobrazí seznam všech položek spuštění, které zjistí Visual Studio, a také položky, které zvolíte ve složce.  

![Tlačítko Spustit](./media/VSIDE_Code_Run_Button.png)  

Visual Studio automaticky rozpozná, projekty, ale skripty (například JavaScript a Python) musí být explicitně vámi zvolené jako položku při spuštění předtím, než se objeví v seznamu. Kromě toho některé položky po spuštění, například nástroje MSBuild a CMake, může mít více konfigurace sestavení, které jsou v tlačítko Spustit rozevíracího seznamu.  

Visual Studio aktuálně podporuje ladění pro následující jazyky:  

- Node.js  

- Python  

- Projekty využívající MSBuild (C#, VB, C++)  

- Všechny spustitelný soubor s soubory PDB (ladicí program Python).  

### <a name="to-debug-nodejs-and-python"></a>Chcete-li ladit Node.js a Python:  
1. Nainstalujte Node.js nebo Python Tools nebo Visual Studio 2017 a Node.js runtime.  

1. V místní nabídce souboru JavaScript v Průzkumníku řešení, vyberte **nastavit jako položku při spuštění** příkaz.  

1. Vyberte **F5** klíč, aby začaly ladění.  

### <a name="to-debug-msbuild-projects"></a>Ladění projektů MSBuild  
1. V nabídce sady Visual Studio zvolte **ladění**. V rozevírací nabídce zvolte projekt nebo vyberte projekt nebo soubor, který chcete zobrazit jako položku při spuštění v Průzkumníku řešení.  

1. Vyberte **F5** klíč, aby začaly ladění.  

### <a name="to-debug-executable-files"></a>Chcete-li ladit spustitelné soubory  
1. V nabídce sady Visual Studio zvolte **ladění**. V rozevírací nabídce zvolte projekt nebo vyberte projekt nebo soubor, který chcete zobrazit jako položku při spuštění v Průzkumníku řešení.  

1. Vyberte **F5** klíč, aby začaly ladění.  

## <a name="enable-custom-build-tools"></a>Povolit vlastní sestavovací nástroje
Visual Studio umí spustit mnoho různých jazyků, ale neví, jak spustit vše. Pokud Visual Studio umí spustit svůj jazyk, můžete spustit kód hned. Pokud spustíte kódu, ale Visual Studio není známo, jak ji spustit, zobrazí informační panel zobrazí výzvu k určení souboru v vaší základu kódu tak, aby fungoval jako položku při spuštění.  

Pokud základu kódu používá vlastní sestavovací nástroje, které nerozpoznal v sadě Visual Studio, ale pak pravděpodobně nebude možné spouštět a ladění kódu v sadě Visual Studio, dokud nedokončíte některé další kroky. Musíte zadat platný spustitelný soubor typu, jako je například kompilátor, spolu se všechny vlastní parametry a argumenty, které vyžadují jazyk. Chcete-li povolit, Visual Studio poskytuje *úlohy sestavení*. Vytvoříte úlohu sestavení a určete všechny položky, které jazyk potřebuje k sestavení a spuštění jeho kód.  

Také můžete vytvořit libovolný sestavení úlohy, které mohou provádět skoro všechny, které chcete. Můžete například vytvořit úlohu k zobrazení seznamu obsahu složky nebo přejmenujte soubor. Nebo můžete vytvořit více cílových vlastní sestavovací úlohy, které provádění akcí, například kompilace a sestavení projektu pomocí konkrétní argumenty. Následující kroky ukazují, jak vytvořit oba typy úloh sestavení.  

#### <a name="to-create-an-arbitrary-build-task"></a>Chcete-li vytvořit úlohu libovolné sestavení  
1. Vyberte soubor nebo složku projekt v Průzkumníku řešení, kam chcete úlohu a v souboru nebo složky (klikněte pravým tlačítkem) místní nabídce vyberte **nakonfigurovat úlohy**.  

  ![Konfigurace úloh](./media/VSIDE_Code_Config_Task.png)

  Výběr **nakonfigurovat úlohy** otevře soubor s názvem tasks.vs.json. Pokud tento soubor neexistuje, vytvoří se. Tento soubor obsahuje úlohami sestavení pro vybraného souboru nebo složky.  

  ![Soubor Tasks.vs.JSON](./media/VSIDE_Code_Tasks_JSON.png)

1. Přidejte následující úlohu sestavení do tasks.vs.json. V tomto příkladu přidáme názvem "Seznamu výstupy" jednoduché úlohu, která obsahuje soubory a podsložky vybrané složky v okně výstupu. (Nová úloha musí být přidaní v rámci pole existujících "úlohy".)  

  ```xml
      {
        "taskName": "List outputs",
        "appliesTo": "*",
        "type": "command",
        "command": "${env.COMSPEC}",
        "args": [
          "dir ${outDir}"
        ]
      },
  ```
  Úloha dokončení sestavení by měl vypadat takto.  

  ![Úlohu libovolný sestavení](./media/VSIDE_Code_Tasks_ArbTask.png)

1. Uložte projekt.  

1. Otevřete v místní nabídce vybrané složky. Měli byste vidět nová úloha libovolný sestavení se zobrazí v dolní části v místní nabídce.  

  ![Příkaz úloh libovolný sestavení](./media/VSIDE_Code_Tasks_ArbTask2.png)

1. Zvolte nový **seznamu výstupy** příkaz k provedení úlohy.  

### <a name="to-create-a-custom-build-task"></a>Chcete-li vytvořit úlohu vlastní sestavení
V tomto postupu přidáme dva vlastní sestavovací úlohy, které využívají nMake sestavení a vyčistit vašeho kódu.  

1. Vyberte soubor projektu v Průzkumníku řešení, který chcete určit jako položku při spuštění později. V nabídce kontextu (klikněte pravým tlačítkem) v souboru zvolte **nakonfigurovat úlohy**.  

  ![Příkaz úloh vlastní sestavení](./media/VSIDE_Code_Tasks_CustTask1.png)

1. Přidejte následující úlohy sestavení do tasks.vs.json. V tomto příkladu přidáme dvě úlohy: jeden názvem "makefile sestavení" které používá příkaz nMake a tím projekt sestavit, druhou s názvem souboru pravidel vyčistit která volá příkaz nMake s argumentem "čistou". Tyto úlohy musí být přidaní v rámci pole existujících "úlohy". (Všimněte si, že jsou pouze příklad úlohami sestavení. Je ve skutečnosti pracovat, je potřeba mít pracovní zátěž, která obsahuje [nNake](/cpp/build/nmake-reference) v systému nainstalována.)

  ```xml
  {
  "taskName": "makefile-build",
  "appliesTo": "makefile",
  "type": "command",
  "contextType": "build",
  "command": "nmake"
  },
  {
  "taskName": "makefile-clean",
  "appliesTo": "makefile",
  "type": "command",
  "contextType": "clean",
  "command": "nmake",
  "args": [
    "clean"
    ]
  },
  ```
  Dokončení vlastní sestavovací úlohy by měl vypadat takto.  

  ![Vlastní sestavovací úlohy](./media/VSIDE_Code_Tasks_CustTask2.png)

1. Uložte projekt.  

1. Otevřete v místní nabídce vybraného souboru. Nové vlastní sestavovací úlohy by se zobrazit uprostřed v místní nabídce.  

  ![Příkaz úloh vlastní sestavení](./media/VSIDE_Code_Tasks_CustTask3.png)

  > [!NOTE]
  > Příkazy se zobrazí pod **nakonfigurovat úlohy** příkaz z důvodu jejich `contextType` nastavení; "sestavení" a "čistou" jsou příkazy sestavení, aby se zobrazovaly v části sestavení uprostřed v místní nabídce.  

  Teď, když mají vlastní sestavovací příkazy přidružené k souboru, můžete určit soubor jako položku při spuštění.  

1. V souboru kontextové nabídce zvolte **nastavit jako položku při spuštění**.  

  ![Příkaz úloh vlastní sestavení](./media/VSIDE_Code_Tasks_CustTask4.png)

1. Na panelu nástrojů vyberte na šipku rozevíracího seznamu vedle tlačítka Start. Tato položka se nyní zobrazí jako možnost.  

  ![Příkaz úloh vlastní sestavení](./media/VSIDE_Code_Tasks_CustTask5.png)

Nyní můžete **spustit** tlačítko nebo **F5** klíče ke spuštění vaší základu kódu. Můžete upravit a ladění vaší základu kódu v sadě Visual Studio, i když Visual Studio nerozpoznal nástroje sestavení základu kódu. Zobrazí se výstup z úlohy sestavení v **výstup** okno a chyby sestavení se zobrazí v **seznam chyb**. Tasks.vs.json sestavení párům souboru úloh nástroje používané vaší codebase sestavení smyčky vnitřní vývoj sady Visual Studio pro vlastní.  

Vlastní sestavovací úlohy mohou být přidány do jednotlivých souborů nebo všechny soubory určitého typu. Například soubory balíčku NuGet lze nakonfigurovat tak, aby měl úlohu "Packages obnovení", nebo všechny zdrojové soubory lze nakonfigurovat tak, aby měl statické analýzy úlohy, jako je například linter pro všechny soubory .js.  

Visual Studio podporuje VSCode `$variable` nahrazení v kořenu tasks.vs.json kromě proměnných prostředí (například `$env.var`) nebo klíče.  

## <a name="specify-build-output"></a>Zadejte sestavení výstupu  
Pokud váš projekt musí být zkompilovány, můžete přidat další značky názvem `output` tasks.vs.json souboru. Zde je příklad.  

`"output": "${workspaceRoot}\\bin\\hellomake.exe"`

Určení umístění výstupu upozorní kde najít výstupu sestavení projektu sady Visual Studio.  

## <a name="tasksvsjson-file-location"></a>Umístění souboru Tasks.vs.JSON  
Ve výchozím nastavení je soubor tasks.vs.json nachází ve skryté složce s názvem `.vs`. Chcete-li zobrazit skryté soubory v sadě Visual Studio, vyberte **zobrazit všechny soubory** tlačítka na panelu nástrojů Průzkumníka řešení.  

![Příkaz úloh libovolný sestavení](./media/VSIDE_Code_Tasks_FileLocation.png)

Soubor tasks.vs.json je skrytý, protože většina uživatelů obecně nechcete použít ke kontrole do správy zdrojového kódu. Ale pokud chcete mít možnost ověřit do správy zdrojového kódu, přetáhněte soubor do kořenového adresáře projektu kde se nebude zobrazovat.  

Ostatní soubory .json mohou být umístěny ve složce neodstraňujte, ale jenom ty, které je možné přesunout jsou tasks.vs.json soubor a soubor launch.vs.json (Pokud je existuje). Soubor launch.vs.json nakonfiguruje ladicího programu sady Visual Studio, zatímco soubor tasks.vs.json nakonfiguruje sestavení v sadě Visual Studio.  

## <a name="see-also"></a>Viz také
[Psaní kódu v editoru kódu a text.](../ide/writing-code-in-the-code-and-text-editor.md)
