---
title: Soubor vnoření pravidla pro Průzkumníka řešení
ms.date: 05/25/2018
ms.topic: conceptual
helpviewer_keywords:
- file nesting
- Solution Explorer, file nesting
author: angelosp
ms.author: angelpe
manager: jillfra
ms.openlocfilehash: a36ca2535785f72756ad66a69c2ebe4d7d5a373b
ms.sourcegitcommit: 32144a09ed46e7223ef7dcab647a9f73afa2dd55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/05/2019
ms.locfileid: "67587029"
---
# <a name="file-nesting-in-solution-explorer"></a>Vnořování souborů v Průzkumníku řešení

**Průzkumník řešení** vnoří souvisejících souborů a uspořádat je a je jednodušeji najít. Například pokud do projektu přidáte formulář Windows Forms, soubor kódu pro formulář je vnořená dole formulář v nástrojích pro **Průzkumníka řešení**. V projektech ASP.NET Core vnořování souborů děláte o krok dál. Můžete si vybrat přednastavení vnoření souborů **vypnout**, **výchozí**, a **webové**. Můžete také [přizpůsobit, jak jsou vnořené soubory](#customize-file-nesting) nebo [vytvořit nastavení specifická pro řešení a projektu](#create-project-specific-settings).

> [!NOTE]
> Tato funkce je momentálně podporována pouze pro projekty ASP.NET Core.

## <a name="file-nesting-options"></a>Vnoření možnosti souboru

![Tlačítko pro zapnutí souboru vnoření zapnuto/vypnuto](media/filenesting_onoff.png)

Dostupné možnosti pro vnořování souborů neupravené jsou:

* **Off**: Tato možnost poskytuje seznam bez stromové struktury souborů bez jakékoli vnoření.

* **Výchozí**: Tato možnost vám poskytne výchozí soubor vnoření chování v **Průzkumníka řešení**. Pokud neexistuje žádná nastavení pro daný projekt typu, jsou vnořené žádné soubory v projektu. Pokud nastavení existuje, například pro webový projekt, použije se vnoření.

* **Web**: Tato možnost se vztahuje **webové** souboru vnoření chování do všech projektů v aktuálním řešení. Má mnoho pravidel a doporučujeme vám ji rezervovat a Řekněte nám, co si myslíte. Na následujícím snímku obrazovky najdete pár příkladů vnoření chování souboru, který dostanete, když je tato možnost:

   ![Vnořování souborů v Průzkumníku řešení](media/filenesting.png)

## <a name="customize-file-nesting"></a>Vlastní nastavení vnořování souborů

Pokud se vám získáte out-of-the-box, můžete vytvořit vlastní, vlastní soubor nastavení, které dáte pokyn, aby vnořování **Průzkumníka řešení** postupy vnořené soubory. Můžete přidat tolik vlastního souboru vnoření nastavení, jak se vám líbí a můžete přepínat mezi nimi podle potřeby. Chcete-li vytvořit nové vlastní nastavení, můžete začít s prázdný soubor nebo můžete použít **webové** nastavení jako výchozí bod:

![Přidání vlastního souboru vnoření pravidel](media/filenesting_addcustom.png)

Doporučujeme použít **webové** nastavení jako vaše počáteční bod vzhledem k tomu je snazší pracovat s něco, která již funkce. Pokud používáte **webové** nastavení jako výchozí bod, *. filenesting.json* souboru vypadá podobně jako následující soubor:

![Použít existující soubor jako základ pro vlastní nastavení vnořování pravidla](media/filenesting_editcustom.png)

Zaměřme se na uzlu **dependentFileProviders** a jeho podřízených uzlů. Každý podřízený uzel je typ pravidla, pomocí sady Visual Studio můžete vnořit soubory. Například **mají stejný název souboru, ale s jinou příponou** je jeden typ pravidla. Dostupná pravidla jsou:

* **extensionToExtension**: Pomocí tohoto typu pravidla můžete vnořit *file.js* pod *file.ts*

* **fileSuffixToExtension**: Pomocí tohoto typu pravidla můžete vnořit *souboru vsdoc.js* pod *file.js*

* **addedExtension**: Pomocí tohoto typu pravidla můžete vnořit *file.html.css* pod *file.html*

* **pathSegment**: Pomocí tohoto typu pravidla můžete vnořit *jquery.min.js* pod *jquery.js*

* **allExtensions**: Pomocí tohoto typu pravidla můžete vnořit *souboru.* * v části *file.js*

* **fileToFile**: Pomocí tohoto typu pravidla můžete vnořit *bower.json* pod *.bowerrc*

### <a name="the-extensiontoextension-provider"></a>Poskytovatel extensionToExtension

Tento zprostředkovatel umožňuje definovat pravidla vnoření souborů pomocí konkrétní přípony souborů. Vezměte v úvahu v následujícím příkladu:

![Příklad pravidla extentionToExtension](media/filenesting_extensiontoextension.png) ![Příklad efekt extentionToExtension](media/filenesting_extensiontoextension_effect.png)

* *Cart.js* je vnořený *cart.ts* kvůli první **extensionToExtension** pravidlo

* *Cart.js* nebyl vnořen v rámci *cart.tsx* protože **.ts** byla zaslána před **.tsx** v pravidlech, a může existovat pouze jeden nadřazený prvek

* *Light.CSS* je vnořený *light.sass* kvůli druhý **extensionToExtension** pravidlo

* *Home.HTML* je vnořený *home.md* kvůli třetí **extensionToExtension** pravidlo

### <a name="the-filesuffixtoextension-provider"></a>Poskytovatel fileSuffixToExtension

Tento zprostředkovatel funguje stejně jako **extensionToExtension** zprostředkovatele s z jediný rozdíl je, který toto pravidlo zjistí příponu souboru, ne jenom rozšíření. Vezměte v úvahu v následujícím příkladu:

![Příklad pravidla fileSuffixToExtension](media/filenesting_filesuffixtoextension.png) ![Příklad efekt fileSuffixToExtension](media/filenesting_filesuffixtoextension_effect.png)

* *portál vsdoc.js* je vnořený *portal.js* z důvodu **fileSuffixToExtension** pravidlo

* všechny ostatní aspekty pravidla funguje stejným způsobem jako **extensionToExtension**

### <a name="the-addedextension-provider"></a>Poskytovatel addedExtension

Tento zprostředkovatel vnoří soubory s příponou další v rámci souboru bez další rozšíření. Další rozšíření může nacházet pouze na konci úplný název souboru.

Vezměte v úvahu v následujícím příkladu:

![Příklad pravidla addedExtension](media/filenesting_addedextension.png) ![Příklad efekt addedExtension](media/filenesting_addedextension_effect.png)

* *File.HTML.CSS* je vnořený *file.html* z důvodu **addedExtension** pravidlo

> [!NOTE]
> Nezadávejte žádné přípony souborů pro `addedExtension` pravidlo; automaticky aplikuje na všechny přípony souborů. To znamená libovolný soubor se stejným názvem a příponou jako jiný soubor s příponou další na konci vnořit jiného souboru. Nelze omezit účinek tohoto zprostředkovatele k jenom určité přípony souborů.

### <a name="the-pathsegment-provider"></a>Poskytovatel pathSegment

Tento zprostředkovatel vnoří soubory s příponou další v rámci souboru bez další rozšíření. Další rozšíření může vyskytovat jenom na střední úplný název souboru.

Vezměte v úvahu v následujícím příkladu:

![Příklad pravidla pathSegment](media/filenesting_pathsegment.png) ![Příklad efekt pathSegment](media/filenesting_pathsegment_effect.png)

* *jQuery.min.js* je vnořený *jquery.js* z důvodu **pathSegment** pravidlo

> [!NOTE]
> - Pokud nezadáte žádné konkrétní přípony souborů pro `pathSegment` pravidlo se vztahuje na všechny přípony souborů. To znamená jakýkoli soubor se stejným názvem a příponou jako jiný soubor s příponou další uprostřed vnořit jiného souboru.
> - Můžete omezit účinek `pathSegment` pravidlo na konkrétní přípony souborů tak, že zadáte následujícím způsobem:
>
>    ```json
>    "pathSegment": {
>       "add": {
>         ".*": [
>           ".js",
>           ".css",
>           ".html",
>           ".htm"
>         ]
>       }
>    }
>    ```

### <a name="the-allextensions-provider"></a>Poskytovatel allExtensions

Tento zprostředkovatel umožňuje definovat pravidla vnoření souborů pro soubory s jakoukoli příponu, ale stejný základní název souboru. Vezměte v úvahu v následujícím příkladu:

![Příklad pravidla allExtensions](media/filenesting_allextensions.png) ![Příklad efekt allExtensions](media/filenesting_allextensions_effect.png)

* *Template.cs* a *template.doc* jsou vnořené pod *template.tt* z důvodu **allExtensions** pravidlo.

### <a name="the-filetofile-provider"></a>Poskytovatel fileToFile

Tento zprostředkovatel umožňuje definovat pravidla vnoření souborů podle celého názvu souboru. Vezměte v úvahu v následujícím příkladu:

![Příklad pravidla fileToFile](media/filenesting_filetofile.png) ![Příklad efekt fileToFile](media/filenesting_filetofile_effect.png)

* *.bowerrc* je vnořený *bower.json* z důvodu **fileToFile** pravidlo

### <a name="rule-order"></a>Pořadí pravidel

Pořadí je důležité v každé části soubor s vlastním nastavením. Můžete změnit pořadí, ve kterém pravidla provedení jejich přesunutím směrem nahoru nebo dolů v **dependentFileProvider** uzlu. Například, pokud máte jednoho pravidla, která provádí **file.js** nadřazený **file.ts** a další pravidlo, které umožňuje **file.coffee** nadřazený **file.ts**, pořadí, v jakém jsou uvedeny v souboru určuje vnoření chování, když jsou všechny tři soubory k dispozici. Protože **file.ts** může mít pouze jeden nadřazený prvek, podle toho, která pravidlo spustí první wins.

Řazení je také důležité pro pravidlo oddíly sami, nikoli pouze pro soubory v rámci oddílu. Jakmile dvojici souborů je nalezena shoda s pravidlem vnoření souborů, ostatní pravidla další dolů v souboru jsou ignorovány a další pár souborů se zpracovává.

### <a name="file-nesting-button"></a>Vnoření souboru – tlačítko

Můžete spravovat všechna nastavení, včetně vlastní nastavení, pomocí stejného tlačítka v **Průzkumníka řešení**:

![Aktivovat vnoření vlastního souboru pravidel](media/filenesting_activatecustom.png)

## <a name="create-project-specific-settings"></a>Vytvoření nastavení specifické pro projekt

Můžete vytvořit nastavení specifická pro řešení a projektu prostřednictvím v místní nabídce (kontextová nabídka) jednotlivých řešení a projektu:

![Vnoření pravidla specifická pro projekt a řešení](media/filenesting_solutionprojectspecific.png)

Specifické řešení a projektu nastavení spolu se aktivní nastavení sady Visual Studio. Například může být soubor prázdný nastavení specifické pro projekt, ale **Průzkumníka řešení** je stále vnořování souborů. Vnoření chování pochází z nastavení specifická pro řešení nebo nastavení sady Visual Studio. Priorita pro sloučení nastavení vnořování souborů je: Visual Studio > řešení > projekt.

Visual Studio ignorovat nastavení specifická pro řešení a specifické pro projekt, můžete říct, i v případě, že soubory existují na disku, když zapnete možnost **ignorovat nastavení řešení a projektů** pod **nástroje**  >  **Možnosti** > **ASP.NET Core** > **souboru vnoření**.

Můžete provést opak a že se sada Visual Studio *pouze* použít konkrétní řešení nebo nastavení specifické pro projekt tak, že nastavíte **kořenové** uzlu **true**. Visual Studio přestane slučování souborů na této úrovni a nebude ho spojovat se soubory výše v hierarchii.

Nastavení specifická pro řešení a specifické pro projekt může být zařazeno do správy zdrojového kódu a celý tým, že funguje v základu kódu můžete je sdílet.

## <a name="disable-file-nesting-rules-for-a-project"></a>Zakázat pravidla vnoření souborů projektu

Můžete zakázat existující pravidla vnoření globálního souboru pro konkrétní řešení nebo projektů s použitím **odebrat** akce zprostředkovatele místo **přidat**. Pokud přidáte následující kód nastavení do projektu, například všechny **pathSegment** pravidla, která mohou existovat globálně tohoto konkrétního projektu jsou zakázané:

```json
"dependentFileProviders": {
  "remove": {
    "pathSegment": {}
  }
}
```

## <a name="see-also"></a>Viz také:

- [Přizpůsobení integrovaného vývojového prostředí](../ide/personalizing-the-visual-studio-ide.md)
- [Řešení a projekty v sadě Visual Studio](solutions-and-projects-in-visual-studio.md)
