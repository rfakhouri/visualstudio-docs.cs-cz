---
title: "Výstup – okno | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.build.output
- vs.debug.output
- vs.output
helpviewer_keywords:
- Output window, about Output window
- Output window
- Toolbox, removing controls
ms.assetid: d8931d88-250e-4db4-963f-2c5b3e99b45f
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1e886e88ad7ab4e943908e003ffe56719bd13211
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="output-window"></a>Okno Výstup
**Výstup** okno můžete zobrazit stavové zprávy pro různé funkce v integrované vývojové prostředí (IDE). Chcete-li otevřít **výstup** okně na řádku nabídek zvolte **zobrazení výstupní** (nebo klikněte na tlačítko CTRL + ALT + O).  
  
> [!WARNING]
>  Ve výstupním okně se nezobrazí v nabídce zobrazení v edicích sady Visual Studio Express. Chcete-li ji zprovoznit, použijte klávesová zkratka CTRL + ALT + e.  
  
## <a name="toolbar"></a>Panel nástrojů  
 **Zobrazit výstup z**  
 Zobrazí jeden nebo více podokna výstup zobrazíte. Několika podoken informací může být k dispozici, v závislosti na tom, které nástroje v prostředí IDE použili **výstup** okna pro doručování zpráv pro uživatele.  
  
 **Vyhledat zprávu v kódu**  
 Přesune kurzor v editoru kódu na řádek, který obsahuje chyby vybrané sestavení.  
  
 **Přejít na předchozí zpráva**  
 Změní fokus v **výstup** časové období pro předchozí chyby sestavení a Posune kurzor na řádek, který obsahuje sestavení Chyba v editoru kódu.  
  
 **Přejděte na další zprávu**  
 Změní fokus v **výstup** okno na další chyby sestavení a Posune kurzor na řádek, který obsahuje sestavení Chyba v editoru kódu.  
  
 **Vymazat vše**  
 Vymaže celý text z **výstup** podokně.  
  
 **Přepnout zalamování řádků**  
 Vypíná a zapíná funkci zalamování **výstup** podokně. Pokud je na zalamování, je text v delší položky, která překračuje oblasti zobrazení zobrazí na následující řádek.  
  
## <a name="output-pane"></a>V podokně výstupu  
 **Výstup** vybrané v podokně **zobrazit výstup z** seznamu zobrazí výstup ze zdroje uvedené.  
  
## <a name="routing-messages-to-the-output-window"></a>Směrování zpráv do okna výstupu  
 K zobrazení **výstup** vždy, když vytváříte projekt, v okně **Obecné, projekty a řešení, možnosti** dialogové okno, vyberte **okno zobrazit výstup při spuštění sestavení**. Zvolte souborem kódu otevřete pro úpravy, **přejít na další zprávu** a **přejít na předchozí zpráva** tlačítka na **výstup** nástrojů v okně vyberte položek v  **Výstup** podokně. Když to uděláte, kurzoru v přeskočí editoru kódu na řádek kódu, kde dojde k vybraný problém.  
  
 Některé funkce IDE a příkazy v vyvolat [příkazové okno](../../ide/reference/command-window.md) poskytovat jejich výstup do **výstup** okno. Výstup z externích nástrojů, jako jsou soubory .bat a .com, které se obvykle zobrazí v okně příkazového řádku, se směruje na **výstup** podokně při výběru **použití výstup – okno** možnost [Správa externích nástrojů](../../ide/managing-external-tools.md). Mnoho dalších druhy zprávy lze zobrazit v **výstup** také podokna. Například když syntaxe Transact-SQL v uložené proceduře bude zkontrolován, cílová databáze, výsledky se zobrazí v **výstup** okno.  
  
 Můžete také programu vaše vlastní aplikace k zápisu diagnostické zprávy v době běhu **výstup** podokně. K tomu použít členy <xref:System.Diagnostics.Debug> třídy nebo <xref:System.Diagnostics.Trace> třídy v <xref:System.Diagnostics> obor názvů knihovně tříd rozhraní .NET Framework. Členové <xref:System.Diagnostics.Debug> – třída zobrazit výstup při sestavování ladění konfigurace vašeho řešení nebo produktu project; členy <xref:System.Diagnostics.Trace> třída zobrazit výstup při vytváření ladění nebo verze konfigurace. Další informace najdete v tématu [diagnostické zprávy v okně výstupu](../../debugger/diagnostic-messages-in-the-output-window.md).  
  
 V [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)], můžete vytvořit vlastní kroky sestavení a události sestavení, jejichž upozornění a chyby se zobrazují a kteří se započítávají do **výstup** podokně. Stisknutím klávesy F1 na řádek výstupu, můžete zobrazit příslušné téma nápovědy. Další informace najdete v tématu [Formátovaní výstupu vlastního kroku sestavení nebo události sestavení](/cpp/ide/formatting-the-output-of-a-custom-build-step-or-build-event).  
  
## <a name="scrolling-behavior"></a>Chování posouvání  
 Pokud používáte automatické procházení v okně výstupu a pak přejděte pomocí myši nebo šipku klíčů, zastaví automatické procházení. Chcete-li pokračovat v automatické procházení, stiskněte CTRL + END.  
  
## <a name="see-also"></a>Viz také  
 [Diagnostické zprávy v okně výstupu.](../../debugger/diagnostic-messages-in-the-output-window.md)   
 [Postupy: řízení ve výstupním okně](http://msdn.microsoft.com/Library/91aebd15-8854-4a7a-9f7d-57376fb4e858)   
 [Kompilaci a sestavování](../../ide/compiling-and-building-in-visual-studio.md)   
 [Principy konfigurací sestavení](../../ide/understanding-build-configurations.md)   
 [Přehled knihovny tříd](/dotnet/standard/class-library-overview)