---
title: Zobrazit zpětný překlad kódu v ladicím programu v sadě Visual Studio | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: 974a3a82ffdb9ed8041d5b7d067c4440d2524c23
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="view-disassembly-code-in-the-visual-studio-debugger"></a>Zobrazit zpětný překlad kódu v ladicím programu sady Visual Studio
Tato funkce je dostupná pouze v případě, že je povoleno ladění na úrovni adresu **možnosti** dialogové okno, **ladění** uzlu. Není k dispozici pro ladění skriptu nebo jazyka SQL.  
  
 **Zpětný překlad** v okně se zobrazí odpovídající pokyny vytvořené kompilátor kódu sestavení. Pokud jsou ladění spravovaného kódu, tyto pokyny sestavení odpovídají nativní kód vytvořené kompilátoru těsně za běhu (JIT), ne Microsoft (MSIL intermediate language) generované kompilátorem sady Visual Studio.  
  
 Kromě pokynů sestavení **zpětný překlad** v okně se zobrazí následující volitelné informace:  
  
-   Adresa paměti, kde se nachází každý instrukcí. U nativních aplikací jedná skutečná adresa paměti. Visual Basic, C# nebo spravovaného kódu je posun od začátku funkce.  
  
-   Zdrojový kód, ze kterého je odvozena kódu sestavení.  
  
-   Kód bajtů – reprezentace bajtů skutečné počítače nebo MSIL pokyny.  
  
-   Názvy symbolů pro adresy paměti.  
  
-   Čísla řádků odpovídající ke zdrojovému kódu.  
  
 Jazyk sestavení pokyny obsahovat klávesové zkratky, které jsou zkratky instrukce názvy a symboly, které představují proměnné, registry a konstanty. Každý počítač – language instrukce je reprezentována symbolické jeden jazyk sestavení, obvykle následuje jeden nebo více proměnných, registry nebo konstanty.  
  
 Pokud nelze číst jazyk sestavení a chcete využít všech výhod okno zpětný překlad, projděte si dobrý adresáře na programovací jazyk sestavení. Jazyk sestavení programování je nad rámec co budeme moci reagovat v Tento stručný úvod do okna zpětný překlad.  
  
 Vzhledem k tomu, že kódu sestavení spoléhá na procesor registry nebo v případě spravovaného kódu, zaregistruje modul common language runtime, vás bude často užitečné k použití okna zpětného překladu ve spojení s okna registry, který umožňuje zkontrolovat registrace obsah.  
  
 Pravděpodobně bude nikdy máte přání nebo třeba zobrazit zkompilovaný kód pokyny v jejich raw, číselné formuláře, nikoli jazyk sestavení. Ale pokud budete chtít udělat, můžete použití okna paměti k tomuto účelu nebo zvolte kód bajtů z místní nabídky v okně zpětný překlad.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-display-the-disassembly-window"></a>Chcete-li zobrazit okno zpětný překlad  
  
-   Při ladění, vyberte **ladění > Windows** a pak klikněte na **zpětný překlad**.
  
### <a name="to-turn-optional-information-on-or-off"></a>Chcete-li volitelné informace zapnutí nebo vypnutí  
  
-   Klikněte pravým tlačítkem myši **zpětný překlad** okně a nastavení nebo vymazání požadované možnosti v místní nabídce.  
  
     Žlutá šipka na levém okraji označuje umístění aktuální bod spuštění. Pro nativní kód odpovídá čítač procesoru pro program. Toto umístění ukazuje další instrukce, který bude spuštěn v programu.  
  
     Další informace najdete v tématu [o stránku nahoru nebo dolů v paměti](../debugger/how-to-page-up-or-down-in-memory.md).  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)   
 [Postupy: použití okna registry](../debugger/how-to-use-the-registers-window.md)