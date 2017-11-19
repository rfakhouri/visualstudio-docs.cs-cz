---
title: "Sdílené barvy pro sadu Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 04/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d11b9a0-6175-4f2e-8e7f-79daee1bfd41
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ccc530a741aaefd7e1faf1bd5f8974e27d9c7fb5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="shared-colors-for-visual-studio"></a>Sdílené barvy pro sadu Visual Studio
Při navrhování uživatelské rozhraní, které používá společné prvky prostředí sady Visual Studio, nebo chcete vaše rozhraní element konzistentní s podobné funkce, použijte existující token názvy v definičních souborech balíčku a vyberte a přiřaďte barvy. To zajišťuje, že vaše uživatelské prostředí zůstává konzistentní s celkovou prostředí Visual Studio a jeho aktualizace automaticky při přidávání nebo aktualizaci motivů.  

Tento článek popisuje běžné prvky uživatelského rozhraní a tokenu názvy, které používají, které můžete použít při vytváření podobné uživatelského rozhraní. Konkrétní informace o tom, jak tyto tokeny barva přístup, najdete v části [služba VSColor Service](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_TheVSColorService).  

Ujistěte se, že jste správně pomocí tokenu názvů:  

-   **Pomocí tokenu názvů založených na funkce, nikoli na barvu sám sebe.** Běžné sdílené barvy jsou přiřazeny k určité prvky rozhraní a jsou určeny pouze pro stejné nebo podobné funkce. Například nemáte opakovaně Barva při stisknutí tlačítka pole se seznamem pro animace průběhu roztočený právě, protože jako barvu. Funkce pole se seznamem a animace se liší, a pokud barvu spojené s poli se seznamem se změní, může to už být vhodnou barvu pro vaše elementu animace. Konzistentním použitím barvy pomáhá orientaci uživatelům a zabránit nejasnostem.  

-   **Použijte barvy a pozadí textu v správnou kombinaci.** Barvy pozadí, které jsou určena pro použití s textem bude mít k přidružené barvy. Nepoužívejte barvy textu, než který je určen pro na pozadí. Pokud není k dispozici k přidružené barvy, nepoužívejte tento barva pozadí pro všechny prostor, kdy očekáváte zobrazení textu. Jiné kombinace textu a barvy pozadí může mít za následek nečitelná rozhraní.  

-   **Pomocí řízení barev, které jsou vhodné pro jejich umístění.** V některých stavech některé ovládací prvky sady Visual Studio nemáte samostatné ohraničení a barvy pozadí. Místo toho se vyzvedávat tyto barvy z plochy za ně. Zajistěte, aby vždy použít token názvy, které jsou vhodné pro umístění, kde jsou umístění ovládacího prvku.  

> [!IMPORTANT]
> Nepoužívejte tokeny nalezen kategorií "Stránka Start" nebo "Jablečného."  

## <a name="common-shared-controls"></a>Běžné ovládací prvky sdílené

Při použití standardní panel příkazů sady Visual Studio ve vaší funkci, budete mít přístup k ovládacím prvkům s vzhledem prostředí. Neměli byste znovu šablony tyto běžné ovládací prvky. Pokud potřebujete k vytvoření vlastního příkazu panelu, může ale muset sestavovat vlastní ovládací prvky. V takovém případě nezapomeňte použít správné tokenu názvy pro každý z těchto ovládacích tak, aby vaše uživatelské prostředí je konzistentní se zbytkem sady Visual Studio.

### <a name="button-controls"></a>ovládací prvky tlačítek

![Tlačítko – ovládací prvek červeně označit](../../extensibility/ux-guidelines/media/0303-155_buttoncontrolredline.png "0303 155_ButtonControlRedline")

| Použití... | Nepoužívejte... |
| --- | --- |
| ... pro tlačítka v také dokumentu, který chcete integrovat s Visual Studio motivů (světlý, světlý, modrá nebo motiv s vysokým kontrastem systému). | ... pro tlačítka, který se zobrazí na vlastní pozadí, který není součástí motivu sady Visual Studio. |

**Tlačítka: standardní stav**

![Standardní tlačítko](../../extensibility/ux-guidelines/media/03.03.Button.Standard.png "03.03.Button.Standard")<br />Standardní tlačítko

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Tlačítko | `CommonControls.Button` |
| Tlačítko ohraničení | `CommonControls.ButtonBorder` |

**Tlačítko: výchozí stav**

![Výchozí tlačítko](../../extensibility/ux-guidelines/media/03.03.Button.Default.png "03.03.Button.Default")<br />Výchozí tlačítko

| Prvek | Název tokenu: Category.color | 
| --- | --- | 
| Tlačítko | `CommonControls.ButtonDefault` |
| Tlačítko ohraničení | `CommonControls.ButtonBorderDefault` |

**Tlačítko: zakázané**  

![Zakázané tlačítko](../../extensibility/ux-guidelines/media/03.03.Button.Disabled.png "03.03.Button.Disabled")<br />Zakázané tlačítko  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Tlačítko | `CommonControls.ButtonDisabled` |
| Tlačítko ohraničení | `CommonControls.ButtonBorderDisabled` |

**Tlačítka: stav hover**  

![Tlačítko při přechodu myší](../../extensibility/ux-guidelines/media/03.03.Button.hover.png "03.03.Button.hover")<br />Tlačítko při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Tlačítko | `CommonControls.ButtonHover` |
| Tlačítko ohraničení | `CommonControls.ButtonBorderHover` |

**Tlačítka: stav při stisknutí tlačítka**  

![Stisknutého tlačítka](../../extensibility/ux-guidelines/media/03.03.Button.Pressed.png "03.03.Button.Pressed")<br />Stisknutého tlačítka  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Tlačítko | `CommonControls.ButtonPressed` |
| Tlačítko ohraničení | `CommonControls.ButtonBorderPressed` |

**Tlačítka: stav cílených**  

![Tlačítko cílených](../../extensibility/ux-guidelines/media/03.03.Button.Focused.png "03.03.Button.Focused")<br />Cílených tlačítko  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Tlačítko | `CommonControls.ButtonFocused` |
| Tlačítko ohraničení | `CommonControls.ButtonBorderFocused` |

### <a name="check-box-controls"></a>Ovládací prvky zaškrtávacích políček  
![Zaškrtněte políčko (červená značka)](../../extensibility/ux-guidelines/media/0303-161_checkboxredline.png "0303 161_CheckboxRedline")<br />Zaškrtněte políčko (červená značka)  

| Použití... | Nepoužívejte... |
| --- | --- |
| ... pro ovládací prvky zaškrtávacích políček dobře obsažené v tomto dokumentu. | ... pro všechny uživatelské rozhraní, které není ovládací prvek zaškrtávací políčko. |

**Zaškrtněte políčko: výchozí stav**  

![Zaškrtněte políčko](../../extensibility/ux-guidelines/media/0303-162_checkbox.png "0303 162_Checkbox")<br />Výchozí zaškrtávací políčko

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `CommonControls.CheckBoxBackground` |
| Ohraničení | `CommonControls.CheckBoxBorder` |
| Text | `CommonControls.CheckBoxText` |
| Glyfy | `CommonControls.CheckBoxGlyph` |

**Zaškrtněte políčko: zakázáno stavu**  

![Zrušené zaškrtávací políčko](../../extensibility/ux-guidelines/media/0303-163_checkboxdisabled.png "0303 163_CheckboxDisabled")<br />Zrušené zaškrtávací políčko  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `CommonControls.CheckBoxBackgroundDisabled` |
| Ohraničení | `CommonControls.CheckBoxBorderDisabled` |
| Text | `CommonControls.CheckBoxTextDisabled` |
| Glyfy | `CommonControls.CheckBoxGlyphDisabled` |

**Zaškrtněte políčko: najeďte stavu**  

 ![Zaškrtněte políčko při přechodu myší](../../extensibility/ux-guidelines/media/0303-164_checkboxhover.png "0303 164_CheckboxHover")<br />Zaškrtněte políčko při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `CommonControls.CheckBoxBackgroundHover` |
| Ohraničení | `CommonControls.CheckBoxBorderHover` |
| Text | `CommonControls.CheckBoxTextHover` |
| Glyfy | `CommonControls.CheckBoxGlyphHover` |  

**Zaškrtněte políčko: stisknutí stavu**  

![Při stisknutí tlačítka zaškrtávací políčko](../../extensibility/ux-guidelines/media/0303-165_checkboxpressed.png "0303 165_CheckboxPressed")<br />Při stisknutí tlačítka zaškrtávací políčko  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `CommonControls.CheckBoxBackgroundPressed` |
| Ohraničení | `CommonControls.CheckBoxBorderPressed` |
| Text | `CommonControls.CheckBoxTextPressed` |
| Glyfy | `CommonControls.CheckBoxGlyphPressed` |  

**Zaškrtněte políčko: zaměřuje stavu**  

![Políčko cílených](../../extensibility/ux-guidelines/media/0303-166_checkboxfocused.png "0303 166_CheckboxFocused")<br />Cílených zaškrtávací políčko  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `CommonControls.CheckBoxBackgroundFocused` |
| Ohraničení | `CommonControls.CheckBoxBorderFocused` |
| Text | `CommonControls.CheckBoxTextFocused` |
| Glyfy | `CommonControls.CheckBoxGlyphFocused` |

### <a name="drop-downs-and-combo-boxes"></a>Rozevírací seznamy a pole se seznamem polí
![Vyřaďte nižší nebo pole se seznamem (červená značka)](../../extensibility/ux-guidelines/media/0303-167_dropdowncomboboxredline.png "0303 167_DropDownComboBoxRedline")<br />Vyřaďte nižší nebo pole se seznamem (červená značka)  

| Použití... | Nepoužívejte... |
| --- | --- |
| ... pro rozevírací seznamy a pole se seznamem pole v dokumentu dobře. | ... pro všechny uživatelské rozhraní, která není pole rozevíracího seznamu nebo pole se seznamem. |  
| | ... pro panel příkazů [rozevírací seznamy](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_CommandDropDown) nebo [pole se seznamem](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_CommandComboBox). |

**Rozevírací seznamy a pole se seznamem polí: výchozí stav**  

![Výchozí rozevírací nižší nebo pole se seznamem](../../extensibility/ux-guidelines/media/0303-168_dropdowncombobox.png "0303 168_DropDownComboBox")<br />Výchozí rozevírací nižší nebo pole se seznamem

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `CommonControls.ComboBoxBackground` |
| Ohraničení | `CommonControls.ComboBoxBorder` |
| Text | `CommonControls.ComboBoxText` |
| Oddělovač | `CommonControls.ComboBoxSeparator` |
| Glyfy | `CommonControls.ComboBoxGlyph` |
| Glyfy pozadí | `CommonControls.ComboBoxGlyphBackground` |

**Rozevírací seznamy a pole se seznamem polí: zakázáno stavu**  

![Zakázané rozevírací nižší nebo pole se seznamem](../../extensibility/ux-guidelines/media/0303-169_dropdowncomboboxdisabled.png "0303 169_DropDownComboBoxDisabled")<br />Zakázané rozevírací nižší nebo pole se seznamem

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `CommonControls.ComboBoxBackgroundDisabled` |
| Ohraničení | `CommonControls.ComboBoxBorderDisabled` |
| Text | `CommonControls.ComboBoxTextDisabled` |
| Oddělovač | `CommonControls.ComboBoxSeparatorDisabled` |
| Glyfy | `CommonControls.ComboBoxGlyphDisabled` |
| Glyfy pozadí | `CommonControls.ComboBoxGlyphBackgroundDisabled` |

**Rozevírací seznamy a pole se seznamem polí: najeďte stavu**  

![Vyřaďte nižší nebo pole se seznamem při přechodu myší](../../extensibility/ux-guidelines/media/0303-170_dropdowncomboboxhover.png "0303 170_DropDownComboBoxHover")<br />Vyřaďte nižší nebo pole se seznamem při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `CommonControls.ComboBoxBackgroundHover` |
| Ohraničení | `CommonControls.ComboBoxBorderHover` |
| Text | `CommonControls.ComboBoxTextHover` |
| Oddělovač | `CommonControls.ComboBoxSeparatorHover` |
| Glyfy | `CommonControls.ComboBoxGlyphHover` |
| Glyfy pozadí | `CommonControls.ComboBoxGlyphBackgroundHover` |

**Rozevírací seznamy a pole se seznamem polí: stisknutí stavu**  

![Stisknutí rozevírací nižší nebo pole se seznamem](../../extensibility/ux-guidelines/media/0303-171_dropdowncomboboxpressed.png "0303 171_DropDownComboBoxPressed")<br />Stisknutí rozevírací nižší nebo pole se seznamem  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `CommonControls.ComboBoxBackgroundPressed` |
| Ohraničení | `CommonControls.ComboBoxBorderPressed` |
| Text | `CommonControls.ComboBoxTextPressed` |
| Oddělovač | `CommonControls.ComboBoxSeparatorPressed` |
| Glyfy | `CommonControls.ComboBoxGlyphPressed` |
| Glyfy pozadí | `CommonControls.ComboBoxGlyphBackgroundPressed` |

**Rozevírací seznamy a pole se seznamem oknech položky zobrazení seznamu: stisknutí stavu**  

 ![Vyřaďte nižší nebo pole se seznamem stisknutí položky zobrazení seznamu](../../extensibility/ux-guidelines/media/0303-174_dropdowncomboboxlistview.png "0303 174_DropDownComboBoxListView")<br />Vyřaďte nižší nebo pole se seznamem stisknutí položky zobrazení seznamu  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí |  `CommonControls.ComboBoxListBackground`<br />`CommonControls.ComboBoxListBackgroundHover`<br />`CommonControls.ComboBoxListItemBackgroundPressed`<br />`CommonControls.ComboBoxListItemBackgroundFocused` |
| Ohraničení | `CommonControls.ComboBoxListBorder`<br />`CommonControls.ComboBoxListBorderHover`<br />`CommonControls.ComboBoxListBorderPressed`<br />`CommonControls.ComboBoxListBorderFocused` |
| Text položky | `CommonControls.ComboBoxListItemText`<br /> `CommonControls.ComboBoxListItemTextHover`<br />`CommonControls.ComboBoxListItemTextPressed`<br />`CommonControls.ComboBoxListItemTextFocused` |
| Stín pozadí | `CommonControls.ComboBoxListBackgroundShadow` |

**Rozevírací seznamy a pole se seznamem polí: zaměřuje stavu**  

![Vyřaďte nižší nebo pole se seznamem s fokusem](../../extensibility/ux-guidelines/media/0303-172_dropdowncomboboxfocused.png "0303 172_DropDownComboBoxFocused")<br />Vyřaďte nižší nebo pole se seznamem s fokusem

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `CommonControls.ComboBoxBackgroundFocused` |
| Ohraničení | `CommonControls.ComboBoxBorderFocused` |
| Text | `CommonControls.ComboBoxTextFocused` |
| Oddělovač | `CommonControls.ComboBoxSeparatorFocused` |
| Glyfy | `CommonControls.ComboBoxGlyphFocused` |
| Glyfy pozadí | `CommonControls.ComboBoxGlyphBackgroundFocused` |

**Rozevírací seznamy a pole se seznamem polí: výběr vstup text**  

![Výběr vstup text rozevíracího nižší nebo pole se seznamem](../../extensibility/ux-guidelines/media/0303-173_dropdowncomboboxtextinput.png "0303 173_DropDownComboBoxTextInput")<br />Vstupní výběr textu rozevírací nižší nebo pole se seznamem  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Zvýrazněte | `CommonControls.ComboBoxTextInputSelection` |

### <a name="tabular-data-grid-controls"></a>Ovládací prvky tabulková data (mřížky)  
Ovládací prvky tabulková data, také známé jako ovládací prvky mřížky, jsou běžné ovládací prvky pro sadu Visual Studio, který můžete použít k zobrazení velkých objemů dat v více sloupců. Ovládací prvky standardní tabulková data naleznete na více místech v sadě Visual Studio: okno Seznam chyb nástroje, sestavy IntelliTrace a zobrazení halda paměti, mimo jiné. Vždy použijte ovládací prvky standardní tabulková data zadaná. Ve výjimečných případech nemusí mít přístup k ovládacím prvkům standardní tabulková data. V těchto situacích používejte následující názvy tokenu zajistit, že uživatelské rozhraní je v souladu s dalšími kontrolami tabulková data v sadě Visual Studio.  

![Ovládání tabulkové data/mřížky (červená značka)](../../extensibility/ux-guidelines/media/0303-197_tabulardatagridcontrolredline.png "0303 197_TabularDataGridControlRedline")<br />Ovládání tabulkové data/mřížky (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... pro tabulkové nebo ovládací prvky mřížky. | ... pro všechny uživatelské rozhraní, které není ovládacího prvku tabulkové nebo mřížky. |

#### <a name="column-headers"></a>Záhlaví sloupců  
Záhlaví sloupců se skládají z na pozadí, ohraničení, textu nadpisu a volitelné glyfy obvykle používá při mřížka je seřazen podle sloupce.  

**Záhlaví sloupce: výchozí stav**

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Header.Default` |
| Popředí (Text) | `Environment.CommandBarTextActive` |
| Popředí (glyfy) | `Header.Glyph` |
| Ohraničení | `Header.SeparatorLine` |

**Záhlaví sloupce: najeďte stavu**

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Header.MouseOver` |
| Popředí (Text) | `Environment.CommandBarTextHover` |
| Popředí (glyfy) | `Header.MouseOverGlyph` |
| Ohraničení | `Header.SeparatorLine` |

**Záhlaví sloupce: stisknutí stavu**

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `CommonControls.CheckBoxBackgroundPressed` |
| Popředí (Text) | `CommonControls.CheckBoxBorderPressed` |
| Popředí (glyfy) | `CommonControls.CheckBoxTextPressed` |
| Ohraničení | `CommonControls.CheckBoxGlyphPressed` |

#### <a name="list-view-items"></a>Zobrazit položky seznamu  
 Zobrazit položky seznamu obsahovat na pozadí a obsah. Obsah může být text, ikonu nebo obojí.  

**Seznam položek zobrazení: výchozí stav**

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Transparentní |
| Popředí (Text) | `Environment.CommandBarTextActive` |
| Ohraničení | Žádné |

**Položky zobrazení seznamu: aktivním stavu**

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `TreeView.SelectedItemActive` |
| Popředí (Text) | `TreeView.SelectedItemActiveText` |
| Ohraničení | Žádné |

**Položky zobrazení seznamu: neaktivní stav**

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `TreeView.SelectedItemInactive` |
| Popředí (Text) | `TreeView.SelectedItemInactiveText` |
| Ohraničení | Žádné |  

### <a name="ui-text"></a>Textu uživatelského rozhraní

#### <a name="instructional-text"></a>Podle požadavků
Podle požadavků nabízí výrazné hlavní vysvětlení, co lze na stránce dialogové okno nebo dokumentu.

![Výchozí pokyny](../../extensibility/ux-guidelines/media/0303_InstructionalText.png "0303_InstructionalText.png")<br />Výchozí pokyny

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (text) | `Environment.ControlText` |

#### <a name="secondary-instructional-text"></a>Sekundární instruktážní text
Některé pokyny v dokumentu stránky s mnoha textu a ovládací prvky, používá hodnotu různých barev. To pomůže nesou, které informace se nejdůležitější a zmenšit prostor celkové hustotu prvky uživatelského rozhraní. (Viz také následující části na text nápovědy.)

![Sekundární pokyny](../../extensibility/ux-guidelines/media/0303_SecondaryInstructionalText.png "0303_SecondaryInstructionalText.png")<br />Sekundární instruktážní text

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (text) | `Environment.ControlEditHintText` |

#### <a name="hint-text"></a>Text nápovědy
Pomocný parametr text se zobrazuje v ovládacím prvku prázdný za ovládací prvek, nebo na povrchu prázdného dokumentu se uživateli zobrazí dalším postupu. Text nápovědy můžete použít s okno nebo ovládací prvek pozadí.

**Výchozí text nápovědy**

![Výchozí text nápovědy](../../extensibility/ux-guidelines/media/0303_HintText.png "0303_HintText.png")<br />Výchozí text nápovědy

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (text) | `Environment.ControlEditHintText` |

**Pomocný parametr požadovaná textu**

![Požadované text nápovědy](../../extensibility/ux-guidelines/media/0303_RequiredHintText.png "0303_RequiredHintText.png")<br />Pomocný parametr požadovaná textu

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (text) | `Environment.ControlRequiredHintText` |
| Pozadí | `Environment.ControlRequiredBackground` |

**Hledaný text ovládacího prvku pole**

> V tématu [vyhledávací pole](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_SearchBoxes) pro další tokeny barva týkající se řízení vyhledávání.

![Hledat text ovládacího prvku pole](../../extensibility/ux-guidelines/media/0303_SearchBoxControl.png "0303_SearchBoxControl.png")<br />Hledaný text ovládacího prvku pole

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (text) | `SearchControl.UnfocusedWatermarkText` |

### <a name="hyperlink"></a>Hypertextový odkaz  
Hypertextový odkaz je jeden ovládací prvek, který nemá pár popředí nebo pozadí. Ve všech případech použijte barvu popředí hypertextový odkaz, který se zobrazí správně v tmavý, šedé a bílé pozadí. Pokud nepoužíváte token barva ovládacího prvku hypertextový odkaz, zobrazí se výchozí systém barvu pro "stisknutí", který bude flash red. To je signál, že ovládací prvek není pomocí tokenu barva správné prostředí.  

![Hypertextový odkaz (červená značka)](../../extensibility/ux-guidelines/media/0303-133_hyperlinkredline.png "0303 133_HyperlinkRedline")<br />Hypertextový odkaz (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... když potřebujete vytvořit vlastní hypertextový odkaz. | ... pro všechno, co není hypertextový odkaz. |

**Hypertextový odkaz: výchozí stav**  

![Výchozí hypertextový odkaz](../../extensibility/ux-guidelines/media/0303-134_hyperlink.png "0303 134_Hyperlink")<br />Výchozí hypertextový odkaz

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (Text) | `Environment.PanelHyperlink` |

**Hypertextový odkaz: hover stavu**

![Hypertextový odkaz na hover](../../extensibility/ux-guidelines/media/0303-135_hyperlinkhover.png "0303 135_HyperlinkHover")<br />Hypertextový odkaz na přechodu.  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (Text) | `Environment.PanelHyperlinkHover` |

**Hypertextový odkaz: stav při stisknutí tlačítka**

![Při stisknutí tlačítka hyperlink](../../extensibility/ux-guidelines/media/0303-136_hyperlinkpressed.png "0303 136_HyperlinkPressed")<br />Při stisknutí tlačítka hypertextový odkaz  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (Text) | `Environment.PanelHyperlinkPressed` |

**Hypertextový odkaz: zakázané**

![Zakázané hyperlink](../../extensibility/ux-guidelines/media/0303-137_hyperlinkdisabled.png "0303 137_HyperlinkDisabled")<br />Zakázané hypertextový odkaz  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (Text) | `Environment.PanelHyperlinkDisabled` |

### <a name="infobars"></a>Infobars  
Infobars se používají k poskytují další informace o daném kontextu a vždy se zobrazí v horní části okna dokumentu nebo okno nástroje.  

![Informační panel (červená značka)](../../extensibility/ux-guidelines/media/0303-138_infobarredline.png "0303 138_InfobarRedline")<br />Informační panel (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... při vytváření vlastní infobars. | ... pro prvky uživatelského rozhraní, které nejsou podobná informačního panelu. |

**Informačním panelu: výchozí stav**

![Výchozí informační panel](../../extensibility/ux-guidelines/media/0303-139_infobar.png "0303 139_Infobar")<br />Výchozí informační panel

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `InfoBar.InfoBarBackground` |
| Popředí (Text) | `InfoBar.InfoBar` |
| Ohraničení | `InfoBar.InfoBarBorder` |

**Zavřít informační panel (&times;) tlačítko: výchozí stav**

![Výchozí zavřete informační panel (&times;) tlačítko](../../extensibility/ux-guidelines/media/0303_InfobarCloseDefault.png "0303_InfobarCloseDefault.png")<br />Výchozí zavřete informační panel (&times;) tlačítko

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `InfoBar.CloseButton` |
| Ohraničení | `InfoBar.CloseButtonBorder` |
| Glyfy | `InfoBar.CloseButtonGlyph` |

**Zavřít informační panel (&times;) tlačítko: najeďte stavu**

![Zavřít informační panel (&times;) tlačítko při přechodu myší](../../extensibility/ux-guidelines/media/0303_InfobarCloseHover.png "0303_InfobarCloseHover.png")<br />Zavřít informační panel (&times;) tlačítko při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `InfoBar.CloseButtonHover` |
| Ohraničení | `InfoBar.CloseButtonHoverBorder` |
| Glyfy | `InfoBar.CloseButtonHoverGlyph` |

**Zavřít informační panel (&times;) tlačítko: stisknutí stavu**

![Stisknutí tlačítka Zavřít informační panel (&times;) tlačítko](../../extensibility/ux-guidelines/media/0303_InfobarClosePressed.png "0303_InfobarClosePressed.png")<br />Stisknutí tlačítka Zavřít informační panel (&times;) tlačítko

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `InfoBar.CloseButtonDown` |
| Ohraničení | `InfoBar.CloseButtonDownBorder` |
| Glyfy | `InfoBar.CloseButtonDownGlyph` |

**Tlačítko hypertextový odkaz informačním panelu: výchozí stav**

![Výchozí tlačítko hypertextový odkaz informační panel](../../extensibility/ux-guidelines/media/0303_InfobarHyperlinkButtonDefault.png "0303_InfobarHyperlinkButtonDefault.png")<br />Výchozí tlačítko hypertextový odkaz informační panel

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (text) | `InfoBar.Hyperlink` |

**Tlačítko hypertextový odkaz informačním panelu: najeďte stavu**

![Tlačítko hypertextový odkaz informačního panelu při přechodu myší](../../extensibility/ux-guidelines/media/0303_InfobarHyperlinkButtonHover.png "0303_InfobarHyperlinkButtonHover.png")<br />Tlačítko hypertextový odkaz informačního panelu při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (text) | `Infobar.HyperlinkMouseOver`<br />(S podtržení) |

**Tlačítko hypertextový odkaz informačním panelu: stisknutí stavu**

![Tlačítko hypertextový odkaz informačního panelu při stisknutí tlačítka](../../extensibility/ux-guidelines/media/0303_InfobarHyperlinkButtonPressed.png "0303_InfobarHyperlinkButtonPressed.png")<br />Tlačítko hypertextový odkaz informačního panelu při stisknutí tlačítka

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (text) | `Infobar.HyperlinkMouseDown`<br />(S podtržení) |

**Hypertextový odkaz vložený informační panel (v rámci věty): výchozí stav**

![Výchozí vložené informační panel hyperlink tlačítko](../../extensibility/ux-guidelines/media/0303_InfobarHyperlinkButtonDefault.png "0303_InfobarHyperlinkButtonDefault.png")<br />Tlačítko výchozí vložené informační panel hypertextový odkaz

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (text) | `InfoBar.Hyperlink` |

**Hypertextový odkaz vložený informační panel (v rámci věty): najeďte stavu**

![Tlačítko hypertextový odkaz vložený informační panel při přechodu myší](../../extensibility/ux-guidelines/media/0303_InfobarHyperlinkInlineHover.png "0303_InfobarHyperlinkInlineHover.png")<br />Tlačítko hypertextový odkaz vložený informační panel při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (text) | `Infobar.HyperlinkMouseOver`<br />(S podtržení) |

**Hypertextový odkaz vložený informační panel (v rámci věty): stisknutí stavu**

![Tlačítko hypertextový odkaz vložený informačním panelu při stisknutí tlačítka](../../extensibility/ux-guidelines/media/0303_InfobarHyperlinkInlinePressed.png "0303_InfobarHyperlinkInlinePressed.png")<br />Stisknutí tlačítka hypertextový odkaz vložený informační panel

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (text) | `Infobar.HyperlinkMouseDown`<br />(S podtržení) |

**Tlačítko informačním panelu: výchozí stav**

![Výchozí tlačítko informační panel](../../extensibility/ux-guidelines/media/0303_InfobarButtonDefault.png "0303_InfobarButtonDefault.png")<br />Výchozí tlačítko informační panel

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `InfoBar.Button` |
| Popředí (text) | `InfoBar.Button` |
| Ohraničení | `InfoBar.ButtonBorder` |

**Tlačítko informačním panelu: najeďte stavu**

![Tlačítko informační panel při přechodu myší](../../extensibility/ux-guidelines/media/0303_InfobarButtonHover.png "0303_InfobarButtonHover.png")<br />Tlačítko informační panel při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `InfoBar.ButtonMouseOver` |
| Popředí (text) | `InfoBar.ButtonMouseOver` |
| Ohraničení | `InfoBar.ButtonMouseOverBorder` |

**Tlačítko informačním panelu: stisknutí stavu**

![Tlačítko informačním panelu při stisknutí tlačítka](../../extensibility/ux-guidelines/media/0303_InfobarButtonPressed.png "0303_InfobarButtonPressed.png")<br />Tlačítko informačním panelu při stisknutí tlačítka

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `InfoBar.ButtonMouseDown` |
| Popředí (text) | `InfoBar.ButtonMouseDown` |
| Ohraničení | `InfoBar.ButtonMouseDownBorder` |

**Tlačítko informačním panelu: zakázáno stavu**

![Tlačítko zakázané informační panel](../../extensibility/ux-guidelines/media/0303_InfobarButtonDisabled.png "0303_InfobarButtonDisabled.png")<br />Tlačítko zakázané informační panel

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `InfoBar.ButtonDisabled` |
| Popředí (text) | `InfoBar.ButtonDisabled` |
| Ohraničení | `InfoBar.ButtonDisabledBorder` |

**Tlačítko informačním panelu: zaměřuje stavu**

![Tlačítko cílených informační panel](../../extensibility/ux-guidelines/media/0303_InfobarButtonFocus.png "0303_InfobarButtonFocus.png")<br />Tlačítko cílených informační panel

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `InfoBar.ButtonFocus` |
| Popředí (text) | `InfoBar.ButtonFocus` |
| Ohraničení | `InfoBar.ButtonFocusBorder` |

### <a name="scroll-bars"></a>Posuvníky  
Posuvníky jsou ve pomocí prostředí Visual Studio a nebudete muset být motivu. Ale můžete rozhodnout, že chcete využít barvy používané v posuvníky tak, aby uživatelské rozhraní vždycky zobrazila konzistentní s tuto část prostředí Visual Studio.  

![Posuvník (červená značka)](../../extensibility/ux-guidelines/media/0303-140_scrollbarredline.png "0303 140_ScrollbarRedline")<br />Posuvník (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... při vytváření uživatelského rozhraní, kterou chcete porovnat posuvníky Visual Studio. | ... pro všechno, co nechcete vždy odpovídat posuvníku uživatelského rozhraní. |

**Posuvník: výchozí stav**  

![Výchozí posuvníku](../../extensibility/ux-guidelines/media/0303-141_scrollbar.png "0303 141_Scrollbar")<br />Výchozí posuvníku

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Posuvník | `Environment.ScrollBarBackground` |
| Popředí (Flash) | `Environment.ScrollBarThumbBackground` |

**Posuvník: najeďte stavu**

![Posuvník při přechodu myší](../../extensibility/ux-guidelines/media/0303-143_scrollbarhover.png "0303 143_ScrollbarHover")<br />Posuvník při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Posuvník | `Environment.ScrollBarBackground` |
| Popředí (Flash) | `Environment.ScrollBarThumbMouseOverBackground` |

*Posuvník: stisknutí stavu**

![Při stisknutí tlačítka posuvníku](../../extensibility/ux-guidelines/media/0303-145_scrollbarpressed.png "0303 145_ScrollbarPressed")<br />Stisknutí posuvníku  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Posuvník | `Environment.ScrollBarBackground` |
| Popředí (Flash) | `Environment.ScrollBarThumbPressedBackground` |

**Šipky posuvníku: výchozí stav**  

![Výchozí posouvací panelu šipky](../../extensibility/ux-guidelines/media/0303-142_scrollbararrow.png "0303 142_ScrollbarArrow")<br />Výchozí posouvací panelu šipky

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ScrollBarArrowBackground`<br />(Nastavte na stejné barvy jako posuvníku.) |
| Popředí (glyfy) | `Environment.ScrollBarArrowGlyph` |

**Šipky posuvníku: najeďte stavu**

![Posuvníku šipku při přechodu myší](../../extensibility/ux-guidelines/media/0303-144_scrollbararrowhover.png "0303 144_ScrollbarArrowHover")<br />Posouvací šipky panelu při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ScrollBarArrowMouseOverBackground`<br />(Nastavte na stejné barvy jako posuvníku.) |
| Popředí (glyfy) | `Environment.ScrollBarArrowGlyphMouseOver` |

**Šipky posuvníku: stisknutí stavu**  

![Při stisknutí tlačítka posouvací šipky panelu](../../extensibility/ux-guidelines/media/0303-146_scrollbararrowpressed.png "0303 146_ScrollbarArrowPressed")<br />Stisknutí posouvací šipky panelu

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ScrollBarArrowPressedBackground`<br />(Nastavte na stejné barvy jako posuvníku.) |
| Popředí (glyfy) | `Environment.ScrollBarArrowGlyphPressed` |

### <a name="BKMK_SearchBoxes"></a>Hledání oken  
Pokud je to možné, použijte běžného ovládacího prvku vyhledávání poskytované prostředí Visual Studio. Barvy pole hledání nebyly nalezeny v kategorii "SearchControl" v **ShellColors.pkgdef** souboru, který obsahuje token názvy pro vstupní pole, akce tlačítka, rozevírací tlačítko a rozevírací nabídky.  

Vyhledávací pole může být jedna z několika stavů, některé z nich se vzájemně vylučují:  

-   "Zaměřuje" nebo "nezaostřená" odkazuje na to, zda je kurzor v textovém poli.  

-   "Aktivní" nebo "neaktivní" odkazuje na tom, jestli má uživatel vstupu vyhledávací dotaz v textovém poli.  

-   "Hover" znamená, že uživatel má moused přes do vyhledávacího pole pomocí myši (Tento stav nahradí všechny ostatní stavy).  

-   "Zakázáno" znamená, že funkce vyhledávání je vypnuté pro aktuální kontext.  

![Vyhledávací pole (červená značka)](../../extensibility/ux-guidelines/media/0303-110_searchboxredline.png "0303 110_SearchBoxRedline")<br />Vyhledávací pole (červená značka)  

| Použití... | Nepoužívejte... |
| --- | --- |
| ... při navrhování vlastních vyhledávací pole. | ... pro všechno, co není vyhledávací pole. |
| | pro všechny položky, které nechcete vždy odpovídají hledání... pole uživatelského rozhraní. |

**Zaměřuje vstupní pole hledání**

![Vstupní pole cílených vyhledávání](../../extensibility/ux-guidelines/media/0303-111_searchinputfieldfocused.png "0303 111_SearchInputFieldFocused")<br />Zaměřuje vstupní pole hledání  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `SearchControl.FocusedBackground` |
| Popředí (Text) | `SearchControl.FocusedBackground` |
| Ohraničení | `SearchControl.FocusedBorder` |
| Oddělovač | `SearchControl.FocusedDropDownSeparator` |

**Vstupní pole nezaostřená, aktivní hledání**

![Vstupní pole hledání nezaostřená](../../extensibility/ux-guidelines/media/0303-114_searchinputfieldunfocused.png "0303 114_SearchInputFieldUnfocused")<br />Vstupní pole nezaostřená, aktivní hledání

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `SearchControl.SearchActiveBackground` |
| Popředí (Text) | `SearchControl.SearchActiveBackground` |
| Ohraničení | `SearchControl.UnfocusedBorder` |
| Oddělovač | `SearchControl.DropDownSeparator` |

**Vstupní pole hledání nezaostřená, neaktivní**

![Vstupní pole hledání nezaostřená, neaktivní](../../extensibility/ux-guidelines/media/0303-114-1_searchinputfieldunfocusedinactive.png "0303. 114 1_SearchInputFieldUnfocusedInactive")<br />Vstupní pole hledání nezaostřená, neaktivní  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `SearchControl.Unfocused` |
| Popředí (Text) | `SearchControl.Unfocused` |
| Ohraničení | `SearchControl.UnfocusedBorder` |
| Oddělovač | `SearchControl.DropDownSeparator` |

**Zvýrazněná vyhledávání vstupní pole (pouze text)**

![Vstupní pole zvýrazněné vyhledávání](../../extensibility/ux-guidelines/media/0303-120_searchinputfieldhighlight.png "0303 120_SearchInputFieldHighlight")<br />Vstupní pole zvýrazněné vyhledávání

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `SearchControl.Selection` |
| Popředí (Text) | `SearchControl.FocusedBackground` |
| Ohraničení | Žádné |
| Oddělovač | `SearchControl.FocusedDropDownSeparator` |

**Vstupní pole zakázáno vyhledávání**

![Zakázáno hledat vstupní pole](../../extensibility/ux-guidelines/media/0303-121_searchinputfielddisabled.png "0303 121_SearchInputFieldDisabled")<br />Vstupní pole zakázáno vyhledávání

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `SearchControl.Disabled` |
| Popředí (Text) | `SearchControl.Disabled` |
| Ohraničení | `SearchControl.DisabledBorder` |
| Oddělovač | `SearchControl.DropDownSeparator` |

**Tlačítko akce cílené hledání.**

![Tlačítko akce hledání zaměřuje](../../extensibility/ux-guidelines/media/0303-112_searchactionbuttonfocused.png "0303 112_SearchActionButtonFocused")<br />Tlačítko akce cílené hledání.

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Žádné |
| Popředí (glyfy vyhledávání) | `SearchControl.SearchGlyph` |
| Popředí (Zastavit glyfy) | `SearchControl.StopGlyph` |
| Popředí (Vymazat glyfy) | `SearchControl.ClearGlyph` |
| Ohraničení | Není k dispozici |

**Tlačítko akce nezaostřená vyhledávání**  

![Tlačítko akce nezaostřená vyhledávání](../../extensibility/ux-guidelines/media/0303-115_searchactionbuttonunfocused.png "0303 115_SearchActionButtonUnfocused")<br />Tlačítko akce nezaostřená vyhledávání

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Není k dispozici |
| Popředí (glyfy vyhledávání) | `SearchControl.SearchGlyph` |
| Popředí (Zastavit glyfy) | `SearchControl.StopGlyph` |
| Popředí (Vymazat glyfy) | `SearchControl.ClearGlyph` |
| Ohraničení | Není k dispozici |

**Stisknutí tlačítka akce vyhledávání**

![Tlačítko akce při stisknutí tlačítka Hledat](../../extensibility/ux-guidelines/media/0303-116-1_searchactionbuttonpressed.png "0303. 116 1_SearchActionButtonPressed")<br />Stisknutí tlačítka akce vyhledávání

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `SearchControl.ActionButtonMouseDown` |
| Popředí (glyfy) | `SearchControl.ActionButtonMouseDownGlyph` |
| Ohraničení | `SearchControl.ActionButtonMouseDownBorder` |

**Tlačítko akce zakázané vyhledávání**

![Tlačítko akce vyhledávání zakázáno](../../extensibility/ux-guidelines/media/0303-122_searchactionbuttondisabled.png "0303 122_SearchActionButtonDisabled")<br />Tlačítko akce zakázané vyhledávání

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Žádné |
| Popředí (glyfy) | `SearchControl.ActionButtonDisabledGlyph` |
| Ohraničení | Žádné |

**Rozevírací tlačítko cílené hledání.**

![Cílené hledání rozevírací tlačítko](../../extensibility/ux-guidelines/media/0303-113_searchdropdownbuttonfocused.png "0303 113_SearchDropdownButtonFocused")<br />Rozevírací tlačítko cílené hledání.

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `SearchControl.FocusedDropDownButton` |
| Popředí (glyfy) | `SearchControl.FocusedDropDownButtonGlyph` |
| Ohraničení | `SearchControl.FocusedDropDownButtonBorder` |

**Rozevírací tlačítko nezaostřená vyhledávání**

![Nezaostřená vyhledávání rozevírací tlačítko](../../extensibility/ux-guidelines/media/0303-116_searchdropdownbuttonunfocused.png "0303 116_SearchDropdownButtonUnfocused")<br />Rozevírací tlačítko nezaostřená vyhledávání

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `SearchControl.UnfocusedDropDownButton` |
| Popředí (glyfy) | `SearchControl.UnfocusedDropDownButtonGlyph` |
| Ohraničení | `SearchControl.UnfocusedDropDownButtonBorder` |

**Bylo stisknuto tlačítko vyhledat rozevíracího seznamu**

![Při stisknutí tlačítka vyhledávání rozevírací tlačítko](../../extensibility/ux-guidelines/media/0303-116-2_searchdropdownbuttonpressed.png "0303. 116 2_SearchDropdownButtonPressed")<br />Bylo stisknuto tlačítko vyhledat rozevíracího seznamu

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `SearchControl.MouseDownDropDownButton` |
| Popředí (glyfy) | `SearchControl.MouseDownDropDownButtonGlyph` |
| Ohraničení | `SearchControl.MouseDownDropDownButtonBorder` |

**Zakázané vyhledávání rozevírací tlačítko**

![Zakázat možnost vyhledávání rozevírací tlačítko](../../extensibility/ux-guidelines/media/0303-123_searchdropdownbuttondisabled.png "0303 123_SearchDropdownButtonDisabled")<br />Zakázané vyhledávání rozevírací tlačítko

| Prvek | Název tokenu: Category.color |
| --- | --- |  
| Pozadí | Žádné |
| Popředí (glyfy) | `SearchControl.DisabledDownButtonGlyph` |
| Ohraničení | Žádné |

#### <a name="search-drop-down-lists"></a>Rozevírací seznamy hledání  
Vyhledávací pole rozevírací nabídky se může být složité něco víc než ostatní rozevíracích nabídek v sadě Visual Studio. "Návrhy hledání" a "možnosti vyhledávání" oddílů se mohou objevit samostatně nebo společně v nabídce, a každé z nich je barevný samostatně. Řádek také odděluje tyto dvě části, když se objeví společně a ohraničení kolem celého rozevírací nabídce.  

![Rozevírací seznam hledání (červená značka)](../../extensibility/ux-guidelines/media/0303-124_searchdropdownredline.png "0303 124_SearchDropdownRedline")<br />Rozevírací seznam hledání (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... při vytváření rozevíracího seznamu vlastní vyhledávání. | ... pro rozevírací seznamy, které se zobrazují v jiném kontextu. |
| ... správné názvy tokenu správný seznam součástí. | ... v libovolné kombinace pozadí nebo popředí, jiné než která byla specifikována. |

**Vyhledávání prvku rozevíracího seznamu**

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Ohraničení | `SearchControl.PopupBorder` |
| Oddělovač | `SearchControl.PopupSectionHeaderSeparator` |
| stínové | `Environment.DropShadowBackground` |

**Navrhované hledání: výchozí stav**

![Výchozí návrhy vyhledávání](../../extensibility/ux-guidelines/media/0303-125_searchsuggested.png "0303 125_SearchSuggested")<br />Výchozí návrhy vyhledávání  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `SearchControl.PopupItemsListBackgroundGradientBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `SearchControl.PopupItemText` |

**Navrhované hledání: najeďte stavu**

![Navrhované hledání při přechodu myší](../../extensibility/ux-guidelines/media/0303-128_searchsuggestedhover.png "0303 128_SearchSuggestedHover")<br />Návrhy vyhledávání v přechodu.

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `SearchControl.PopupControlMouseOverBackgroundGradientBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `SearchControl.PopupMouseOverItemText` |
| Ohraničení | `SearchControl.PopupControlMouseOverBorder` |

**Možnosti vyhledávání: výchozí stav**

![Hledání políčko](../../extensibility/ux-guidelines/media/0303-126_searchcheckbox.png "0303 126_SearchCheckbox")<br />Výchozí možnosti vyhledávání (zaškrtávací políčko)  

![Možnosti vyhledávání](../../extensibility/ux-guidelines/media/0303-127_searchoptions.png "0303 127_SearchOptions")<br />Výchozí možnosti vyhledávání (odkaz)  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `SearchControl.PopupSectionBackgroundGradientBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (políčko text) | `SearchControl.PopupCheckboxText` |
| Popředí (text odkazu) | `SearchControl.PopupButtonText` |
| Pozadí záhlaví | `SearchControl.PopupSectionHeaderGradientBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (text záhlaví) | `SearchControl.PopupSectionHeaderText` |

**Možnosti vyhledávání: najeďte stavu**

![Možnosti (zaškrtávací políčko) vyhledávání na hover](../../extensibility/ux-guidelines/media/0303-129_searchcheckboxhover.png "0303 129_SearchCheckboxHover")<br />Možnosti hledání (zaškrtávací políčko) při přechodu myší  

![Možnosti (odkaz) vyhledávání na hover](../../extensibility/ux-guidelines/media/0303-130_searchoptionshover.png "0303 130_SearchOptionsHover")<br />Možnosti hledání (odkaz) při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `SearchControl.PopupControlMouseOverBackgroundGradientBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (políčko text) | `SearchControl.PopupCheckboxMouseDownText` |
| Popředí (text odkazu) | `SearchControl.PopupButtonMouseDownText` |
| Ohraničení | `SearchControl.PopupControlMouseOverBorder` |

**Možnosti vyhledávání: stisknutí stavu**  

![Možnosti hledání (zaškrtávací políčko) stisknutí](../../extensibility/ux-guidelines/media/0303-131_searchsuggestedpressed.png "0303 131_SearchSuggestedPressed")<br />Stisknutí možností hledání (zaškrtávací políčko)   

![Možnosti hledání (odkaz) stisknutí](../../extensibility/ux-guidelines/media/0303-132_searchoptionspressed.png "0303 132_SearchOptionsPressed")<br />Stisknutí možností hledání (odkaz)  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Zaškrtněte políčko pozadí | `SearchControl.PopupControlMouseDownBackgroundGradientBegin`<br />`SearchControl.PopupControlMouseDownBackgroundGradientEnd`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (políčko text) | `SearchControl.PopupCheckboxMouseDownText` |
| Odkaz pozadí | `SearchControl.PopupButtonMouseDownBackgroundGradientBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (text odkazu) | `SearchControl.PopupButtonMouseDownText` |

###  <a name="BKMK_TreeView"></a>Zobrazení stromu  
Několik nástroj windows, včetně Průzkumníku řešení, Průzkumníka serveru a zobrazení tříd implementovat hierarchická organizace schéma jejichž barvy jsou řízeny názvy barev v `TreeView` kategorie. Všechny položky v zobrazení stromu mít barvy pozadí a text. Položky, které mít člověk vnořené podřízené elementy mají rovněž glyfů, které indikují rozbalit nebo sbalit položky.  

![Stromové zobrazení (červená značka)](../../extensibility/ux-guidelines/media/0303-147_treeviewredline.png "0303 147_TreeViewRedline")<br />Stromové zobrazení (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... kdekoli potřebujete implementovat hierarchické zobrazení organizace. | ... pro všechno, co není podobná stromové zobrazení. |
| | ... v libovolné kombinace pozadí nebo popředí, jiné než která byla specifikována. |

**Položka stromu zobrazení: výchozí stav**

![Položka zobrazení stromu výchozí](../../extensibility/ux-guidelines/media/0303-148_treeview.png "0303 148_TreeView")<br />Výchozí položky zobrazení stromu

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `TreeView.Background` |
| Popředí (Text) | `TreeView.Background` |
| Popředí (glyfy) | `TreeView.Glyph` |
| Ohraničení | Žádné |

**Položka stromu zobrazení: najeďte stavu**

![Položka stromu zobrazení při přechodu myší](../../extensibility/ux-guidelines/media/0303-149_treeviewhover.png "0303 149_TreeViewHover")<br />Položka stromu zobrazení při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `TreeView.Background` |  
| Popředí (Text) | `TreeView.Background` |
| Popředí (glyfy) | `TreeView.GlyphMouseOver` |
| Ohraničení | Žádné |

**Položka stromu zobrazení: přetáhněte přes stavu**

![Stromové zobrazení položky přetáhněte přes](../../extensibility/ux-guidelines/media/0303-150_treeviewdragover.png "0303 150_TreeViewDragOver")<br />Položka stromu zobrazení na přetáhněte přes  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `TreeView.DragOverItem` |
| Popředí (Text) | `TreeView.DragOverItem` |
| Popředí (glyfy) | `TreeView.DragOverItemGlyph` |
| Ohraničení | Žádné |

**Položka stromu zobrazení: vybraná, zaměřuje stavu**

![Vybrané a zaměřuje položky zobrazení stromu](../../extensibility/ux-guidelines/media/0303-151_treeviewfocused.png "0303 151_TreeViewFocused")<br />Položka stromu vybrané a zaměřují se zobrazení

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `TreeView.SelectedItemActive` |
| Popředí (Text) | `TreeView.SelectedItemActive` |
| Popředí (glyfy) | `TreeView.SelectedItemActiveGlyph` |
| Ohraničení | `TreeView.FocusVisualBorder` |

**Položka stromu zobrazení: vybrané, nezaostřená stavu**  

![Položka stromu vybrané a nezaostřená zobrazení](../../extensibility/ux-guidelines/media/0303-152_treeviewunfocused.png "0303 152_TreeViewUnfocused")<br />Položka stromu vybrané a nezaostřená zobrazení

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `TreeView.SelectedItemInactive` |
| Popředí (Text) | `TreeView.SelectedItemInactive` |
| Popředí (glyfy) | `TreeView.SelectedItemInactiveGlyph` |
| Ohraničení | Žádné |

**Položka stromu zobrazení: při přechodu myší, vybrán a zaměřuje stavu**

![Vybrané a zaměřuje položka stromového zobrazení na hover](../../extensibility/ux-guidelines/media/0303-153_treeviewfocusedhover.png "0303 153_TreeViewFocusedHover")<br />Položka zobrazení stromu vybrané a zaměřují se při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `TreeView.SelectedItemActive` |
| Popředí (Text) | `TreeView.SelectedItemActive` |
| Popředí (glyfy) | `TreeView.SelectedItemActiveGlyphMouseOver` |
| Ohraničení | `TreeView.FocusVisualBorder` |

**Položka stromu zobrazení: aktivované, vybrané a nezaostřená stavu**

![Položka stromu vybrané a nezaostřená zobrazení při přechodu myší](../../extensibility/ux-guidelines/media/0303-154_treeviewunfocusedhover.png "0303 154_TreeViewUnfocusedHover")<br />Položka stromu vybrané a nezaostřená zobrazení při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `TreeView.SelectedItemInactive` |
| Popředí (Text) | `TreeView.SelectedItemInactive` |
| Popředí (glyfy) | `TreeView.SelectedItemActiveGlyphMouseOver` |
| Ohraničení | Žádné |

## <a name="shell-appearance"></a>Vzhled prostředí

### <a name="background"></a>Pozadí  
Na pozadí prostředí se skládá ze dvou vrstev. Vrstva dolní představuje plnou barvou, které pokrývá celý IDE. Horní vrstvě odpovídá pod příkaz police a mezi kanály automaticky skrýt okna nástroje na levé a pravé hrany rozhraní IDE. Horní a dolní vrstvy pozadí jsou nastaveny na stejné barvy ve tmavý a světlý motivů.  

![Visual Studio shell pozadí (červená značka)](../../extensibility/ux-guidelines/media/0303-187_shellbackgroundredline.png "0303 187_ShellBackgroundRedline")<br />Visual Studio shell pozadí (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... pro míst, kde chcete porovnat na pozadí prostředí Visual Studio. | ... jako výplň pro míst, na které nejsou pozadí plochy. |
| | ... jako pozadí umístit na popředí elementy. |

**Dolní vrstvy prostředí vzhledu**

| Prvek | Název tokenu: Category.color |
| --- | --- |  
| Pozadí | `Environment.EnvironmentBackground` |

**Vzhled prostředí horní vrstvě**

> Přechodu zastaví nastaven na stejnou hodnotu barev v aplikaci Visual Studio 2013 tmavý a světlý motivů.

| Prvek | Název tokenu: Category.color |
| --- | --- |  
| Pozadí | `Environment.EnvironmentBackgroundGradientBegin`<br />`Environment.EnvironmentBackgroundGradientEnd`<br />`Environment.EnvironmentBackgroundGradientMiddle1`<br />`Environment.EnvironmentBackgroundGradientMiddle2` |  

### <a name="command-shelf"></a>Příkaz police  
Dvě sady tokenu názvy se používají pro pozadí police příkaz: jedno nastaveno pro kde je umístěna panelu nabídek a jeden pro kde panely příkazů nacházejí. Skupinu panelu konkrétní příkaz má svou vlastní hodnoty barvu pozadí, které jsou podrobněji popsána v části "panel příkazů". Nabídky panelu a příkaz panelu textu je popsané v části panelu nabídek a příkazů, v uvedeném pořadí.  

![Visual Studio příkaz police (červená značka)](../../extensibility/ux-guidelines/media/0303-188_commandshelfredline.png "0303 188_CommandShelfRedline")<br />Visual Studio příkaz police (červená značka)  

| Použití... | Nepoužívejte... |
| --- | --- |
| ... v oblastech, kde umístit nabídek a panelů nástrojů. | ... pro oblasti, které nejsou podobná police příkaz. |
|... s kombinací název tokenu správné pozadí nebo popředí. | |

**Příkaz police nabídek**

> Přechodu zastaví nastaven na stejnou hodnotu barev v aplikaci Visual Studio 2013 tmavý a světlý motivů.

| Prvek | Název tokenu: Category.color |
| --- | --- |  
| Pozadí | `Environment.CommandShelfHighlightGradientBegin`<br /><br />`Environment.CommandShelfHighlightGradientMiddle`<br />`Environment.CommandShelfHighlightGradientEnd` |

** Příkaz police příkazového řádku **

> Přechodu zastaví nastaven na stejnou hodnotu barev v aplikaci Visual Studio 2013 tmavý a světlý motivů.

| Prvek | Název tokenu: Category.color |
| --- | --- |  
| Pozadí | `Environment.CommandShelfBackgroundGradientBegin`<br />`Environment.CommandShelfBackgroundGradientMiddle`<br />`Environment.CommandShelfBackgroundGradientEnd` |

## <a name="manifest-designer"></a>Návrhář manifestu  
Návrhář manifestu byla vytvořena jako způsob, jak bylo snazší upravit soubor manifestu v projektech pro systém Windows 8 a Windows Phone 8. Zatímco je k dispozici pro využívání žádné sdílené framework, může být vhodné pro vás tak, aby odpovídaly návrh rozložení a barvy orientaci/navigační karty a celková struktura. Další informace o rozložení. Podrobnosti najdete v tématu [rozložení pro sadu Visual Studio](../../extensibility/ux-guidelines/layout-for-visual-studio.md).  

![Návrhář manifestu (červená značka)](../../extensibility/ux-guidelines/media/0303-175_manifestdesignerredline.png "0303 175_ManifestDesignerRedline")<br />Návrhář manifestu (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... pro návrháře, které jsou podobné návrháře manifestu. | ... Pokud máte víc než 6 karty. |
| místo použití běžných ovládacích prvků karty v horní části editoru v tomto dokumentu... i. | ... pro všechny uživatelské rozhraní, které není struktuře návrháře manifestu. |

**Vybraná karta manifestu Návrhář: výchozí stav**

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `ManifestDesigner.TabActive` |
| Ohraničení | Žádné |

**Manifestu podokně vybrané popis Návrhář: výchozí stav**

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `ManifestDesigner.DescriptionPane` |

**Manifestu Návrhář vybraného obsahu stránce: výchozí stav**

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `ManifestDesigner.Background` |
| Dialogové okno Pomocník textu | `ManifestDesigner.WatermarkText`<br />(Tento název tokenu neodpovídá jeho funkce.) |

**Karta manifestu Návrhář: zrušit stavu**

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `ManifestDesigner.Tab.Inactive` |

**Karta manifestu Návrhář: najeďte stavu**

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `ManifestDesigner.Tab.Mouseover` |

## <a name="command-structures"></a>Příkaz struktury  

###  <a name="BKMK_CommandMenus"></a>Nabídky  
Nabídky dochází na několika místech v sadě Visual Studio: panelu přejděte z hlavní nabídky, vložených v dokumentu nebo nástroj windows nebo na klikněte pravým tlačítkem na různých místech v celém rozhraní IDE. Implementace nabídky přidružené další prvky uživatelského rozhraní, jsou popsané v části pro odpovídající element. Vždy byste měli používat standardní nabídky implementace poskytované prostředí Visual Studio. Ve výjimečných případech však nemusí mít přístup k standardní nabídky Visual Studio. V těchto situacích používejte následující názvy tokenu zajistit, že uživatelské rozhraní je v souladu s jiné nabídky v sadě Visual Studio.  

![Visual Studio nabídky (červená značka)](../../extensibility/ux-guidelines/media/0303-000_menuredline.png "0303 000_MenuRedline")<br />Visual Studio nabídky (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... když potřebujete vytvořit vlastní nabídku.| ... barvu pozadí samostatně. Vždy používejte kombinaci pozadí nebo popředí jako zadaný. |
| ... Pokud máte nové komponenty uživatelského rozhraní, která se má zjistit shoda v sadě Visual Studio nabídkách.| |

#### <a name="menu-titles"></a>Názvy nabídek  
Nadpisy nabídky obsahovat na pozadí, ohraničení a textu nadpisu, jakož i volitelné glyf, obvykle v případě, že v nabídce se nachází v řádku nabídek.  

![Název nabídky (červená značka)](../../extensibility/ux-guidelines/media/0303-001_menutitleredline.png "0303 001_MenuTitleRedline")<br />Název nabídky (červená značka)  

| Použití... | Nepoužívejte... |
| --- | --- |
| ... vždy, když vytváříte název vlastní nabídky. | ... pro všechny položky, které nechcete vždy odpovídat názvu nabídky. |
| | ... v libovolné kombinace pozadí nebo popředí, jiné než která byla specifikována. |

**Název nabídky: výchozí stav**

![Výchozí název nabídky](../../extensibility/ux-guidelines/media/0303-002_menutitledefault.png "0303 002_MenuTitleDefault")<br />Výchozí název nabídky

![Výchozí název nabídky glyfem](../../extensibility/ux-guidelines/media/0303-003_menutitlewithglyphdefault.png "0303 003_MenuTitleWithGlyphDefault")<br />Výchozí název nabídky glyfem

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Žádné |
| Popředí (text) | `Environment.CommandBarTextActive` |
| Popředí (glyfy) | `Environment.CommandBarMenuGlyph` |
| Ohraničení | Žádné |

**Název nabídky: najeďte stavu**  

![Název nabídky při přechodu myší](../../extensibility/ux-guidelines/media/0303-004_menutitlehover.png "0303 004_MenuTitleHover")<br />Název nabídky při přechodu myší  

![Název nabídky glyfem při přechodu myší](../../extensibility/ux-guidelines/media/0303-005_menutitlewithglyphhover.png "0303 005_MenuTitleWithGlyphHover")<br />Název nabídky glyfem při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.CommandBarMouseOverBackgroundBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (text) | `Environment.CommandBarTextHover` |
| Popředí (glyfy) | `Environment.CommandBarMenuMouseOverGlyph` |  
| Ohraničení | `Environment.CommandBarBorder` |

**Název nabídky: stisknutí stavu**  

![Stisknutí tlačítka nabídky název](../../extensibility/ux-guidelines/media/0303-006_menutitlepressed.png "0303 006_MenuTitlePressed")<br />Název při stisknutí tlačítka nabídky

![Stisknutí tlačítka nabídky Název glyfy](../../extensibility/ux-guidelines/media/0303-007_menutitlewithglyphpressed.png "0303 007_MenuTitleWithGlyphPressed")<br />Stisknutí tlačítka nabídky Název glyfy

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.CommandBarMenuBackgroundGradientBegin`<br/>(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.CommandBarTextActive` |
| Popředí (glyfy) | `Environment.CommandBarMenuMouseDownGlyph` |
| Ohraničení | `Environment.CommandBarMenuBorder`<br />(Jenom levé, horní a pravé straně.) |  

**Název nabídky: zakázáno stavu**  

![Zakázané název nabídky glyfem](../../extensibility/ux-guidelines/media/0303-008_menutitlewithglyphdisabled.png "0303 008_MenuTitleWithGlyphDisabled")<br />Název zakázané nabídky glyfem

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Žádné |
| Popředí (Text) | `Environment.CommandBarTextInactive` |
| Popředí (glyfy) | `Environment.CommandBarTextInactive` |
| Ohraničení | Žádné |

#### <a name="menu-items"></a>Položky nabídky
Položku jednotlivé nabídky se skládá z nabídky text a volitelné ikony, zaškrtněte políčko nebo dílčí glyfů. Jeho pozadí a text. Změna barvy při přechodu myší. Tento token barva je pár pozadí nebo popředí.  

![Položky nabídky červeně označit](../../extensibility/ux-guidelines/media/0303-009_menuitemredline.png "0303 009_MenuItemRedline")  

| Použití... | Nepoužívejte...  |
|---|---|
| ... pro všechny rozevíracího seznamu, je spuštěno z nabídek nebo na panelu příkazů. | ... pro rozevíracím seznamu se v jiném kontextu. |
| | ... v libovolné kombinace pozadí nebo popředí, jiné než která byla specifikována. |

**Položky nabídky: výchozí stav**

![Výchozí položky nabídky](../../extensibility/ux-guidelines/media/0303-010_menudefault.png "0303 010_MenuDefault")<br />Výchozí položky nabídky  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.CommandBarMenuBackgroundGradientBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.CommandBarTextActive` |
| Popředí (dílčí glyfy) | `Environment.CommandBarMenuSubmenuGlyph` |
| Ohraničení | `Environment.CommandBarMenuBorder` |
| Ikona kanál pozadí | `Environment.CommandBarMenuIconBackground` |
| Oddělovač | `Environment.CommandBarMenuSeparator` |
| stínové | `Environment.DropShadowBackground` |

**Položky nabídky: zaškrtnutí a vybrat stavy**  

![Nabídky zaškrtnutí](../../extensibility/ux-guidelines/media/0303-011_menuchecked.png "0303 011_MenuChecked")<br />Položky nabídky zaškrtnuté

![Nabídky vybrané](../../extensibility/ux-guidelines/media/0303-012_menuselected.png "0303 012_MenuSelected")<br />Vybrané položky nabídky    

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Značky zaškrtnutí | `Environment.CommandBarCheckBox` |  
| Pozadí značky zaškrtnutí | `Environment.CommandBarSelectedIcon` |  
| Ikona pozadí | `Environment.CommandBarSelected` |
| Ikona ohraničení | `Environment.CommandBarSelectedBorder` |

**Položky nabídky: najeďte stavu**  

![Nabídky hover](../../extensibility/ux-guidelines/media/0303-013_menuhover.png "0303 013_MenuHover")<br />Položky nabídky při přechodu myší

![Nabídky hover zaškrtnutí](../../extensibility/ux-guidelines/media/0303-014_menuhoverchecked.png "0303 014_MenuHoverChecked")<br />Zaškrtnuté položky nabídky při přechodu myší

![Nabídky hover vybrané](../../extensibility/ux-guidelines/media/0303-015_menuhoverselected.png "0303 015_MenuHoverSelected")<br />Vybrané položky nabídky při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.CommandBarMenuItemMouseOver` |
| Popředí (Text) | `Environment.CommandBarMenuItemMouseOver` |
| Popředí (dílčí glyfy) | `Environment.CommandBarMenuMouseOverSubmenuGlyph` |
| Značky zaškrtnutí | `Environment.CommandBarCheckBoxMouseOver` |
| Pozadí značky zaškrtnutí | `Environment.CommandBarHoverOverSelectedIcon` |
| Ikona pozadí | `Environment.CommandBarHoverOverSelected` |
| Ikona ohraničení | `Environment.CommandBarHoverOverSelectedIconBorder` |

**Položky nabídky: zakázáno stavu**  

![Nabídky zakázáno](../../extensibility/ux-guidelines/media/0303-016_menudisabled.png "0303 016_MenuDisabled")<br />Zakázaná položka nabídky

![Nabídka zakázat možnost zkontrolovat](../../extensibility/ux-guidelines/media/0303-017_menudisabledchecked.png "0303 017_MenuDisabledChecked")<br />Zakázaná položka nabídky s značky zaškrtnutí

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Popředí (Text) | `Environment.CommandBarTextInactive` |
| Popředí (dílčí glyfy) | `Environment.CommandBarMenuSubmenuGlyph` |
| Značky zaškrtnutí | `Environment.CommandBarCheckBoxDisabled` |
| Pozadí značky zaškrtnutí | `Environment.CommandBarSelectedIconDisabled` |

### <a name="command-bars"></a>Panely příkazů  
Panelu příkazů můžete zobrazit na více místech v prostředí Visual Studio IDE, zejména příkaz police a embedded v nástroji nebo okna dokumentu.  

Obecně platí vždy používejte standardní příkaz implementace panelu poskytované prostředí Visual Studio. Použití standardní mechanismus zajišťuje, že všechny podrobnosti o visual se zobrazí správně a že interaktivní prvky, budou chovat konzistentní s dalšími kontrolami příkazového řádku Visual Studio. Ale v případě potřeby můžete vytvořit vlastní panel příkazů, zajistěte, aby vám stylů správně pomocí následující názvy tokenu.  

![Červená linka panel příkazů](../../extensibility/ux-guidelines/media/0303-018_commandbarredline.png "0303 018_CommandBarRedline")<br />Panel příkazů (červená značka)  

![Tlačítko přetečení červeně označit](../../extensibility/ux-guidelines/media/0303-019_overflowbuttonredline.png "0303 019_OverflowButtonRedline")<br />Tlačítko přetečení (červená značka)  

| Použití... | Nepoužívejte... |
| --- | --- |
| ... v místech, kde je nutné panelu příkazů embedded, ale není možné použít standardní implementace panelu příkaz Visual Studio. | ... pro prvky uživatelského rozhraní, které nejsou podobné na panelu příkazů. |
| | ... pro součásti panelu příkaz než pro který tokenu názvy jsou určené. |

#### <a name="command-bar-groups"></a>Příkaz panelu skupiny  
Skupinu příkazového řádku se skládá z sadu související ovládací prvky příkazového řádku a může obsahovat libovolný počet tlačítek, rozdělení tlačítka, rozevírací nabídky, pole se seznamem nebo nabídky. Barvy pro tyto ovládací prvky jsou řízená tokenu názvy a jsou jednotlivě jinde popsané v této příručce. Oddělovací čáry slouží k rozdělení skupinu příkazového řádku na související podskupiny.  

![Skupina pruh příkazu červeně označit](../../extensibility/ux-guidelines/media/0303-020_commandbargroupredline.png "0303 020_CommandBarGroupRedline")<br />Skupina pruh příkazu (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |  
| ... v místech, kde je nutné panelu příkazů embedded, ale není možné použít standardní implementace panelu příkaz Visual Studio. | ... pro prvky uživatelského rozhraní, které nejsou podobné na panelu příkazů. |
| | ... pro součásti panelu příkaz než pro který tokenu názvy jsou určené. |

**Skupina pruh příkazu: výchozí stav**  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.CommandBarGradientBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Ohraničení | `Environment.CommandBarToolBarBorder` |
| Přetažením úchytu | `Environment.CommandBarDragHandle` |
| Oddělovač | `Environment.CommandBarToolBarSeparator`<br />`Environment.CommandBarToolBarSeparatorHighlight` |

#### <a name="command-icons"></a>Ikony příkazů  
![Ikona příkazu červeně označit](../../extensibility/ux-guidelines/media/0303-021_commandiconredline1.png "0303 021_CommandIconRedline1")<br />Ikona příkazu (červená značka)  

![Ikona příkazu s textem červeně označit](../../extensibility/ux-guidelines/media/0303-022_commandiconredline2.png "0303 022_CommandIconRedline2")<br />Ikona příkazu s textem (červená značka)  

| Použití... | Nepoužívejte... |
| --- | --- |
| ... pro všechny tlačítka, které se umístí na panelu příkazů. | ... pro ovládací prvky, které mají své vlastní názvy tokenu. |
| | ... v libovolné kombinace pozadí nebo popředí, jiné než která byla specifikována. |

**Ikona příkazu: výchozí stav**  

![Příkaz výchozí ikonu](../../extensibility/ux-guidelines/media/0303-023_commandicondefault.png "0303 023_CommandIconDefault")<br />Výchozí ikona příkazu.

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Není k dispozici (dědí z příkazového řádku pozadí) |
| Popředí (Text) | `Environment.CommandBarTextActive` |
| Ohraničení | Není k dispozici |

**Ikona příkazu: Výchozí vybraný stav**

![Výchozí, ikona vybraný příkaz](../../extensibility/ux-guidelines/media/0303-024_commandicondefaultselected.png "0303 024_CommandIconDefaultSelected")<br />Výchozí, ikona vybraný příkaz  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.CommandBarSelected` |
| Popředí (Text) | `Environment.CommandBarTextSelected` |
| Ohraničení | `Environment.CommandBarSelectedBorder` |

**Ikona příkazu: hover nebo fokus stavy**  

![Příkaz ikonu na hover nebo fokus](../../extensibility/ux-guidelines/media/0303-025_commandiconhover.png "0303 025_CommandIconHover")<br />Příkaz ikonu na hover nebo fokusu

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.CommandBarMouseOverBackgroundBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.CommandBarTextHover` |
| Ohraničení | `Environment.CommandBarBorder` |

**Ikona příkazu: hover nebo fokus stavy, vybrané**

![Vybraný příkaz ikonu na hover nebo fokus](../../extensibility/ux-guidelines/media/0303-026_commandiconhoverselected.png "0303 026_CommandIconHoverSelected")<br />Vybraný příkaz ikonu na hover nebo fokusu

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.CommandBarHoverOverSelected` |
| Popředí (Text) | `Environment.CommandBarTextHoverOverSelected` |
| Ohraničení | `Environment.CommandBarHoverOverSelectedIconBorder` |

 **Ikona příkazu: stisknutí stavu**  

![Stisknutí ikona příkazu](../../extensibility/ux-guidelines/media/0303-027_commandiconpressed.png "0303 027_CommandIconPressed")<br />Ikona při stisknutí tlačítka příkazu.

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.CommandBarMouseDownBackgroundBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.CommandBarTextMouseDown` |
| Ohraničení | `Environment.CommandBarBorder` |

**Ikona příkazu: zakázáno stavu**  

![Ikona zakázané příkazu](../../extensibility/ux-guidelines/media/0303-028_commandicondisabled.png "0303 028_CommandIconDisabled")<br />Ikona zakázané příkazu.

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Není k dispozici (dědí z příkazového řádku pozadí) |
| Popředí (Text) | `Environment.CommandBarTextInactive` |
| Ohraničení | Není k dispozici |

####  <a name="BKMK_CommandComboBox"></a>Příkaz panelu pole se seznamem

> [!IMPORTANT]
> Pole se seznamem jsou podobná rozevírací seznamy, ale zahrnout oblast upravovat text. Pokud vaše rozevíracího seznamu nezahrnuje oblast upravovat text, použijte tokeny barvu pro [příkazu panelu rozevírací seznamy](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_CommandDropDown).  

![Červená linka příkazovém řádku – pole se seznamem](../../extensibility/ux-guidelines/media/0303-029_comboboxredline.png "0303 029_ComboBoxRedline")<br />Pole se seznamem příkazového řádku (červená značka)  

| Použití... | Nepoužívejte... |
| --- | --- |
| ... při vytváření vlastní pole se seznamem. | ... pro všechno, co nechcete, aby vždy tak, aby odpovídaly příkaz panel uživatelského rozhraní. |
| ... při vytváření panel příkazů, který je podobný pole se seznamem. | ... Pokud máte přístup k stylem pole se seznamem. |

**Příkaz panelu pole se seznamem vstupní: výchozí stav**

![Příkaz panelu pole se seznamem vstupní](../../extensibility/ux-guidelines/media/0303-030_comboboxinputfield.png "0303 030_ComboBoxInputField")<br />Příkaz panelu pole se seznamem vstupní  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ComboBoxBackground` |
| Popředí (Text) | `Environment.ComboBoxText` |
| Ohraničení | `Environment.ComboBoxBorder` |
| Oddělovač | Žádný oddělovač |

**Příkazového řádku rozevíracího seznamu tlačítka: výchozí stav**  

![Pole se seznamem pole rozevírací & č. 45; dolů,](../../extensibility/ux-guidelines/media/0303-031_comboboxdropdownbutton.png "0303 031_ComboBoxDropdownButton")<br />Příkazového řádku rozevíracího seznamu tlačítka

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Není k dispozici (dědí z příkazového řádku pozadí) |
| Popředí (glyfy) | `Environment.ComboBoxGlyph` |

**Příkaz panelu rozevíracího seznamu: výchozí stav**

![Příkaz panelu rozevíracího seznamu](../../extensibility/ux-guidelines/media/0303-032_comboboxdropdownlist.png "0303 032_ComboBoxDropdownList")<br />Příkaz panelu rozevíracího seznamu

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ComboBoxPopupBackgroundBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.ComboBoxItemText` |
| Ohraničení | `Environment.ComboBoxPopupBorder` |

**Příkaz panelu pole se seznamem vstupní: najeďte stavu**  

![Příkaz panelu pole se seznamem vstupní při přechodu myší](../../extensibility/ux-guidelines/media/0303-033_comboboxinputfieldhover.png "0303 033_ComboBoxInputFieldHover")<br />Příkaz panelu pole se seznamem vstupní při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ComboBoxMouseOverBackgroundBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.ComboBoxMouseOverText` |
| Ohraničení | `Environment.ComboBoxMouseOverBorder` |
| Oddělovač | `Environment.ComboBoxMouseOverSeparator` |

 **Příkazového řádku rozevíracího seznamu tlačítka: najeďte stavu**  

![Příkazového řádku rozevíracího seznamu tlačítka při přechodu myší](../../extensibility/ux-guidelines/media/0303-034_comboboxdropdownbuttonhover.png "0303 034_ComboBoxDropdownButtonHover")<br />Příkazového řádku rozevíracího seznamu tlačítka při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ComboBoxButtonMouseOverBackground` |
| Popředí (glyfy) | `Environment.ComboBoxMouseOverGlyph` |

**Příkaz panelu rozevíracího seznamu: najeďte stavu**

 ![Příkaz panelu rozevíracího seznamu při přechodu myší](../../extensibility/ux-guidelines/media/0303-035_comboboxdropdownlisthover.png "0303 035_ComboBoxDropdownListHover")<br />Příkaz panelu rozevíracího seznamu při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí (položka nabídky) | `Environment.ComboBoxItemMouseOverBackground` |
| Popředí (Text) | `Environment.ComboBoxItemMouseOverText` |
| Ohraničení (položka nabídky) | `Environment.ComboBoxItemMouseOverBorder` |

 **Příkaz panelu pole se seznamem vstupní: zaměřuje stavu**  

![Zaměřuje příkazovém řádku vstupní pole se seznamem](../../extensibility/ux-guidelines/media/0303-036_comboboxinputfieldfocused.png "0303 036_ComboBoxInputFieldFocused")<br />Zaměřuje příkazového řádku pole se seznamem vstupní

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ComboBoxFocusedBackground` |
| Popředí (Text) | `Environment.ComboBoxFocusedText` |
| Ohraničení | `Environment.ComboBoxFocusedBorder` |
| Oddělovač | `Environment.ComboBoxFocusedButtonSeparator` |

**Příkazového řádku rozevíracího seznamu tlačítka: zaměřuje stavu**  

![Zaměřuje příkazovém řádku rozevírací tlačítko](../../extensibility/ux-guidelines/media/0303-037_comboboxdropdownbuttonfocused.png "0303 037_ComboBoxDropdownButtonFocused")<br />Cílených příkazovém řádku rozevírací tlačítko

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ComboBoxFocusedButtonBackground` |
| Popředí (glyfy) | `Environment.ComboBoxFocusedGlyph` |

 **Příkaz panelu pole se seznamem vstupní: stisknutí stavu**  

![Stisknutí příkaz panelu vstupní pole se seznamem](../../extensibility/ux-guidelines/media/0303-038_comboboxinputfieldpressed.png "0303 038_ComboBoxInputFieldPressed")<br />Stisknutí příkazového řádku pole se seznamem vstupní

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ComboBoxMouseDownBackground` |
| Popředí (Text) | `Environment.ComboBoxMouseDownText` |
| Ohraničení | `Environment.ComboBoxMouseDownBorder` |
| Oddělovač | `Environment.ComboBoxMouseDownSeparator` |

**Příkazového řádku rozevíracího seznamu tlačítka: stisknutí stavu**

![Stisknutí příkazovém řádku rozevírací tlačítko](../../extensibility/ux-guidelines/media/0303-039_comboboxdropdownbuttonpressed.png "0303 039_ComboBoxDropdownButtonPressed")<br />Stisknutí příkazovém řádku rozevírací tlačítko  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ComboBoxButtonMouseDownBackground` |
| Popředí (glyfy) | `Environment.ComboBoxMouseDownGlyph` |

**Příkaz panelu pole se seznamem vstupní: zakázáno stavu**  

![Zakázat příkaz panelu vstupní pole se seznamem](../../extensibility/ux-guidelines/media/0303-041_comboboxinputfielddisabled.png "0303 041_ComboBoxInputFieldDisabled")<br />Zakázané příkazovém řádku vstupní pole se seznamem  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ComboBoxDisabledBackground` |
| Popředí (Text) | `Environment.ComboBoxDisabledText` |
| Ohraničení | `Environment.ComboBoxDisabledBorder` |
| Oddělovač | Žádný oddělovač |

**Příkazového řádku rozevíracího seznamu tlačítka: zakázáno stavu**  

![Zakázat příkaz panelu rozevírací tlačítko](../../extensibility/ux-guidelines/media/0303-040_comboboxdropdownbuttondisabled.png "0303 040_ComboBoxDropdownButtonDisabled")<br />Zakázané příkazovém řádku rozevírací tlačítko

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Žádné |
| Popředí (glyfy) | `Environment.ComboBoxDisabledGlyph` |

####  <a name="BKMK_CommandDropDown"></a>Příkaz panelu rozevírací seznamy

> [!IMPORTANT]
>  Rozevírací seznamy jsou podobné pole se seznamem, ale nemají upravovat text oblasti. Pokud se rozevírací seznam obsahuje oblast upravovat text, použijte tokeny barvu pro [příkazový řádek se seznamem](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_CommandComboBox).  

![Příkaz panelu rozevíracího seznamu (červená značka)](../../extensibility/ux-guidelines/media/0303-042_dropdownredline.png "0303 042_DropdownRedline")<br />Příkaz panelu rozevíracího seznamu (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... při vytváření ovládacích prvků vlastní rozevíracího seznamu. | ... pro všechno, co není podobná rozevíracího seznamu. |
| | ... pro pole se seznamem nebo tlačítka rozdělení. |   

**Příkaz panelu rozevírací výběr pole: výchozí stav**  

![Výchozí příkazovém řádku rozevírací výběr pole](../../extensibility/ux-guidelines/media/0303-043_dropdownselectionfield.png "0303 043_DropdownSelectionField")<br />Výchozí příkazového řádku rozevírací výběr pole  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.DropDownBackground` |
| Popředí (Text) | `DropDownText` |
| Ohraničení | `DropDownBorder` |
| Oddělovač | Žádný oddělovač |

**Příkazového řádku rozevíracího seznamu tlačítka: výchozí stav**

![Výchozí příkazovém řádku rozevírací tlačítko](../../extensibility/ux-guidelines/media/0303-044_dropdownbutton.png "0303 044_DropdownButton")<br />Výchozí příkazového řádku rozevíracího seznamu tlačítka  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Žádné |
| Popředí (glyfy) | `Environment.DropDownGlyph` |

**Příkaz panelu rozevíracího seznamu: výchozí stav**

![Výchozí příkazovém řádku rozevíracího seznamu](../../extensibility/ux-guidelines/media/0303-045_dropdownlist.png "0303 045_DropdownList")<br />Výchozí příkazového řádku rozevíracího seznamu  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.DropDownPopupBackgroundBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.ComboBoxItemText` |
| Ohraničení | `Environment.DropDownPopupBorder` |
| stínové | `Environment.DropShadowBackground` |

**Příkaz panelu rozevírací výběr pole: najeďte stavu**  

![Příkaz panelu rozevírací výběr pole při přechodu myší](../../extensibility/ux-guidelines/media/0303-046_dropdownselectionfieldhover.png "0303 046_DropdownSelectionFieldHover")<br />Příkaz panelu rozevírací výběr pole při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.DropDownMouseOverBackgroundBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.DropDownMouseOverText` |
| Ohraničení | `Environment.DropDownMouseOverBorder` |
| Oddělovač | `Environment.DropDownButtonMouseOverSeparator` |

**Příkazového řádku rozevíracího seznamu tlačítka: najeďte stavu**  

![Příkazového řádku rozevíracího seznamu tlačítka při přechodu myší](../../extensibility/ux-guidelines/media/0303-047_dropdownbuttonhover.png "0303 047_DropdownButtonHover")<br />Příkazového řádku rozevíracího seznamu tlačítka při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.DropDownButtonMouseOverBackground` |
| Popředí (glyfy) | `Environment.DropDownMouseOverGlyph` |

**Příkaz panelu rozevíracího seznamu: najeďte stavu**  

![Příkaz panelu rozevíracího seznamu při přechodu myší](../../extensibility/ux-guidelines/media/0303-048_dropdownlisthover.png "0303 048_DropdownListHover")<br />Příkaz panelu rozevíracího seznamu při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí (položka nabídky) | `Environment.ComboBoxItemMouseOverBackground` |
| Popředí (Text) | `Environment.ComboBoxItemMouseOverText` |
| Ohraničení (položka nabídky) | `Environment.ComboBoxItemMouseOverBorder` |

 **Příkaz panelu rozevírací výběr pole: stisknutí stavu**  

![Vyřaďte & č. 45; dolů výběr pole stisknutí](../../extensibility/ux-guidelines/media/0303-049_dropdownselectionfieldpressed.png "0303 049_DropdownSelectionFieldPressed")<br />Stisknutí příkaz panelu rozevírací výběr pole

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.DropDownMouseDownBackground` |
| Popředí (Text) | `Environment.DropDownMouseDownText` |
| Ohraničení | `Environment.DropDownMouseDownBorder` |
| Oddělovač | `Environment.DropDownButtonMouseDownSeparator` |

**Příkazového řádku rozevíracího seznamu tlačítka: stisknutí stavu**

![Stisknutí příkazovém řádku rozevírací tlačítko](../../extensibility/ux-guidelines/media/0303-050_dropdownbuttonpressed.png "0303 050_DropdownButtonPressed")<br />Stisknutí příkazovém řádku rozevírací tlačítko  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.DropDownButtonMouseDownBackground` |
| Popředí (glyfy) | `Environment.DropDownMouseDownGlyph` |

**Příkaz panelu rozevírací výběr pole: zakázáno stavu**  

![Zakázané příkazovém řádku rozevírací výběr pole](../../extensibility/ux-guidelines/media/0303-051_dropdownselectionfielddisabled.png "0303 051_DropdownSelectionFieldDisabled")<br />Zakázané příkazovém řádku rozevírací výběr pole

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.DropDownDisabledBackground` |
| Popředí (Text) | `Environment.DropDownDisabledText` |
| Ohraničení | `Environment.DropDownDisabledBorder` |
| Oddělovač | Žádný oddělovač |

**Příkazového řádku rozevíracího seznamu tlačítka: zakázáno stavu**

![Zakázat příkaz panelu rozevírací tlačítko](../../extensibility/ux-guidelines/media/0303-052_dropdownbuttondisabled.png "0303 052_DropdownButtonDisabled")<br />Zakázané příkazovém řádku rozevírací tlačítko

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Není k dispozici |
| Popředí (glyfy) | `Environment.DropDownDisabledGlyph` |

#### <a name="command-bar-split-buttons"></a>Panel příkazů rozdělení tlačítka
Tlačítka rozdělení sdílet mnoho názvů tokenu s další ovládací prvky příkazového řádku, např. tlačítka, nabídky a příkazového řádku textu. Všechny potřebné akce a rozevírací tlačítko tokenu názvy jsou zde opakuje ke zvýšení pohodlí. Rozevírací seznamy tlačítko rozdělení jsou implementací [příkazu panelu nabídek](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_CommandMenus).  

![Tlačítko rozdělení červeně označit](../../extensibility/ux-guidelines/media/0303-053_splitbuttonredline.png "0303 053_SplitButtonRedline")<br />Tlačítko rozdělení příkazového řádku (červená značka)  

| Použití... | Nepoužívejte... |
| --- | --- |
| ... při vytváření vlastní rozdělení tlačítko. | ... pro jiné druhy tlačítka. |
| | ... v libovolné kombinace pozadí nebo popředí, jiné než která byla specifikována. |

**Tlačítko rozdělení příkazového řádku: výchozí stav**  

![Výchozí tlačítko rozdělení panelu příkaz](../../extensibility/ux-guidelines/media/0303-054_splitbutton.png "0303 054_SplitButton")<br />Tlačítko rozdělení výchozího příkazového řádku  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Žádné |
| Popředí (Text) | `Environment.CommandBarTextActive` |
| Popředí (glyfy) | `Environment.CommandBarSplitButtonGlyph` |
| Ohraničení | Není k dispozici |
| Oddělovač | Není k dispozici |

**Tlačítko rozdělení příkazového řádku: najeďte stavu**  

![Tlačítko při přechodu myší rozdělení na panelu příkazů](../../extensibility/ux-guidelines/media/0303-055_splitbuttonhover.png "0303 055_SplitButtonHover")<br />Tlačítko při přechodu myší rozdělení příkazového řádku

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.CommandBarMouseOverBackgroundBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.CommandBarTextHover` |
| Popředí (glyfy) | `Environment.CommandBarSplitButtonMouseOverGlyph` |
| Ohraničení | `Environment.CommandBarBorder` |
| Oddělovač | `Environment.CommandBarSplitButtonSeparator` |

**Tlačítko rozdělení příkazového řádku: stisknutí stavu**  

![Stisknutí příkazového řádku tlačítko rozdělení](../../extensibility/ux-guidelines/media/0303-056_splitbuttonpressed.png "0303 056_SplitButtonPressed")<br />Tlačítko rozdělení panelu při stisknutí tlačítka příkazů  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.CommandBarMouseDownBackgroundBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.CommandBarTextMouseDown` |
| Popředí (glyfy) | `Environment.CommandBarSplitButtonMouseDownGlyph` |
| Ohraničení | `Environment.CommandBarBorder` |
| Oddělovač | Není k dispozici |

**Tlačítko rozdělení příkazového řádku: zakázáno stavu**

![Zakázat příkaz tlačítko rozdělení panelu](../../extensibility/ux-guidelines/media/0303-057_splitbuttondisabled.png "0303 057_SplitButtonDisabled")<br />Tlačítko rozdělení zakázané příkazového řádku

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Není k dispozici |
| Popředí (Text) | `Environment.ComboBoxItemTextInactive` |
| Popředí (glyfy) | `Environment.CommandBarTextInactive` |
| Ohraničení | Není k dispozici |
| Oddělovač | Není k dispozici |

#### <a name="command-bar-more-options-and-overflow-buttons"></a>Příkaz panelu více možností a 'Overflow' tlačítka  
Tlačítko "Další možnosti" se používá při skupinu příkazového řádku lze přizpůsobit přidáním nebo odebráním související panelu příkazů. Tlačítko "Přetečení" se zobrazí, když panelu příkazů se zkrátí z důvodu nedostatku místa na vodorovné a na klikněte na tlačítko se zobrazí nabídku, která obsahuje panelu příkazů, který nelze zobrazit. Barvy pro tyto dvě tlačítka jsou řízeny stejnou sadu tokenu názvy.  

![Příkaz panelu tlačítko "Další možnosti" (červeně označit)](../../extensibility/ux-guidelines/media/0303-058_moreoptionsredline.png "0303 058_MoreOptionsRedline")<br />Příkaz panelu tlačítko 'Další možnosti' (červená značka)  

| Použití... | Nepoužívejte... |
| --- | --- |
| ... pro vlastní, další možnosti' nebo 'Overflow' tlačítek. | ... pro tlačítka, která nemají podobné funkce jako více možností nebo tlačítko 'Overflow'. |

**Příkaz panelu 'Overflow' tlačítka a další možnosti: výchozí stav**  

![Výchozí příkazovém řádku tlačítko 'Další možnosti'](../../extensibility/ux-guidelines/media/0303-059_moreoptions.png "0303 059_MoreOptions")<br />Výchozí tlačítko 'Další možnosti' panel příkazů

![Výchozí příkazovém řádku 'Overflow' tlačítko](../../extensibility/ux-guidelines/media/0303-060_overflow.png "0303 060_Overflow")<br />Výchozí příkazového řádku 'Overflow' tlačítka

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.CommandBarOptionsBackground` |
| Popředí (glyfy) | `Environment.CommandBarOptionsGlyph` |

**Příkaz panelu 'Overflow' tlačítka a další možnosti: najeďte stavu**

![Příkaz panelu tlačítko 'Další možnosti' při přechodu myší](../../extensibility/ux-guidelines/media/0303-061_moreoptionshover.png "0303 061_MoreOptionsHover")<br />Příkaz panelu na hover tlačítko 'Další možnosti.  

![Příkaz 'Overflow' tlačítko panelu při přechodu myší](../../extensibility/ux-guidelines/media/0303-062_overflowoptions.png "0303 062_OverflowOptions")<br />Příkaz 'Overflow' tlačítko panelu při přechodu myší   

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.CommandBarOptionsMouseOverBackgroundBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (glyfy) | `Environment.CommandBarOptionsMouseDownGlyph` |

**Příkaz panelu 'Overflow' tlačítka a další možnosti: stisknutí stavu**  

![Stisknutí příkazovém řádku tlačítko 'Další možnosti'](../../extensibility/ux-guidelines/media/0303-063_moreoptionspressed.png "0303 063_MoreOptionsPressed")<br />Stisknutí příkazovém řádku tlačítko 'Další možnosti.  

![Přetečení stisknutí](../../extensibility/ux-guidelines/media/0303-064_overflowpressed.png "0303 064_OverflowPressed")<br />Stisknutí tlačítka 'Overflow' příkazového řádku  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.CommandBarOptionsMouseDownBackgroundBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (glyfy) | `Environment.CommandBarOptionsMouseDownGlyph` |

## <a name="document-windows"></a>Okna dokumentu  
Vzhledem k tomu, že jste zadali v prostředí Visual Studio není nutné k replikaci okna dokumentu. Ale můžete rozhodnout, že chcete využít barvy používané v dokumentu windows tak, aby uživatelské rozhraní vždycky zobrazila konzistentní s tuto část prostředí Visual Studio.  

Při použití tokenů barva okna dokumentu, dávejte pozor, je použít jenom pro podobné elementy a vždy v párech. Pokud nemáte učiníte, můžete získat neočekávané výsledky v uživatelském rozhraní.  

### <a name="document-window-frames"></a>Rámce okna dokumentu  
Okna dokumentu lze ukotveného v prostředí IDE nebo plovoucí jako samostatném okně. Pokud okna dokumentu je plovoucí mimo rozhraní IDE, se stále nachází v dokumentu také a má pozadí, ohraničení, text a karta barev, které jsou stejné jako když je součástí prostředí IDE. Dokument je však umístěn uvnitř rámce, který má svou vlastní pozadí, ohraničení a barvy textu. Pokud je nástroj windows jsou v dokumentu také ukotveno, dědí z tokenu názvy oken dokumentu chování a barvu pro jejich karty.  

![Okna ukotveného dokumentu (červená značka)](../../extensibility/ux-guidelines/media/0303-065_dockeddocumentwindowredline.png "0303 065_DockedDocumentWindowRedline")<br />Okna ukotveného dokumentu (červená značka)  

![Plovoucího okna dokumentu (červená značka)](../../extensibility/ux-guidelines/media/0303-066_floatingdocumentwindowredline.png "0303 066_FloatingDocumentWindowRedline")<br />Plovoucího okna dokumentu (červená značka)  

| Použití... | Nepoužívejte... |
| --- | --- |
| ... kdekoli vytváříte uživatelské rozhraní, které chcete porovnat okna dokumentu. | pro všechny uživatelské rozhraní, které chcete změnit, pokud nechcete automaticky... prostředí má aktualizace motivu. |

**Okna dokumentu ukotvený nebo plovoucí: výchozí stav**  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Závisí na typu dokumentu |
| Popředí (Text) | Závisí na typu dokumentu |
| Ohraničení | `Environment.ToolWindowBorder` |

**Cílených plovoucí rámce okna dokumentu: výchozí stav**

![Výchozí zaměřuje, plovoucí rámce okna dokumentu](../../extensibility/ux-guidelines/media/0303-067_framefocused.png "0303 067_FrameFocused")<br />Výchozí zaměřuje, plovoucí rámce okna dokumentu

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ToolWindowFloatingFrame` |
| Popředí (Text) | `Environment.ToolWindowFloatingFrame` |
| Popředí (glyfy) | `Environment.RaftedWindowButtonActiveGlyph` |
| Ohraničení | `Environment.MainWindowActiveDefaultBorder` |
| Ohraničení (glyfy) | `Environment.RaftedWindowButtonActiveBorder`<br />(Nastavený na transparentní) |

**Rámec okna dokumentu nezaostřená, plovoucí: výchozí stav**  

![Rámec okna výchozí dokument nezaostřená, plovoucí](../../extensibility/ux-guidelines/media/0303-068_frameunfocused.png "0303 068_FrameUnfocused")<br />Výchozí dokument nezaostřená, plovoucí rámce okna

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ToolWindowFloatingFrameInactive` |
| Popředí (Text) | `Environment.ToolWindowFloatingFrameInactive` |
| Popředí (glyfy) | `Environment.RaftedWindowButtonInactiveGlyph` |
| Ohraničení | `Environment.MainWindowInactiveBorder` |
| Ohraničení (glyfy) | `Environment.RaftedWindowButtonInactiveBorder`<br />(Nastavený na transparentní) |

**Cílených plovoucí rámce okna dokumentu: najeďte stavu**

![Cílených plovoucí rámce okna dokumentu při přechodu myší](../../extensibility/ux-guidelines/media/0303-069_framefocusedhover.png "0303 069_FrameFocusedHover")<br />Cílených plovoucí rámce okna dokumentu při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí (glyfy) | `Environment.RaftedWindowButtonHoverActive` |
| Popředí (glyfy) | `Environment.RaftedWindowButtonHoverActiveGlyph` |
| Ohraničení (glyfy) | `Environment.RaftedWindowButtonHoverActiveBorder` |

**Rámec okna dokumentu nezaostřená, plovoucí: najeďte stavu**  

![Dokument nezaostřená, plovoucí rámce okna při přechodu myší](../../extensibility/ux-guidelines/media/0303-070_frameunfocusedhover.png "0303 070_FrameUnfocusedHover")<br />Nezaostřená, při přechodu myší plovoucí rámce okna dokumentu

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí (glyfy) | `EnvironmentRaftedWindowButtonHoverInactive` |
| Popředí (glyfy) | `Environment.RaftedWindowButtonHoverInactiveGlyph` |
| Ohraničení (glyfy) | `Environment.RaftedWindowButtonHoverInactiveBorder` |

**Cílených plovoucí rámce okna dokumentu: stisknutí stavu**  

![Cílených plovoucí rámce okna dokumentu na stiskněte](../../extensibility/ux-guidelines/media/0303-071_framefocusedpressed.png "0303 071_FrameFocusedPressed")<br />Cílených na stiskněte plovoucí rámce okna dokumentu

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí (glyfy) | `Environment.RaftedWindowButtonDown` |
| Popředí (glyfy) | `Environment.RaftedWindowButtonDownGlyph` |
| Ohraničení (glyfy) | `Environment.RaftedWindowButtonDownBorder` |

### <a name="document-tabs"></a>Záložky dokumentů  
Karty dokumentů se nacházejí v kartě kanál k označení, které dokumenty jsou momentálně otevřené, společně s které z nich je vybrána aktuální nebo aktivní dokument. Nástroj windows můžete také ukotven v kanálu kartě dokumentu, pokud uživatel umístí je existuje. V této situaci se používají stejné barvy karta jako okna dokumentu. Při vytváření uživatelského rozhraní, budete chtít vždy odpovídat dokumentu okno barvy (včetně aktualizace motivu nebo pokud jsou nové motivy nainstalované) a pak odkazovat na tyto tokeny barev.  

![Karet dokumentů (červená značka)](../../extensibility/ux-guidelines/media/0303-072_documenttabredline.png "0303 072_DocumentTabRedline")<br />Karet dokumentů (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... kdekoli vytváříte uživatelské rozhraní, které chcete odpovídající karty dokumentů a automaticky se vyzvedávat aktualizace motivu nebo nové barev motivů. | ... pro všechny uživatelské rozhraní, které nechcete automaticky změnit, když prostředí má motiv aktualizovat. |

#### <a name="open-document-tabs"></a>Otevřete dokument karty  
Každý otevřete dokument má na kartě v kanálu kartě dokumentu, který zobrazí její název. Dokumenty můžou být buď vybrána nebo otevřít na pozadí, a jejich karty odrážela tyto stavy:  

-   Vybraná karta představuje dokumentu, který je dobře zobrazené v dokumentu. Vybraná karta má ohraničení dokumentu, který rozšiřuje dobře mezi horním okrajem dokumentu.  

-   Pozadí karty jsou všechny karty dokumentů, které nejsou aktuálně vybraná karta. Po kliknutí na, stane vybraná karta a získat všechny barvy textu, ohraničení a pozadí z těchto názvů tokenu.  

![Otevřete dokument karta (červená značka)](../../extensibility/ux-guidelines/media/0303-073_opendocumenttabredline.png "0303 073_OpenDocumentTabRedline")<br />Otevřete dokument karta (červená značka)

| Použití...  | Nepoužívejte... |
| --- | --- |
| ... při vytváření vlastní dokument karty. | ... u tabulátorů předběžných (preview). |
| | pro všechny uživatelské rozhraní, které nechcete automaticky změnit, pokud má prostředí... aktualizace motivu. |

**Karta vybrané, cílených dokumentu**  

![Vybraná, zaměřuje kartu dokumentu](../../extensibility/ux-guidelines/media/0303-074_selectedtabfocused.png "0303 074_SelectedTabFocused")<br />Karta vybrané, cílených dokumentu

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.FileTabSelectedGradientTop`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.FileTabSelectedText` |
| Ohraničení | `Environment.FileTabSelectedBorder`<br />(Nastavte na stejné barvy jako pozadí). |
| Dokument ohraničení | `Environment.FileTabDocumentBorderBackground` |

**Karta vybrané, nezaostřená dokumentu**

![Karta vybrané, nezaostřená dokumentu](../../extensibility/ux-guidelines/media/0303-075_selectedtabunfocused.png "0303 075_SelectedTabUnfocused")<br />Karta vybrané, nezaostřená dokumentu

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.FileTabInactiveGradientTop`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.FileTabInactiveText` |
| Ohraničení | `Environment.FileTabInactiveBorder`<br />(Nastavte na stejné barvy jako pozadí). |
| Dokument ohraničení | `Environment.FileTabInactiveDocumentBorderBackground` |

**Karta dokumentu pozadí: výchozí stav**  

![Výchozí pozadí dokumentu kartě](../../extensibility/ux-guidelines/media/0303-076_backgroundtab.png "0303 076_BackgroundTab")<br />Karta výchozí pozadí dokumentu  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.FileTabBackground` |
| Popředí (Text) | `Environment.FileTabText` |
| Ohraničení | `Environment.FileTabBorder`<br />(Nastavte na stejné barvy jako pozadí). |

**Karta dokumentu pozadí: najeďte stavu**  

![Karta dokumentu pozadí při přechodu myší](../../extensibility/ux-guidelines/media/0303-077_backgroundtabhover.png "0303 077_BackgroundTabHover")<br />Karta dokumentu pozadí při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.FileTabHotGradientTop`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.FileTabHotText` |
| Ohraničení | `Environment.FileTabHotBorder`<br />(Nastavte na stejné barvy jako pozadí). |

#### <a name="preview-tab"></a>Karta náhled  
Také se nazývá "předběžným" kartě. Karta náhled se zobrazí na pravé straně kanálu kartě dokumentu, když uživatel klikne na položku v okně Nástroj Průzkumník řešení. To funguje jako náhled dokumentu a také umožňuje uživateli možnost zachovat dokument otevřít na levé straně kanálu kartě dokumentu. Současně lze otevřít pouze jeden preview kartu otevřete. Náhled karty mají obě na pozadí a vybrané stavy, jako třeba otevřených karet a může být cílených nebo nezaostřená v jejich aktivním stavu.  

![Karta náhled (červená značka)](../../extensibility/ux-guidelines/media/0303-078_previewtabredline.png "0303 078_PreviewTabRedline")<br />Karta náhled (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... odkudkoli vytváříte předběžné verzi preview a mají některé elementu na aktuální karta barvu náhledu. | ... pro jakýkoli druh dokument nebo kartu, která není předběžné (preview). |
| | pro všechny uživatelské rozhraní, které nechcete automaticky změnit, pokud má prostředí... aktualizace motivu. |

**Karta náhled cílených, vybrané**  

![Karta náhled cílených, vybrané](../../extensibility/ux-guidelines/media/0303-079_previewtabfocused.png "0303 079_PreviewTabFocused")<br />Karta náhled cílených, vybrané

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.FileTabProvisionalSelectedActive` |
| Popředí (Text) | `Environment.FileTabProvisionalSelectedActiveForeground` |
| Ohraničení | `Environment.FileTabProvisionalSelectedActiveBorder`<br />(Nastavte na stejné barvy jako pozadí). |
| Dokument ohraničení | `Environment.FileTabProvisionalSelectedActiveBorder` |

**Karta náhled nezaostřená, vybrané**  

![Karta náhled nezaostřená, vybrané](../../extensibility/ux-guidelines/media/0303-080_previewtabunfocused.png "0303 080_PreviewTabUnfocused")<br />Karta náhled nezaostřená, vybrané

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.FileTabProvisionalSelectedInactive` |
| Popředí (Text) | `Environment.FileTabProvisionalSelectedInactiveForeground` |
| Ohraničení | `Environment.FileTabProvisionalSelectedInactiveBorder` |
| Dokument ohraničení | `Environment.FileTabProvisionalSelectedInactiveBorder` |

**Karta Náhled pozadí: výchozí stav**  

![Karta náhled výchozí pozadí](../../extensibility/ux-guidelines/media/0303-081_previewbackgroundtab.png "0303 081_PreviewBackgroundTab")<br />Karta náhled výchozí pozadí  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.FileTabProvisionalInactive` |
| Popředí (Text) | `Environment.FileTabProvisionalInactiveForeground` |
| Ohraničení | `Environment.FileTabProvisionalInactiveBorder`<br />(Nastavte na stejné barvy jako pozadí). |

**Karta Náhled pozadí: najeďte stavu**  

![Karta Náhled pozadí při přechodu myší](../../extensibility/ux-guidelines/media/0303-082_previewbackgroundtabhover.png "0303 082_PreviewBackgroundTabHover")<br />Karta Náhled pozadí při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.FileTabProvisionalHover` |
| Popředí (Text) | `Environment.FileTabProvisionalHoverForeground` |
| Ohraničení | `Environment.FileTabProvisionalHoverBorder`<br />(Nastavte na stejné barvy jako pozadí). |

#### <a name="document-overflow-button"></a>Tlačítko přetečení dokumentu  
Tlačítko přetečení dokument k dispozici, pokud je jeden nebo více dokumentů otevřít, bez ohledu na to, jestli je svislý prostor v aktuální konfiguraci podle všechny karty dokumentů. Rozevírací nabídky přetečení dokumentu, který je kontrolován [příkazu panelu nabídek](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_CommandMenus) barvy, zobrazí seznam všechny otevřené dokumenty, viditelné a skryté a změny přetečení glyfy v závislosti na tom, jestli jsou všechny otevřené dokumenty zobrazí v kartě kanál.  

![Tlačítko přetečení dokument (červená značka)](../../extensibility/ux-guidelines/media/0303-083_overflowredline.png "0303 083_OverflowRedline")<br />Tlačítko přetečení dokument (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... při vytváření vlastní dokument tlačítko přetečení. | ... pro uživatelské rozhraní, které není podobná tlačítko přetečení. |
| | ... pro panelu přetečení příkazů. |

**Tlačítko přetečení dokument: výchozí stav**  

![Výchozí dokument přetečení tlačítko](../../extensibility/ux-guidelines/media/0303-084_overflow.png "0303 084_Overflow")<br />Výchozí dokument přetečení tlačítko

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.DocWellOverflowButtonBackground` |
| Popředí (glyfy) | `Environment.DocWellOverflowButtonGlyph` |
| Ohraničení | Není k dispozici |

**Tlačítko přetečení dokument: najeďte stavu**

![Tlačítko dokument přetečení při přechodu myší](../../extensibility/ux-guidelines/media/0303-085_overflowhover.png "0303 085_OverflowHover")<br />Tlačítko dokument přetečení při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.DocWellOverflowButtonMouseOverBackground` |
| Popředí (glyfy) | `Environment.DocWellOverflowButtonMouseOverGlyph` |
| Ohraničení | `Environment.DocWellOverflowButtonMouseOverBorder` |

**Tlačítko přetečení dokument: stisknutí stavu**  

![Dokument na stiskněte tlačítko přetečení](../../extensibility/ux-guidelines/media/0303-086_overflowpressed.png "0303 086_OverflowPressed")<br />Dokument na stiskněte tlačítko přetečení

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.DocWellOverflowButtonMouseDownBackground` |
| Popředí (glyfy) | `Environment.DocWellOverflowButtonMouseDownGlyph` |
| Ohraničení | `Environment.DocWellOverflowButtonMouseDownBorder` |

### <a name="tagging"></a>Označování  
Visual Studio podporuje označování, což umožňuje uživatelům vyhledávat klíčová slova pro účely sledování deklarovat. Například projektu správci a vývojáři mohou použít Team Foundation Server (TFS) k označení pracovní položky. Následující tabulky zadejte název, barvu pro samotné značky a "zavřete ikona" glyf, který se zobrazí v hover a vybrané stavy.  

![Označování v sadě Visual Studio (červená značka)](../../extensibility/ux-guidelines/media/0303-176_taggingredline.png "0303 176_TaggingRedline")<br />Označování v sadě Visual Studio (červená značka)  

| Použití... | Nepoužívejte... |
| --- | --- |
| ... pro uživatelské rozhraní, které podporuje označování. | ... pro žádný jiný druh uživatelského rozhraní. |

#### <a name="tags"></a>Značky  

**Značky: výchozí stav**

![Výchozí značka](../../extensibility/ux-guidelines/media/0303-177_tag.png "0303 177_Tag")<br />Výchozí značka

| Prvek | Název tokenu: Category.color |
| --- | --- |  
| Pozadí | `Tag.Background` |
| Popředí (Text) | `Tag.Background` |

**Značky: stav hover**  

![Značka při přechodu myší](../../extensibility/ux-guidelines/media/0303-178_taghover.png "0303 178_TagHover")<br />Značka při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |  
| Pozadí | `Tag.HoverBackground` |
| Popředí (Text) | `Tag.HoverBackgroundText` |

**Značky: stisknutí stavu**

![Stisknutí značka](../../extensibility/ux-guidelines/media/0303-179_tagpressed.png "0303 179_TagPressed")<br />Při stisknutí tlačítka značky  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Tag.PressedBackground` |
| Popředí (Text) | `Tag.PressedBackgroundText` |

**Značky: vybraném stavu**

![Vybrané značky](../../extensibility/ux-guidelines/media/0303-180_tagselected.png "0303 180_TagSelected")<br />Vybranou značku  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Tag.SelectedBackground` |
| Popředí (Text) | `Tag.SelectedBackgroundText` |

#### <a name="close-times-tag-glyph"></a>Zavřít (&times;) glyfy značky

**Zavřít (&times;) značky glyfy: výchozí stav**

![Výchozí Zavřít (&times;) značky glyfy](../../extensibility/ux-guidelines/media/0303-181_tagglyph.png "0303 181_TagGlyph")<br />Výchozí Zavřít (&times;) glyfy značky

| Prvek | Název tokenu: Category.color |
| --- | --- |  
| Pozadí | Není k dispozici |
| Popředí (glyfy) | `Tag.TagHoverGlyph` |

**Zavřít (&times;) značky glyfy: najeďte stavu**

![Zavřít (&times;) značky glyfy při přechodu myší](../../extensibility/ux-guidelines/media/0303-182_tagglyphhover.png "0303 182_TagGlyphHover")<br />Zavřít (&times;) značky glyfy při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Tag.TagHoverGlyphHoverBackground` |
| Popředí (glyfy) | `Tag.TagHoverGlyphHover` |
| Ohraničení | `Tag.TagHoverGlyphHoverBorder` |

**Zavřít (&times;) značky glyfy: stisknutí stavu**

![Stisknutí tlačítka Zavřít (&times;) značky glyfy](../../extensibility/ux-guidelines/media/0303-183_tagglyphpressed.png "0303 183_TagGlyphPressed")<br />Stisknutí tlačítka Zavřít (&times;) glyfy značky

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Tag.TagHoverGlyphPressedBackground` |
| Popředí (glyfy) | `Tag.TagHoverGlyphPressed` |
| Ohraničení | `Tag.TagHoverGlyphPressedBorder` |

**Vybrané značky s Zavřít (&times;) glyfy: výchozí stav**

![Výchozí vybranou značku s Zavřít (&times;) glyfy](../../extensibility/ux-guidelines/media/0303-184_tagselected.png "0303 184_TagSelected")<br />Výchozí vybranou značku s Zavřít (&times;) glyfy

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Není k dispozici |
| Popředí (glyfy) | `Tag.TagSelectedGlyph` |

**Vybrané značky s Zavřít (&times;) glyfy: najeďte stavu**  

![Vybrané značky s Zavřít (&times;) glyfy při přechodu myší](../../extensibility/ux-guidelines/media/0303-185_tagselectedhover.png "0303 185_TagSelectedHover")<br />Vybrané značky s Zavřít (&times;) glyfy při přechodu myší  


| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Tag.TagSelectedGlyphHoverBackground` |
| Popředí (glyfy) | `Tag.TagSelectedGlyphHover` |
| Ohraničení | `Tag.TagSelectedGlyphHoverBorder` |

**Vybrané značky s Zavřít (&times;) glyfy: stisknutí stavu**  

![Vybraná, stisknutí značky s Zavřít (&times;) glyfy](../../extensibility/ux-guidelines/media/0303-186_tagselectedpressed.png "0303 186_TagSelectedPressed")<br />Vybraná, stisknutí značky s Zavřít (&times;) glyfy

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Tag.TagSelectedGlyphPressedBackground` |
| Foreground(Glyph) | `Tag.TagSelectedGlyphPressed` |
| Ohraničení | `Tag.TagSelectedGlyphPressedBorder` |

## <a name="tool-windows"></a>Nástroje systému windows  
Není nutné k replikaci nástroj windows, protože jste poskytované prostředí Visual Studio. Ale můžete rozhodnout, že chcete využít barvy používané v nástroji windows tak, aby uživatelské rozhraní vždycky zobrazila konzistentní s tuto část prostředí Visual Studio.  

![Okno nástroje (červená značka)](../../extensibility/ux-guidelines/media/0303-087_toolwindowredline.png "0303 087_ToolWindowRedline")<br />Okno nástroje (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... kdekoli vytváříte uživatelské rozhraní, které chcete porovnat nástroje systému windows. | pro všechny uživatelské rozhraní, které nechcete automaticky změnit, pokud má prostředí... aktualizace motivu. |

### <a name="tool-window-frame"></a>Rámce okna nástrojů  
Okna nástrojů v sadě Visual Studio se používají pro celou řadu různých úloh a může existovat v jednom z několika různých stavů. Pokud je otevřené okno nástroje, lze přiřadit k všechny čtyři strany oblasti dokumentu. Nástroje systému windows můžete také uvolnit mimo prostředí IDE, odkud můžou změnit jejich umístění kdekoli v rámci obrazovce uživatele. Plovoucí windows vždycky nacházejí v prostředí IDE. Nakonec nástroje systému windows lze ukotvit jako dokument windows a zobrazí jako karty v dobře dokumentu. Okna nástrojů, které byly ukotven jako dokument windows, se zobrazí v části pomocí tokenu názvy okna dokumentu.  

![Rámce okna nástrojů (červená značka)](../../extensibility/ux-guidelines/media/0303-088_toolwindowframeredline.png "0303 088_ToolWindowFrameRedline")<br />Rámce okna nástrojů (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... kdekoli vytváříte uživatelské rozhraní, které chcete porovnat nástroje systému windows. | pro všechny uživatelské rozhraní, které nechcete automaticky změnit, pokud má prostředí... aktualizace motivu. |

**Okno ukotveného nástroje**  

![Okno ukotveného nástroje](../../extensibility/ux-guidelines/media/0303-089_toolwindowdocked.png "0303 089_ToolWindowDocked")<br />Okno ukotveného nástroje  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ToolWindowBackground` |
| Ohraničení | `Environment.ToolWindowBorder` |

**Číslo s plovoucí čárkou, zaměřuje okno nástroje**

![Číslo s plovoucí čárkou, zaměřuje okno nástroje](../../extensibility/ux-guidelines/media/0303-090_toolwindowfocused.png "0303 090_ToolWindowFocused")<br />Číslo s plovoucí čárkou, zaměřuje okno nástroje

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ToolWindowBackground` |
| Ohraničení | `Environment.MainWindowActiveDefaultBorder` |

**Plovoucí okno nezaostřená nástroje**  

![Plovoucí, nezaostřená okno nástroje](../../extensibility/ux-guidelines/media/0303-091_toolwindowunfocused.png "0303 091_ToolWindowUnfocused")<br />Plovoucí okno nezaostřená nástroje  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ToolWindowBackground` |
| Ohraničení | `Environment.MainWindowInactiveBorder` |

### <a name="toolbox-like-windows"></a>Jako sada nástrojů windows
V panelu nástrojů je jednou z nejčastěji používaných běžné okna nástrojů v sadě Visual Studio. Je v podstatě ovládacím prvkem strom s speciální motivů a stylů použít.  

![Sada nástrojů jako okno (červená značka)](../../extensibility/ux-guidelines/media/0303-189_toolboxredline.png "0303 189_ToolboxRedline")<br />Sada nástrojů jako okno (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... při navrhování okno nástroje, který chcete být vždy konzistentní s sady nástrojů prostředí. | pro všechno, co není podobná sady nástrojů uživatelského rozhraní,... nebo pokud si nejste jisti, zda uživatelské rozhraní bude mít problémy sady nástrojů prostředí barvy změnit. |

**Sada nástrojů uzly: výchozí stav**

![Výchozí sada nástrojů nadřazený uzel](../../extensibility/ux-guidelines/media/0303-190_toolboxparentnode.png "0303 190_ToolboxParentNode")<br />Nadřazený uzel výchozí sady nástrojů

![Výchozí sada nástrojů podřízený uzel](../../extensibility/ux-guidelines/media/0303-191_toolboxchildnode.png "0303 191_ToolboxChildNode")<br />Výchozí sada nástrojů podřízený uzel.

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ToolboxContent`<br />(Položky) |
| Pozadí | `Environment.ToolWindowBackground`<br />(Jednotlivé položky nebo celé okno, pokud žádné dostupné ovládací prvky) |
| Ohraničení | Žádné |
| Popředí (glyfy) | `Environment.ToolboxContent` |
| Popředí (Text) | `Environment.ToolboxContent` |

**Sada nástrojů podřízené uzly: najeďte stavu**

![Sada nástrojů podřízený uzel při přechodu myší](../../extensibility/ux-guidelines/media/0303-192_toolboxchildnodehover.png "0303 192_ToolboxChildNodeHover")<br />Sada nástrojů podřízený uzel při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ToolboxContentMouseOver`<br />(Jenom pro jednotlivé položky) |
| Ohraničení | Žádné |
| Popředí (Text) | `Environment.ToolboxContentMouseOver`<br />(Jenom pro jednotlivé položky) |

**Vybraná sada nástrojů uzly: zaměřuje stavu**

![Sada nástrojů cílených, vybrané nadřazený uzel](../../extensibility/ux-guidelines/media/0303-193_toolboxparentnodefocused.png "0303 193_ToolboxParentNodeFocused")<br />Nadřazený uzel cílených, vybrané sady nástrojů  

![Sada nástrojů cílených, vybraný podřízený uzel](../../extensibility/ux-guidelines/media/0303-194_toolboxchildnodefocused.png "0303 194_ToolboxChildNodeFocused")<br />Sada nástrojů cílených, vybraný podřízený uzel.

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `TreeView.SelectedItemActive`<br />Z [stromovém zobrazení](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_TreeView) kategorie |
| Ohraničení | `TreeView.FocusVisualBorder`<br />Z [stromovém zobrazení](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_TreeView) kategorie |
| Popředí (glyfy) | `TreeView.SelectedItemActive`<br />Z [stromovém zobrazení](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_TreeView) kategorie |
| Popředí (Text) | `TreeView.SelectedItemActive`<br />Z [stromovém zobrazení](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_TreeView) kategorie |

**Vybraná sada nástrojů uzly: nezaostřená stavu**

![Sada nástrojů vybrané, nezaostřená nadřazený uzel](../../extensibility/ux-guidelines/media/0303-195_toolboxparentnodeunfocused.png "0303 195_ToolboxParentNodeUnfocused")<br />Nadřazený uzel vybrané, nezaostřená sada nástrojů  

![Sada nástrojů vybrané, nezaostřená podřízený uzel](../../extensibility/ux-guidelines/media/0303-196_toolboxchildnodeunfocused.png "0303 196_ToolboxChildNodeUnfocused")<br />Sada nástrojů vybrané, nezaostřená podřízený uzel.  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `TreeView.SelectedItemInactive`<br />Z [stromovém zobrazení](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_TreeView) kategorie |
| Ohraničení | Žádné |
| Popředí (glyfy) | `TreeView.SelectedItemInactive`<br />Z [stromovém zobrazení](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_TreeView) kategorie |
| Popředí (Text) | `TreeView.SelectedItemInactive`<br />Z [stromovém zobrazení](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_TreeView) kategorie |

### <a name="tool-window-title-bar"></a>Okna nástrojů  
Ohraničení panelu název není true ohraničení, je silných řádku v horní části záhlaví. Nemá název tokenu pro jeho nezaostřená stavu.  

![Nástroj okna (červená značka)](../../extensibility/ux-guidelines/media/0303-092_toolwindowtitlebarredline.png "0303 092_ToolWindowTitleBarRedline")<br />Nástroj okna (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... kdekoli vytváříte uživatelské rozhraní, které chcete porovnat nástroje systému windows. | pro všechny uživatelské rozhraní, které nechcete automaticky změnit, pokud má prostředí... aktualizace motivu. |

**Cílených záhlaví**

![Cílených záhlaví](../../extensibility/ux-guidelines/media/0303-093_titlebarfocused.png "0303 093_TitleBarFocused")<br />Cílených záhlaví

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.TitleBarActiveGradientBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.TitleBarActiveText` |
| Ohraničení | `Environment.TitleBarActiveBorder`<br />(Nastavte na stejné barvy jako pozadí). |
| Přetažením úchytu | `Environment.TitleBarDragHandleActive` |

**Nezaostřená záhlaví**  

![Záhlaví nezaostřená](../../extensibility/ux-guidelines/media/0303-094_titlebarunfocused.png "0303 094_TitleBarUnfocused")<br />Nezaostřená záhlaví

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.TitleBarInactiveGradientBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.TitleBarInactiveText` |
| Ohraničení | Není k dispozici |
| Přetažením úchytu | `Environment.TitleBarDragHandle` |

#### <a name="tool-window-title-bar-buttons"></a>Tlačítka panelu nadpis okna nástrojů  
![Title panelu tlačítko (červená značka)](../../extensibility/ux-guidelines/media/0303-095_titlebarbuttonredline.png "0303 095_TitleBarButtonRedline")<br />Title panelu tlačítko (červená značka)  

| Použití... | Nepoužívejte... |
| --- | --- |
| ... pro tlačítka v uživatelské rozhraní, které používá tokeny barva od záhlaví nástroj okno. | ... pro tlačítka v jiných umístění. |
| | ... v libovolné kombinace pozadí nebo popředí, jiné než která byla specifikována. |

**Zaměřuje tlačítek na panelu title: výchozí stav**

![Výchozí, zaměřuje tlačítek na panelu název](../../extensibility/ux-guidelines/media/0303-096_titlebarbuttonfocused.png "0303 096_TitleBarButtonFocused")<br />Výchozím tlačítek na panelu cílených název  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Není k dispozici |
| Popředí (glyfy) | `Environment.ToolWindowButtonActiveGlyph` |
| Ohraničení | Není k dispozici |

**Tlačítka panelu nezaostřená title: výchozí stav**

![Výchozí, tlačítek na panelu nezaostřená název](../../extensibility/ux-guidelines/media/0303-097_titlebarbuttonunfocused.png "0303 097_TitleBarButtonUnfocused")<br />Výchozím tlačítek na panelu nezaostřená název    

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | Není k dispozici |
| Popředí (glyfy) | `Environment.ToolWindowButtonInactiveGlyph` |
| Ohraničení | Není k dispozici |

**Zaměřuje tlačítek na panelu title: najeďte stavu**  

![Zaměřuje tlačítek na panelu název při přechodu myší](../../extensibility/ux-guidelines/media/0303-098_titlebarbuttonfocusedhover.png "0303 098_TitleBarButtonFocusedHover")<br />Tlačítka panelu cílených název při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ToolWindowButtonHoverActive` |
| Popředí (glyfy) | `Environment.ToolWindowButtonHoverActiveGlyph` |
| Ohraničení | `Environment.ToolWindowButtonHoverActiveBorder` |

**Tlačítka panelu nezaostřená title: najeďte stavu**  

![Tlačítka panelu nezaostřená název při přechodu myší](../../extensibility/ux-guidelines/media/0303-099_titlebarbuttonunfocusedhover.png "0303 099_TitleBarButtonUnfocusedHover")<br />Tlačítka panelu nezaostřená název při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ToolWindowButtonHoverInactive` |
| Popředí (glyfy) | `Environment.ToolWindowButtonHoverInactiveGlyph` |
| Ohraničení | `Environment.ToolWindowButtonHoverInactiveBorder` |

**Zaměřuje tlačítek na panelu title: stisknutí stavu**

![Zaměřuje na stisknutím tlačítka panelu název](../../extensibility/ux-guidelines/media/0303-100_titlebarbuttonfocusedpressed.png "0303 100_TitleBarButtonFocusedPressed")<br />Tlačítka panelu cílených název na stisknutím klávesy

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ToolWindowButtonDown` |
| Popředí (glyfy) | `Environment.ToolWindowButtonDownActiveGlyph` |
| Ohraničení | `Environment.ToolWindowButtonDownBorder` |

**Tlačítka panelu nezaostřená title: stisknutí stavu**

![Tlačítka panelu nezaostřená title na stiskněte](../../extensibility/ux-guidelines/media/0303-101_titlebarbuttonunfocusedpressed.png "0303 101_TitleBarButtonUnfocusedPressed")<br />Tlačítka panelu nezaostřená title na stisknutím klávesy  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ToolWindowButtonDown` |
| Popředí (glyfy) | `Environment.ToolWindowButtonDownInactiveGlyph` |
| Ohraničení | `Environment.ToolWindowButtonDownBorder` |

### <a name="tool-window-tabs"></a>Nástroj okna karet  
![Karta okna nástroje (červená značka)](../../extensibility/ux-guidelines/media/0303-102_toolwindowtabredline.png "0303 102_ToolWindowTabRedline")<br />Karta okna nástroje (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... kdekoli vytváříte uživatelské rozhraní, které chcete porovnat nástroje systému windows. | pro všechny uživatelské rozhraní, které nechcete automaticky změnit, pokud má prostředí... aktualizace motivu. |

**Karta nástroje cílených na vybrané okno**

![Vybraná, zaměřuje karta okna nástroje](../../extensibility/ux-guidelines/media/0303-103_toolwindowtabfocused.png "0303 103_ToolWindowTabFocused")<br />Karta nástroje cílených na vybrané okno

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ToolWindowTabSelectedTab` |
| Popředí (Text) | `Environment.ToolWindowTabSelectedActiveText` |
| Ohraničení | `Environment.ToolWindowTabSelectedBorder`<br />(Nastavte na stejné barvy jako pozadí). |

**Karta okna vybrané, nezaostřená nástroje**  

![Karta okna nástroje vybrané, nezaostřená](../../extensibility/ux-guidelines/media/0303-104_toolwindowtabunfocused.png "0303 104_ToolWindowTabUnfocused")<br />Karta okna vybrané, nezaostřená nástroje

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ToolWindowTabSelectedTab` |
| Popředí (Text) | `Environment.ToolWindowTabSelectedText` |
| Ohraničení | `Environment.ToolWindowTabSelectedBorder`<br />(Nastavte na stejné barvy jako pozadí). |

**Karta okna nástroje pozadí: výchozí stav**

![Karta okna nástroje výchozí pozadí](../../extensibility/ux-guidelines/media/0303-105_toolwindowbackgroundtab.png "0303 105_ToolWindowBackgroundTab")<br />Karta okna nástroje výchozí pozadí  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ToolWindowTabGradientBegin`<br />`Environment.ToolWindowTabGradientEnd`<br />(Přechodu zastaví nastaven na stejnou hodnotu barev v sadě Visual Studio 2013.) |
| Popředí (Text) | `Environment.ToolWindowTabText` |
| Ohraničení | `Environment.ToolWindowTabBorder` |

**Karta okna nástroje pozadí: najeďte stavu**

![Karta okna nástroje pozadí při přechodu myší](../../extensibility/ux-guidelines/media/0303-106_toolwindowbackgroundtabhover.png "0303 106_ToolWindowBackgroundTabHover")<br />Karta okna nástroje pozadí při přechodu myší

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.ToolWindowTabMouseOverBackgroundBegin`<br />`Environment.ToolWindowTabMouseOverBackgroundEnd`<br />(Přechodu zastaví nastaven na stejnou hodnotu barev v sadě Visual Studio 2013.) |
| Popředí (Text) | `Environment.ToolWindowTabMouseOverText` |
| Ohraničení | `Environment.ToolWindowTabMouseOverBorder`<br />(Nastavte na stejné barvy jako pozadí). |  

### <a name="auto-hide-tabs"></a>Automaticky skrýt karty  

![Automaticky skrýt karty (červená značka)](../../extensibility/ux-guidelines/media/0303-107_autohideredline.png "0303 107_AutoHideRedline")automaticky skrýt karty (červená značka)

| Použití... | Nepoužívejte... |
| --- | --- |
| ... kdekoli vytváříte uživatelské rozhraní, které chcete porovnat skrytý automaticky nástroj okno karty. | pro všechny uživatelské rozhraní, které nechcete automaticky změnit, pokud má prostředí... aktualizace motivu. |

**Automaticky skrýt karty: výchozí stav**  

![Karta výchozí automaticky skrýt](../../extensibility/ux-guidelines/media/0303-108_autohidetab.png "0303 108_AutoHideTab")<br />Karta výchozí automaticky skrýt

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.AutoHideTabBackgroundBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.AutoHideTabText` |
| Ohraničení | `Environment.AutoHideTabBorder` |

**Automaticky skrýt karty: najeďte stavu**

![Karta automaticky skrýt při přechodu myší](../../extensibility/ux-guidelines/media/0303-109_autohidetabhover.png "0303 109_AutoHideTabHover")<br />Karta automaticky skrýt při přechodu myší  

| Prvek | Název tokenu: Category.color |
| --- | --- |
| Pozadí | `Environment.AutoHideTabMouseOverBackgroundBegin`<br />(Ukončení přechodu pro tento token nepoužívá v motivu uživatelského rozhraní.) |
| Popředí (Text) | `Environment.AutoHideTabMouseOverText` |
| Ohraničení | `Environment.AutoHideTabMouseOverBorder` |
