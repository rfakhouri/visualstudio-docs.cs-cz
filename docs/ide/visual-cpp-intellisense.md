---
title: Visual C++ Intellisense | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d0a00fb9fa52bcba39f4648fc3ffb9800890ac30
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="visual-c-intellisense"></a>Visual C++ IntelliSense

IntelliSense pro jazyk C++ je k dispozici pro samostatné soubory stejně jako u souborů, které jsou součástí projektu jazyka C++. V projektech pro různé platformy některé funkce IntelliSense jsou k dispozici v souborech sada a .c v projektu sdíleného kódu i v případě, že jste v kontextu Android nebo iOS.

## <a name="intellisense-features-in-c"></a>Funkce technologie IntelliSense v jazyce C++

IntelliSense je název zadaný pro sadu funkcí, které kódování pohodlnější. Vzhledem k tomu, že jiné osoby mít různé návrhy o tom, co je vhodné, prakticky všechny funkce technologie IntelliSense můžete povolit nebo zakázat v **možnosti** dialogovém **textového editoru**  >  **C/C++** > **rozšířené**. **Možnosti** dialogové okno je k dispozici **nástroje** nabídky v řádku nabídek.

![Možnosti nástrojů – dialogové okno](../ide/media/sintellisensecpptoolsoptions.PNG)

Položky nabídky a klávesové zkratky, viz následující obrázek můžete použít pro přístup k technologii IntelliSense.

![Nabídky IntelliSense](../ide/media/vs2015_cpp_intellisense_menu.png)

### <a name="statement-completion-and-member-list"></a>Seznam dokončení a člen – příkaz

Když začnete psát klíčové slovo, typ, funkce, název proměnné nebo jiného programu elementu, který rozpoznává kompilátor, editor nabízí dokončit slovo za vás.

Seznam ikony a jejich významy, naleznete v části [zobrazení tříd a ikony v prohlížeči objekt](../ide/class-view-and-object-browser-icons.md).

![Visual C&#43;&#43; Complete Word window](../ide/media/vs2015_cpp_complete_word.png "vs2015_cpp_complete_word")

Při prvním vyvolání seznam členů pouze zobrazuje členy, které jsou dostupné pro aktuální kontext. Pokud vyberete **Ctrl**+**J** po, který se zobrazí všechny členy, bez ohledu na usnadnění přístupu. Pokud vyvolání ho třetí čas, zobrazí se i širší seznam prvky programu. Můžete vypnout seznam členů v **možnosti** dialogovém **textového editoru** > **C/C++** > **Obecné**  >  **Automatický seznam členů**.

![Visual C&#43;&#43; Member List](../ide/media/vs2015_cpp_list_members.png "vs2015_cpp_list_members")

### <a name="parameter-help"></a>Parametr nápovědy

Když zadáte žádná levá složená závorka volání funkce nebo lomená závorka v deklaraci třídy šablony proměnné, představuje editoru malém okně s typy parametrů pro každé přetížení funkce nebo konstruktor. Parametr "aktuální"&mdash;v závislosti na umístění kurzoru&mdash;je tučným písmem. Informace o parametrech v můžete vypnout **možnosti** dialogovém **textového editoru** > **C/C++** > **Obecné**  >  **Informace o parametrech**.

![Visual C&#43;&#43; Parameter Help](../ide/media/vs_2015_cpp_param_help.png "vs_2015_cpp_param_help")

### <a name="quick-info"></a>Rychlé informace

Když najedete myší do proměnné, zobrazí se vložené, která obsahuje informace o typu a záhlaví, ve kterém je definovaný typ malém okně. Podržte ukazatel nad volání funkce zobrazíte podpis funkce. Můžete vypnout v rychlé informace **možnosti** dialogovém **textového editoru** > **C/C++** > **Upřesnit**  >  **Automaticky rychlé informace**.

![Visual C&#43;&#43; QuickInfo](../ide/media/vs2015_cpp_quickinfo.png "vs2015_cpp_quickInfo")

### <a name="error-squiggles"></a>Chyba podtržení vlnovkou

Podtržení vlnovkou pod element programu (proměnné, – klíčové slovo, složené závorce, název typu a tak dále) volání pozornost chyba nebo potenciální chyby v kódu. Zelená vlnovku se zobrazí, když napíšete dopředného deklarace, a tak poznáte, že stále nutné zapsat implementace. Fialové vlnovku se zobrazí v sdílený projekt když dojde k chybě v kódu, který není aktuálně aktivní, třeba když pracují v kontextu systému Windows, ale něco zadat, která by byla v kontextu Android chybu. Červenou vlnovkou označuje kompilátoru chyby nebo upozornění v active kód, který je potřeba řešit.

![Visual C & č. 43; & č. 43; podtržení vlnovkou chyba](../ide/media/vs2015_cpp_error_quiggles.png "vs2015_cpp_error_quiggles")

### <a name="code-colorization-and-fonts"></a>Kód zabarvení a písem

Výchozí barev a písem lze změnit v **možnosti** dialogovém **prostředí** > **písma a barev**. Můžete změnit písmo pro mnoho uživatelského rozhraní windows tady, ne jenom editoru. Nastavení, které jsou specifické pro C++ začínat řetězcem "C++"; ostatní nastavení jsou pro všechny jazyky.

### <a name="cross-platform-intellisense"></a>Cross-platform IntelliSense

V projektu sdíleného kódu některé funkce IntelliSense, jako je například podtržení vlnovkou jsou k dispozici i v případě, že pracujete v kontextu systému Android. Pokud píšete některé kód, který by mělo za následek chybu v projektu na neaktivní, IntelliSense stále zobrazuje podtržení vlnovkou, ale jsou v barvu než podtržení vlnovkou chyby v aktuálním kontextu.

Zde je aplikace OpenGLES nakonfigurovaný tak, aby sestavení pro Android a iOS. Na obrázku upravovaný sdíleného kódu. V první bitovou kopii aktivní projekt je Android:

![Aktivní projekt je projektu pro Android. ] (../ide/media/intellisensecppcrossplatform.png "IntelliSenseCppCrossPlatform")

Všimněte si následujících akcí:

- #Else větve na řádku 8 je zobrazeno šedě udávajících neaktivní oblast, protože __ANDROID\_ \_ je definována pro projekt pro Android.

- S pozdravem proměnná na řádku 11 je inicializován s identifikátorem HELLO, který má fialové vlnovku. Je to proto, že žádný identifikátor HELLO je definována v projektu pro iOS teď neaktivní. Když v Android by kompilace projektu řádku 11, nebude v iOS. Vzhledem k tomu, že to je sdílené kód, který je něco byste měli změnit, i když se zkompiluje v konfiguraci aktivní.

- Řádek 12 obsahuje červenou vlnovkou identifikátor BYE; Tento identifikátor není definován v aktuálně vybraném aktivního projektu.

Nyní změňte aktivní projekt iOS.StaticLibrary a Všimněte si, jak podtržení vlnovkou změnit.

![iOS je vybrán jako aktivní projekt. ] (../ide/media/intellisensecppcrossplatform2.png "IntelliSenseCppCrossPlatform2")

Všimněte si následujících akcí:

- #Ifdef větev na řádku 6 je zobrazeno šedě udávajících neaktivní oblast, protože __ANDROID\_ \_ pro iOS projektu není definován.

- S pozdravem proměnná na řádku 11 je inicializován s identifikátorem HELLO, která má nyní červenou vlnovkou. Je to proto, že žádný identifikátor HELLO je definován v projektu iOS momentálně aktivní.

- Řádek 12 obsahuje fialové vlnovku identifikátor BYE; Tento identifikátor není definován v současné době neaktivní Android.NativeActivity projektu.

### <a name="intellisense-for-stand-alone-files"></a>IntelliSense pro samostatné soubory

Když otevřete jeden soubor mimo žádného projektu, se stále objevuje IntelliSense. Můžete povolit nebo zakázat konkrétní funkce IntelliSense **možnosti** dialogovém **textového editoru** > **C/C++**  >  **Rozšířené**. Konfigurace technologie IntelliSense pro jednotlivé soubory, které nejsou součástí projektu, vyhledejte **IntelliSense a procházení pro soubory bez projektu** části.

![Visual C & č. 43; & č. 43; jeden soubor intellisense](../ide/media/vs2015_cpp_single_file_intellisense.png "vs2015_cpp_single_file_intellisense")

Ve výchozím nastavení jedním souborem IntelliSense pouze používá standardní zahrnují adresáře, které chcete najít soubory hlaviček. Pokud chcete přidat další adresáře, otevřete místní nabídce na uzlu řešení a přidejte do adresáře **ladění zdrojového kódu** seznamu, jak ukazuje následující obrázek:

![Přidání cesty do souboru záhlaví. ] (../ide/media/intellisensedebugyourcode.jpg "IntelliSenseDebugYourCode")

## <a name="see-also"></a>Viz také

[Používání atributu IntelliSense](../ide/using-intellisense.md)