---
title: Mapování metod v zásobníku volání při ladění v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-modeling
ms.topic: conceptual
f1_keywords:
- vs.progression.debugwithcodemaps
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- call stacks, code maps
- Call Stack window, mapping calls
- debugging [Visual Studio], diagramming the call stack
- call stacks, mapping
- Call Stack window, visualizing
- debugging code visually
- debugging [Visual Studio], mapping the call stack
- call stacks, visualizing
- debugging, code maps
- Call Stack window, tracing calls visually
- Call Stack window, show on code map
- debugging [Visual Studio], tracing the call stack visually
- debugging [Visual Studio], visualizing the call stack
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9ad5108a801b02125c3627933d1891372f3369a2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="map-methods-on-the-call-stack-while-debugging-in-visual-studio"></a>Mapování metod v zásobníku volání při ladění v sadě Visual Studio
Vytvoření mapy kódu pro vizuální trasování zásobníku volání při ladění. Můžete si dělat poznámky na mapě ke sledování kódu činnosti tak, abyste se mohli zaměřit na hledání chyb.  

 ![Ladění pomocí zásobníky volání na map kódu](../debugger/media/debuggermap_overview.png "DebuggerMap_Overview")  

 Budete potřebovat:  

-   [Visual Studio Enterprise](https://www.visualstudio.com/downloads/download-visual-studio-vs)  

-   Kód, který můžete ladit, jako je například Visual C#, Visual Basic, C++, JavaScript nebo X ++  

 Další informace:  

-   [Video: Ladění vizuálně s integrací ladicí program Mapa kódu (Channel 9)](http://go.microsoft.com/fwlink/?LinkId=293418)

-   [Mapování zásobníku volání](#MapStack)

-   [Zkontrolujte poznámky o kód](#MakeNotes)

-   [Aktualizace mapa s další zásobníku volání](#UpdateMap)

-   [Přidání souvisejících kódu do mapy](#AddRelatedCode)

-   [Najít chyby pomocí mapy](#FindBugs)

-   [MODUL OTÁZKY A ODPOVĚDI](#QA)  

 Podrobnosti příkazů a akcích, které můžete použít při práci s map kódu najdete v tématu [Procházet a uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md).  

##  <a name="MapStack"></a> Mapování zásobníku volání  

1.  Spusťte ladění. (Klávesové: **F5**)  

2.  Když aplikace přejde do režimu pozastavení nebo krok do funkce, vyberte **Mapa kódu**. (Klávesové: **Ctrl** + **Shift** + **`**)  

     ![Zvolte Mapa kódu zahájíte mapování zásobníku volání](../debugger/media/debuggermap_choosecodemap.png "DebuggerMap_ChooseCodeMap")  

     Aktuální aktuální zásobník volání se zobrazí oranžově na mapě nového kódu:  

     ![Najdete v zásobníku volání na mapě kódu](../debugger/media/debuggermap_seeundocallstack.png "DebuggerMap_SeeUndoCallStack")  

     Mapy se aktualizuje automaticky, když budete pokračovat, ladění. V tématu [aktualizovat mapy další zásobníkem volání](#UpdateMap).  

##  <a name="MakeNotes"></a> Zkontrolujte poznámky o kód  
 Přidejte komentář ke sledování, co se děje v kódu. Chcete-li přidat nový řádek v komentář, stiskněte **Shift + vrátit**.  

 ![Přidejte komentář k zásobník volání na mapě kódu](../debugger/media/debuggermap_addcomment.png "DebuggerMap_AddComment")  

##  <a name="UpdateMap"></a> Aktualizace mapa s další zásobníku volání  
 Spuštění vaší aplikace na další zarážku nebo krok do funkce. Mapování přidá nový zásobník volání.  

 ![Mapa kódu aktualizace další zásobníkem volání](../debugger/media/debuggermap_addclearcallstack.png "DebuggerMap_AddClearCallStack")  

##  <a name="AddRelatedCode"></a> Přidání souvisejících kódu do mapy  
 Nyní máte k dispozici mapu - co dále? Pokud pracujete s C# nebo Visual Basic, přidejte položky, jako je například pole, vlastnosti a jiných metod pro sledování, co se děje v kódu.  

 Dvakrát klikněte na metodu zobrazíte jeho definice kód, nebo pomocí místní nabídky pro metodu. (Klávesové: Vyberte metodu na mapu a stiskněte klávesu **F12**)  

 ![Přejděte do definice kód pro metodu na mapě kódu](../debugger/media/debuggermap_gotocodedefinition.png "DebuggerMap_GoToCodeDefinition")  

 Přidejte položky, které chcete sledovat na mapě.  

 ![Zobrazit pole v metodě na mapě kódu zásobník volání](../debugger/media/debuggermap_showfields.png "DebuggerMap_ShowFields")  

> [!NOTE]
>  Ve výchozím nastavení přidávání položek do mapy také přidá nadřazených uzlů skupiny například třída, obor názvů a sestavení. To je užitečné, abyste zajistili, že mapy jednoduché můžete vypnout pomocí této funkce **zahrnují nadřazené položky** tlačítka na panelu nástrojů mapy nebo stisknutím klávesy **CTRL** při přidávání položek.  

 ![Pole související s metodu na mapě kódu zásobník volání](../debugger/media/debuggermap_showedfields.png "DebuggerMap_ShowedFields")  

 Zde můžete snadno zobrazit metody, které používají stejná pole. Poslední přidané položky se zobrazí zeleně.  

 Pokračujte v sestavování mapy, pokud chcete zobrazit další kód.  

 ![Najdete v části metody, které používají pole: Mapa kódu zásobník volání](../debugger/media/debuggermap_findallreferences.png "DebuggerMap_FindAllReferences")  

 ![Metody, které používají pole na mapě kódu zásobník volání](../debugger/media/debuggermap_foundallreferences.png "DebuggerMap_FoundAllReferences")  

##  <a name="FindBugs"></a> Najít chyby pomocí mapy  
 Vizualizace kódu můžete nalézt chyby rychleji. Předpokládejme například, že jste příčin chyb v aplikaci pro kreslení. Když nakreslíte čáru a pokusíte se vrátit akci zpět, nic se nestane, dokud nenakreslíte další čáru.  

 Nastavte zarážky v `clear`, `undo`, a `Repaint` metody, spusťte ladění a sestavení mapy podobné následujícímu:  

 ![Přidejte jiný zásobník volání na mapě kódu](../debugger/media/debuggermap_addpaintobjectcallstack.png "DebuggerMap_AddPaintObjectCallStack")  

 Všimněte si, že všechny uživatelské gesta na volání map `Repaint`, s výjimkou `undo`. To mohou vysvětlit, proč `undo` nefunguje okamžitě.  

 Po oprava chyby a pokračovat spuštění programu, mapy přidá nové volání z `undo` k `Repaint`:  

 ![Přidat nové zásobník volání k volání metody na mapě kódu](../debugger/media/debuggermap_addnewcallforrepaint.png "DebuggerMap_AddNewCallForRepaint")  

##  <a name="QA"></a> Q & A  

-   **Ne všechny hovory se zobrazí na mapě. Proč?**  

     Ve výchozím nastavení zobrazí se pouze vlastní kód na mapě. Externí kódu najdete ji v zapnout **zásobníkem volání** okno:  

     ![Zobrazení externí kódu pomocí okno zásobník volání](../debugger/media/debuggermap_callstackmenu.png "DebuggerMap_CallStackMenu")  

     nebo vypněte **povolit volbu pouze vlastní kód** v sadě Visual Studio možnosti ladění:  

     ![Zobrazit externí kódu pomocí dialogovém okně Možnosti](../debugger/media/debuggermap_debugoptions.png "DebuggerMap_DebugOptions")  

-   **Změna mapy kód vliv?**  

     Změna mapy neovlivní kód žádným způsobem. Nebojte se přejmenovat, přesunout nebo odebrat cokoli na mapě.  

-   **Co tato zpráva znamená: "diagramu může být založeno na starší verzi kód"?**  

     Po poslední aktualizaci mapy mohl být kód změněn. Například volání do mapy nemusí již v kódu existovat. Zavřete zprávu a potom zkuste znovu sestavit řešení před opětovnou aktualizací mapy.  

-   **Jak řídit mapy rozložení?**  

     Otevřete **rozložení** nabídky na panelu nástrojů mapy:  

    -   Změňte výchozí rozložení.  

    -   Chcete-li zastavit, změna uspořádání mapy automaticky, vypněte **automaticky rozložení při ladění**.  

    -   Chcete-li po přidání položek, změna uspořádání map co nejméně, vypněte **přírůstkové rozložení**.  

-   **Můžete s ostatními uživateli sdílet mapy?**  

     Můžete exportovat mapu, odeslat ji ostatním uživatelům, pokud máte aplikaci Microsoft Outlook, nebo ji uložit do vašeho řešení, abyste ji mohli vrátit se změnami do řízení verzí Team Foundation.  

     ![Sdílené složky volání zásobníku Mapa kódu s ostatními](../debugger/media/debuggermap_sharewithothers.png "DebuggerMap_ShareWithOthers")  

-   **Jak zabráním mapy v přidávání nových zásobníky volání automaticky?**  

     Zvolte ![tlačítko &#45; zásobníku volání zobrazit na mapě kódu automaticky](../debugger/media/debuggermap_automaticupdateicon.gif "DebuggerMap_AutomaticUpdateIcon") na panelu nástrojů mapy. Ručně přidat aktuální zásobníku volání do mapy, stiskněte klávesu **Ctrl** + **Shift** + **`**.  

     Mapy bude pokračovat, zvýraznění existující zásobníky volání na mapě při ladění.  

-   **Co ikony položky a dvojice šipek, které znamenají?**  

     Chcete-li získat další informace o položce, přesuňte ukazatel myši nad ním a podívejte se na popisku položky. Můžete také zobrazit **legendy** se dozvíte, co znamená každá ikona.  

     ![Co znamenají ikony na mapě kódu zásobník volání ] (../debugger/media/debuggermap_showlegend.png "DebuggerMap_ShowLegend")  

 Další informace:  

-   [Mapování zásobníku volání](#MapStack)

-   [Zkontrolujte poznámky o kód](#MakeNotes)

-   [Aktualizace mapa s další zásobníku volání](#UpdateMap)

-   [Přidání souvisejících kódu do mapy](#AddRelatedCode)

-   [Najít chyby pomocí mapy](#FindBugs)  

## <a name="see-also"></a>Viz také  
 [Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md)   
 [Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)   
 [Nalezení potenciálních problémů pomocí analyzátorů mapy kódu](../modeling/find-potential-problems-using-code-map-analyzers.md)   
 [Procházení a změna uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md)
