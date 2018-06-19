---
title: Přejděte kódu v sadě Visual Studio
ms.date: 09/26/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code editor, navigation
- code editor, go to
- code editor, go to definition
- code editor, go to line
- code editor, peek definition
- code editor, navigation bar
- go to definition
- peek definition
- go to line
- go to
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9293565b4a238b1486f491c5a343d83364fba088
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
ms.locfileid: "34448607"
---
# <a name="navigate-code"></a>Přejděte kódu

Visual Studio poskytuje mnoho způsobů přejděte v editoru kódu. Toto téma shrnuje různé způsoby, můžete přejít kódu a poskytuje odkazy na témata, které patří do více podrobností.

## <a name="navigate-backward-and-navigate-forward-commands"></a>Přejděte zpět a přejděte dál příkazy

Můžete použít **přejděte zpětné** (**Ctrl**+**-**) a **přejděte dál** ( **CTRL**+**Shift**+**-**) tlačítek na panelu nástrojů pro přesun kurzoru do předchozího umístění, nebo pro návrat k další Poslední umístění z předchozího umístění. Tato tlačítka zachovat poslední 20 umístění kurzoru. Tyto příkazy jsou také k dispozici na **zobrazení** nabídce v části **přejděte zpětné** a **přejděte dál**.

![Navigační tlačítka vpřed a zpět](../ide/media/vs2017_nav_buttons.png)

## <a name="navigation-bar"></a>Navigační panel

Můžete použít **navigační panel** (rozevíracího seznamu polí v horní části okna kódu) přejděte na kód základu kódu. Můžete přejít přímo na na typ nebo člen. Na navigačním panelu se zobrazí, když upravíte kód v jazyka Visual Basic, c nebo C++ – kód základní. Částečné třídy, mohou být zakázány členy definované mimo aktuální soubor kódu (se zobrazí šedě).

 ![Navigační panel kódu](../ide/media/vside_navigation_bar.png)

Můžete přejít okolo rozevírací seznamy následujícím způsobem:

- Přejděte do jiného projektu, který je součástí aktuální soubor, vyberte v levé rozevíracího seznamu.

- Přejděte na třídy nebo typu, vyberte ho uprostřed rozevíracího seznamu.

- Přejít přímo na procedury nebo jiného člena třídy, vyberte ho v pravém rozevíracího seznamu.

- Pokud chcete Přesun zaměření z okna kódu na navigačním panelu, stiskněte kombinaci kláves **Ctrl**+**F2**.

- Chcete-li přesun zaměření pole z pole na navigačním panelu, stiskněte **kartě** klíč.

- Chcete-li vybrat položku navigační panel se fokus a vraťte se do okna kód, stiskněte **Enter** klíč.

- Vrátit fokus z navigačního panelu kód bez provedení výběru, stiskněte **Esc** klíč.

Skrytí navigačního panelu, změnit **navigační panel** možnost **textový Editor, všechny jazyky** nastavení (**nástroje** > **možnosti**  >  **Textového editoru** > **všechny jazyky**), nebo můžete změnit nastavení pro jednotlivé jazyky.

## <a name="find-all-references"></a>Najít všechny odkazy

Vyhledá všechny odkazy na vybraný prvek v řešení. To můžete použít ke kontrole možné vedlejší účinky z velké refaktoring nebo ověření "neaktivní" kódu. Stiskněte klávesu **F8** přejít mezi výsledky. Další informace najdete v tématu [najít odkazy ve vašem kódu](finding-references.md).

Vstup        | Funkce
------------ | ---
**Klávesnice** | Umístěte ukazatel myši na text někde uvnitř název typu a stiskněte klávesu **Shift**+**F12**
**Myš**    | Vyberte **najít všechny odkazy** z místní nabídky

## <a name="reference-highlighting"></a>Zvýrazňování odkazu

Po kliknutí na tlačítko symbol ve zdrojovém kódu, jsou všechny instance tohoto symbolu zvýrazněných v dokumentu. Zvýrazněná symboly může zahrnovat deklarace a odkazy a mnoho dalších symboly, který **najít všechny odkazy** by vrátit. Patří mezi ně názvy tříd, objekty, proměnné, metod a vlastností. V kódu Visual Basic jsou také vyznačené klíčová slova pro mnoho řídicí struktury. Chcete-li přejít na další nebo předchozí zvýrazněný symbol, stiskněte **Ctrl**+**Shift**+**šipka dolů** nebo **Ctrl** + **Shift**+**šipka nahoru**. Můžete změnit barvu zvýraznění v **nástroje** > **možnosti** > **prostředí** > **písem a Barvy** > **zvýrazněná odkaz**.

## <a name="go-to-commands"></a>Přejít na příkazy

Přejít na má následující příkazy, které jsou k dispozici v **upravit** nabídky v části **přejít na**:

- **Přejít na řádek** (**Ctrl**+**G**): přesunout do zadané číslo řádku v aktivním dokumentu.

- **Přejděte na všechny** (**Ctrl**+**T** nebo **Ctrl**+**,**): přesunout do řádku zadaný typ soubor, člen nebo symbol.

- **Přejděte na soubor** (**Ctrl**+**1**, **Ctrl**+**F**): přesunout do zadaného souboru řešení.

- **Přejděte na typ** (**Ctrl**+**1**, **Ctrl**+**T**): přesunout do zadaného typu ve řešení.

- **Přejděte na člen** (**Ctrl**+**1**, **Ctrl**+**M**): přesunout do zadaného člena v řešení.

- **Přejděte na Symbol** (**Ctrl**+**1**, **Ctrl**+**S**): přesunout do zadaného symbol v řešení.

Viz informace o těchto příkazech v [najít kód pomocí příkazů přejít na](../ide/go-to.md) tématu.

## <a name="go-to-definition"></a>Přechod na definici

Přejít k definici přejdete k definici vybraného prvku. Další informace najdete v tématu [přejít k definici a prohlížení definice](../ide/go-to-and-peek-definition.md).

Vstup        | Funkce
------------ | ---
**Klávesnice** | Umístěte ukazatel myši na text někde uvnitř název typu a stiskněte klávesu **F12**
**Myš**    | Klikněte pravým tlačítkem na název typu a vyberte **přejít k definici** nebo stiskněte klávesu **Ctrl** a klikněte na název typu (nové pro Visual Studio 2017 verzi 15.4)

## <a name="peek-definition"></a>Funkce Náhled definice

Funkce Náhled definice zobrazí definici vybraného prvku v okně bez nutnosti opustit vaše aktuální umístění v editoru kódu. Další informace najdete v tématu [postupy: zobrazení a úpravy kódu s použitím funkce Náhled definice](../ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md) a [přejít k definici a prohlížení definice](../ide/go-to-and-peek-definition.md).

Vstup        | Funkce
------------ | ---
**Klávesnice** | Umístěte ukazatel myši na text někde uvnitř název typu a stiskněte klávesu **Alt**+**F12**
**Myš**    | Klikněte pravým tlačítkem na název typu a vyberte **funkce Náhled definice** nebo stiskněte klávesu **Ctrl** a klikněte na název typu (Pokud máte **otevřít v zobrazení funkce Náhled definice** možnost zaškrtnuto)

## <a name="go-to-implementation"></a>Přejít na implementaci

Přejít na implementaci můžete přejít ze základní třídy nebo typ, který má jeho implementace. Pokud existují více implementace, uvidíte je uvedené v **Najít výsledky Symbol** okno:

Vstup        | Funkce
------------ | ---
**Klávesnice** | Umístěte ukazatel myši na text někde uvnitř název typu a stiskněte klávesu **Ctrl**+**F12**
**Myš**    | Klikněte pravým tlačítkem na název typu a vyberte **přejděte k implementaci**

## <a name="call-hierarchy"></a>Hierarchie volání

Můžete zobrazit volání do a z metody v [okna hierarchie volání](../ide/reference/call-hierarchy.md):

Vstup        | Funkce
------------ | ---
**Klávesnice** | Umístěte ukazatel myši na text někde uvnitř název typu a stiskněte klávesu **Ctrl**+**tisíc**, **Ctrl**+**T**
**Myš**    | Klikněte pravým tlačítkem na název člena a vyberte **zobrazení hierarchie volání**

## <a name="next-method-and-previous-method-commands-visual-basic"></a>Další příkazy metoda a předchozí – metoda (Visual Basic)

V souborech kód jazyka Visual Basic použijte tyto příkazy ke přesuňte kurzor na různé metody. Zvolte **upravit** > **Next – metoda** nebo **upravit** > **předchozí metoda**.

## <a name="structure-visualizer"></a>Struktura Vizualizéru

Funkci struktura vizualizér v ukazuje editoru kódu *struktury Průvodce řádky* -vertical přerušovanou řádky, které označují odpovídající složené závorky v vaší základu kódu. Díky tomu je snazší zjistit, kde logické bloky begin a end.

![Struktura Vizualizéru](../ide/media/vside_structure_visualizer.png)

Chcete-li zakázat řádky struktury průvodce, přejděte na **nástroje** > **možnosti** > **textového editoru** > **Obecné** a zrušte zaškrtnutí **zobrazit čáry Průvodce struktura** pole.

## <a name="enhanced-scroll-bar"></a>Rozšířené posuvníku

Rozšířené posuvníku v okně kód vám pomůže získat reálný zobrazení kódu. V režimu mapy uvidíte náhledy kód při přesunutí ukazatele nahoru a dolů posuvníku. Další informace najdete v tématu [postupy: přizpůsobení posuvníku sledují kódu](../ide/how-to-track-your-code-by-customizing-the-scrollbar.md).

## <a name="codelens-information"></a>Informace o Codelensu

Můžete najít informace o konkrétní kód, jako jsou změny a kdo provedli tyto změny, odkazy, chyb, pracovní položky, kód recenze a jednotky stav testu, když používáte Codelensu v editoru kódu. Codelensu funguje jako z pohotového zobrazení, když použijete Visual Studio Enterprise s produktem Team Foundation Server. V tématu [nalezení změn kódu a další historie](../ide/find-code-changes-and-other-history-with-codelens.md).

## <a name="see-also"></a>Viz také

- [Funkce editoru kódu](../ide/writing-code-in-the-code-and-text-editor.md)
- [Zobrazení hierarchie volání](../ide/reference/call-hierarchy.md)
