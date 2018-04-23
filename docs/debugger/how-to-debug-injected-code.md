---
title: 'Postupy: ladění vloženého kódu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.injected
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- assembly language, viewing
- debugging [C++], viewing assembly code
- debugging [C++], injected code
- debugging [C++], enabling source annotation
- injected code
- Show Source Code command [debugger]
- debugging [C++], using attributes
- disassembly code, debugging
ms.assetid: a1b4104d-d49e-451f-a91e-e39ceaf35875
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bf602d8ee670e5fce8602cb50d2aaa1066b501de
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-debug-injected-code"></a>Postupy: Ladění vloženého kódu
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, vyberte v nabídce Nástroje pro nastavení importu a exportu. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
 Pomocí atributů může výrazně zjednodušit C++ programování. Další informace najdete v tématu [koncepty](/cpp/windows/attributed-programming-concepts). Některé atributy se interpretují přímo kompilátorem. Ostatní atributy vložení kódu do programu zdroj, který pak zkompiluje kompilátoru. Tento kód vložený umožňuje snadnější programování snížením kód, který máte k zápisu. V některých případech ale chyby může způsobit selhání při je prováděna vloženého kódu aplikace. V takovém případě budete pravděpodobně chtít podívat vloženého kódu. Visual Studio poskytuje dva způsoby, jak je zobrazen vloženého kódu:  
  
-   Vložený kód v můžete zobrazit **zpětný překlad** okno.  
  
-   Pomocí [/Fx](/cpp/build/reference/fx-merge-injected-code), můžete vytvořit sloučené zdrojový soubor, který obsahuje původní a vloženého kódu.  
  
 **Zpětný překlad** v okně se zobrazí jazyka sestavení pokyny, které odpovídají zdrojový kód a kód vloženy atributy. Kromě toho **zpětný překlad** okně se zobrazí, ke které je poznámka zdrojového kódu.  
  
### <a name="to-turn-on-source-annotation"></a>Chcete-li na zdrojové poznámky  
  
-   Klikněte pravým tlačítkem myši **zpětný překlad** okně a zvolte **zobrazit zdrojový kód** z místní nabídky.  
  
     Pokud znáte umístění atribut v okně zdroj, můžete použít místní nabídky k vyhledání kód vložený na **zpětný překlad** okno.  
  
### <a name="to-view-injected-code"></a>Chcete-li zobrazit vloženého kódu  
  
1.  Ladicí program musí být v režimu přerušení.  
  
2.  V okně zdrojového kódu umístěte kurzor před atribut jejichž vloženého kódu, které chcete zobrazit.  
  
3.  Klikněte pravým tlačítkem a vyberte **přejděte k zpětný překlad** z místní nabídky.  
  
     Pokud je atribut umístění téměř aktuální bod spuštění, můžete vybrat **zpětný překlad** okna z **ladění** nabídky.  
  
### <a name="to-view-the-disassembly-code-at-the-current-execution-point"></a>Chcete-li zobrazit zpětný překlad kódu k aktuálnímu bodu provádění  
  
1.  Ladicí program musí být v režimu přerušení.  
  
2.  Z **ladění** nabídce zvolte **Windows**a klikněte na tlačítko **zpětný překlad**.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)