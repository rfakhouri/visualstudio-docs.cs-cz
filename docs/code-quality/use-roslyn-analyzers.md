---
title: Použití a konfiguraci Roslyn analyzátorů v sadě Visual Studio | Microsoft Docs
ms.date: 03/26/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 17758b8cd901a03e2ce4f93fe5dfcfdbe97eadab
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="configure-and-use-roslyn-analyzer-rules"></a>Konfigurovat a používat pravidla analyzátoru Roslyn

Pravidla analyzátoru kompilátoru platformu .NET ("Roslyn"), nebo *diagnostiky*, analýza kódu C# nebo Visual Basic, jak budete zadávat. Každý diagnostiky má výchozí závažnost a potlačení stav, který může ji přepsat pro váš projekt. Tento článek se týká nastavení pravidlo závažnost, použití sad pravidel a potlačení porušení.

## <a name="analyzers-in-solution-explorer"></a>Analyzátory v Průzkumníku řešení

Můžete provést většinu přizpůsobení analyzátor Diagnostika z **Průzkumníku řešení**. Pokud jste [instalaci analyzátorů](../code-quality/install-roslyn-analyzers.md) jako balíčku NuGet, **analyzátorů** uzel se zobrazí v části **odkazy** nebo **závislosti** uzlu v  **Průzkumník řešení**. Pokud rozbalíte **analyzátorů**a potom rozbalte položku sestavení analyzátor, uvidíte všechny diagnostiky v sestavení.

![Uzel analyzátorů v Průzkumníku řešení](media/analyzers-expanded-in-solution-explorer.png)

Můžete zobrazit vlastnosti Diagnostika, včetně jeho popis a výchozí závažnost v **vlastnosti** okno. Chcete-li zobrazit vlastnosti, klikněte pravým tlačítkem na pravidlo a vyberte **vlastnosti**, nebo vyberte pravidlo a potom stiskněte klávesu **Alt**+**Enter**.

![Diagnostické vlastnosti v vlastnosti – okno](media/analyzer-diagnostic-properties.png)

Chcete-li naleznete v online dokumentaci k Diagnostika, klikněte pravým tlačítkem na diagnostiky a vyberte **zobrazit nápovědu**.

Ikonami vedle jednotlivých Diagnostika v rámci **Průzkumníku řešení** odpovídají ikony můžete vidět v sada při otevření v editoru pravidel:

- "i" v kruh označuje [závažnost](#rule-severity) z **informace**
- "!" v trojúhelníku označuje [závažnost](#rule-severity) z **upozornění**
- Určuje symbol "x" v kruh [závažnost](#rule-severity) z **chyba**
- označuje "i" v kolečko na pozadí light stejné barvy [závažnost](#rule-severity) z **Hidden**
- na šipku dolů ve kruh označuje, zda je potlačeno diagnostiky

![Diagnostika ikony v Průzkumníku řešení](media/diagnostics-icons-solution-explorer.png)

## <a name="rule-sets"></a>Sady pravidel

A [sadu pravidel](../code-quality/using-rule-sets-to-group-code-analysis-rules.md) je soubor XML, která ukládá stav závažnosti a potlačení pro jednotlivé diagnostiky. Sady pravidel platí pro jeden projekt a projekt může mít několik sady pravidel. Chcete-li zobrazit aktivní pravidlo nastavené v editoru, klikněte pravým tlačítkem na **analyzátorů** uzlu v **Průzkumníku řešení** a vyberte **otevřete Active pravidlo nastavené**. Pokud je to poprvé připojujete pravidlo nastavit, soubor s názvem  *\<název projektu > Analýza* se přidá do projektu a zobrazí se v **Průzkumníku řešení**.

> [!NOTE]
> Sady pravidel patří analýza statické (binární) kódu a Roslyn pravidla analyzátoru.

Můžete změnit aktivní sada pravidel pro projekt na **analýza kódu** karta Vlastnosti projektu. Vyberte pravidlo nastavené v **spuštění této sady pravidel** rozevíracího seznamu. Můžete také otevřít sadu z pravidel **analýza kódu** stránka vlastností výběrem **otevřete**.

## <a name="rule-severity"></a>Pravidlo závažnosti

Můžete nakonfigurovat závažnost pravidla analyzátoru nebo *diagnostiky*, pokud jste [nainstalovat analyzátory](../code-quality/install-roslyn-analyzers.md) jako balíčku NuGet. Následující tabulka uvádí možnosti závažnost Diagnostics:

|Závažnost|Chování v době sestavení|Chování editoru|
|-|-|-|
|Chyba|Porušení zobrazí jako *chyby* v **seznam chyb** v příkazového řádku sestavení výstup a způsobit sestavení selhání.|Poškozený kód je podtržený červeným vlnovkou a označené podle červený čtvereček posuvníku.|
|Upozornění|Porušení zobrazí jako *upozornění* v **seznam chyb** a v příkazového řádku sestavení výstupu, ale nezpůsobí sestavení selhání.|Poškozený kód je podtržený se zeleným vlnovkou a označena pomocí malé zelená pole na posuvníku.|
|Informace o|Porušení zobrazí jako *zprávy* v **seznam chyb**a vůbec ve výstupu sestavení příkazového řádku.|Poškozený kód je podtržený s šedá vlnovkou a označena pomocí malé šedé pole na posuvníku.|
|Hidden|Non viditelné pro uživatele.|Non viditelné pro uživatele. Diagnostiky se hlásí k modulu diagnostiky IDE, ale.|
|Žádné|Zcela potlačit.|Zcela potlačit.|

Kromě toho můžete "obnovit" závažnost pravidlo nastavením na **výchozí**. Každý diagnostiky má výchozí závažnost, která si můžete prohlédnout ve **vlastnosti** okno.

Následující snímek obrazovky ukazuje tři různé diagnostické porušení v editoru kódu s tři různé závažnosti. Všimněte si, barva vlnovkou, jakož i pole malé posuvníku na pravé straně.

![Chyby, upozornění a informace o porušení v editoru kódu](media/diagnostics-severity-colors.png)

Následující snímek obrazovky ukazuje stejné tři porušení zásad, jak se zobrazují v **seznam chyb**:

![Chyby, upozornění a informace o porušení v seznam chyb](media/diagnostics-severities-in-error-list.png)

Můžete změnit závažnost pravidla z **Průzkumníku řešení**, nebo v  *\<název projektu > Analýza* soubor, který je přidán do řešení po provedení změny závažnost pravidla v  **Průzkumník řešení**.

![Sada pravidel pro soubor v Průzkumníku řešení](media/ruleset-in-solution-explorer.png)

### <a name="to-set-rule-severity-from-solution-explorer"></a>Chcete-li nastavit pravidlo závažnost v Průzkumníku řešení

1. V **Průzkumníku řešení**, rozbalte položku **odkazy** > **analyzátorů** (**závislosti**  >  **Analyzátorů** pro projekty .NET Core).

1. Rozbalte sestavení, které obsahuje pravidlo, které chcete nastavit závažnost pro.

1. Klikněte pravým tlačítkem myši na pravidlo a vyberte **nastavit závažnost nastavit pravidlo**. V rozevírací nabídce vyberte jednu z možností závažnosti.

   Závažnost pro pravidlo je uloženo v souboru sady active pravidla.

### <a name="to-set-rule-severity-in-the-rule-set-file"></a>Chcete-li nastavit pravidlo závažnost v pravidle nastavit soubor

1. Otevřete soubor pravidlo nastavit poklepáním v **Průzkumníku řešení**, vyberete **otevřete Active pravidlo nastavené** v nabídce klikněte pravým tlačítkem **analyzátorů** uzlu, nebo výběrem **Otevřete** na **analýza kódu** stránku vlastností projektu.

1. Vyhledejte pravidlo rozšířením jeho obsahující sestavení.

1. V **akce** sloupce, vyberte hodnotu otevřete rozevírací seznam a vyberte požadované závažnost ze seznamu.

   ![Sada pravidel pro soubor otevřete v editoru](media/ruleset-file-in-editor.png)

## <a name="suppress-violations"></a>Potlačit porušení

Chcete-li potlačit porušení pravidel několika způsoby:

- Chcete-li potlačit všechny aktuální porušení, vyberte **analyzovat** > **spuštění analýzy kódu a potlačit aktivní problémy** v řádku nabídek. To se někdy označuje jako "baselining".

- K potlačení Diagnostika z **Průzkumníku řešení**, nastavte jeho závažnost na **žádné**.

- Chcete-li potlačit Diagnostika z editoru sadu pravidel, zrušte zaškrtnutí políčka vedle jeho názvu nebo nastavte **akce** k **žádné**.

- Chcete-li potlačit Diagnostika z editoru kódu, umístěte kurzor na řádku kódu pomocí porušení a stiskněte klávesu **Ctrl**+**.** Chcete-li otevřít **rychlé akce** nabídky. Vyberte **potlačit CAxxxx** > **ve zdroji** nebo **potlačit CAxxxx** > **v souboru potlačení**.

   ![Potlačit diagnostiky z nabídky rychlé akce](media/suppress-diagnostic-from-editor.png)

- K potlačení Diagnostika z **seznam chyb**, klikněte pravým tlačítkem na chybu, varování nebo zprávu a vyberte **potlačit** > **zdroje v** nebo **Potlačit** > **v souboru potlačení**.

   - Pokud vyberete **zdroje v**, **zobrazení náhledu změn** otevře dialogové okno a zobrazuje náhled jazyka C# [#pragma – upozornění](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning) nebo Visual Basic [#Disable upozornění](/dotnet/visual-basic/language-reference/directives/directives) – direktiva, která je přičtena ke zdrojovému kódu.

      ![Verze Preview přidání #pragma – upozornění v souboru kódu](media/pragma-warning-preview.png)

   - Pokud vyberete **v souboru potlačení**, **zobrazení náhledu změn** otevře dialogové okno a zobrazuje náhled <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atribut, který je přidán do globální suppressions souboru.

      ![Verze Preview přidání do souboru potlačení suppressmessage – atribut](media/preview-changes-in-suppression-file.png)

   V **zobrazení náhledu změn** dialogovém okně, vyberte **použít**.

> [!NOTE]
> V projektu .NET Core přidáte odkaz na projekt, který NuGet analyzátorů, má-li tyto analyzátorů se automaticky přidají do projektu závislé příliš. Pokud chcete zakázat toto chování, pokud je závislý projekt projektu testů jednotek, například označit balíček NuGet jako soukromý v *.csproj* nebo *.vbproj* odkazované projektu:
>
> ```xml
> <PackageReference Include="Microsoft.CodeAnalysis.FxCopAnalyzers" Version="2.6.0" PrivateAssets="all" />
> ```

## <a name="see-also"></a>Viz také

- [Přehled Roslyn analyzátorů v sadě Visual Studio](../code-quality/roslyn-analyzers-overview.md)
- [Odeslání Roslyn chyby analyzátoru](https://github.com/dotnet/roslyn-analyzers/issues)
- [Použití sady pravidel](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [Potlačení upozornění analýzy kódu](../code-quality/in-source-suppression-overview.md)