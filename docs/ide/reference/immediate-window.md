---
title: "Příkazové podokno | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
f1_keywords:
- VS.ImmediateWindow
helpviewer_keywords:
- design-time expression evaluation
- Immediate window
- first-chance exception notifications
ms.assetid: d33e7937-73f3-4c69-9df0-777a8713c6f2
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 026223f89822f2d76aa1185da8691c538b15ee62
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="immediate-window"></a>Příkazové podokno
**Immediate** okno slouží k ladění a vyhodnocení výrazů, spusťte příkazy, vytisknout hodnoty proměnných a tak dále. Umožňuje zadejte výrazy pro vyhodnocení nebo provedený jazyk vývoj během ladění. K zobrazení **Immediate** okno, otevřete projekt, a pak vyberte **Windows** z **ladění** nabídku a vyberte **Immediate**, nebo stiskněte kombinaci kláves CTRL + ALT + I.  
  
 Můžete toto okno na jednotlivé problém [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] příkazy. Zahrnout dostupné příkazy `EvaluateStatement`, které lze přiřadit hodnoty proměnné. **Immediate** okno také podporuje technologii IntelliSense.  
  
## <a name="displaying-the-values-of-variables"></a>Zobrazení hodnot proměnných  
 Toto okno může být užitečné při ladění aplikace. Chcete-li například zkontrolujte hodnotu proměnné `varA`, můžete použít [příkaz Tisk](../../ide/reference/print-command.md):  
  
```  
>Debug.Print varA  
```  
  
 Otazník (?) je alias `Debug.Print`, takže můžete zapsat také tento příkaz:  
  
```  
>? varA  
```  
  
 Obě verze tento příkaz vrátí hodnotu proměnné `varA`.  
  
> [!NOTE]
>  K problému [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] v **Immediate** okna, je nutné před příkaz s znaménko (>). Chcete-li zadat více příkazů, přepněte na **příkaz** okno.  
  
## <a name="design-time-expression-evaluation"></a>Vyhodnocení výrazu pro dobu návrhu  
 Můžete použít **Immediate** okno spuštění funkce nebo podprogramu v době návrhu.  
  
#### <a name="to-execute-a-function-at-design-time"></a>Chcete-li spustit funkci v době návrhu  
  
1.  Zkopírujte následující kód do [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] Konzolová aplikace:  
  
    ```vb
    Module Module1  
  
        Sub Main()  
            MyFunction(5)  
        End Sub  
  
        Function MyFunction(ByVal input as Integer) As Integer  
            Return input * 2  
        End Function  
  
    End Module  
    ```  
  
2.  Na **ladění** nabídky, klikněte na tlačítko **Windows**a potom klikněte na **Immediate**.  
  
3.  Typ `?MyFunction(2)` v **Immediate** okna a potom stiskněte klávesu Enter.  
  
     **Immediate** spustí okno `MyFunction` a zobrazit `4`.  
  
Pokud funkce nebo podprogramu obsahuje zarážku, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] by došlo k přerušení spuštění v odpovídajícím bodě. Ladicí program windows pak můžete zkontrolovat stav aplikací. Další informace najdete v části [návod: ladění v době návrhu](../../debugger/walkthrough-debugging-at-design-time.md).  
  
Vyhodnocení výrazu pro dobu návrhu nelze použít v typy projektů, které vyžadují spuštění prostředí pro spuštění, včetně [!INCLUDE[trprVSTOshort](../../ide/reference/includes/trprvstoshort_md.md)] projekty, webové projekty, projekty Smart Device Project a SQL projekty.  
  
### <a name="design-time-expression-evaluation-in-multi-project-solutions"></a>Vyhodnocení výrazu doby návrhu v řešení vícenásobného projektu  
 Při vytváření kontextu pro vyhodnocení výrazu pro dobu návrhu, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] odkazuje na aktuálně vybrané projekt v Průzkumníku řešení. Pokud nebyl vybraný žádný projekt v Průzkumníku řešení [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] pokusí zjistit hodnotu funkce proti spouštěný projekt. Pokud funkci nelze vyhodnotit v aktuálním kontextu, zobrazí se chybová zpráva. Pokud chcete vyhodnotit funkci v projektu, který není počáteční projekt pro řešení a zobrazí se chyba, zkuste vybrat projekt v Průzkumníku řešení a pokus opakujte vyhodnocení.  
  
## <a name="entering-commands"></a>Zadávání příkazů  
 Je nutné zadat větší než přihlásit (>) při vystavování [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] příkazů v **Immediate** okno. Pomocí klávesy šipka nahoru a dolů šipka možné procházet dřív vydaných příkazů.  
  
|Úloha|Řešení|Příklad|  
|----------|--------------|-------------|  
|Vyhodnocení výrazu.|Adresa výraz s otazníkem (?).|`? a+b`|  
|Dočasně zadejte režim příkazu v režimu okamžité (pro spuštění jednoduchého příkazu).|Zadejte příkaz zahájením ho literálu s větším než přihlašovací (>).|`>alias`|  
|Umožňuje přepnout do příkazové okno.|Zadejte `cmd` do okna, zahájením literálu ho s větším než přihlašovací (>).|`>cmd`|  
|Přepněte zpátky na hodnot proměnných.|Zadejte `immed` do okna bez znak větší než (>).|`immed`|  
  
## <a name="mark-mode"></a>Režim označení  
 Když kliknete na kterýkoli předchozí řádek v **Immediate** okně můžete posunutí automaticky do režimu značky. To umožňuje vybrat, upravovat a zkopírujte text z předchozích příkazů, jako by v každém textovém editoru a vložit do aktuálního řádku.  
  
## <a name="the-equals--sign"></a>Symbolem rovná se (=)  
 Okno používané k zadání `EvaluateStatement` příkaz určuje, zda znak rovná se (=) interpretována jako relační operátor nebo operátor přiřazení.  
  
 V **Immediate** okně znak rovná se (=) interpretována jako operátor přiřazení. Tak například příkaz  
  
```  
>Debug.EvaluateStatement(varA=varB)  
```  
  
 přiřadí do proměnné `varA` hodnotu proměnné `varB`.  
  
 V **příkaz** okně naopak znak rovná se (=) interpretována jako operátor porovnání. Operace přiřazení v nelze použít **příkaz** okno. Ano, například pokud hodnoty proměnných `varA` a `varB` jsou různé a potom příkaz  
  
```  
>Debug.EvaluateStatement(varA=varB)  
```  
  
 Vrátí hodnotu `False`.  
  
## <a name="first-chance-exception-notifications"></a>Oznámení o první odpovídající výjimce  
 V některých konfiguracích nastavení se zobrazí oznámení o první odpovídající výjimce v **Immediate** okno.  
  
#### <a name="to-toggle-first-chance-exception-notifications-in-the-immediate-window"></a>K přepnutí první odpovídající výjimce oznámení v příkazové podokno  
  
1.  Na **zobrazení** nabídky, klikněte na tlačítko **ostatní okna**a klikněte na tlačítko **výstup**.  
  
2.  Klikněte pravým tlačítkem na oblasti textového **výstup** okno a vyberte nebo zrušte výběr **zprávy o výjimkách**.  
  
## <a name="see-also"></a>Viz také  
 [Procházení kódu s ladicím programem](../../debugger/navigating-through-code-with-the-debugger.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Ladění v sadě Visual Studio](../../debugger/debugging-in-visual-studio.md)   
 [Základy ladicího programu](../../debugger/debugger-basics.md)   
 [Návod: Ladění v době návrhu](../../debugger/walkthrough-debugging-at-design-time.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)   
 [Používání regulárních výrazů v sadě Visual Studio](../../ide/using-regular-expressions-in-visual-studio.md)