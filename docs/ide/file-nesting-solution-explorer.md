---
title: Soubor vnoření pravidla pro Průzkumníku řešení
ms.date: 05/25/2018
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
helpviewer_keywords:
- file nesting
- Solution Explorer, file nesting
author: angelosp
ms.author: angelpe
manager: douge
ms.openlocfilehash: bc4ba4c019801c4461313149c0f3befacefa93d2
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37118142"
---
# <a name="customize-file-nesting-in-solution-explorer"></a>Přizpůsobení vnořování souborů v Průzkumníku řešení

Vnoření souvisejících souborů v **Průzkumníku řešení** není nový, ale dokud teď jste měli žádnou kontrolu nad vnoření pravidla. Můžete si vybrat mezi přednastavení **vypnout**, **výchozí** a **webové**, ale můžete také upravit vnoření přesně ke své libosti. Můžete například vytvořit konkrétní řešení a specifická nastavení projektu, ale také další informace o všech této později. Nejprve přejděte přes dostanete se na pole.

> [!NOTE]
> Tato funkce je aktuálně podporuje jenom pro projekty ASP.NET Core.

## <a name="file-nesting-options"></a>Soubor vnoření možnosti

![Tlačítko pro zapnutí souboru vnoření zapnutí nebo vypnutí](media/filenesting_onoff.png)

Jsou k dispozici možnosti pro vnoření neupravené souboru:

* **Vypnout**: Tato možnost vám dává plochý seznam souborů, bez jakékoli vnoření.

* **Výchozí**: Tato možnost vám dává výchozí soubor vnoření chování v **Průzkumníku řešení**. Pokud neexistují žádná nastavení pro typ daného projektu, jsou vnořeny žádné soubory v projektu. Pokud nastavení existuje, například pro webový projekt, použije se vnoření.

* **Webové**: Tato možnost se vztahuje **webové** souboru vnoření chování na všechny projekty v aktuálním řešení. Obsahuje mnoho pravidel a doporučujeme vám ji rezervovat a dejte nám vědět, co si myslíte. Následující snímek obrazovky upozorňuje jenom několik příkladů vnoření chování souboru, kterou můžete získat pomocí této možnosti:

   ![Soubor vnoření v Průzkumníku řešení](media/filenesting.png)

## <a name="customize-file-nesting"></a>Přizpůsobení souboru vnoření

Pokud vám nevyhovuje, zobrazí se na pole, můžete vytvořit vlastní, vlastního souboru vnoření nastavení, které dávají pokyn **Průzkumníku řešení** jak lze vnořit soubory. Můžete přidat libovolný počet vlastního souboru vnoření nastavení, jak se vám líbí a můžete přepnout mezi nimi podle potřeby. Pokud chcete vytvořit nové vlastní nastavení, můžete začít s prázdný soubor, nebo můžete použít **webové** nastavení jako výchozí bod:

![Přidání vlastního souboru vnoření pravidla](media/filenesting_addcustom.png)

Doporučujeme použít **webové** nastavení jako váš výchozí bod, protože je snazší s ním pracovat něco, která již funkce. Pokud použijete **webové** nastavení jako počáteční bod, *. filenesting.json* soubor bude vypadat podobně jako následující soubor:

![Použít existující soubor vnoření pravidla jako základ pro vlastní nastavení](media/filenesting_editcustom.png)

Umožňuje zaměřit se na uzlu **dependentFileProviders** a jeho podřízené uzly. Každý podřízený uzel je typ pravidla, Visual Studio můžete použít k vnořit soubory. Například **mají stejný název souboru, avšak jiné rozšíření** je jeden typ pravidla. Jsou uvedená dostupná pravidla:

* **extensionToExtension**: pomocí tohoto typu pravidla vnořit *file.js* pod *file.ts*

* **fileSuffixToExtension**: pomocí tohoto typu pravidla vnořit *soubor vsdoc.js* pod *file.js*

* **addedExtension**: pomocí tohoto typu pravidla vnořit *file.html.css* pod *file.html*

* **pathSegment**: pomocí tohoto typu pravidla vnořit *jquery.min.js* pod *jquery.js*

* **allExtensions**: pomocí tohoto typu pravidla vnořit *soubor.* * v části *file.js*

* **fileToFile**: pomocí tohoto typu pravidla vnořit *bower.json* pod *.bowerrc*

### <a name="the-extensiontoextension-provider"></a>Zprostředkovatel extensionToExtension

Tento zprostředkovatel umožňuje definovat pravidla vnoření souborů pomocí konkrétní přípony souborů. Podívejte se na následující příklad:

![extentionToExtension příklad pravidla](media/filenesting_extensiontoextension.png) ![Příklad vliv extentionToExtension](media/filenesting_extensiontoextension_effect.png)

* *Cart.js* vnořen v části *cart.ts* z důvodu první **extensionToExtension** pravidlo

* *Cart.js* není vnořené pod *cart.tsx* protože **.ts** zaslána před **.tsx** v pravidlech, a může existovat jenom jednou nadřazenou položkou.

* *Light.CSS* vnořen v části *light.sass* z důvodu druhý **extensionToExtension** pravidlo

* *Home.HTML* vnořen v části *home.md* z důvodu třetí **extensionToExtension** pravidlo

### <a name="the-filesuffixtoextension-provider"></a>Zprostředkovatel fileSuffixToExtension

Tento zprostředkovatel funguje podobně jako **extensionToExtension** zprostředkovatele s z jenom rozdíl je pravidlo bude vypadat na příponě souboru místo právě rozšíření. Podívejte se na následující příklad:

![fileSuffixToExtension příklad pravidla](media/filenesting_filesuffixtoextension.png) ![Příklad vliv fileSuffixToExtension](media/filenesting_filesuffixtoextension_effect.png)

* *portál vsdoc.js* vnořen v části *portal.js* z důvodu **fileSuffixToExtension** pravidlo

* každý další aspekt pravidla funguje stejným způsobem jako **extensionToExtension**

### <a name="the-addedextension-provider"></a>Zprostředkovatel addedExtension

Tento zprostředkovatel vnořena souborů s příponou další pod soubor bez další rozšíření. Další rozšíření může vyskytovat pouze na konci úplný název souboru. Podívejte se na následující příklad:

![addedExtension příklad pravidla](media/filenesting_addedextension.png) ![Příklad vliv addedExtension](media/filenesting_addedextension_effect.png)

* *File.HTML.CSS* vnořen v části *file.html* z důvodu **addedExtension** pravidlo

### <a name="the-pathsegment-provider"></a>Zprostředkovatel pathSegment

Tento zprostředkovatel vnořena souborů s příponou další v souboru bez další rozšíření. Další rozšíření může vyskytovat pouze ve středu úplný název souboru. Podívejte se na následující příklad:

![pathSegment příklad pravidla](media/filenesting_pathsegment.png) ![Příklad vliv pathSegment](media/filenesting_pathsegment_effect.png)

* *jQuery.min.js* vnořen v části *jquery.js* z důvodu **pathSegment** pravidlo

### <a name="the-allextensions-provider"></a>Zprostředkovatel allExtensions

Tento zprostředkovatel umožňuje definovat pravidla vnoření souborů pro soubory s jakoukoli příponu ale stejný název základního souboru. Podívejte se na následující příklad:

![allExtensions příklad pravidla](media/filenesting_allextensions.png) ![Příklad vliv allExtensions](media/filenesting_allextensions_effect.png)

* *Template.cs* a *template.doc* jsou vnořeny pod *template.tt* z důvodu **allExtensions** pravidlo.

### <a name="the-filetofile-provider"></a>Zprostředkovatel fileToFile

Tento zprostředkovatel umožňuje definovat souboru vnoření pravidla založená na celé názvy souborů. Podívejte se na následující příklad:

![fileToFile příklad pravidla](media/filenesting_filetofile.png) ![Příklad vliv fileToFile](media/filenesting_filetofile_effect.png)

* *.bowerrc* vnořen v části *bower.json* z důvodu **fileToFile** pravidlo

### <a name="rule-order"></a>Pořadí pravidel

Pořadí je důležité v každé části souboru vlastní nastavení. Pořadí, ve kterém jsou prováděny pravidla pomocí přesunutí nahoru nebo dolů uvnitř můžete změnit **dependentFileProvider** uzlu. Například, pokud máte jednoho pravidla, která vytváří **file.js** nadřazeného **file.ts** a jiné pravidlo, které umožňuje **file.coffee** nadřazeného **file.ts**, pořadí, ve kterém se zobrazí v souboru stanoví vnoření chování, pokud jsou přítomné všechny tři soubory. Vzhledem k tomu **file.ts** může mít pouze jednu nadřazenou položku, podle toho, která pravidlo provádí první wins.

Pořadí je důležité pro pravidlo oddíly sami, ne jenom pro soubory v rámci oddílu. Jakmile pár soubory se najde shoda s vnoření pravidla souborů, ostatní pravidla další dolů v souboru jsou ignorovány a zpracování další pár souborů.

### <a name="file-nesting-button"></a>Tlačítko vnoření soubor

Můžete spravovat všechna nastavení, včetně vlastní nastavení, prostřednictvím stejné tlačítka na **Průzkumníku řešení**:

![Aktivovat vlastního souboru vnoření pravidla](media/filenesting_activatecustom.png)

## <a name="create-solution-specific-and-project-specific-settings"></a>Vytvoření nastavení specifická řešení a projektu

Můžete vytvořit nastavení specifická řešení a projektu prostřednictvím místní nabídky pro každé řešení a projektu:

![Řešení a pravidla týkající se projektu vnoření](media/filenesting_solutionprojectspecific.png)

Specifické řešení a projektu nastavení spolu se aktivní nastavení sady Visual Studio. Například můžete mít soubor prázdného projektu konkrétní nastavení, ale **Průzkumníku řešení** je stále vnoření soubory. Vnoření chování pochází z nastavení specifických pro řešení nebo nastavení sady Visual Studio. Prioritu pro slučování vnoření nastavení souboru je: Visual Studio > řešení > projekt.

Visual Studio ignorovat nastavení specifická řešení a projektu, můžete zjistit, i když soubory existují na disku, když zapnete možnost **ignorovat nastavení řešení a projektu** pod **nástroje**  >  **Možnosti** > **ASP.NET Core** > **souboru vnoření**.

Můžete provést jako opak a řekněte sady Visual Studio *pouze* použít konkrétní řešení nebo nastavení pro konkrétní projekt, nastavením **kořenové** uzlu **true**. Visual Studio přestane sloučení souborů na této úrovni a nebude ho spojovat se soubory vyšší nahoru v hierarchii.

Specifické řešení a projektu nastavení lze do správy zdrojového kódu a celý tým funguje na základu kódu můžete sdílet je zkontrolovat.

## <a name="disable-global-file-nesting-rules-for-a-particular-solution-or-project"></a>Zakázat globální soubor vnoření pravidla pro konkrétní řešení nebo projektu

Existující pravidla vnoření globální souborů pro projekty nebo konkrétní řešení můžete zakázat pomocí **odebrat** akce pro zprostředkovatele místo **přidat**. Pokud přidejte následující kód nastavení do projektu, například všechny **pathSegment** pravidla, která mohou existovat globálně pro tento konkrétní projekt jsou zakázány:

```json
"dependentFileProviders": {
  "remove": {
    "pathSegment": {}
  }
}
```

## <a name="see-also"></a>Viz také:

- [Přizpůsobení integrovaného vývojového prostředí](../ide/personalizing-the-visual-studio-ide.md)
