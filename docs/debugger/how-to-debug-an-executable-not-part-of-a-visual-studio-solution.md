---
title: 'Postupy: ladění spustitelného souboru, který není součástí řešení sady Visual Studio | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], executables
- executable files, importing
- executable files, debugging outside of projects
ms.assetid: 3ea176e8-1ce5-42c4-b7a2-abe3a2765033
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2fe24d79fed27892a46b8534e0e39b2f60075c8b
ms.sourcegitcommit: 81e9d90843ead658bc73b30c869f25921d99e116
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2018
ms.locfileid: "52304425"
---
# <a name="how-to-debug-an-executable-that-is-not-part-of-a-visual-studio-solution-c-c-visual-basic-f"></a>Postupy: ladění spustitelného souboru, který není součástí řešení sady Visual Studio (C#, C++, Visual Basic, F#)

V některých případech můžete chtít ladit spustitelný soubor (soubor .exe), který není součástí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu. To může být spustitelný soubor vytvořený mimo sadu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nebo spustitelný soubor obdrželi od někoho jiného.  
  
Obvyklá odpověď na tento problém je spuštění spustitelného souboru mimo sadu Visual Studio a připojit se k němu pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ladicího programu. Další informace najdete v tématu [připojení k běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
Připojení k aplikaci vyžaduje určité ruční kroky, což trvá několik sekund. Toto mírné zpoždění znamená, že připojení nepomůže, pokud se pokoušíte ladit problém, ke které dojde během spouštění. Kromě toho Pokud ladíte program, který nečeká na vstup uživatele a rychle skončí, pravděpodobně nemáte čas připojit se k němu. Pokud máte [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] a [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] nainstalované, můžete vytvořit projekt EXE pro takový program.

> [!NOTE]
>  Ne všechny programovací jazyky podporují projekty EXE.

Jestliže ladíte spustitelný soubor, který není součástí řešení sady Visual Studio, je dostupné funkce ladění může být omezená, ať už jste připojení ke spuštěnému spustitelnému souboru nebo přidat spustitelného souboru k [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení.

- Pokud máte zdrojový kód, nejlepším řešením je import zdrojového kódu do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a vytvoření ladicího sestavení spustitelného souboru v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].
- Pokud nemáte zdrojového kódu, a pokud spustitelný soubor se sestavil bez [informace o ladění](../debugger/how-to-set-debug-and-release-configurations.md) v kompatibilním formátu, jsou k dispozici funkce ladění velmi omezená. 
  
### <a name="to-create-an-exe-project-for-an-existing-executable"></a>Chcete-li vytvořit projekt EXE pro stávající spustitelný soubor  
  
1.  Na **souboru** nabídky, klikněte na tlačítko **otevřít** a vyberte **projektu**.  
  
2.  V **otevřít projekt** dialogové okno, klikněte rozevírací seznam vedle **název_souboru** a vyberte **všechny soubory projektu**.  
  
3.  Vyhledejte spustitelný soubor a klikněte na tlačítko **OK**.  

    Tím se vytvoří dočasné řešení, která obsahuje spustitelný soubor.

5.  Spusťte spustitelný soubor výběrem příkazu ke spuštění, například **Start**, z **ladění** nabídky.    
  
### <a name="to-import-an-executable-into-a-visual-studio-solution"></a>Import spustitelného souboru do řešení sady Visual Studio  
  
1.  Na **souboru** nabídky, přejděte k **přidat projekt**a potom klikněte na tlačítko **existující projekt**.  
  
2.  V **přidat existující projekt** dialogové okno, klikněte rozevírací seznam vedle **název_souboru** a vyberte **všechny soubory projektu**.  
  
3.  Vyhledejte a vyberte spustitelný soubor.  
  
4.  Klikněte na tlačítko **OK**.  
  
5.  Spusťte spustitelný soubor výběrem příkazu ke spuštění, například **Start**, z **ladění** nabídky.    
  
## <a name="see-also"></a>Viz také  
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Soubory DBG](/previous-versions/visualstudio/visual-studio-2010/da528y14(v=vs.100))