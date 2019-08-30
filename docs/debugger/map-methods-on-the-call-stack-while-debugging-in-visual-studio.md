---
title: Vytvoření vizuální mapy zásobníku volání | Microsoft Docs
ms.date: 11/26/2018
ms.topic: conceptual
f1_keywords:
- vs.progression.debugwithcodemaps
dev_langs:
- CSharp
- VB
- FSharp
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
ms.assetid: d6a72e5e-f88d-46fc-94a3-1789d34805ef
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 62fb77590a20b0e31648cab10f310851fd65820e
ms.sourcegitcommit: 44e9b1d9230fcbbd081ee81be9d4be8a485d8502
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2019
ms.locfileid: "70179992"
---
# <a name="create-a-visual-map-of-the-call-stack-while-debugging-c-visual-basic-c-javascript"></a>Vytvoření vizuální mapy zásobníku volání při ladění (C#, Visual Basic, C++, JavaScript)

Vytvořte mapu kódu pro vizuální sledování zásobníku volání během ladění. Můžete si dělat poznámky na mapě, abyste mohli sledovat, co kód dělá, abyste se mohli soustředit na hledání chyb.

Postup najdete v tomto videu: [Video: Vizuální ladění díky integraci ladicího programu mapy kódu (kanál 9)](http://go.microsoft.com/fwlink/?LinkId=293418)

Podrobnosti o příkazech a akcích, které můžete použít s mapami kódu, najdete v tématu [procházení a změna uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md).

>[!IMPORTANT]
>Mapy kódu můžete vytvořit pouze v [edici Visual Studio Enterprise](https://visualstudio.microsoft.com/downloads).

Tady je rychlý pohled na mapu kódu:

 ![Ladění se zásobníky volání na mapách kódu](../debugger/media/debuggermap_overview.png "DebuggerMap_Overview")

## <a name="MapStack"></a> Mapování zásobníku volání

1. V projektu Visual Studio Enterprise C#, Visual Basic, C++nebo JavaScriptu spusťte ladění výběrem **ladění** > **Spustit ladění** nebo stisknutím klávesy **F5**.

1. Jakmile vaše aplikace přejde do režimu přerušení nebo přejdete do funkce, vyberte**Mapa kódu** **ladění** > nebo stiskněte klávesy **CTRL**+**SHIFT**+. **`**

   Aktuální aktuální zásobník volání se zobrazí oranžově na mapě nového kódu:

   ![Zobrazit zásobník volání na mapě kódu](../debugger/media/debuggermap_seeundocallstack.png "DebuggerMap_SeeUndoCallStack")

Mapa kódu se aktualizuje automaticky při pokračování ladění. Změna položek mapy nebo rozložení neovlivní kód jakýmkoli způsobem. Nebojte se přejmenovat, přesunout nebo odebrat cokoli na mapě.

Chcete-li získat další informace o položce, najeďte myší na ni a podívejte se na popis položky. Můžete také vybrat možnost **Legenda** na panelu nástrojů a zjistit, co všechny ikony znamenají.

![Legenda mapy kódu](../debugger/media/debuggermap_showlegend.png "Legenda mapy kódu")

>[!NOTE]
>Zpráva, **kterou diagram může být založena na starší verzi kódu** v horní části mapy kódu, znamená, že kód může být změněn po poslední aktualizaci mapy. Například volání do mapy nemusí již v kódu existovat. Zavřete zprávu a potom zkuste znovu sestavit řešení před opětovnou aktualizací mapy.

## <a name="map-external-code"></a>Mapování externího kódu

Ve výchozím nastavení zobrazí se pouze vlastní kód na mapě. Chcete-li zobrazit externí kód na mapě:

- V okně **zásobník volání** klikněte pravým tlačítkem myši a vyberte **Zobrazit externí kód**:

  ![Zobrazit externí kód pomocí okna zásobník volání](../debugger/media/debuggermap_callstackmenu.png "DebuggerMap_CallStackMenu")
- Nebo zrušte zaškrtnutí **políčka Povolit pouze můj kód** v **nástroji** sady Visual Studio (nebo **ladění**) >**ladění** **možností** > :

  ![Zobrazit externí kód pomocí dialogového okna Možnosti](../debugger/media/debuggermap_debugoptions.png "DebuggerMap_DebugOptions")

## <a name="control-the-maps-layout"></a>Řízení rozložení mapy

Změna rozložení mapy neovlivní kód jakýmkoli způsobem.

Chcete-li ovládat rozložení mapy, vyberte nabídku **rozložení** na panelu nástrojů mapa.

V nabídce **rozložení** můžete:

- Změňte výchozí rozložení.
- Zastavit přeuspořádání mapy automaticky tak, že zrušíte výběr **automatického rozložení při ladění**.
- Přeuspořádání mapy co nejmenší, když přidáváte položky, tak, že zrušíte výběr **přírůstkového rozložení**.

## <a name="MakeNotes"></a> Tvorba poznámek o kódu

Můžete přidat komentáře pro sledování, co se děje v kódu.

Komentář přidáte tak, že kliknete pravým tlačítkem na mapu kódu a vyberete **Upravit** > **Nový komentář**a pak zadáte komentář.

Chcete-li přidat nový řádek v komentáři, stiskněte klávesu **SHIFT**+**ENTER**.

 ![Přidat komentář do zásobníku volání na mapě kódu](../debugger/media/debuggermap_addcomment.png "DebuggerMap_AddComment")

## <a name="UpdateMap"></a> Aktualizace mapy s následujícím zásobníkem volání.

Při spuštění aplikace na další zarážku nebo krok do funkce bude mapa automaticky přidávat nové zásobníky volání.

![Aktualizace mapy kódu s následujícím zásobníkem volání](../debugger/media/debuggermap_addclearcallstack.png "DebuggerMap_AddClearCallStack")

Chcete-li zastavit mapování pro automatické přidávání nových zásobníků volání, vyberte možnost ![Zobrazit zásobník volání na mapě kódu automaticky](../debugger/media/debuggermap_automaticupdateicon.gif "Zobrazit zásobník volání na mapě kódu") na panelu nástrojů mapa kódu. Mapa stále zvýrazní existující zásobníky volání. Chcete-li ručně přidat aktuální zásobník volání k mapě, stiskněte **Ctrl**+**Shift**+ **`** .

## <a name="AddRelatedCode"></a> Přidání souvisejícího kódu do mapy

Teď, když máte mapu, C# nebo Visual Basic, můžete přidat položky, jako jsou pole, vlastnosti a jiné metody, abyste mohli sledovat, co se děje v kódu.

Chcete-li přejít na definici metody v kódu, poklikejte na metodu v mapě, nebo ji vyberte a stiskněte klávesu **F12**, nebo klikněte na ni pravým tlačítkem myši a vyberte **Přejít k definici**.

![Přejít na definici kódu pro metodu na mapě kódu](../debugger/media/debuggermap_gotocodedefinition.png "DebuggerMap_GoToCodeDefinition")

Chcete-li přidat položky, které chcete sledovat na mapě, klikněte pravým tlačítkem myši na metodu a vyberte položky, které chcete sledovat. Poslední přidané položky se zobrazí zeleně.

![Pole související s metodu na mapě kódu zásobníku volání](../debugger/media/debuggermap_showedfields.png "DebuggerMap_ShowedFields")

>[!NOTE]
>Ve výchozím nastavení přidávání položek do mapy také přidá nadřazené uzly skupiny, například třídy, oboru názvů a sestavení. Tuto funkci můžete vypnout a zapnout tak, že vyberete tlačítko **Zahrnout nadřazené prvky** na panelu nástrojů mapa kódu nebo když při přidávání položek stisknete **klávesu CTRL** .

![Zobrazit pole v metodu na mapě kódu zásobníku volání](../debugger/media/debuggermap_showfields.png "DebuggerMap_ShowFields")

Pokračujte v sestavování mapy, pokud chcete zobrazit další kód.

 ![Zobrazit metody, které používají pole: mapy kódu zásobníku volání](../debugger/media/debuggermap_findallreferences.png "DebuggerMap_FindAllReferences")

 ![Metody, které používají pole na mapě kódu zásobníku volání](../debugger/media/debuggermap_foundallreferences.png "DebuggerMap_FoundAllReferences")

## <a name="FindBugs"></a> Najít chyby pomocí mapy
 Vizualizace kódu můžete nalézt chyby rychleji. Předpokládejme například, že zkoumáte chybu v aplikaci pro kreslení. Když nakreslíte čáru a pokusíte se vrátit akci zpět, nic se nestane, dokud nenakreslíte další čáru.

 Proto nastavte zarážky v `clear`, `undo`, a `Repaint` metody, spustit ladění a vytvořit mapu podobné následujícímu:

 ![Přidat jiný zásobník volání k mapě kódu](../debugger/media/debuggermap_addpaintobjectcallstack.png "DebuggerMap_AddPaintObjectCallStack")

 Všimněte si, že všechna gesta uživatelů na mapě volají `Repaint`, s výjimkou `undo`. To může vysvětlit, proč `undo` nefunguje okamžitě.

 Po opravě chyby a pokračování ve spouštění aplikace mapa přidá nové volání z `undo` do: `Repaint`

 ![Přidat nový zásobník volání k volání metody na mapě kódu](../debugger/media/debuggermap_addnewcallforrepaint.png "DebuggerMap_AddNewCallForRepaint")

## <a name="share-the-map-with-others"></a>Sdílet mapu s ostatními

Můžete exportovat mapu, odeslat ji ostatním uživatelům v aplikaci Microsoft Outlook, uložit je do vašeho řešení a vrátit se do správy verzí.

Pokud chcete mapu sdílet nebo uložit, použijte **share** na panelu nástrojů mapa kódu.

![Sdílení mapy kódu zásobníku volání s ostatními](../debugger/media/debuggermap_sharewithothers.png "Sdílení mapy kódu zásobníku volání s ostatními")

## <a name="see-also"></a>Viz také:
[Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md)

[Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)

[Nalezení potenciálních problémů pomocí analyzátorů mapy kódu](../modeling/find-potential-problems-using-code-map-analyzers.md)

[Procházení a změna uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md)
