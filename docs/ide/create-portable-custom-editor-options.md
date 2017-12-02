---
title: "Pomocí nastavení EditorConfig ve Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 10/27/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editorconfig [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.openlocfilehash: 39b3228e64257552c8b629e421c9b5aa4f0e0931
ms.sourcegitcommit: 5f5587a1bcf4aae995c80d54a67b4b461f8695f3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/29/2017
---
# <a name="create-portable-custom-editor-settings-with-editorconfig"></a>Vytvořte nastavení editoru přenosné, vlastní s EditorConfig

Nastavení editoru textu v sadě Visual Studio se vztahují na všechny projekty daného typu. Ano, například pokud změníte textového editoru jazyka C# nastavení, toto nastavení platí pro *všechny* projektů C# v sadě Visual Studio. V některých případech můžete však použít konvence, které se liší od vašich vlastních předvoleb, osobní editor. [EditorConfig](http://editorconfig.org/) soubory umožňují tomu popisující běžné možnosti text editoru, jako je například velikost odsazení v jednotlivých projektů. EditorConfig nastavení, které jsou obsaženy v souboru .editorconfig, který je umístěný společně se soubory kódu a projekt, mají přednost před globální text v sadě Visual Studio nastavení editoru. To znamená, které můžete přizpůsobit, každý základu kódu použít nastavení editoru textu, které jsou specifické pro daného projektu. Ne modulu plug-in se vyžaduje k použití této funkce v sadě Visual Studio.

## <a name="coding-consistency"></a>Kódování konzistence

Nastavení v souborech EditorConfig vám umožní udržovat konzistentní kódování styly a nastavení v základu kódu, například styl odsazení, Šířka karty, znaky konce řádku, kódování, a další, bez ohledu na to, editor nebo IDE používáte. Například při kódování v jazyce C#, pokud má vaše codebase konvence pro přednost tomu, že odsazení vždy obsahovat pět znaků, místo, dokumenty používat kódování UTF-8 a každý řádek vždy končí CR/LF, můžete nakonfigurovat soubor .editorconfig to provést.

Konvence, které používáte na osobní projekty kódování mohou lišit od těch v týmových projektech používat. Může například dáváte přednost tomu, že pokud jste se kódování, odsazení přidá znaku tabulátoru. Váš tým ale můžou upřednostňovat že odsazení přidá čtyři znaky místo znaku tabulátoru. Soubory EditorConfig vyřešit tento problém tím, že vám v konfiguraci pro jednotlivé scénáře.

Vzhledem k tomu, že nastavení jsou obsaženy v souboru v základu kódu, jejich přenosu společně s tohoto základu kódu. Tak dlouho, dokud otevření souboru kódu v editoru EditorConfig předpisy, se implementují nastavení editoru textu. Další informace o souborech EditorConfig najdete v tématu [EditorConfig.org](http://editorconfig.org/) webu.

## <a name="override-editorconfig-settings"></a>Přepsání nastavení EditorConfig

Když přidáte soubor .editorconfig do složky v hierarchii souboru, jeho nastavení platí pro všechny příslušné soubory na této úrovni a pod ním. Pokud chcete přepsat nastavení EditorConfig pro konkrétní projekt nebo základu kódu tak, aby používala jiný konvence než EditorConfig souboru na nejvyšší úrovni, stačí přidáte soubor .editorconfig do kořenového adresáře vaší codebase úložišti nebo projektu adresář. Zajistěte, aby se umístí ```root=true``` vlastnost v souboru tak nevypadá všechny další si strukturu adresáře pro soubory .editorconfig Visual Studio. Nové nastavení EditorConfig souboru uplatní na souborů na stejné úrovni a jakéhokoliv podadresáře.

```
# top-most EditorConfig file
root = true
```

![EditorConfig hierarchie](../ide/media/vside_editorconfig_hierarchy.png)

EditorConfig soubory se čtou shora dolů a nejbližší EditorConfig soubory se čtou poslední. Konvence z odpovídající části EditorConfig se použijí v pořadí, ve kterém byly pro čtení, takže názvů v blíže soubory mají přednost před.

## <a name="supported-settings"></a>Podporovaná nastavení

Editor v sadě Visual Studio podporuje následující ze základní sady [EditorConfig vlastnosti](http://editorconfig.org/#supported-properties):

- indent_style
- indent_size
- tab_width
- end\_of_line
- Znaková sada
- kořen

Nastavení editoru EditorConfig jsou podporovány ve všech jazycích podporovaných v sadě Visual Studio, s výjimkou XML. Kromě toho EditorConfig podporuje [kódu stylu](../ide/editorconfig-code-style-settings-reference.md) a [pojmenování](../ide/editorconfig-naming-conventions.md) konvence pro C# a Visual Basic.

## <a name="editing-editorconfig-files"></a>Úprava EditorConfig souborů

Visual Studio poskytuje některé technologie IntelliSense pro úpravy .editorconfig souborů. Pokud chcete upravit velké množství .editorconfig souborů, můžete zjistit [služba jazyka EditorConfig](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) rozšíření užitečné.

Jakmile upravíte soubor EditorConfig, musíte znovu načtete soubory s kódem pro nová nastavení vstoupila v platnost.

## <a name="adding-and-removing-editorconfig-files"></a>Přidávání a odebírání souborů EditorConfig

Přidání EditorConfig souboru do projektu nebo codebase bude není převést stávající styly na nové. Například pokud máte odsazení v souboru, které jsou naformátované se karty a přidat soubor EditorConfig, který odsadí prostory, nebude získat znaky odsazení převedeny do prostorů. Však žádné nové řádky kódu se bude formátovat podle EditorConfig souboru.

Když odeberete soubor EditorConfig z projektu nebo základu kódu, musí zavřete a znovu otevřít soubory se vrátit do editoru globální nastavení pro nové řádky kódu.

## <a name="example"></a>Příklad

Následuje příklad, který se zobrazuje stav odsazení fragmentu kódu C# před a po přidání souboru .editorconfig do projektu. **Karty** nastavení v **možnosti** dialogové okno pro textového editoru Visual Studio je nastavena k vytvoření mezer při stisknutí volby **kartě** klíč.

![Karta nastavení textového editoru](../ide/media/vside_editorconfig_tabsetting.png)

Podle očekávání, stisknete **kartě** klíč na další řádek odsadí řádek přidáním čtyři další prázdné znaky.

![Před použitím EditorConfig kódu](../ide/media/vside_editorconfig_before.png)

Přidáme nový soubor s názvem .editorconfig na projekt s tímto obsahem. `[*.cs]` Nastavení znamená, že tato změna se projeví pouze pro soubory kódu C# v tomto projektu.

```
# Top-most EditorConfig file
root = true

# Tab indentation
[*.cs]
indent_style = tab
```

Teď, když stisknete **kartě** klíčů, můžete získat karta znaků místo prostory.

![Tabulátor přidá znak tabulátoru](../ide/media/vside_editorconfig_tab.png)

## <a name="troubleshooting-editorconfig-settings"></a>Řešení potíží s EditorConfig nastavení

Pokud je soubor EditorConfig kdekoli v strukturu adresáře nebo vyšší umístění vašeho projektu, Visual Studio použije nastavení editoru v tomto souboru k editoru. V takovém případě se může zobrazit následující zpráva ve stavovém řádku:

   **"Uživatelských předvoleb pro tento typ souboru se přepisují konvence psaní kódu pro tento projekt."**

To znamená, že pokud editor nastavení na **nástroje**, **možnosti**, **textového editoru** (například velikost odsazení a styl, velikost tabulátoru nebo konvence kódování) jsou určené v Soubor EditorConfig nebo vyšší na projekt v strukturu adresáře, názvů v souboru EditorConfig přepíše nastavení v možnosti. Toto chování můžete řídit přepnutím **projektu postupujte podle konvence kódování** možnost **nástroje**, **možnosti**, **textového editoru**. Zrušte zaškrtnutí možnosti se vypne EditorConfig podpora pro Visual Studio.

![Možnosti nástrojů – postupujte podle projektu konvence kódování](media/coding_conventions_option.png)

Najdete všechny soubory .editorconfig v nadřazené adresáře otevřením příkazového řádku a spuštěním následujícího příkazu z kořenového adresáře disku, který obsahuje projektu:

```
dir .editorconfig /s
```

Obor názvů vaší EditorConfig můžete ovládat nastavením ```root=true``` vlastnost v souboru .editorconfig v kořenovém adresáři vašeho úložiště nebo v adresáři, který se nachází váš projekt. Visual Studio vyhledá soubor s názvem .editorconfig v adresáři otevřený soubor a každý nadřazený adresář. Visual Studio zastaví hledání, pokud je dosaženo filepath kořenové, nebo pokud souboru .editorconfig ```root=true``` nalezen.

## <a name="see-also"></a>Viz také

[Pravidla týkající se rozhraní .NET kódu stylu](../ide/editorconfig-code-style-settings-reference.md)  
[Podpora EditorConfig služby jazyk](../extensibility/supporting-editorconfig.md)  
[EditorConfig.org](http://editorconfig.org/)  
[Psaní kódu v editoru](writing-code-in-the-code-and-text-editor.md)