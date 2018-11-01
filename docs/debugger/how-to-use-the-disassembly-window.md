---
title: Zobrazit zpětný překlad kódu v ladicím programu v sadě Visual Studio | Dokumentace Microsoftu
ms.custom: H1Hack27Feb2017
ms.date: 10/30/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.disassembly
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- assembly language, debugging inline assembly code
- breakpoints, Disassembly window
- Disassembly window
- machine code
ms.assetid: eaf84dd0-c82d-481b-af51-690b74e7794c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 51510d09a1840035bb96817d30aebdcd6bf3ebd7
ms.sourcegitcommit: be938c7ecd756a11c9de3e6019a490d0e52b4190
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2018
ms.locfileid: "50671141"
---
# <a name="view-disassembly-code-in-the-visual-studio-debugger"></a>Zobrazit zpětný překlad kódu v ladicím programu sady Visual Studio

**Zpětný překlad** okno zobrazuje kódu sestavení odpovídajícího pokynů vytvořeným kompilátorem. Pokud ladíte spravovaný kód, tyto pokyny k sestavení odpovídají na nativní kód vytvořený kompilátorem Just-in-Time (JIT), ne Microsoft intermediate language (MSIL) vytvořený kompilátorem Visual Studio.  
  
> [!NOTE]
> Chcete-li využívají všech výhod **zpětný překlad** okně pochopit nebo osvojte si Základy [programovací jazyk sestavení](https://wikipedia.org/wiki/Assembly_language).
  
Tato funkce dostupná pouze pokud je povoleno ladění na úrovni adres. Není k dispozici pro skript nebo ladění SQL. 

Kromě pokyny sestavení **zpětný překlad** okna můžete zobrazit následující volitelné informace:  
  
- Adresa paměti, kde se nachází každou instrukci. U nativních aplikací je skutečná adresa paměti. V jazyce Visual Basic C#, nebo spravovaný kód, je posun od začátku této funkce.  
  
- Zdrojový kód, ze kterého je odvozen kódu sestavení.  
  
- Kód bajtů, to znamená, byte reprezentace skutečný nebo instrukce jazyka MSIL.  
  
- Názvy symbolů pro adresy paměti.  
  
- Čísla řádků zdrojového kódu.  
  
Instrukcí sestavení jazyka jsou tvořeny *klávesových zkratek*, které jsou zkratky pro instrukcí názvy a *symboly* proměnné, registry a konstanty. Každou instrukci strojového jazyka je reprezentován jeden symbol jazyka sestavení může volitelně následovat jednoho nebo více symbolů.  
  
Kód sestavení spoléhá na registrech procesoru, nebo pro spravovaný kód registruje modul common language runtime. Můžete použít **zpětný překlad** okno spolu s **zaregistruje** okno, které umožňuje zkoumat obsah registru.  
  
Chcete-li zobrazit pokyny strojového kódu v jejich původním formátu číselné, nikoli jako jazyk sestavení, použijte **paměti** okno nebo vyberte **kód bajtů** z místní nabídky v **zpětný překlad**  okna.  
  
## <a name="use-the-disassembly-window"></a>Použití okna zpětného překladu

Povolit **zpětný překlad** okně v části **nástroje** > **možnosti** (nebo **nástroje**  >  **Možnosti**) > **ladění**vyberte **povolit ladění na úrovni adres**.

Chcete-li otevřít **zpětný překlad** okno během ladění, vyberte **Windows** > **zpětný překlad** nebo stiskněte klávesu **Alt** + **8**.

> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](../ide/personalizing-the-visual-studio-ide.md).  
  
Pro volitelné informace zapnout nebo vypnout, klikněte pravým tlačítkem **zpětný překlad** okna a nastavení nebo vymazat požadované možnosti v místní nabídce.  

Žlutá šipka na levém okraji označí aktuální bod provádění. Pro nativní kód odpovídá bod provádění programu čítače CPU. Toto umístění se zobrazí další instrukci, která se spustí ve svém programu.  

## <a name="see-also"></a>Viz také:  

* [O stránku nahoru nebo dolů v paměti](../debugger/how-to-page-up-or-down-in-memory.md)
* [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)
* [Postupy: použití okna registry](../debugger/how-to-use-the-registers-window.md)
