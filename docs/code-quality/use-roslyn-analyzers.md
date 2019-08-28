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
ms.openlocfilehash: 5c5af5c98be92e52c356e0f20eaf437f66878690
ms.sourcegitcommit: 8a699df154464387f327691dce507d7c3d0e2aab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/27/2019
ms.locfileid: "70060441"
---
# <a name="use-code-analyzers"></a>Použití analyzátorů kódu

Analyzátory kódu .NET Compiler Platform ("Roslyn") analyzují C# kód nebo Visual Basic při psaní. Každé *diagnostice* nebo pravidlo má výchozí závažnost a stav potlačení, který může být pro váš projekt přepsán. Tento článek popisuje nastavení závažnosti pravidla, použití sad pravidel a potlačení porušení.

## <a name="analyzers-in-solution-explorer"></a>Analyzátory v Průzkumník řešení

Z **Průzkumník řešení**můžete provádět většinu úprav diagnostiky analyzátoru. Pokud [nainstalujete analyzátory](../code-quality/install-roslyn-analyzers.md) jako balíček NuGet, pod uzlem **odkazy** nebo **závislosti** v **Průzkumník řešení**se zobrazí uzel **analyzátory** . Pokud rozbalíte **analyzátory**a pak rozbalíte jedno ze sestavení analyzátoru, uvidíte všechny diagnostiky v sestavení.

![Uzel analyzátorů v Průzkumník řešení](media/analyzers-expanded-in-solution-explorer.png)

V okně **vlastnosti** můžete zobrazit vlastnosti diagnostiky, včetně jeho popisu a výchozí závažnosti. Chcete-li zobrazit vlastnosti, klikněte pravým tlačítkem na pravidlo a vyberte **vlastnosti**, nebo vyberte pravidlo a stiskněte klávesu **ALT**+**ENTER**.

![Diagnostické vlastnosti v okno Vlastnosti](media/analyzer-diagnostic-properties.png)

Pokud chcete zobrazit online dokumentaci pro diagnostiku, klikněte pravým tlačítkem na diagnostiku a vyberte **Zobrazit nápovědu**.

Ikony vedle každé diagnostiky v **Průzkumník řešení** odpovídají ikonám, které vidíte v sadě pravidel při jejich otevírání v editoru:

- znak "i" v kruhu indikuje [závažnost](#rule-severity) **informací**
- znak "!" v trojúhelníku označuje [závažnost](#rule-severity) **Upozornění**
- znak "x" v kruhu indikuje [závažnost](#rule-severity) **chyby**
- znak "i" v kruhu na pozadí s světlou barvou označuje [závažnost](#rule-severity) **skrytého**
- Šipka dolů v kruhu indikuje, že je diagnostika potlačena.

![Ikony diagnostiky v Průzkumník řešení](media/diagnostics-icons-solution-explorer.png)

## <a name="rule-sets"></a>Sady pravidel

[Sada pravidel](../code-quality/using-rule-sets-to-group-code-analysis-rules.md) je soubor XML, který ukládá závažnost a stav potlačení pro jednotlivé diagnostiky.

> [!NOTE]
> Sady pravidel mohou zahrnovat pravidla z analyzátoru starší verze i analyzátory kódu.

Chcete-li upravit aktivní sadu pravidel v editoru sad pravidel, klikněte pravým tlačítkem myši na uzel**analyzátory** **odkazů** > v **Průzkumník řešení** a vyberte možnost **Otevřít aktivní sadu pravidel**. Pokud se jedná o první úpravu sady pravidel, sada Visual Studio vytvoří kopii výchozího souboru sady pravidel a pojmenuje jej  *\<ProjectName >. ruleset*a přidá ho do projektu. Tato vlastní sada pravidel se také stal aktivní sadou pravidel pro váš projekt.

Chcete-li změnit aktivní sadu pravidel pro projekt, přejděte na kartu **Analýza kódu** vlastností projektu. Vyberte sadu pravidel ze seznamu v části **Spustit tuto sadu pravidel**. Chcete-li otevřít sadu pravidel, vyberte možnost **otevřít**.

> [!NOTE]
> Projekty .NET Core a .NET Standard nepodporují příkazy nabídky pro sady pravidel v **Průzkumník řešení**, například **otevřete aktivní sadu pravidel**. Chcete-li určit nevýchozí sadu pravidel pro projekt .NET Core nebo .NET Standard, přidejte do souboru projektu ručně [vlastnost **CodeAnalysisRuleSet** ](using-rule-sets-to-group-code-analysis-rules.md#specify-a-rule-set-for-a-project) . Pravidla můžete konfigurovat v rámci sady pravidel v uživatelském rozhraní editoru sad pravidel sady Visual Studio.

## <a name="rule-severity"></a>Závažnost pravidla

Pokud nainstalujete analyzátory jako balíček NuGet, můžete nakonfigurovat závažnost pravidel analyzátoru [](../code-quality/install-roslyn-analyzers.md) nebo *diagnostiky*. V následující tabulce jsou uvedeny možnosti závažnosti pro diagnostiku:


::: moniker range="vs-2019"
|severity|Chování při sestavení|Chování editoru|
|-|-|-|
|Chyba|Porušení se zobrazují jako *chyby* v **Seznam chyb** a ve výstupu sestavení příkazového řádku a způsobují selhání sestavení.|Poškozený kód je podtržen červenou vlnovkou a označený malým červeným polem na posuvníku.|
|Upozornění|Porušení se zobrazí jako *Upozornění* v **Seznam chyb** a ve výstupu sestavení příkazového řádku, ale nezpůsobí selhání sestavení.|Poškozený kód je podtržený zelenou vlnovkou a označený malým zeleným polem na posuvníku.|
|Doporučení|Porušení se zobrazí jako *zprávy* v **Seznam chyb**, a ne vůbec ve výstupu sestavení příkazového řádku.|Poškozený kód je podtržený šedou vlnovkou a označený malým šedým polem na posuvníku.|
|Tich|Uživatel není viditelný.|Uživatel není viditelný. Diagnostika se oznamuje diagnostickému modulu IDE, ale.|
|Žádné|Zcela potlačeno.|Zcela potlačeno.|
::: moniker-end

::: moniker range="< vs-2019"
|severity|Chování při sestavení|Chování editoru|
|-|-|-|
|Chyba|Porušení se zobrazují jako *chyby* v **Seznam chyb** a ve výstupu sestavení příkazového řádku a způsobují selhání sestavení.|Poškozený kód je podtržen červenou vlnovkou a označený malým červeným polem na posuvníku.|
|Upozornění|Porušení se zobrazí jako *Upozornění* v **Seznam chyb** a ve výstupu sestavení příkazového řádku, ale nezpůsobí selhání sestavení.|Poškozený kód je podtržený zelenou vlnovkou a označený malým zeleným polem na posuvníku.|
|Informace o|Porušení se zobrazí jako *zprávy* v **Seznam chyb**, a ne vůbec ve výstupu sestavení příkazového řádku.|Poškozený kód je podtržený šedou vlnovkou a označený malým šedým polem na posuvníku.|
|Hidden|Uživatel není viditelný.|Uživatel není viditelný. Diagnostika se oznamuje diagnostickému modulu IDE, ale.|
|Žádné|Zcela potlačeno.|Zcela potlačeno.|
::: moniker-end

Můžete také resetovat závažnost pravidla tím, že ji nastavíte na **výchozí**. Každé diagnostice má výchozí závažnost, kterou lze zobrazit v okně **vlastnosti** .

Následující snímek obrazovky ukazuje tři různá narušení diagnostiky v editoru kódu se třemi různými závažnostmi. Všimněte si barvy vlnovky a také malého pole posuvníku na pravé straně.

![Chyba, upozornění a porušení informací v editoru kódu](media/diagnostics-severity-colors.png)

Následující snímek obrazovky ukazuje stejná tři porušení zásad, která se zobrazují v **Seznam chyb**:

![Došlo k chybě, varování a porušení informací v Seznam chyb](media/diagnostics-severities-in-error-list.png)

Závažnost pravidla můžete změnit z **Průzkumník řešení**nebo v rámci  *\<souboru ProjectName >. ruleset* , který se přidá do řešení po změně závažnosti pravidla v **Průzkumník řešení**.

![Soubor sady pravidel v Průzkumník řešení](media/ruleset-in-solution-explorer.png)

### <a name="set-rule-severity-from-solution-explorer"></a>Nastavit závažnost pravidla z Průzkumník řešení

1. V **Průzkumník řešení**rozbalte položku > **analyzátory** odkazů ( > **analyzátory** závislostí pro projekty .NET Core).

1. Rozbalte sestavení, které obsahuje pravidlo, pro které chcete nastavit závažnost.

1. Klikněte pravým tlačítkem na pravidlo a vyberte **nastavit závažnost sady pravidel**. V rozevírací nabídce vyberte jednu z možností závažnosti.

   Závažnost pravidla se uloží do souboru aktivní sady pravidel.

### <a name="set-rule-severity-in-the-rule-set-file"></a>Nastavte závažnost pravidla v souboru sady pravidel.

1. Otevřete soubor [sady pravidel](analyzer-rule-sets.md) tak, že na **Průzkumník řešení**něj dvakrát kliknete a vyberete **Otevřít aktivní sadu pravidel** v nabídce na pravé straně uzlu **analyzátory** , nebo výběrem možnosti **otevřít** na stránce vlastností **Analýza kódu** pro projekt.

1. Přejděte k pravidlu tak, že rozbalíte jeho obsahující sestavení.

1. Ve sloupci **Akce** výběrem hodnoty otevřete rozevírací seznam a v seznamu vyberte požadovanou závažnost.

   ![Soubor sady pravidel je otevřen v editoru.](media/ruleset-file-in-editor.png)

## <a name="suppress-violations"></a>Potlačit porušení

Existuje několik způsobů, jak potlačit porušení pravidel:

- Z nabídky **analyzovat**

  Vyberte možnost **analyzovat** > **Spustit analýzu kódu a potlačením aktivních problémů** na řádku nabídek potlačíte všechna aktuální porušení. Někdy se označuje jako "monitorování standardních hodnot".

- Z **Průzkumník řešení**

  Pokud chcete potlačit porušení v **Průzkumník řešení**, nastavte závažnost pravidla na None ( **žádné**).

- Z **editoru sad pravidel**

  Chcete-li potlačit porušení z editoru sady pravidel, zrušte zaškrtnutí políčka vedle jeho názvu nebo nastavte **akci** na **možnost žádné**.

- Z **editoru kódu**

  Chcete-li potlačit porušení z editoru kódu, umístěte kurzor na řádek kódu s porušením a stiskněte klávesu **CTRL**+ **.** Otevřete nabídku **rychlé akce** . Vyberte možnost **potlačit CAXXXX** > **ve zdroji nebo v souboru potlačení**.

  ![Potlačit diagnostiku z nabídky rychlé akce](media/suppress-diagnostic-from-editor.png)

- Z **Seznam chyb**

  Můžete potlačit jednu nebo více diagnostik z **Seznam chyb** tím, že vyberete ty, které chcete potlačit, a potom klikněte pravým tlačítkemmyši a vyberete možnost potlačit > **ve zdroji nebo v souboru potlačení**.

  - Pokud potlačíte **zdroj**, otevře se dialogové okno **Náhled změn** , ve kterém se zobrazí C# náhled [#pragma varování](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning) nebo Visual Basic #Disable direktivu [Upozornění](/dotnet/visual-basic/language-reference/directives/directives) , která je přidána do zdrojového kódu.

    ![Náhled Přidání upozornění #pragma v souboru kódu](media/pragma-warning-preview.png)

  - Pokud vyberete možnost **v souboru potlačení**, otevře se dialogové okno **Náhled změn** a zobrazí <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> náhled atributu, který je přidán do globálního souboru potlačení.

    ![Náhled přidání atributu SuppressMessage do souboru potlačení](media/preview-changes-in-suppression-file.png)

  V dialogovém okně **Náhled změn** vyberte **použít**.

  > [!NOTE]
  > Pokud nevidíte možnost nabídky potlačit v **Průzkumník řešení**, porušení pravděpodobně přijde z buildu a ne za živou analýzu. **Seznam chyb** zobrazuje narušení diagnostiky nebo pravidla, a to od živých analýz kódu i sestavení. Vzhledem k tomu, že diagnostika sestavení může být zastaralá, například pokud jste upravili kód pro opravu porušení, ale ještě nebyla znovu sestavena, nemůžete tuto diagnostiku z **Seznam chyb**potlačit. Diagnostika z živých analýz nebo IntelliSense je vždy aktuální s aktuálními zdroji a lze ji potlačit z **Seznam chyb**. Pokud chcete z výběru vyloučit diagnostiku *sestavení* , přepněte filtr zdroje **Seznam chyb** z **Build + IntelliSense** na **pouze IntelliSense**. Pak vyberte diagnostiku, kterou chcete potlačit, a pokračujte podle postupu popsaného výše.
  >
  > ![Zdrojový filtr Seznam chyb v aplikaci Visual Studio](media/error-list-filter.png)

## <a name="command-line-usage"></a>Použití příkazového řádku

Při sestavování projektu na příkazovém řádku se porušení pravidla zobrazí ve výstupu sestavení, pokud jsou splněny následující podmínky:

- Analyzátory jsou nainstalovány jako balíček NuGet a nikoli jako rozšíření VSIX.

- V kódu projektu je porušeno jedno nebo více pravidel.

- [Závažnost](#rule-severity) narušeného pravidla je nastavena na možnost **Upozornění**, v takovém případě porušení nezpůsobí selhání sestavení nebo **Chyba**. v takovém případě porušení způsobí selhání sestavení.

Podrobnosti výstupu sestavení neovlivňují, zda jsou zobrazena porušení pravidel. I při **tiché** podrobnostech se ve výstupu sestavení zobrazí porušení pravidel.

> [!TIP]
> Pokud jste zvyklí spouštět starší verzi analýzy z příkazového řádku, a to buď pomocí *FxCopCmd. exe* , nebo pomocí nástroje MSBuild s příznakem **RunCodeAnalysis** , zde je postup, jak to udělat pomocí analyzátorů kódu.

Chcete-li zobrazit narušení analyzátoru na příkazovém řádku při sestavování projektu pomocí nástroje MSBuild, spusťte příkaz podobný tomuto:

```cmd
msbuild myproject.csproj /target:rebuild /verbosity:minimal
```

Následující obrázek ukazuje výstup sestavení příkazového řádku z sestavení projektu, který obsahuje porušení pravidla analyzátoru:

![Výstup nástroje MSBuild s porušením pravidla](media/command-line-build-analyzers.png)

## <a name="dependent-projects"></a>Závislé projekty

Pokud v projektu .NET Core přidáte odkaz na projekt, který obsahuje analyzátory NuGet, tyto analyzátory jsou také automaticky přidány do závislého projektu. Chcete-li toto chování zakázat, například pokud je závislý projekt projekt testování částí, označte balíček NuGet jako soukromý v souboru *. csproj* nebo *. vbproj* odkazovaného projektu nastavením atributu **PrivateAssets** :

```xml
<PackageReference Include="Microsoft.CodeAnalysis.FxCopAnalyzers" Version="2.9.0" PrivateAssets="all" />
```

## <a name="see-also"></a>Viz také:

- [Přehled analyzátorů kódu v aplikaci Visual Studio](../code-quality/roslyn-analyzers-overview.md)
- [Odeslat chybu analyzátoru kódu](https://github.com/dotnet/roslyn-analyzers/issues)
- [Použití sad pravidel](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [Potlačit upozornění analýzy kódu](../code-quality/in-source-suppression-overview.md)
