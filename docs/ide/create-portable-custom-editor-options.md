---
title: Pomocí nastavení EditorConfig v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 12/13/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editorconfig [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.openlocfilehash: e9ea6cde08724c00c4595774decea35b2bce44f4
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/28/2018
---
# <a name="create-portable-custom-editor-settings-with-editorconfig"></a>Vytvořte nastavení editoru přenosné, vlastní s EditorConfig

Ve Visual Studio 2017, můžete přidat [EditorConfig](http://editorconfig.org/) souboru do projektu nebo codebase vynutit konzistentní kódování styly pro všechny uživatele, který funguje v základu kódu. Nastavení EditorConfig mají přednost před globální text v sadě Visual Studio nastavení editoru. To znamená, které můžete přizpůsobit, každý základu kódu použít nastavení editoru textu, které jsou specifické pro daného projektu. V sadě Visual Studio, stále můžete nastavit vlastní předvolby osobní editor **možnosti** dialogové okno. Tato nastavení platí vždy, když pracujete v codebase bez *.editorconfig* souboru, nebo když *.editorconfig* soubor není přepsat příslušného nastavení. Příkladem takových předvoleb je odsazení styl&mdash;tabulátory, nebo mezery.

Nastavení EditorConfig podporuje mnoho editory kódu a integrovaného vývojového prostředí, včetně sady Visual Studio. Je přenosné komponenty, která přenáší pomocí kódu a může vynutit kódování styly i mimo Visual Studio.

> [!NOTE]
> Když přidáte soubor EditorConfig do projektu v sadě Visual Studio, formátování existující kód není změnit, dokud se formátovat dokument (**upravit** > **Upřesnit**  >  **Formátovat dokument** nebo **Ctrl**+**tisíc**, **Ctrl**+**D**). Žádné nové řádky kódu jsou však formátovaného podle nastavení EditorConfig.

## <a name="coding-consistency"></a>Kódování konzistence

Nastavení v souborech EditorConfig vám umožní udržovat konzistentní kódování styly a nastavení v základu kódu, například styl odsazení, Šířka karty, znaky konce řádku, kódování, a další, bez ohledu na to, editor nebo IDE používáte. Například při kódování v jazyce C#, pokud má vaše codebase konvence k dáváte přednost, že odsazení vždy obsahovat pět znaků místa, dokumenty použijte kódování UTF-8 a každý řádek vždy končí CR/LF, můžete nakonfigurovat *.editorconfig* soubor se to udělat.

Konvence, které používáte na osobní projekty kódování mohou lišit od těch v týmových projektech používat. Může například dáváte přednost tomu, že pokud jste se kódování, odsazení přidá znaku tabulátoru. Váš tým ale můžou upřednostňovat že odsazení přidá čtyři znaky místo znaku tabulátoru. Soubory EditorConfig vyřešit tento problém tím, že vám v konfiguraci pro jednotlivé scénáře.

Vzhledem k tomu, že nastavení jsou obsaženy v souboru v základu kódu, jejich přenosu společně s tohoto základu kódu. Tak dlouho, dokud otevření souboru kódu v editoru EditorConfig předpisy, se implementují nastavení editoru textu. Další informace o souborech EditorConfig najdete v tématu [EditorConfig.org](http://editorconfig.org/) webu.

## <a name="supported-settings"></a>Podporovaná nastavení

Editor v sadě Visual Studio podporuje základní sady [EditorConfig vlastnosti](http://editorconfig.org/#supported-properties):

- indent_style
- indent_size
- tab_width
- end\_of_line
- Znaková sada
- trim\_trailing_whitespace
- insert\_final_newline
- kořen

Nastavení editoru EditorConfig jsou podporovány ve všech jazycích podporovaných v sadě Visual Studio, s výjimkou XML. Kromě toho EditorConfig podporuje [kódu stylu](../ide/editorconfig-code-style-settings-reference.md) a [pojmenování](../ide/editorconfig-naming-conventions.md) konvence pro C# a Visual Basic.

## <a name="adding-and-removing-editorconfig-files"></a>Přidávání a odebírání souborů EditorConfig

Přidání EditorConfig souboru do projektu nebo codebase nepřevádí existující styly na nové. Například pokud máte odsazení v souboru, které jsou naformátované se karty a přidat soubor EditorConfig, který odsadí prostory, znaky odsazení nebudou automaticky převedena do prostorů. Však žádné nové řádky kódu jsou formátovaná podle EditorConfig souboru. Kromě toho pokud formátovat dokument (**upravit** > **Upřesnit** > **formátovat dokument** nebo **Ctrl** + **Tisíc**, **Ctrl**+**D**), nastavení v souboru EditorConfig platí do existujícího kódu.

Když odeberete soubor EditorConfig z projektu nebo základu kódu, musí zavřete a znovu otevřít soubory se vrátit do editoru globální nastavení pro nové řádky kódu.

### <a name="to-add-an-editorconfig-file-to-a-project-or-solution"></a>Chcete-li přidat soubor EditorConfig na projekt nebo řešení

1. Otevřete projekt nebo řešení v sadě Visual Studio. Vyberte uzel na projekt nebo řešení, podle toho, jestli vaše *.editorconfig* nastavení by se měly používat pro všechny projekty v řešení nebo pouze jeden. Můžete také vybrat složku v projekt nebo řešení pro přidání *.editorconfig* do souboru.

1. V řádku nabídek zvolte **projektu** > **přidat novou položku...** , nebo stiskněte klávesu **Ctrl**+**Shift**+**A**.

   **Přidat novou položku** otevře se dialogové okno.

1. Do kategorií na levé straně vyberte **Obecné**a potom zvolte **textový soubor** šablony. V **název** textové pole, zadejte `.editorconfig` a potom zvolte **přidat**.

   *.Editorconfig* souboru se zobrazí v Průzkumníku řešení a otevře v editoru.

   ![.editorconfig soubor v Průzkumníku řešení](media/editorconfig-in-solution-explorer.png)

1. Upravte soubor podle potřeby, třeba:

   ```EditorConfig
   root = true

   [*.{cs,vb}]
   indent_size = 4
   trim_trailing_whitespace = true

   [*.cs]
   csharp_new_line_before_open_brace = methods
   ```

Alternativně můžete nainstalovat [služba jazyka EditorConfig rozšíření](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig). Po instalaci tohoto rozšíření, jednoduše vyberte **přidat** > **.editorconfig soubor** z nabídky řešení uzel, uzel projektu nebo libovolné složky v Průzkumníku řešení klikněte pravým tlačítkem nebo kontextu.

![Přidat .editorconfig soubor s příponou](media/editorconfig-extension-add.png)

## <a name="override-editorconfig-settings"></a>Přepsání nastavení EditorConfig

Když přidáte *.editorconfig* soubor do složky v hierarchii souboru, jeho nastavení se vztahují na všechny příslušné soubory na této úrovni a nižší. Můžete také přepsat EditorConfig nastavení pro konkrétní projekt, codebase nebo součástí základu kódu, tak, aby ho používá jiný konvence než ostatní části základu kódu. To může být užitečné, když začlenit kód z někde jinde a nechcete měnit jeho konvence.

Chcete-li přepsat některých nebo všech nastavení EditorConfig, přidejte *.editorconfig* souboru na úrovni hierarchie souboru chcete použít tyto přepsaného nastavení. Nové nastavení souboru EditorConfig se vztahují na soubory na stejné úrovni a jakéhokoliv podadresáře.

![EditorConfig hierarchie](../ide/media/vside_editorconfig_hierarchy.png)

Pokud chcete přepsat některé, ale ne všechna nastavení, zadejte pouze tyto nastavení v *.editorconfig* souboru. Pouze vlastnosti, které explicitně seznamu v souboru nižší úrovně se přepíšou. Další nastavení z vyšší úrovně *.editorconfig* soubory nadále platí. Pokud chcete zajistit, aby _žádné_ nastavení z _žádné_ vyšší úrovně *.editorconfig* soubory platí pro tuto část základu kódu, přidejte ```root=true``` vlastnost, která má nižší úrovně *.editorconfig* souboru:

```EditorConfig
# top-most EditorConfig file
root = true
```

EditorConfig soubory se čtou shora dolů a nejbližší EditorConfig soubory se čtou poslední. Konvence z odpovídající části EditorConfig se použijí v pořadí, ve kterém byly pro čtení, takže názvů v blíže soubory mají přednost před.

## <a name="editing-editorconfig-files"></a>Úprava EditorConfig souborů

Visual Studio můžete upravit *.editorconfig* soubory tím, že poskytuje seznamy dokončení IntelliSense.

![IntelliSense v souboru .editorconfig](media/editorconfig-intellisense-no-extension.png)

Jakmile upravíte soubor EditorConfig, musíte znovu načtete soubory s kódem pro nová nastavení vstoupila v platnost.

Pokud chcete upravit množství *.editorconfig* souborů, můžete zjistit [služba jazyka EditorConfig rozšíření](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) užitečné. Některé funkce tohoto rozšíření zahrnují syntaxe zvýraznění, vylepšené IntelliSense, ověřování a formátování kódu.

![IntelliSense s příponou EditorConfig služba jazyka](media/editorconfig-intellisense.png)

## <a name="example"></a>Příklad

Následující příklad ukazuje stav odsazení fragmentu kódu C#, před a po přidání *.editorconfig* souboru do projektu. **Karty** nastavení v **možnosti** dialogové okno pro textového editoru Visual Studio je nastavena k vytvoření mezer při stisknutí volby **kartě** klíč.

![Karta nastavení textového editoru](../ide/media/vside_editorconfig_tabsetting.png)

Podle očekávání, stisknete **kartě** klíč na další řádek odsadí řádek přidáním čtyři další prázdné znaky.

![Před použitím EditorConfig kódu](../ide/media/vside_editorconfig_before.png)

Přidat nový soubor s názvem *.editorconfig* na projekt s tímto obsahem. `[*.cs]` Nastavení znamená, že tato změna platí pouze pro soubory kódu C# v projektu.

```EditorConfig
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

To znamená, že pokud editor nastavení na **nástroje** > **možnosti** > **textového editoru** (například velikost odsazení a styl, velikost tabulátoru nebo kódování konvence) jsou určené v souboru EditorConfig nebo vyšší na projekt v strukturu adresáře, názvů v souboru EditorConfig potlačit nastavení ve **možnosti**. Toto chování můžete řídit přepnutím **projektu postupujte podle konvence kódování** možnost **nástroje** > **možnosti**  >  **Textového editoru**. Zrušte zaškrtnutí možnosti vypne EditorConfig podpora pro Visual Studio.

![Možnosti nástrojů – postupujte podle projektu konvence kódování](media/coding_conventions_option.png)

Můžete najít žádné *.editorconfig* soubory v adresářích nadřazené otevřením příkazového řádku a spuštěním následujícího příkazu z kořenového adresáře disku, který obsahuje projektu:

```Shell
dir .editorconfig /s
```

Obor názvů vaší EditorConfig můžete ovládat nastavením ```root=true``` vlastnost v *.editorconfig* soubor v kořenovém adresáři vašeho úložiště nebo v adresáři, který se nachází váš projekt. Visual Studio hledá soubor s názvem *.editorconfig* v adresáři otevřený soubor a každý nadřazený adresář. Hledání končí, když dorazí do kořenové filepath nebo *.editorconfig* soubor s ```root=true``` nalezen.

## <a name="see-also"></a>Viz také

[Pravidla týkající se rozhraní .NET kódu stylu](../ide/editorconfig-code-style-settings-reference.md)  
[Zásady vytváření názvů .NET](../ide/editorconfig-naming-conventions.md)  
[Podpora EditorConfig služby jazyk](../extensibility/supporting-editorconfig.md)  
[EditorConfig.org](http://editorconfig.org/)  
[Psaní kódu v editoru](writing-code-in-the-code-and-text-editor.md)
