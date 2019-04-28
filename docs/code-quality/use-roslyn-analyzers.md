---
title: Závažnost pravidla analyzátoru a potlačení
ms.date: 03/26/2019
ms.topic: conceptual
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 56637ee7826b944d739e170faf22ae354abd8adc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62821306"
---
# <a name="use-roslyn-analyzers"></a>Používání analyzátorů Roslyn

Pravidla analyzátoru .NET compiler Platform ("Roslyn"), nebo *diagnostiky*, analýza kódu C# nebo Visual Basic během psaní. Každý diagnostiky má výchozí závažnost a potlačení stavu, ve kterém můžete přepsat pro váš projekt. Tento článek se týká nastavení závažnost pravidla, použití sad pravidel a potlačení porušení.

## <a name="analyzers-in-solution-explorer"></a>Analyzátory v Průzkumníku řešení

Můžete provést mnoho přizpůsobení analyzátor Diagnostika z **Průzkumníka řešení**. Pokud jste [instalace analyzátorů](../code-quality/install-roslyn-analyzers.md) jako balíček NuGet, **analyzátory** uzel se zobrazí v části **odkazy** nebo **závislosti** uzel v  **Průzkumník řešení**. Pokud rozbalíte **analyzátory**a potom rozbalte některou sestavení analyzátoru, zobrazí se všechny diagnostiky v sestavení.

![Analyzátory uzlu v Průzkumníkovi řešení](media/analyzers-expanded-in-solution-explorer.png)

Můžete zobrazit vlastnosti diagnostiky, včetně jeho popis a výchozí závažnost, **vlastnosti** okno. Chcete-li zobrazit vlastnosti, klikněte pravým tlačítkem na pravidlo a vyberte **vlastnosti**, nebo vyberte pravidlo a potom stiskněte klávesu **Alt**+**Enter**.

![Diagnostické vlastnosti v okně Vlastnosti](media/analyzer-diagnostic-properties.png)

Chcete-li najdete v online dokumentaci pro diagnostiku, klikněte pravým tlačítkem na diagnostiky a vyberte **zobrazit nápovědu**.

Ikony vedle každého Diagnostika v rámci **Průzkumníka řešení** odpovídají ikony se zobrazí v pravidle nastavit po otevření v editoru:

- Označuje, "i" v kruhu [závažnost](#rule-severity) z **informace**
- "!" v trojúhelníku označuje [závažnost](#rule-severity) z **upozornění**
- Označuje, "x" v kruhu [závažnost](#rule-severity) z **chyba**
- Označuje, "i" v kruhu na pozadí světlé [závažnost](#rule-severity) z **skryté**
- na šipku dolů v kruhu Určuje, že je potlačeno diagnostiky

![Diagnostika ikony v Průzkumníku řešení](media/diagnostics-icons-solution-explorer.png)

## <a name="rule-sets"></a>Sady pravidel

A [sada pravidel, která](../code-quality/using-rule-sets-to-group-code-analysis-rules.md) je soubor XML, který ukládá stav závažnosti a potlačení pro jednotlivé diagnostiky.

> [!NOTE]
> Sady pravidel můžete zahrnout pravidla z analýza statického kódu (binární) a analyzátory Roslyn.

Upravit aktivní sadu pravidel v editoru sad pravidel, klikněte pravým tlačítkem na **odkazy** > **analyzátory** uzel v **Průzkumníka řešení** a vyberte **Otevřít aktivní sadu pravidel**. Pokud je to poprvé, při úpravě sady pravidel, Visual Studio vytvoří kopii výchozí pravidlo soubor sady, pojmenuje ho  *\<projectname > Analýza*a přidá jej do projektu. Tohoto vlastního pravidla i nastavení se změní aktivní sadu pravidel pro váš projekt.

Chcete-li změnit aktivní sadu pravidel pro projekt, přejděte na **analýzy kódu** karta Vlastnosti projektu. Vyberte sadu ze seznamu pravidel **spustit tuto sadu pravidel**. Chcete-li otevřít sadu pravidel, vyberte **otevřete**.

> [!NOTE]
> Projekty .NET core a .NET Standard nepodporují příkazy nabídky pro sady pravidel **Průzkumníka řešení**, například **otevřít aktivní sadu pravidel**. Chcete-li určit jiné než výchozí sadu pravidel pro projekt .NET Core nebo .NET Standard ručně [přidat **CodeAnalysisRuleSet** vlastnosti do souboru projektu](using-rule-sets-to-group-code-analysis-rules.md#specify-a-rule-set-for-a-project). Můžete nakonfigurovat pravidla v rámci sadu pravidel v sadě Visual Studio, sada pravidel uživatelské rozhraní editoru.

## <a name="rule-severity"></a>Závažnost pravidla

Můžete nakonfigurovat závažnost pravidla analyzátoru nebo *diagnostiky*, pokud jste [instalace analyzátorů](../code-quality/install-roslyn-analyzers.md) jako balíček NuGet. Následující tabulka uvádí možnosti závažnosti pro diagnostiku:

|Severity|Chování sestavení|Chování editoru|
|-|-|-|
|Chyba|Narušení se zobrazují jako *chyby* v **seznam chyb** a do příkazového řádku výstup sestavení a sestavení selže.|Poškozený kód je podtržený s červenou vlnovkou a označené jako malé červeným rámečkem posuvníku.|
|Upozornění|Narušení se zobrazují jako *upozornění* v **seznam chyb** do příkazového řádku výstup sestavení, ale nezpůsobí sestavení selhala.|Poškozený kód je podtržený s zelenou vlnovkou a označené pomocí malé zeleného pole do oblasti posuvníku.|
|Informace o|Narušení se zobrazují jako *zprávy* v **seznam chyb**a vůbec ne ve výstupu sestavení z příkazového řádku.|Poškozený kód je podtržený s šedá vlnovkou a označené pomocí malé šedé pole do oblasti posuvníku.|
|Hidden|Non viditelné pro uživatele.|Non viditelné pro uživatele. Diagnostiky se hlásí k modulu diagnostiky integrovaného vývojového prostředí, ale.|
|Žádné|Zcela potlačit.|Zcela potlačit.|

Kromě toho můžete "obnovit" závažnost pravidla nastavením na **výchozí**. Každý diagnostiky má výchozí závažnost, která si můžete prohlédnout ve **vlastnosti** okna.

Následující snímek obrazovky ukazuje tři různé diagnostické narušení v editoru kódu, s třemi jinou závažností. Všimněte si, že barvu podtržení, stejně jako malé pole do oblasti posuvníku na pravé straně.

![Chyba, upozornění a informace o narušení v editoru kódu](media/diagnostics-severity-colors.png)

Následující snímek obrazovky ukazuje stejný tři porušení zásad, jak se objeví v **seznam chyb**:

![Chyba, upozornění a informace o narušení v seznamu chyb](media/diagnostics-severities-in-error-list.png)

Můžete změnit závažnost pravidla z **Průzkumníka řešení**, nebo v rámci  *\<projectname > Analýza* soubor, který je přidán do řešení, když změníte závažnost pravidla v  **Průzkumník řešení**.

![Soubor sady pravidel v Průzkumníku řešení](media/ruleset-in-solution-explorer.png)

### <a name="set-rule-severity-from-solution-explorer"></a>Nastavit závažnost pravidla z Průzkumníka řešení

1. V **Průzkumníka řešení**, rozbalte **odkazy** > **analyzátory** (**závislosti**  >  **Analyzátory** pro projekty .NET Core).

1. Rozbalte položku, která obsahuje pravidlo, které chcete nastavit závažnost pro sestavení.

1. Klikněte pravým tlačítkem na pravidlo a vyberte **nastavit závažnost pravidla nastavit**. V rozevírací nabídce vyberte jednu z možností závažnosti.

   Závažnost pravidla je uložen v souboru sady pravidel aktivní.

### <a name="set-rule-severity-in-the-rule-set-file"></a>Nastavit závažnost pravidla v souboru sady pravidel

1. Otevřít [sada pravidel, která](analyzer-rule-sets.md) souboru poklepáním v **Průzkumníku řešení**, kde vyberou **otevřít aktivní sadu pravidel** v nabídce klepněte pravým tlačítkem myši **analyzátory** uzlu, nebo výběrem **otevřít** na **analýzy kódu** stránku vlastností pro projekt.

1. Vyhledejte pravidlo tak, že rozbalíte její obsahující sestavení.

1. V **akce** sloupce, vyberte hodnotu, otevřete rozevírací seznam a vyberte požadovaný závažnost ze seznamu.

   ![Soubor sady pravidel, které jsou otevřeny v editoru](media/ruleset-file-in-editor.png)

## <a name="suppress-violations"></a>Potlačit porušení

Potlačit porušení pravidel několika způsoby:

- Z **analyzovat** nabídky

   Vyberte **analyzovat** > **spustit analýzu kódu a potlačit aktivních problémů** na panelu nabídek potlačí všechna aktuální porušení pravidel. To se někdy označuje jako "monitorování standardních hodnot".

- Z **Průzkumníka řešení**

   Potlačit narušení v **Průzkumníka řešení**, nastavit závažnost pravidla **žádný**.

- Z **s editorem sad pravidel**

   Chcete-li potlačit porušení z editoru sad pravidel, zrušte zaškrtnutí políčka vedle jeho názvu nebo nastavte **akce** k **žádný**.

- Z **editoru kódu**

   Potlačit porušení z editoru kódu, umístěte kurzor na řádek kódu s porušení a stiskněte klávesu **Ctrl**+**.** Chcete-li otevřít **rychlé akce** nabídky. Vyberte **potlačit CAXXXX** > **ve zdroji nebo v souboru potlačení**.

   ![Potlačit diagnostiku z nabídky rychlé akce](media/suppress-diagnostic-from-editor.png)

- Z **seznam chyb**

   Můžete potlačit diagnostiku pro jeden nebo více z **seznam chyb** výběrem ty, které chcete potlačit, a klikněte pravým tlačítkem myši a vyberete **potlačit** > **Source/In v Souboru potlačení**.

   - Pokud jste potlačit **zdroje v**, **náhled změn** dialogové okno se otevře a zobrazí náhled C# [varování #pragma](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning) nebo Visual Basic [#Disable upozornění](/dotnet/visual-basic/language-reference/directives/directives) – direktiva, která je přidána ke zdrojovému kódu.

      ![Přidání upozornění #pragma v souboru kódu ve verzi Preview](media/pragma-warning-preview.png)

   - Pokud vyberete **v souboru potlačení**, **náhled změn** dialogové okno se otevře a zobrazí náhled <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atribut, který se přidá do soubor globálního potlačení.

      ![Přidání atributu SuppressMessage do souboru potlačení ve verzi Preview](media/preview-changes-in-suppression-file.png)

   V **náhled změn** dialogového okna, vyberte **použít**.

   > [!NOTE]
   > Pokud se nezobrazí **potlačit** nabídky v **Průzkumníka řešení**, porušení pravděpodobně pochází z sestavení a ne za analýzu. **Seznam chyb** zobrazí diagnostiky nebo pravidlo porušení z obou živá analýza kódu a sestavení. Protože Diagnostika sestavení může být zastaralá, například pokud jste upravili kódu, chcete-li vyřešit porušení zásad, ale nebyly znovu sestavit, nelze potlačit tato Diagnostika z **seznam chyb**. Diagnostika živých analýzy nebo technologie IntelliSense, jsou vždy aktuální s aktuálním zdroji a lze potlačit z **seznam chyb**. Vyloučit *sestavení* Diagnostika z výběru, přepínat **seznam chyb** zdrojový filtr ze sloupce **sestavení + IntelliSense** k **pouze technologie Intellisense**. Vyberte diagnostiky, které chcete potlačit a pokračovat, jak je popsáno výše.
   >
   > ![Filtr zdroje seznam chyb v sadě Visual Studio](media/error-list-filter.png)

## <a name="command-line-usage"></a>Použití příkazového řádku

Při sestavování projektu na příkazovém řádku se porušení pravidel se zobrazí ve výstupu sestavení. Pokud jsou splněny následující podmínky:

- Analyzátory jsou nainstalovány jako balíček Nuget a ne jako rozšíření VSIX.

- Jeden nebo více pravidel se poruší, v projektu kódu.

- [Závažnost](#rule-severity) porušená pravidla je nastaven na hodnotu **upozornění**, v takovém případě narušení nezpůsobí, aby sestavení selhalo, nebo **chyba**, v takovém případě narušení způsobit, že sestavení selže.

Podrobnost výstupu sestavení nemá vliv, zda jsou zobrazeny porušení pravidel. I přes **quiet** podrobností, porušení pravidel se zobrazí ve výstupu sestavení.

> [!TIP]
> Pokud jste zvyklí na spuštění z příkazového řádku, buď pomocí statické analýzy kódu *FxCopCmd.exe* nebo prostřednictvím msbuild s parametrem / **RunCodeAnalysis** příznak, tady je postup, který s analyzátory Roslyn.

Analyzátor narušení zobrazíte na příkazovém řádku při vytváření projektu pomocí nástroje msbuild, spusťte příkaz takto:

```cmd
msbuild myproject.csproj /target:rebuild /verbosity:minimal
```

Následující obrázek ukazuje sestavení z příkazového řádku výstup z operace sestavení projektu, který obsahuje porušení pravidla analyzátoru:

![Výstup nástroje MSBuild s porušení pravidla](media/command-line-build-analyzers.png)

## <a name="dependent-projects"></a>Závislých projektů

V projektu .NET Core Pokud přidáte odkaz na projekt, který má NuGet analyzátory těchto Analyzátory se automaticky přidají do závislý projekt příliš. Chcete-li zakázat toto chování, například pokud závislý projekt je projekt testování částí, označte balíček NuGet jako v privátní *.csproj* nebo *.vbproj* soubor Odkazovaný projekt tak, že nastavíte **PrivateAssets** atribut:

```xml
<PackageReference Include="Microsoft.CodeAnalysis.FxCopAnalyzers" Version="2.9.0" PrivateAssets="all" />
```

## <a name="see-also"></a>Viz také:

- [Přehled analyzátory Roslyn v sadě Visual Studio](../code-quality/roslyn-analyzers-overview.md)
- [Odeslání chyby analyzátoru Roslyn](https://github.com/dotnet/roslyn-analyzers/issues)
- [Použití sad pravidel](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [Potlačení upozornění analýzy kódu](../code-quality/in-source-suppression-overview.md)