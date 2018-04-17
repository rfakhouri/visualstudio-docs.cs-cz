---
title: 'Rychlé zahájení: Analýza kódu pro C/C++ | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- C/C++ code analysis
- code analysis,C/C++
author: mikeblome
ms.author: mblome
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: efba8b220bc078436921c437f0cb382870b3277b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="quickstart-code-analysis-for-cc"></a>Rychlý úvod: Analýza kódu pro C/C++

Pravidelně systémem analýza kódu C nebo C++ kódu, lze vylepšit kvalitu aplikace. To vám může pomoct najít běžné problémy, porušení osvědčených postupů programovací nebo závad, které je obtížné zjistit prostřednictvím testování. Upozornění analýzy kódu se liší od kompilátoru chyby a upozornění, protože analýza kódu hledá vzory konkrétního kódu, které jsou platné, ale stále vytvořit problémy pro vás nebo další uživatelé, kteří používají váš kód.

## <a name="configure-rule-sets-for-a-project"></a>Konfigurace sady pravidel pro projekt

1. V **Průzkumníku řešení**, otevřete místní nabídku pro název projektu a zvolte **vlastnosti**.

2. Následující kroky jsou volitelné:

    1. V **konfigurace** a **platformy** seznamy, zvolte sestavení konfigurace a cílové platformy.

    2. Ve výchozím nastavení analýza kódu sestavu upozornění kód, který je automaticky generován externí nástroje. Chcete-li zobrazit upozornění generovaného kódu, zrušte **potlačit výsledky z generovaného kódu** zaškrtávací políčko.

        > [!NOTE]
        > Tato možnost není chyby analýzy kódu a upozornění z generovaného kódu při potlačit chyby a upozornění se zobrazí ve formulářích a šablony. Můžete zobrazit i udržovat zdrojový kód pro formuláře nebo šablony.

3. Analýza kódu spustit v každém projektu je sestaven pomocí vybrané konfigurace, vyberte **povolit analýzy kódu pro C/C++ v sestavení** zaškrtávací políčko. Vám může také ruční spuštění analýzy kódu otevřením **analyzovat** nabídky a pak vyberete **spuštění analýzy kódu na** *ProjectName*.

4. V **spuštění této sady pravidel** seznamu, proveďte jednu z následujících akcí:

    - Vyberte sadu pravidel, který chcete použít.

    - Zvolte  **\<Procházet... >** zadat existující vlastní pravidlo nastavit, který se nenachází v seznamu.

    - Definování [vlastní sady pravidel](../code-quality/how-to-create-a-custom-rule-set.md).

### <a name="standard-cc-rule-sets"></a>Sady pravidel standardní C/C++

Visual Studio obsahuje dva standardní sadu pravidel pro nativní kód:

|Sada pravidel|Popis|
|--------------|-----------------|
|Microsoft nativní Minimální doporučená pravidla|Této sady pravidel se zaměřuje na nejdůležitější problémy v nativním kódu, včetně potenciální bezpečnostní díry a dojde k chybě aplikace. Toto pravidlo nastavit v žádné sadě vlastní pravidlo, že které vytvoříte pro nativní projekty by měla obsahovat.|
|Microsoft nativní doporučená pravidla|Této sady pravidel obsahuje širokou škálu problémy. Obsahuje všechna pravidla v Microsoft nativní Minimální doporučená pravidla.|

## <a name="run-code-analysis"></a>Spuštění analýzy kódu

Na stránce analýzy kódu na stránkách vlastností projektu můžete nakonfigurovat analýzy kódu pro spuštění pokaždé, když, sestavení projektu. Analýza kódu můžete také spustit ručně.

Spuštění analýzy kódu pro řešení:

- Na **sestavení** nabídce zvolte **spustit analýza kódu v řešení**.

 Ke spuštění analýzy kódu v projektu:

- V Průzkumníku řešení klikněte na název projektu.

- Na **sestavení** nabídce zvolte **spuštění analýzy kódu na** *název projektu*.

 Kompiluje projekt nebo řešení a analýza kódu spustí. Výsledky se zobrazí v seznamu chyb.

## <a name="analyze-and-resolve-code-analysis-warnings"></a>Analýza a tvorba řešení upozornění analýzy kódu

Chcete-li analyzovat konkrétní upozornění, zvolte název upozornění v seznamu chyb. Toto upozornění se rozšíří zobrazíte další informace o problému. Pokud je to možné, analýza kódu zobrazuje čísla řádků a analýzy logiky, která vedla k upozornění. Podrobné informace o upozornění, včetně možná řešení problému zvolte ID upozornění k zobrazení jeho odpovídající online téma nápovědy.

Pokud vyberete upozornění, řádek kódu, který způsobil upozornění zvýrazněn v editoru kódu v sadě Visual Studio.

Po zjištění problému, abyste ho mohli vyřešit ve vašem kódu. Spusťte analýza kódu a ujistěte se, že toto upozornění se již v seznamu chyb a není má vaše oprava vyvolá žádné nové upozornění.

## <a name="suppress-code-analysis-warnings"></a>Potlačení upozornění analýzy kódu

Existují situace, kdy můžete rozhodnout není opravte upozornění analýzy kódu. Můžete se rozhodnout řešení upozornění vyžaduje příliš mnoho Změna kódu ve vztahu k pravděpodobnost, že problém vyvstanou v jakékoli reálného provádění kódu. Nebo možná se domníváte, že není vhodný pro konkrétní kontext analýzy, který se používá v upozornění. Jednotlivé upozornění můžete potlačit tak, aby se nebude zobrazovat v seznamu chyb.

Potlačit upozornění:

1. Pokud není zobrazí podrobné informace, vyberte název upozornění rozbalte ho.

2. Vyberte **akce** odkaz v dolní části upozornění.

3. Zvolte **potlačit zpráva** a potom zvolte **zdroje v**.

 Potlačení zprávu vloží `#pragma warning (disable:` *WarningId* `)` , potlačí upozornění pro řádek kódu.

## <a name="create-work-items-for-code-analysis-warnings"></a>Vytváření pracovních položek pro kód upozornění analýzy

Můžete použít funkce sledování pracovní položky do protokolu chyb z Visual Studia. Chcete-li tuto funkci používat, je nutné se připojit k instanci serveru Team Foundation Server.

**Chcete-li vytvořit pracovní položku pro jeden nebo více upozornění kódu C/C++**

1. V seznamu chyb rozbalte a vyberte upozornění

2. V místní nabídce pro upozornění, vyberte **vytvoření pracovní položky**a potom vyberte typ pracovní položky.

3. Visual Studio vytvoří jeden pracovní položku pro vybrané upozornění a pracovní položky se zobrazí v okně dokumentu rozhraní IDE.

4. Přidat další informace a potom vyberte **uložit pracovní položka**.

## <a name="search-and-filter-code-analysis-results"></a>Hledat a filtr výsledky analýzy kódu

Můžete hledat dlouhými seznamy zprávy upozornění a můžete filtrovat upozornění v řešení vícenásobného projektu.

- **Pro upozornění filtru podle názvu nebo id upozornění**: zadejte do pole hledání klíčové slovo.

- **Pro upozornění filtru podle závažnosti**: ve výchozím kódu analýzy zprávy jsou přiřazeny závažnost **upozornění**. Můžete přiřadit závažnost jednu nebo více zpráv jako **chyba** v vlastní pravidlo. Na **závažnost** sloupec **seznam chyb**, příkaz na šipku rozevíracího seznamu a potom klepněte na ikonu filtru. Zvolte **upozornění** nebo **chyba** k zobrazení pouze zprávy, které jsou přiřazeny příslušné závažnosti. Zvolte **Vybrat vše** zobrazíte všechny zprávy.

## <a name="see-also"></a>Viz také

[Analýza kódu pro C/C++](../code-quality/code-analysis-for-c-cpp-overview.md)