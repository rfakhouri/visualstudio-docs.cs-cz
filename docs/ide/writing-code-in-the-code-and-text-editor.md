---
title: Editor funkce v sadě Visual Studio Code | Microsoft Docs
ms.custom: ''
ms.date: 02/23/2018
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code, editing [Visual Studio]
- code editor [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a7aacedac2045dcf069ea2d8a0f406d6322d7ca6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="features-of-the-code-editor"></a>Funkce editoru kódu

Editoru Visual Studio poskytuje řadu funkcí, které usnadňují můžete zapsat a spravovat kódu a text. Můžete rozbalit nebo sbalit různé bloky kódu pomocí osnovy. Další informace o kódu pomocí IntelliSense, **Prohlížeč objektů**a hierarchie volání. Kód můžete najít pomocí funkce, jako **přejít na**, **přejít k definici**, a **najít všechny odkazy**. Můžete vložit bloky kódu s fragmenty kódu a kódu můžete vygenerovat pomocí funkce **generování před využitím**. Pokud jste před editoru Visual Studio nikdy nepoužívali, projděte si téma [úpravy si kód](https://www.visualstudio.com/features/ide-vs) rychlý přehled.

Zobrazí se váš kód v několika různými způsoby. Ve výchozím nastavení **Průzkumníku řešení** ukazuje kódu uspořádané podle soubory. Kliknutím na **zobrazení tříd** karta v dolní části okna zobrazení kódu uspořádané podle třídy.

Můžete hledat a nahradit text v jedné nebo více souborů. Další informace najdete v tématu [hledání a nahrazování textu](../ide/finding-and-replacing-text.md). Regulární výrazy slouží k vyhledání a nahrazení textu. Další informace najdete v tématu [pomocí regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).

Různé jazyky Visual Studio nabízejí různé sady funkcí a v některých případech funkce chovat jinak v různých jazycích. Řadu tyto rozdíly jsou určené v popis jednotlivých funkcí, ale další informace můžete najdete v částech na konkrétní jazyky Visual Studio.

## <a name="editor-features"></a>Funkce editoru

|||
|-|-|
|Barevné zvýrazňování syntaxe|Některé prvky syntaxe kódu a kódu souborů, abychom je odlišili se zobrazí odlišně. Například klíčová slova (, jako `using` v jazyce C# a `Imports` v jazyce Visual Basic) jedné barvy, ale typy (například `Console` a `Uri`) jsou jiné barvy. Další prvky syntaxe jsou také obarvené, například textové literály a komentáře. C++ pomocí barvy rozlišit mezi typy, výčty a makra mezi dalších tokenů.<br /><br /> Zobrazí se výchozí barvu pro každý typ, a můžete změnit barvu pro libovolný element specifickou syntaxi v [písma a barvy, prostředí, dialogové okno Možnosti](../ide/reference/fonts-and-colors-environment-options-dialog-box.md), které lze otevřít z **nástroje** nabídky.|
|Chyby a upozornění značky|Při přidávání kódu a sestavení řešení, může se zobrazit (a) různě barevných podtržení vlnovkou (označované jako podtržení vlnovkou) nebo (b) žárovek zobrazovaných v kódu. Podtržení vlnovkou Red označují chyby syntaxe, modrá označuje chyby kompilátoru, zelená označuje upozornění a Fialová označuje jiné typy chyb. [Žárovek](../ide/perform-quick-actions-with-light-bulbs.md) navrhnout opravy problémů a usnadňují použití opravy.<br /><br /> Zobrazí se výchozí barvu pro každý vlnovku chyb a upozornění v **nástroje** > **možnosti** > **prostředí**  >   **Písma a barev** dialogové okno. Vyhledejte **Chyba syntaxe**, **Chyba kompilátoru**, **upozornění**, a **jiné chybě**.|
|Související závorky|Kurzor je umístěn na otevřenou složenou závorku v souboru kódu, se zvýrazní ji a pravé složené závorce, které obsahuje. Tato funkce vám dává okamžitou zpětnou vazbu na nesprávně umístěny nebo chybějící složené závorky. Můžete zapnout závorky zapnout nebo vypnout pomocí **automatické zvýraznění oddělovač** nastavení (**nástroje** > **možnosti**  >   **Textový Editor**). Barva zvýraznění v můžete změnit **písma a barev** nastavení (**nástroje** > **možnosti** > **prostředí**). Vyhledejte **složených závorek odpovídající (zvýraznit)** nebo **složených závorek odpovídající (obdélníku)**.|
|Struktura Vizualizéru|Řádky tečkovaná připojit odpovídající složené závorky v kódu soubory usnadnit zobrazíte otvírání a zavírání dvojice závorek. To vám může pomoci najít kód ve vaší codebase rychleji. Tyto řádky můžete zapnout nebo vypnout pomocí **zobrazit pokyny struktura** v **zobrazení** části **nástroje** > **možnosti**  >  **Textového editoru** > **Obecné** stránky.|
|Čísla řádků|Čísla řádků lze zobrazit na levém okraji okna kódu. Ve výchozím nastavení nejsou zobrazeny. Můžete zapnout tato možnost **textový Editor, všechny jazyky** nastavení (**nástroje** > **možnosti** > **textovéhoeditoru**  >  **Všechny jazyky**). Čísla řádků pro jednotlivé programovací jazyky můžete zobrazit tak, že změníte nastavení pro tyto jazyky (**nástroje** > **možnosti** > **textového editoru**   >   **\<jazyk >**). Čísla řádků tisknout, musíte vybrat **zahrnout čísla řádků** v **tisku** dialogové okno.|
|Sledování změn|Barva levého okraje můžete ke sledování změn, které jste udělali v souboru. Změny, které jste provedli, protože soubor otevřít, ale není uložené jsou rozlišeny pomocí žlutý pruh na levým okrajem (označované jako výběr okraje). Po uložení změn (ale před jeho zavřením soubor), stane se z panelu zelená. Pokud změnu zrušit, po uložení souboru, stane se z panelu oranžová. Chcete-li tuto funkci vypnutí a zapnutí, změňte **sledování změn** možnost **textového editoru** nastavení (**nástroje** > **možnosti**  >  **Textového editoru**).|
|Výběr kódu a Text.|Můžete vybrat text v režimu standardní nepřetržitý proud nebo v režimu pole, ve kterém můžete vybrat obdélníková část textu místo sadu řádků. Můžete vybrat v režimu pole klávesu ALT přetahování myší přes výběr (nebo stiskněte klávesu ALT + SHIFT + \<klávesa se šipkou >). Výběr zahrnuje všechny znaky v obdélníku definované prvního znaku a poslední znak ve výběru. Nic zadali nebo vložit do vybrané oblasti vložen na stejném místě na každém řádku.|
|Lupa|Můžete přiblížit nebo oddálit žádné kódu – okno tak, že stisknete a podržíte klávesu CTRL a přesunutí kolečka myši (nebo kombinace kláves CTRL + SHIFT +. zvýšení a CTRL + SHIFT +, aby se snížila). Pole zvětšení v levém dolním rohu okna kód můžete taky nastavit určité měřítko. Úroveň přiblížení nefunguje v systému windows nástroj.|
|Virtuální prostor|Ve výchozím nastavení ukončení řádků v sadě Visual Studio editory po poslední znak tak, aby šipka vpravo na konci řádku Posune kurzor na začátek následujícího řádku. V některých jiných editory řádku nemá na konci za poslední znak a kurzor můžete umístit kdekoli v řádku. Virtuální prostor v editoru v můžete povolit **nástroje** > **možnosti** > **textového editoru** > **všechny Jazyky** nastavení. Všimněte si, že můžete povolit buď **virtuální adresní prostor** nebo **zalamování**, ale ne obojí.|
|Tisk|Můžete použít možnosti v **tisku** dialogové okno pro zahrnutí čísla řádků nebo skrytí sbalené oblasti kódu při tisku souboru. V **vzhled stránky** dialogové okno, můžete také vytisknout úplnou cestu a název souboru tak, že zvolíte **záhlaví stránky**.<br /><br /> Možnosti tisku Barva můžete nastavit v **nástroje** > **možnosti** > **prostředí** > **písem a Barvy** dialogové okno. Zvolte **tiskárny** v **zobrazit nastavení pro** seznamu, chcete-li přizpůsobit barvy tisku. Můžete zadat jiné barvy pro tisk souboru než pro úpravy souboru.|
|Globální zpět a znovu|**Vrátit zpět poslední akci globální** a **znovu provést poslední akci globální** příkazy **upravit** nabídky vrácení nebo opakování globální akce, které ovlivňují více souborů. Globální akce zahrnují přejmenování třída nebo obor názvů, provádění operace hledání a nahrazování přes řešení, refaktoring do databáze nebo další akci, která změní více souborů. Můžete použít globální akci zpět a vrátit příkazy na akce v aktuální relaci sady Visual Studio, i když zavřete řešení, ve kterém byla použita akce.|

## <a name="advanced-editing-features"></a>Rozšířené úpravy funkce

Počet pokročilé funkce můžete najít na **upravit** > **Upřesnit** nabídky na panelu nástrojů. Všechny tyto funkce jsou dostupné pro všechny typy souborů kódu.

|||
|-|-|
|Formátovat dokument|Nastaví správné odsazení řádků kódu a přesune složené závorky na samostatné řádky v dokumentu.|
|Výběr formátu|Nastaví správné odsazení řádků kódu a přesune složené závorky k oddělení řádků ve výběru.|
|Převedení na tabulátory vybrané řádky|Změny úvodní mezery na karty, kde je to vhodné.|
|Zrušit tabulátory vybrané řádky|Změny úvodní karet do prostorů. Pokud chcete převést všechny mezery v souboru na kartách (nebo všechny karty do prostorů), můžete použít `Edit.ConvertSpacesToTabs` a `Edit.ConvertTabsToSpaces` příkazy. Tyto příkazy nezobrazí v sadě Visual Studio nabídky, ale můžete je volat z okna rychlý přístup nebo příkazové okno.|
|Převést na velká písmena|Změní všechny znaky v výběr na velká písmena, nebo pokud není nic vybráno, změny znak na pozici kurzoru na velká písmena.|
|Převést na malá písmena|Změní všechny znaky v výběr na malá písmena, nebo pokud není nic vybráno, změny znak na pozici kurzoru na malá písmena.|
|Přesunout vybrané řádky nahoru|Přesune vybraný řádek až jeden řádek. Zástupce: ALT + Šipka nahoru.|
|Přesunout vybrané řádky dolů|Přesune vybraný řádek dolů jeden řádek. Zástupce: ALT + Šipka dolů.|
|Odstranit vodorovné prázdné znaky|Odstraní tabulátory, nebo mezery na konci aktuálního řádku.|
|Zobrazit prázdné znaky|Zobrazí jako vyvolané tečky a karty jako dvojice šipek, prostory. Konec souboru se zobrazí jako obdélníková glyf. Pokud **nástroje** > **možnosti** > **textového editoru** > **všechny jazyky**  >  **Zalamování** > **zobrazit viditelné glyfy pro zalamování** je vybrána, že glyfy se zobrazí také.|
|Zalamování řádků|Způsobí, že všechny řádky v dokumentu mají být zobrazeny v okně kód. Můžete zalamování řádků v textovém editoru všechny jazyky nastavení vypněte a zapněte (**nástroje** > **možnosti** > **textového editoru**  >  **Všechny jazyky**).|
|Označení výběru jako komentáře|Přidá komentář znaků k výběru nebo aktuálního řádku.|
|Zrušením komentáře u výběru|Odebere komentář znaky z výběru nebo aktuálního řádku.|
|Zvětšit odsazení řádky|Přidá na kartě (nebo ekvivalentní prostory) do vybraných řádků nebo aktuálního řádku.|
|Zmenšit odsazení řádku|Odebere z vybraných řádků nebo aktuálního řádku na kartě (nebo ekvivalentní prostory).|
|Vyberte značky|V dokumentu, který obsahuje značky (například XML nebo HTML) vybere značky.|
|Vybrat obsah značky|V dokumentu, který obsahuje značky (například XML nebo HTML) vybere obsah.|

## <a name="navigate-and-find-code"></a>Orientuje a hledá kódu

Přesunutím v editoru kódu v několika různými způsoby, včetně zpětné procházení a předává do předchozí body vložení zobrazení definice typ nebo člen a přechod na konkrétní metodu pomocí navigačního panelu. Další informace najdete v části [navigace v kódu](navigating-code.md).

## <a name="finding-references-in-your-code-base"></a>Hledání odkazů základního kódu

Chcete-li zjistit, kde jsou elementy konkrétní kódu odkazovat v celé vaší základu kódu, můžete použít **najít všechny odkazy** příkaz. Navíc po kliknutí na typ nebo člen **zvýrazňování odkazu** funkce automaticky označuje všechny odkazy na tento typ nebo člen. Další informace najdete v tématu [hledání odkazy ve vašem kódu](finding-references.md).

## <a name="customize-the-editor"></a>Přizpůsobení editoru

Můžete sdílet nastavení sady Visual Studio s jinou developer, mají nastavení v souladu s standard nebo obnovit výchozí nastavení sady Visual Studio pomocí **Průvodce importem a exportem nastavení** příkaz na  **Nástroje pro** nabídky. V **Průvodce importem a exportem nastavení**, můžete změnit obecné nastavení vybrané nebo jazyk a nastavení pro konkrétní projekt.

Chcete-li definovat nové klávesové zkratky nebo změnit stávající klávesové zkratky, přejděte na **nástroje** > **možnosti** > **prostředí**  >  **Klávesnice**. Další informace o zkratky najdete v tématu [výchozí klávesové zkratky](../ide/default-keyboard-shortcuts-in-visual-studio.md).

Další informace o přizpůsobení editoru najdete v tématu [přizpůsobení editoru](../ide/customizing-the-editor.md). Možnosti editoru specifické pro JavaScript najdete v tématu [možností editoru JavaScript](../ide/reference/options-text-editor-javascript-formatting.md).

## <a name="see-also"></a>Viz také

- [Integrované vývojové prostředí sady Visual Studio](../ide/visual-studio-ide.md)
- [Začínáme s C++ v sadě Visual Studio](../ide/quickstart-cpp.md)
- [Začínáme s C# a ASP.NET v sadě Visual Studio](../ide/tutorial-csharp-aspnet-core.md)
- [Začínáme s Pythonem v sadě Visual Studio](../ide/quickstart-python.md)
