---
title: "Navigace v kódu | Microsoft Docs"
ms.custom: 
ms.date: 09/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
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
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7b81517d8d8e0cc6dd1386525f7a2129ed18851c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="navigating-code"></a>Navigace v kódu  
Visual Studio poskytuje mnoho způsobů přejděte v editoru kódu. Toto téma shrnuje různé způsoby, můžete přejít kódu a poskytuje odkazy na témata, které patří do více podrobností.  

## <a name="navigate-backward-and-navigate-forward-commands"></a>Přejděte zpět a přejděte dál příkazy  
Můžete použít **přejděte zpětné** (**Ctrl + -**) a **přejděte dál** (**kombinaci kláves Ctrl + Shift + -**) tlačítek na panelu nástrojů přesunout bod vložení do předchozího umístění, nebo pro návrat do novější umístění z předchozího umístění. Tato tlačítka zachovat poslední 20 umístění kurzoru. Tyto příkazy jsou také k dispozici na **zobrazení** nabídce v části **přejděte zpětné** a **přejděte dál**.  

![Navigační tlačítka vpřed a zpět](../ide/media/vs2017_nav_buttons.png)  

## <a name="navigation-bar"></a>Navigační panel
Můžete použít **navigační panel** (rozevíracího seznamu polí v horní části okna kódu) přejděte na kód základu kódu. Můžete přejít přímo na na typ nebo člen. Na navigačním panelu se zobrazí, když upravíte kód v jazyka Visual Basic, c nebo C++ – kód základní. Částečné třídy, mohou být zakázány členy definované mimo aktuální soubor kódu (se zobrazí šedě).  

 ![Navigační panel kódu](../ide/media/vside_navigation_bar.png)

Můžete přejít okolo rozevírací seznamy následujícím způsobem:  

-   Přejděte do jiného projektu, který je součástí aktuální soubor, vyberte v levé rozevíracího seznamu.

-   Přejděte na třídy nebo typu, vyberte ho uprostřed rozevíracího seznamu.  

-   Přejít přímo na procedury nebo jiného člena třídy, vyberte ho v pravém rozevíracího seznamu.  

-   Pokud chcete Přesun zaměření z okna kódu na navigačním panelu, stiskněte kombinaci kláves **Ctrl + F2**.  

-   Chcete-li přesun zaměření pole z pole na navigačním panelu, stiskněte **kartě** klíč.  

-   Chcete-li vybrat položku navigační panel se fokus a vraťte se do okna kód, stiskněte **Enter** klíč.  

-   Vrátit fokus z navigačního panelu kód bez provedení výběru, stiskněte **Esc** klíč.  

Skrytí navigačního panelu, změnit **navigační panel** možnost v nastavení textový Editor, všechny jazyky (**nástroje**, **možnosti**, **textového editoru**, **Všechny jazyky**), nebo můžete změnit nastavení pro jednotlivé jazyky.  

## <a name="find-all-references"></a>Najít všechny odkazy  
Vyhledá všechny odkazy na vybraný prvek v řešení. To můžete použít ke kontrole možné vedlejší účinky z velké refaktoring nebo ověření "neaktivní" kódu. Stiskněte klávesu **F8** přejít mezi výsledky. Další informace najdete v tématu [hledání odkazy ve vašem kódu](finding-references.md).  

Vstup        | Funkce 
------------ | ---
**Klávesnice** | Umístěte ukazatel myši na text někde uvnitř název typu a stiskněte klávesu **Shift + F12**  
**Myš**    | Vyberte **najít všechny odkazy** z místní nabídky  

## <a name="reference-highlighting"></a>Zvýrazňování odkazu
Po kliknutí na tlačítko symbol ve zdrojovém kódu, jsou všechny instance tohoto symbolu zvýrazněných v dokumentu. Zvýrazněná symboly může zahrnovat deklarace a odkazy a mnoho dalších symboly, který **najít všechny odkazy** by vrátit. Patří mezi ně názvy tříd, objekty, proměnné, metod a vlastností. V kódu Visual Basic jsou také vyznačené klíčová slova pro mnoho řídicí struktury. Chcete-li přejít na další nebo předchozí zvýrazněný symbol, stiskněte **kombinaci kláves Ctrl + Shift + šipka dolů** nebo **kombinaci kláves Ctrl + Shift + šipka nahoru**. Můžete změnit barvu zvýraznění v **nástroje**, **možnosti**, **prostředí**, **písma a barev**, **Highlighted Odkaz.**  

## <a name="go-to-commands"></a>Přejít na příkazy  
Přejít na má následující příkazy, které jsou k dispozici v **upravit** nabídky v části **přejít na**:  

- **Přejít na řádek** (**kombinaci kláves Ctrl + G**): přesunout do zadané číslo řádku v aktivním dokumentu.  

- **Přejděte na všechny** (**kombinaci kláves Ctrl + T** nebo **Ctrl +,**): přesunout do zadaného řádku, typ, soubor, člen nebo symbol.  

- **Přejděte na soubor** (**Ctrl + 1**, **kombinaci kláves Ctrl + F**): přesunout do zadaného souboru v řešení.  

- **Přejděte na typ** (**Ctrl + 1**, **kombinaci kláves Ctrl + T**): přesunout do zadaného typu v řešení.  

- **Přejděte na člen** (**Ctrl + 1**, **kombinaci kláves Ctrl + M**): přesunout do zadaného člena v řešení.  

- **Přejděte na Symbol** (**Ctrl + 1**, **kombinaci kláves Ctrl + S**): přesunout na zadaný symbol v řešení.  

Viz informace o těchto příkazech v [najít kód pomocí příkazů přejít na](../ide/go-to.md) tématu.  

## <a name="go-to-definition"></a>Přechod na definici  
Přejít k definici přejdete k definici vybraného prvku. Další informace najdete v tématu [funkce Náhled definice a přejděte do definice](../ide/go-to-and-peek-definition.md).  

Vstup        | Funkce 
------------ | ---
**Klávesnice** | Umístěte ukazatel myši na text někde uvnitř název typu a stiskněte klávesu **F12**
**Myš**    | Klikněte pravým tlačítkem na název typu a vyberte **přejít k definici** nebo stiskněte klávesu **Ctrl** a klikněte na název typu (nové pro Visual Studio 2017 verzi 15.4)  

## <a name="peek-definition"></a>Funkce Náhled definice  
Funkce Náhled definice zobrazí definici vybraného prvku v okně bez nutnosti opustit vaše aktuální umístění v editoru kódu. Další informace najdete v tématu [postupy: zobrazení a úpravy kódu podle pomocí funkce Náhled definice](../ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md) a [funkce Náhled definice a přejděte do definice](../ide/go-to-and-peek-definition.md).  

Vstup        | Funkce 
------------ | ---
**Klávesnice** | Umístěte ukazatel myši na text někde uvnitř název typu a stiskněte klávesu **Alt + F12**
**Myš**    | Klikněte pravým tlačítkem na název typu a vyberte **funkce Náhled definice** nebo stiskněte klávesu **Ctrl** a klikněte na název typu (Pokud máte **otevřít v zobrazení funkce Náhled definice** možnost zaškrtnuto)  

## <a name="go-to-implementation"></a>Přejít na implementaci  
Přejít na implementaci můžete přejít ze základní třídy nebo typ, který má jeho implementace. Pokud existují více implementace, uvidíte je uvedené v **Najít výsledky Symbol** okno:  

Vstup        | Funkce 
------------ | ---
**Klávesnice** | Umístěte ukazatel myši na text někde uvnitř název typu a stiskněte klávesu **kombinaci kláves Ctrl + F12**
**Myš**    | Klikněte pravým tlačítkem na název typu a vyberte **přejděte k implementaci**  

## <a name="call-hierarchy"></a>Hierarchie volání  
Hierarchie volání ukazuje volání metody v okně hierarchie volání:  

Vstup        | Funkce 
------------ | ---
**Klávesnice** | Umístěte ukazatel myši na text někde uvnitř název typu a stiskněte klávesu **Ctrl + K**, **kombinaci kláves Ctrl + T**  
**Myš**    | Klikněte pravým tlačítkem na název člena a vyberte **zobrazení hierarchie volání**  

## <a name="next-method-and-previous-method-commands-visual-basic"></a>Další příkazy metoda a předchozí – metoda (Visual Basic)  
V souborech kód jazyka Visual Basic použijte tyto příkazy ke přesuňte kurzor na různé metody. Zvolte **upravit**, **Next – metoda** nebo **upravit**, **předchozí metoda**.  

## <a name="structure-visualizer"></a>Struktura Vizualizéru  
Funkci struktura vizualizér v ukazuje editoru kódu *struktury Průvodce řádky* -vertical přerušovanou řádky, které označují odpovídající složené závorky v vaší základu kódu. Díky tomu je snazší zjistit, kde logické bloky begin a end.  

![Struktura Vizualizéru](../ide/media/vside_structure_visualizer.png)  

Pokud chcete zakázat řádky struktury průvodce, přejděte na **nástroje**, **možnosti**, **textového editoru**, **Obecné** a zrušte zaškrtnutí **zobrazit struktury Průvodce řádky** pole.  

## <a name="enhanced-scroll-bar"></a>Rozšířené posuvníku
Rozšířené posuvníku v okně kód vám pomůže získat reálný zobrazení kódu. V režimu mapy uvidíte náhledy kód při přesunutí ukazatele nahoru a dolů posuvníku. Další informace najdete v tématu [postupy: sledování si kód přizpůsobením posuvníku](../ide/how-to-track-your-code-by-customizing-the-scrollbar.md).  

## <a name="codelens-information"></a>Informace o Codelensu
Můžete najít informace o konkrétní kód, jako jsou změny a kdo provedli tyto změny, odkazy, chyb, pracovní položky, kód recenze a jednotky stav testu, když používáte Codelensu v editoru kódu. Codelensu funguje jako z pohotového zobrazení, když použijete Visual Studio Enterprise s produktem Team Foundation Server. V tématu [nalezení změn kódu a další historie](../ide/find-code-changes-and-other-history-with-codelens.md).  

## <a name="see-also"></a>Viz také  
[Psaní kódu v editoru kódu a text.](../ide/writing-code-in-the-code-and-text-editor.md) 
