---
title: "Písma a barvy, prostředí, dialogové okno Možnosti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPag.Environment.Fonts_And_Colors
- VS.ToolsOptionsPages.FontsAndColors
- VS.ToolsOptionsPages.Environment.Fonts_And_Colors
- VS.Environment.Fonts And Colors
helpviewer_keywords:
- colors, customizing IDE
- Query and View Designer, customizing
- fonts, editors
- menus, customizing
- Table Designer, customizing
- Database Designer, customizing environment
- default colors
- accessibility, options
- editors, customizing
- designers, customizing environment
- defaults, colors
- printers, customizing
ms.assetid: c767d302-51ed-47a8-a527-c07bce2aa485
caps.latest.revision: "27"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 23e6712dbf66c898757176aca9e89b98de2f65bc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="fonts-and-colors-environment-options-dialog-box"></a>Písma a barvy, prostředí, dialogové okno Možnosti
**Písma a barev** stránky **možnosti** dialogové okno umožňuje vytvořit vlastní písma a barev režim pro různé prvky uživatelského rozhraní v integrované vývojové prostředí (IDE). Tohoto dialogového okna můžete přejít pomocí kliknutím na tlačítko **Nástroje / možnosti**a potom vyberete **prostředí / písma a barev**. Pokud tato stránka se nezobrazí v seznamu, vyberte **zobrazit všechna nastavení** v **možnosti** dialogové okno.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).  
  
 Barva schéma změny se projeví během relace, ve kterém je provedete. Změny barev můžete vyhodnotit otevřením jiná instance sady Visual Studio a vytvoření podmínek, za kterých byste měli použít.  
  
 **Zobrazit nastavení pro**  
 Zobrazí seznam všech prvků uživatelského rozhraní, pro které můžete změnit schémata písma a barev. Po výběru položky z tohoto seznamu, můžete upravit nastavení barvu pro vybranou položku v **zobrazení položek**.  
  
-   **Textový Editor**  
  
     Změny styl písma, velikosti a barvy zobrazení nastavení pro textový Editor ovlivňují vzhledu textu v textovém editoru výchozí. Tato nastavení neovlivní dokumenty otevřít v textovém editoru mimo prostředí IDE.  
  
-   **Tiskárny**  
  
     Změny styl písma, velikosti a barvy zobrazení nastavení tiskárny ovlivní vzhledu textu v dokumentech na tištěných.  
  
    > [!NOTE]
    >  Podle potřeby můžete vybrat různé výchozí písma pro tisk než používá pro zobrazení v textovém editoru. To může být užitečné při tisku kód, který obsahuje jak jednobajtové tak dvoubajtové znaky.  
  
-   **Dokončování příkazů**  
  
     Změní písmo a velikosti pro text, který se zobrazí v dokončování automaticky otevírané okno v editoru.  
  
-   **Popis tlačítka editoru**  
  
     Změní písmo a velikosti pro text, který se zobrazí v popisu zobrazí v editoru.  
  
-   **Prostředí písma**  
  
     Změní písmo, styl a velikost pro všechny prvky rozhraní uživatele IDE, které ještě nemají samostatnou možností v **zobrazit nastavení pro.** Například tato možnost se vztahuje na **– úvodní stránka** , ale nebude mít vliv **výstup** okno.  
  
-   **[Všechny Text nástroj Windows]**  
  
     Změny styl písma, velikosti a barvy zobrazení nastavení pro tuto položku vliv vzhledu textu v systému windows nástroje, které mají podokna výstup v prostředí IDE. Například výstup – okno příkazové okno, hodnot proměnných, atd.  
  
    > [!NOTE]
    >  Změní na text **[všechna okna textových nástrojů]** položky se projeví během relace, ve kterém je provedete. Tyto změny můžete vyhodnotit otevřením jiná instance sady Visual Studio.  
  
**Použít výchozí nastavení**  
Obnoví písma a barev hodnoty seznamu vybranou položku v **zobrazit nastavení pro**. **Použití** tlačítko se zobrazí, když jsou k dispozici pro výběr jiná schémata zobrazení. Například můžete ze dvou režimů tiskárny.  
  
**Písem (tučné písmo znamená pevnou šířkou písem)**  
Zobrazí seznam všech písem v systému nainstalována. Když poprvé objeví v rozevírací nabídce, aktuální písmo pro vybraný v elementu **zobrazit nastavení pro** zvýrazní pole. Pevné písem – které jsou lépe zarovnat v editoru – tučným písmem.  
  
**Velikost**  
Velikosti pro zvýrazněná písmo bodu seznamy, které jsou k dispozici. Změna velikosti písma ovlivní všechny **zobrazení položek** pro **zobrazit nastavení pro** výběr.  
  
**Zobrazení položek**  
Uvádí položky, pro které můžete změnit barvu popředí a na pozadí.  
  
> [!NOTE]
>  **Prostý Text** je výchozí položku zobrazení. Jako takový přiřazené vlastnosti **ve formátu prostého textu** bude přepsáno vlastnosti, které jsou přiřazeny k ostatním položkám zobrazení. Například, pokud přiřadíte barvu blue k **ve formátu prostého textu** a na zelenou barvu **identifikátor**, všechny identifikátory zobrazí zeleně. V tomto příkladu **identifikátor** vlastnosti přepsání **ve formátu prostého textu** vlastnosti.  
  
 Zobrazit položky patří:  
  
|Zobrazení položek|Popis|  
|------------------|-----------------|  
|**Prostý Text**|Text v editoru.|  
|**Vybraný Text**|Text, který je zahrnut v aktuálním výběru, když má právě fokus, editoru.|  
|**Neaktivní vybraný Text**|Text, který je zahrnut v aktuálním výběru při editoru ztratil fokus.|  
|**Okraj indikátoru**|Okraje v levém z editoru kódu kde se zobrazují zarážky a ikony záložky.|  
|**Čísla řádků**|Volitelné čísla, která se zobrazí vedle každého řádku kódu|  
|**Zobrazit prázdné znaky**|Mezery, tabulátory a word zabalení ukazatele|  
|**Záložka**|Řádky, které mají záložky. **Záložka** se zobrazí, pokud je zakázána okraj indikátoru.|  
|**Závorky (zvýraznit)**|Zvýraznění, který je obvykle tučné písmo pro odpovídající složené závorky.|  
|**Závorky (obdélníku)**|Zvýraznění, který je obvykle šedé obdélníku na pozadí.|  
|**Zarážek (zakázáno)**|Nepoužívá se.|  
|**Zarážek (povoleno)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují jednoduché zarážky. Tuto možnost lze použít pouze v případě, že příkaz úrovni zarážky jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti](../../debugger/general-debugging-options-dialog-box.md).|  
|**Zarážek (chyba)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují zarážky, které jsou v chybovém stavu. Použít pouze v případě, že příkaz úrovni zarážky jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti](../../debugger/general-debugging-options-dialog-box.md).|  
|**Zarážek (upozornění)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují zarážky, které jsou ve stavu varování. Použít pouze v případě, že příkaz úrovni zarážky jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti](../../debugger/general-debugging-options-dialog-box.md).|  
|**Breakpoint – pokročilé (zakázáno)**|Určuje, že barva zvýraznění pro příkazy nebo řádky, které obsahují zakázáno podmíněného a stiskněte klávesu započítány zarážky. Použít pouze v případě, že příkaz úrovni zarážky jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti](../../debugger/general-debugging-options-dialog-box.md).|  
|**Breakpoint – pokročilé (povoleno)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují podmíněné a stiskněte klávesu započítány zarážky. Použít pouze v případě, že příkaz úrovni zarážky jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti](../../debugger/general-debugging-options-dialog-box.md).|  
|**Breakpoint – pokročilé (chyba)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují podmíněné a stiskněte klávesu započítány zarážky, které jsou v chybovém stavu. Použít pouze v případě, že příkaz úrovni zarážky jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti](../../debugger/general-debugging-options-dialog-box.md).|  
|**Breakpoint – pokročilé (upozornění)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují podmíněné a stiskněte klávesu započítány zarážky, které jsou ve stavu varování. Použít pouze v případě, že příkaz úrovni zarážky jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti](../../debugger/general-debugging-options-dialog-box.md).|  
|**Breakpoint – namapované (zakázáno)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují zakázané namapované zarážky. Platí pro ASP nebo ASP.NET ladění, pokud příkaz úrovni zarážky jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti Pole](../../debugger/general-debugging-options-dialog-box.md).|  
|**Breakpoint – - namapované (povoleno)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují namapované zarážky. Platí pro ASP nebo ASP.NET ladění, pokud příkaz úrovni zarážky jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti Pole](../../debugger/general-debugging-options-dialog-box.md).|  
|**Breakpoint – namapované (chyba)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují namapované zarážky v chybovém stavu. Platí pro ASP nebo ASP.NET ladění, pokud příkaz úrovni zarážky jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti Pole](../../debugger/general-debugging-options-dialog-box.md).|  
|**Breakpoint – namapované (upozornění)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují namapované zarážky ve stavu varování. Platí pro ASP nebo ASP.NET ladění, pokud příkaz úrovni zarážky jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti Pole](../../debugger/general-debugging-options-dialog-box.md).|  
|**Uživatelská klíčová slova jazyka C/C++**|Konstanta v souboru konkrétní kódu definované pomocí `#define` – direktiva.|  
|**Vrátí volání**|Určuje barvu zvýraznění pro příkazy zdroj nebo řádky, které oznámí návratový body volání kontextu je přepnuta do bloku-horní části zásobníku při ladění.|  
|**Pole závislé fragmentu kódu**|Pole, které se aktualizují, když se mění aktuální upravitelné pole.|  
|**Pole fragmentu kódu**|Upravitelné pole, když je aktivní fragmentu kódu.|  
|**Sbalitelné textu**|Blok textu nebo kód, který můžou být směřující zobrazení v editoru kódu.|  
|**Komentář**|Komentáře kódu.|  
|**Chyba kompilátoru**|Modré podtržení vlnovkou v editoru indikující chybu kompilátoru.|  
|**Pokrytí nedotčených oblasti**|Kód, která není předmětem testování částí.|  
|**Pokrytí částečně dotýkal oblasti**|Kód, který má byla částečně předmětem testování částí.|  
|**Pokrytí dotýkal oblasti**|Kód, který má byla úplně předmětem testování částí.|  
|**Komentář šablon stylů CSS**|Komentáře v kaskádových stylů. Příklad:<br /><br /> / * Komentář\*/|  
|**Šablon stylů CSS – klíčové slovo**|Klíčová slova v stylů CSS.|  
|**Název vlastnosti funkce CSS**|Název vlastnosti, jako je například pozadí.|  
|**Hodnota vlastnosti CSS**|Hodnota přiřazená k vlastnosti, například blue.|  
|**Selektor šablon stylů CSS**|Řetězec, který identifikuje přizpůsobitelné prvky odpovídající pravidlo vztahuje. Selektor může být buď jednoduchý selektor, takové 'H1 nebo kontextové selektor, jako je například "H1 B", který se skládá z několika jednoduchých selektorů.|  
|**Hodnotu řetězce šablon stylů CSS**|Řetězec v kaskádových stylů.|  
|**Aktuální seznam umístění**|Aktuálního řádku přešli v okně nástroje seznamu, jako je například výstup – okno nebo najít výsledky windows.|  
|**Aktuální příkaz**|Určuje barvu zvýraznění pro příkaz zdroj na řádek, který označuje aktuální pozici krok při ladění.|  
|**Změnit Data ladicí program**|Barva textu slouží k zobrazení změněná data uvnitř **zaregistruje** a **paměti** systému windows.|  
|**Definice okna pozadí**|Barva pozadí **definice kódu** okno.|  
|**Definice okna aktuální shoda**|Aktuální definice v **definice kódu** okno.|  
|**Název souboru zpětný překlad**|Barva textu slouží k zobrazení souboru název zalomení uvnitř **zpětný překlad** okno.|  
|**Zpětný překlad zdroje**|Barva textu slouží k zobrazení původní řádky uvnitř **zpětný překlad** okno.|  
|**Zpětný překlad – Symbol**|Barva textu slouží k zobrazení názvy symbolů uvnitř **zpětný překlad** okno.|  
|**Zpětný překlad textu**|Barva textu slouží k zobrazení operační kód a obsažená data **zpětný překlad** okno.|  
|**Vyloučené kódu**|Kód, který není pro kompilovat, za podmíněného direktivy preprocesoru například `#if`.|  
|**Identifikátor**|Identifikátory v kódu, například názvy tříd, metod názvy a názvy proměnných.|  
|**– Klíčové slovo**|Klíčová slova pro daný jazyk, které jsou vyhrazené. Příklad: třída a oboru názvů.|  
|**Adresa paměti**|Barva textu slouží k zobrazení sloupci adresa uvnitř **paměti** okno.|  
|**Změnit paměti**|Barva textu slouží k zobrazení změněná data uvnitř **paměti** okno.|  
|**Data paměti**|Barva textu slouží k zobrazení dat uvnitř M**zašifrování** okno.|  
|**Nejde přečíst paměti**|Barva textu slouží k zobrazení nečitelná paměťové oblasti v rámci **paměti** okno.|  
|**Číslo**|Číslo v kódu, který představuje skutečný číselná hodnota.|  
|**Operátor**|Operátory, jako například +, -, a! =.|  
|**Další chyby**|Jiné typy chyb, nevztahuje podtržení vlnovkou jiné chyby. V současné době to zahrnuje článku neslušní úpravy v dialogu Upravit a pokračovat.|  
|**Preprocesor – klíčové slovo**|Klíčová slova, jako používá preprocesor #include.|  
|**Oblast jen pro čtení**|Kód, který nelze upravovat. Například kód zobrazený v okně zobrazení definice kód nebo kód, který nemůže být upraven během upravit a pokračovat.|  
|**Refaktoring pozadí**|Barva pozadí **zobrazení náhledu změn** dialogové okno.|  
|**Refaktoring aktuální pole**|Barva aktuálního elementu, který chcete být rozdělili v pozadí **zobrazení náhledu změn** dialogové okno.|  
|**Refaktoring závislé pole**|Barva odkazů elementu, který chcete být rozdělili v **zobrazení náhledu změn** dialogové okno.|  
|**Data registru**|Barva textu slouží k zobrazení obsažená data **zaregistruje** okno.|  
|**Zaregistrovat NAT**|Barva textu slouží k zobrazení nerozpoznané dat a objektů uvnitř **zaregistruje** okno.|  
|**Inteligentní značky**|Používá se k označení obrys, když jsou vyvolány inteligentních značek.|  
|**Značky SQL DML**|Platí pro editoru jazyka Transact-SQL. Příkazy DML v tohoto editoru jsou označené ohraničující blue pole ve výchozím nastavení.|  
|**Zastaralý kód**|Systém čeká na aktualizace nahrazené kód. V některých případech upravit a pokračovat nelze použít změny kódu okamžitě, ale je použít později budete pokračovat, ladění. K tomu dochází, pokud chcete upravit funkci, která musí volat funkci aktuálně spuštěné, nebo pokud přidáte více než 64 bajtů nové proměnné na funkci čekání na v zásobníku volání. V takovém případě ladicí program zobrazí dialogové okno "Upozornění na starý kód", a nahrazené kód bude pokračovat v provádění až do dokončení dotyčném funkce a nebude volán znovu. Upravit a pokračovat platí v daném čase změny kódu.|  
|**Řetězec**|Textové literály.|  
|**Řetězce (C# @ typu Verbatim)**|Textové literály v jazyce C#, které se interpretují doslovné. Příklad:<br /><br /> @"x"|  
|**Chyba syntaxe**|Analyzovat chyby.|  
|**Zástupce seznamu úkolů**|Pokud **seznam úkolů** zástupce se přidá na řádek a okraj indikátoru je zakázáno, bude mít zvýrazněná řádku.|  
|**Tracepoint (zakázáno)**|Nepoužívá se.|  
|**Tracepoint (povoleno)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují jednoduché tracepoints. Tuto možnost lze použít pouze v případě, že příkaz úrovni tracepoints jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti](../../debugger/general-debugging-options-dialog-box.md).|  
|**Tracepoint (chyba)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují tracepoints, které jsou v chybovém stavu. Tuto možnost lze použít pouze v případě, že příkaz úrovni tracepoints jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti](../../debugger/general-debugging-options-dialog-box.md).|  
|**Tracepoint (upozornění)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují tracepoints, které jsou ve stavu varování. Tuto možnost lze použít pouze v případě, že příkaz úrovni tracepoints jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti](../../debugger/general-debugging-options-dialog-box.md).|  
|**Tracepoint - rozšířené (zakázáno)**|Určuje, že barva zvýraznění pro příkazy nebo řádky, které obsahují zakázáno podmíněného a stiskněte klávesu započítány tracepoints. Tuto možnost lze použít pouze v případě, že příkaz úrovni tracepoints jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti](../../debugger/general-debugging-options-dialog-box.md).|  
|**Tracepoint - rozšířené (povoleno)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují podmíněné a stiskněte klávesu započítány tracepoints. Tuto možnost lze použít pouze v případě, že příkaz úrovni tracepoints jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti](../../debugger/general-debugging-options-dialog-box.md).|  
|**Tracepoint - rozšířené (chyba)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují podmíněné a stiskněte klávesu započítány tracepoints, které jsou v chybovém stavu. Tuto možnost lze použít pouze v případě, že příkaz úrovni tracepoints jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti](../../debugger/general-debugging-options-dialog-box.md).|  
|**Tracepoint - rozšířené (upozornění)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují podmíněné a stiskněte klávesu započítány tracepoints, které jsou ve stavu varování. Tuto možnost lze použít pouze v případě, že příkaz úrovni tracepoints jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti](../../debugger/general-debugging-options-dialog-box.md).|  
|**Tracepoint - namapované (zakázáno)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují zakázané tracepoints namapované. Platí pro ASP nebo ASP.NET ladění, pokud příkaz úrovni zarážky jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti Pole](../../debugger/general-debugging-options-dialog-box.md).|  
|**Tracepoint - namapované (povoleno)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují namapované tracepoints. Platí pro ASP nebo ASP.NET ladění, pokud příkaz úrovni zarážky jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti Pole](../../debugger/general-debugging-options-dialog-box.md).|  
|**Tracepoint - namapované (chyba)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují namapované tracepoints v chybovém stavu. Platí pro ASP nebo ASP.NET ladění, pokud příkaz úrovni zarážky jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti Pole](../../debugger/general-debugging-options-dialog-box.md).|  
|**Tracepoint - namapované (upozornění)**|Určuje barvu zvýraznění pro příkazy nebo řádky, které obsahují namapované tracepoints ve stavu varování. Platí pro ASP nebo ASP.NET ladění, pokud příkaz úrovni zarážky jsou aktivní nebo **zvýrazněte řádek celý zdrojový zarážky nebo aktuální příkaz** možnost na [Obecné, ladění, dialogové okno Možnosti Pole](../../debugger/general-debugging-options-dialog-box.md).|  
|**Sledování změn po uložení**|Řádky kódu, které byly změněny vzhledem k tomu, že byl soubor otevřít, ale jsou uloženy na disk.|  
|**Sledování změn před uložit**|Řádky kódu, které byly změněny vzhledem k tomu, že byl soubor otevřít, ale nejsou uloženy na disk.|  
|**Typy uživatelů**|Uživatelem definované typy.|  
|**Uživatel zadá (delegáti)**|Zadejte barvu delegáti.|  
|**Uživatel zadá (výčty)**|Zadejte barvu použitou pro výčty.|  
|**Uživatel zadá (rozhraní)**|Zadejte barvu pro rozhraní.|  
|**Typy uživatelů (hodnota typy)**|Zadejte barvu pro typy hodnot, jako je například struktury v jazyku C#.|  
|**Číst pouze značky jazyka Visual Basic**|Značku specifické pro použitý pro určení Šif, např. výjimka oblastí, definici metody a volání mimo úroveň listu rámce jazyka Visual Basic.|  
|**Upozornění**|Upozornění kompilátoru.|  
|**Cesta řádky upozornění**|Používá se pro statické analýzy upozornění řádky.|  
|**Atribut XML**|Názvy atributů.|  
|**Uvozovky atributu XML**|Znaky uvozovek pro atributy XML.|  
|**Hodnota atributu XML**|Obsah XML atributů.|  
|**Části XML Cdata**|Obsah \<! [ CDATA [...]] >.|  
|**Komentáře XML**|Obsah \<!---->.|  
|**Oddělovač XML**|Syntaxe jazyka XML oddělovače, včetně <, <?, <!, \<!--,-->,?\>, \<! [,]] > a [,].|  
|**Atribut Doc XML**|Hodnota dokumentace xml, jako atribut \<název parametru = "I" > kde je obarvené "I".|  
|**Komentáře Doc XML**|Komentáře v dokumentační komentáře xml.|  
|**Doc – značka XML**|Značky v dokumentu XML jako komentáře<br /><br /> /// \<Souhrn >.|  
|**XML – klíčové slovo**|Klíčová slova DTD jako CDATA, IDREF a data NDATA.|  
|**Název XML**|Názvy elementů a název cílové zpracování pokynů.|  
|**Pokyny pro zpracování XML**|Obsah zpracování pokynů, není včetně název cílové.|  
|**Textu XML**|Obsah elementu prostý text.|  
|**XSLT – klíčové slovo**|Názvy elementů XSLT.|  
  
 **Položka popředí**  
 Obsahuje seznam dostupných barev lze vybrat popředí položky vybrané v **zobrazení položek**. Protože některé položky se vztahují a má proto Udržovat schéma konzistentní zobrazení, změna barvu popředí text změní také výchozí hodnoty pro prvky, jako je chyba kompilátoru, – klíčové slovo nebo operátor.  
  
 **Automatické** položky můžete barvu popředí dědí od ostatních zobrazení položek, jako **prostý Text**. Použití této možnosti, když změníte barvu položky zděděné zobrazení barvy související zobrazení položek také automaticky změnit. Například pokud jste vybrali **automatické** hodnota **Chyba kompilátoru** a později změnit barvu **prostý Text** na červený, **Chyba kompilátoru**by také automaticky převezmou červenou barvu.  
  
 **Výchozí** barvu, která zobrazuje dobu položky první spuštění sady Visual Studio. Kliknutím **použít výchozí hodnoty** tlačítko obnoví na tuto barvu.  
  
 **Vlastní**  
 Zobrazí dialogové okno barvy a umožní vám nastavit vlastní barvu pro vybranou položku v seznamu položky zobrazení.  
  
> [!NOTE]
>  Nastavení barvy pro zobrazení počítač může být omezena možnost definovat vlastní barvy. Například, pokud je počítač nakonfigurován pro zobrazení 256 barev a vyberte vlastní barvu ze **barva** dialogové okno, rozhraní IDE výchozí hodnoty na nejbližší dostupné **základní barvu** a zobrazí se v černé barvy **Barva** preview pole.  
  
 **Pozadí položky**  
 Obsahuje paletu barev, ze kterého můžete zvolit barvu pozadí pro vybranou položku v **zobrazení položek**. Protože některé položky se vztahují a má proto Udržovat schéma konzistentní zobrazení, změna barvy pozadí textu také změní výchozí hodnoty pro prvky, jako je chyba kompilátoru, – klíčové slovo nebo operátor.  
  
 **Automatické** položky můžete barvu pozadí dědí od ostatních zobrazení položek, jako **prostý Text**. Použití této možnosti, když změníte barvu položky zděděné zobrazení barvy související zobrazení položek také automaticky změnit. Například pokud jste vybrali **automatické** hodnota **Chyba kompilátoru** a později změnit barvu **prostý Text** na červený, **Chyba kompilátoru**by také automaticky převezmou červenou barvu.  
  
 **Výchozí** barvu, která zobrazuje dobu položky první spuštění sady Visual Studio. Kliknutím **použít výchozí hodnoty** tlačítko obnoví na tuto barvu.  
  
 **Vlastní**  
 Zobrazí dialogové okno barvy a umožní vám nastavit vlastní barvu pro vybranou položku v seznamu položky zobrazení.  
  
 **Bold**  
 Vyberte tuto možnost, chcete-li zobrazit text vybrané **zobrazení položek** tučným písmem. Tučně je pak snadno identifikujete v editoru.  
  
 **Ukázka**  
 Zobrazuje ukázku styl písma, velikosti a barevné schéma **zobrazit nastavení pro** a **zobrazení položek** vybrané. Toto pole můžete zobrazit náhled výsledků, jak můžete experimentovat s různými možnostmi formátování.  
  
## <a name="see-also"></a>Viz také  
 [Dialogové okno Možnosti prostředí](../../ide/reference/environment-options-dialog-box.md)   
 [Dialogové okno Možnosti](../../ide/reference/options-dialog-box-visual-studio.md)   
 [Postupy: Změna písma a barev](../../ide/how-to-change-fonts-and-colors-in-visual-studio.md)