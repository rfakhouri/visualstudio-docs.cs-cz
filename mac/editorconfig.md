---
title: EditorConfig
description: Pomocí souboru editorconfig povolit konzistentní projektu kódování styly v sadě Visual Studio for Mac.
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 26A0DE31-2FBF-4E1B-99FB-083111AA1680
ms.openlocfilehash: 336ec5ef0779bcd67302bea7b51851dced531a7d
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957386"
---
# <a name="creating-and-editing-a-custom-editorconfig-file"></a>Vytváření a úpravy vlastního souboru EditorConfig

V sadě Visual Studio pro Mac, můžete přidat [EditorConfig](http://editorconfig.org/) souboru do projektu nebo codebase vynutit konzistentní kódování styly pro všechny uživatele, který funguje v základu kódu. Nastavení v souboru EditorConfig deklarována mají přednost před globální text v sadě Visual Studio nastavení editoru. Pomocí EditorConfig v rámci projektu nebo kód vám umožní nastavit vaše kódování styl, předvoleb a upozornění pro váš projekt. To usnadňuje všechny Visual Studio pro Mac uživatelům dodržovat postupy kódování projektu.

[EditorConfig](http://editorconfig.org/) souborů jsou podporovány v mnohé editory integrovaného vývojového prostředí a kód, včetně Visual Studio 2017. 

## <a name="supported-settings"></a>Podporovaná nastavení

Editor v sadě Visual Studio podporuje základní sady [EditorConfig vlastnosti](http://editorconfig.org/#supported-properties):

- `indent_style`
- `indent_size`
- `tab_width`
- `end_of_line`
- `charset`
- `trim_trailing_whitespace`
- `insert_final_newline`
- `root`

Také podporuje EditorConfig [formátování kódu stylu](https://docs.microsoft.com/visualstudio/ide/editorconfig-code-style-settings-reference) v jazyce C#.

## <a name="add-an-editorconfig-file-to-a-project"></a>Přidání souboru EditorConfig do projektu

### <a name="adding-a-new-editorconfig-file"></a>Přidání nového souboru EditorConfig

1. Otevřete projekt v sadě Visual Studio for Mac. Vyberte uzel projektu, který chcete přidat soubory do.

2. S vybraným uzlem projektu, přejděte na **soubor > Nový soubor...** v panelu nabídek otevřete **nový soubor** dialogové okno.

3. Zvolte **různé > prázdný textový soubor** a pojmenujte ho **název** `.editorconfig`. Stiskněte klávesu **nový** k vytvoření souboru a otevře ji v editoru:

    ![Dialogové okno Nový soubor](media/editorconfig-image1.png)

4. Upravte soubor. Příklad:

    ```EditorConfig
    # This file is the top-most EditorConfig file
    root = true

    # All Files
    [*]
    indent_style = space
    indent_size = 8
    insert_final_newline = false
    trim_trailing_whitespace = false

    [*.cs]
    csharp_new_line_before_open_brace = none
    ```

4. Přidání souboru nelze automaticky aktualizovat nastavení. Nastavení, z `.editorconfig` souboru, vyberte uzel projektu a zvolte **Upravit > Formát > Formátovat dokument** z řádku nabídek:

    ![Položka nabídky dokumentu formátu](media/editorconfig-image2.png)

### <a name="adding-an-existing-editorconfig-file"></a>Přidání existující soubor EditorConfig

Pokud pracujete s projektem nebo řešení, která již obsahuje `.editorconfig` souboru, není nic, které musíte udělat při aplikaci nastavení. Žádné nové řádky kódu jsou formátovaná podle nastavení EditorConfig. Upozorňujeme ale, který při Visual Studio pro Mac respektuje `.editorconfig` soubory na úrovni řešení, se nemusí zobrazit v panelu řešení pro kvůli fakt soubory počínaje `.` jsou skryté soubory v systému macOS.

Možná budete chtít použít existující `.editorconfig` soubor ve vašem projektu. Pokud chcete přidat existující soubor, musíte nejprve zobrazíte skryté soubory v hledání tím, že zadáte následující příkaz v **Terminálové**:

```bash
$ defaults write com.apple.Finder AppleShowAllFiles true
$ killall Finder
```

Jednou `.editorconfig` souboru je viditelná, přetáhněte ji do vašeho projektu uzlu. Pokud máte na výběr následující dialogové okno, vyberte **zkopírujte soubor do adresáře** možnost a vyberte **OK**:

![Položka nabídky dokumentu formátu](media/editorconfig-image3.png)

Nastavení, z `.editorconfig` souboru, vyberte uzel projektu a zvolte **Upravit > Formát > Formátovat dokument** z řádku nabídek.

## <a name="editing-an-editorconfig-file"></a>Úpravy souboru EditorConfig

Soubory EditorConfig použijte rozložení přehledné souboru a zadejte nastavení, které jsou vysvětleny níže použijeme předchozí příklad:


```EditorConfig
# This file is the top-most EditorConfig file
root = true

# All Files
[*]
indent_style = space
indent_size = 4
insert_final_newline = false
trim_trailing_whitespace = false

[*.cs]
csharp_new_line_before_open_brace = none
```

Nastavení `root` k `true` bude příznak tento soubor jako soubor nejvyšší základu kódu a všechny novější `.editorconfig` soubory v projektu budou ignorovány, jak je popsáno v [přepsat nastavení EditorConfig](#override-editorconfig-settings) části.

Každá část je označený jako hranaté (**[]**) složené závorky a určuje informace o typech souborů by měl týkají následující vlastnosti.

V příkladu nahoře některá nastavení se použijí na všechny soubory v projektu a ostatní budou přidány pouze pro soubory C#. Na následujících snímcích obrazovky zobrazit před a po `.editorconfig` bylo použito nastavení:

**Před**:

![Před aplikací nastavení editorconfig](media/editorconfig-image4.png)

**Po**:

![Po použití nastavení editorconfig](media/editorconfig-image5.png)

Další informace o dostupných nastaveních EditorConfig najdete v tématu [.NET kódování nastavení konvence pro EditorConfig](https://docs.microsoft.com/visualstudio/ide/editorconfig-code-style-settings-reference) článku a [podporované vlastnosti](http://editorconfig.org/#supported-properties) části na oficiální dokumentaci.

## <a name="override-editorconfig-settings"></a>Přepsání nastavení EditorConfig

Je možné mít více než jeden `.editorconfig` souborů v každé řešení. Visual Studio pro Mac čtení `.editorconfig` soubory shora dolů v řešení, přidávání a přepsáním nastavení, jako je přejde. To znamená, že nastavení v `.editorconfig` _nejbližší_ do souboru, který upravujete, bude mít prioritu. 

Pokud chcete zajistit, aby _žádné_ nastavení z libovolné vyšší úrovně `.editorconfig` soubory platí pro tuto část základu kódu, přidejte `root=true` vlastnost do horní části nižší úrovni `.editorconfig` souboru:

```EditorConfig
# top-most EditorConfig file
root = true
```