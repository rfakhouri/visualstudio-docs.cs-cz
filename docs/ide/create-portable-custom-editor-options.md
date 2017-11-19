---
title: "Vytvořte nastavení editoru přenosné, vlastní s EditorConfig | Microsoft Docs"
ms.custom: 
ms.date: 10/27/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editor
ms.assetid: 
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.openlocfilehash: 2c1df6f8e34d2b8e72486dd804ba57f0dcf2406b
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2017
---
# <a name="create-portable-custom-editor-settings-with-editorconfig"></a>Vytvořte nastavení editoru přenosné, vlastní s EditorConfig
Nastavení editoru textu v sadě Visual Studio se vztahují na všechny projekty daného typu. Ano, například pokud změníte textového editoru jazyka C# nastavení, toto nastavení platí pro *všechny* projektů C# v sadě Visual Studio. V některých případech můžete však použít konvence, které se liší od vašich vlastních předvoleb, osobní editor. [EditorConfig](http://editorconfig.org/) soubory umožňují to tím, že poskytuje společné text možností editoru na jednotlivých projektů. EditorConfig nastavení, které jsou obsaženy v souboru .editorconfig přidán do vaší codebase, mají přednost před globální nastavení editoru textu v sadě Visual Studio. To znamená, které můžete přizpůsobit, každý základu kódu použít nastavení textového editoru, kterému dáváte přednost. Ne modulu plug-in se vyžaduje k použití této funkce v sadě Visual Studio.

## <a name="coding-consistency"></a>Kódování konzistence
Nastavení v souborech EditorConfig umožňují zachovat konzistentní kódování styly a nastavení pro jazyk, například styl odsazení, Šířka karty, znaky konce řádku, kódování, a další, použít v codebase bez ohledu na to, editor nebo IDE. Například při kódování v jazyce C#, pokud má vaše codebase konvence pro přednost tomu, že odsazení vždy obsahovat pět znaků, místo, dokumenty používat kódování UTF-8 a každý řádek vždy končí CR/LF, můžete nakonfigurovat soubor .editorconfig to provést.

Konvence, které používáte na osobní projekty kódování mohou lišit od těch v týmových projektech používat. Může například dáváte přednost tomu, že pokud jste se kódování, stisknutím klávesy Tab přidá znaku TABULÁTORU. Váš tým ale můžou upřednostňovat že odsazení přidá čtyři znaky místo znaku TABULÁTORU. Soubory EditorConfig vyřešit tento problém tím, že vám v konfiguraci pro jednotlivé scénáře.

Vzhledem k tomu, že nastavení jsou obsaženy v souboru v základu kódu, jejich přenosu společně s tohoto základu kódu. Tak dlouho, dokud otevření souboru kódu v editoru EditorConfig předpisy, se implementují nastavení editoru textu. Další informace o souborech EditorConfig najdete v tématu [EditorConfig.org](http://editorconfig.org/) webu.

## <a name="override-editorconfig-settings"></a>Přepsání nastavení EditorConfig
Když přidáte .editorconfig soubor do složky v hierarchii souboru, jeho nastavení platí pro všechny příslušné soubory na této úrovni a pod ním. Pokud chcete přepsat nastavení EditorConfig pro konkrétní projekt nebo základu kódu tak, aby používala jiný konvence než nejvyšší úrovně .editorconfig soubor, stačí přidáte .editorconfig souboru do kořenového adresáře vaší codebase úložišti nebo projektu adresář. Zajistěte, aby se umístí ```root=true``` vlastnost v souboru, Visual Studio nevypadá pro všechny .editorconfig soubory další si strukturu adresáře. Nové nastavení .editorconfig souboru uplatní na úrovni, ve kterém se nachází a soubory do jakéhokoliv podadresáře.

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
- end_of_line
- Znaková sada
- kořen

Kromě toho podporuje [pravidla týkající se rozhraní .NET kódu stylu](../ide/editorconfig-code-style-settings-reference.md).  

Nastavení EditorConfig jsou podporovány ve všech jazycích podporovaných v sadě Visual Studio, s výjimkou XML.

## <a name="intellisense"></a>IntelliSense
Visual Studio poskytuje omezenou IntelliSense pro úpravy .editorconfig souborů. Pokud chcete upravit velké množství .editorconfig souborů, můžete zjistit [služba jazyka EditorConfig](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) rozšíření užitečné.

## <a name="example"></a>Příklad
Tady je příklad, který se zobrazuje stav odsazení fragmentu kódu C# před a po přidání souboru .editorconfig do projektu. **Karty** nastavení v **možnosti** dialogové okno pro textového editoru Visual Studio je nastavena k vytvoření mezer při stisknutí volby **kartě** klíče v kódu.

![Karta nastavení textového editoru](../ide/media/vside_editorconfig_tabsetting.png)

Podle očekávání, stisknete **kartě** klíč na další řádek odsadí řádek přidáním čtyři další prázdné znaky.

![Před použitím EditorConfig kódu](../ide/media/vside_editorconfig_before.png)

Přidáme nový soubor s názvem .editorconfig na projekt s tímto obsahem. `[*.cs]` Nastavení znamená, že tato změna se projeví pouze pro soubory .cs v tomto projektu.  

![Přidání .editorconfig souboru do projektu](../ide/media/vside_editorconfig_addconfig.png)

Teď, když stisknete **kartě** klíčů, můžete získat karta znaků místo prostory.

![Karta přidá znak tabulátoru](../ide/media/vside_editorconfig_tab.png)

> [!NOTE]
>  Přidávání .editorconfig souboru do projektu nebo codebase bude není převést stávající styly k nové, se vztahuje pouze na nově přidané řádky. Pokud odeberete .editorconfig soubory z projektu nebo základu kódu, musíte znovu načtete soubory kódu pro nastavení editoru a vrátit se zpátky do globální nastavení. Všechny chyby v souborech .editorconfig jsou zaznamenány v okně Seznam chyb v sadě Visual studio.

## <a name="troubleshooting-editorconfig-settings"></a>Řešení potíží s EditorConfig nastavení
Pokud je soubor EditorConfig kdekoli v strukturu adresáře nebo vyšší umístění vašeho projektu, Visual Studio použije nastavení editoru v tomto souboru k editoru. V takovém případě se může zobrazit následující zpráva ve stavovém řádku:

**"Uživatelských předvoleb pro tento typ souboru se přepisují konvence psaní kódu pro tento projekt."**

To znamená, že pokud editor nastavení na **nástroje**, **možnosti**, **textového editoru** (například velikost odsazení, velikost tabulátoru odsazovat styl &mdash; karty nebo mezery ani kódování konvence například použití `var`) jsou určené v souboru EditorConfig nebo vyšší na projekt v adresářovou strukturu názvů v souboru EditorConfig přepíší nastavení v možnostech. Toto chování můžete řídit přepnutím **projektu postupujte podle konvence kódování** možnost **nástroje**, **možnosti**, **textového editoru**. Zrušte zaškrtnutí možnosti se vypne EditorConfig podpora pro Visual Studio.

![Možnosti nástrojů – postupujte podle projektu konvence kódování](media/coding_conventions_option.png)

Soubory .editorconfig můžete najít v nadřazené adresáře tak, že otevřete příkazový řádek a spuštěním následujícího příkazu z kořenového adresáře disku, který obsahuje projektu:

```
dir .editorconfig /s
```

Obor názvů vaší EditorConfig můžete ovládat nastavením ```root=true``` vlastnost v souboru .editorconfig v kořenovém adresáři vašeho úložiště nebo v adresáři, který se nachází váš projekt. Visual Studio vyhledá soubor s názvem .editorconfig v adresáři otevřený soubor a každý nadřazený adresář. Visual Studio zastaví hledání, pokud je dosaženo filepath kořenové, nebo pokud soubor .editorconfig s ```root=true``` nalezen.

## <a name="support-editorconfig-for-your-language-service"></a>Podpora EditorConfig služby jazyk
Ve většině případů při implementaci služby jazykové sady Visual Studio, je žádné další kroky potřebné k podpoře EditorConfig universal vlastnosti. Editor základní automaticky vyhledá a načte soubor .editorconfig, když uživatelé otevřít soubory, a nastaví příslušná text možnosti vyrovnávací paměti a zobrazení. Některé služby jazyk však rozhodnout používá možnost zobrazení příslušné kontextové text namísto použití globální nastavení pro položky, jako jsou karty a prostory, když uživatel upravuje nebo formátování textu. V těchto případech služba jazyka musí být aktualizované kvůli podpoře EditorConfig soubory.

Toto jsou změny, které jsou potřebné k aktualizaci služby jazyk pro podporu EditorConfig soubory, tak, že nahradíte globální konfiguraci _konkrétní jazyk_ možnost s _kontextové_ možnost:  

### <a name="indent-style"></a>Styl odsazení
Nahraďte:  

Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.fInsertTabs  
_nebo_  
Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs  

Pomocí:  

! textBufferOptions.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)  
_nebo_  
! textView.Options.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)  

### <a name="indent-size"></a>Velikost odsazení
Nahraďte:  

Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uIndentSize  
_nebo_  
Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.IndentSize  

Pomocí:  

textBufferOptions.GetOptionValue(DefaultOptions.IndentSizeOptionId)  
_nebo_  
textView.Options.GetOptionValue(DefaultOptions.IndentSizeOptionId)  

### <a name="tab-size"></a>Velikost tabulátoru
Nahraďte:  

Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uTabSize  
_nebo_  
Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.TabSize  

Pomocí:  

textBufferOptions.GetOptionValue(DefaultOptions.TabSizeOptionId)  
_nebo_  
textView.Options.GetOptionValue(DefaultOptions.TabSizeOptionId)  

## <a name="see-also"></a>Viz také
[Pravidla týkající se rozhraní .NET kódu stylu](../ide/editorconfig-code-style-settings-reference.md)  
[EditorConfig.org](http://editorconfig.org/)  
[Psaní kódu v editoru](writing-code-in-the-code-and-text-editor.md)