---
title: "Postupy: ladění spustitelné soubory, které není součástí řešení sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "23"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: be07be0e1374360a96b6672b095dcc039c6bb4f0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-debug-an-executable-that-is-not-part-of-a-visual-studio-solution"></a>Postupy: ladění spustitelné soubory, které není součástí řešení sady Visual Studio
V některých případech můžete chtít ladění spustitelné soubory (soubor .exe), které není součástí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu. To může být spustitelný soubor můžete vytvořit mimo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nebo jenom spustitelný soubor, který jste dostali od někoho jiného.  
  
Obvyklé odpověď na tento problém je spustit spustitelný soubor mimo Visual Studio a připojte se pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ladicí program. Další informace najdete v tématu [přiřadit běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
Připojení k aplikaci vyžaduje některé ruční kroky, takže bude trvat několik sekund. Tato mírnému zpoždění znamená, že připojení nebude pomoci, pokud chcete ladit problém, který nastane při spuštění. Navíc pokud ladíte program, který nečeká na vstup uživatele a rychle dokončí, nemusí mít čas k němu připojí. Pokud máte [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] a [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] nainstalován, můžete vytvořit projekt EXE pro takového programu.

> [!NOTE]
>  Ne všechny programovací jazyky podporují EXE projekty.

Při ladění spustitelné soubory, které není součástí řešení sady Visual Studio, může být k dispozici funkce ladění omezená, zda připojení spuštění spustitelného souboru nebo přidejte spustitelný soubor [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení.

- Pokud máte ve zdrojovém kódu, je nejlepším postupem je importovat do zdrojového kódu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a vytvořit sestavení ladicí verze spustitelného souboru v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].
- Pokud nemáte zdrojový kód, a pokud spustitelný soubor byl vytvořený bez [informace o ladění](../debugger/how-to-set-debug-and-release-configurations.md) kompatibilní formát, jsou k dispozici funkce ladění velmi omezená. 
  
### <a name="to-create-an-exe-project-for-an-existing-executable"></a>K vytvoření projektu pro existující spustitelný soubor EXE  
  
1.  Na **soubor** nabídky, klikněte na tlačítko **otevřete** a vyberte **projektu**.  
  
2.  V **otevřeného projektu** dialogové okno, klikněte na tlačítko rozevíracího seznamu vedle **název souboru** a vyberte **všechny soubory projektu**.  
  
3.  Vyhledejte spustitelný soubor a klikněte na tlačítko **OK**.  

    Tím se vytvoří dočasný řešení, které obsahuje spustitelný soubor.

5.  Spustit spustitelný soubor výběrem příkaz provádění **spustit**, z **ladění** nabídky.    
  
### <a name="to-import-an-executable-into-a-visual-studio-solution"></a>K importu spustitelný soubor do řešení sady Visual Studio  
  
1.  Na **soubor** nabídky, přejděte na příkaz **přidat projekt**a potom klikněte na **existující projekt**.  
  
2.  V **přidat existující projekt** dialogové okno, klikněte na tlačítko rozevíracího seznamu vedle **název souboru** a vyberte **všechny soubory projektu**.  
  
3.  Vyhledejte a vyberte spustitelný soubor.  
  
4.  Click **OK**.  
  
5.  Spustit spustitelný soubor výběrem příkaz provádění **spustit**, z **ladění** nabídky.    
  
## <a name="see-also"></a>Viz také  
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Soubory DBG](http://msdn.microsoft.com/en-us/91e449e9-8b65-4123-960f-2107cd1f1cfd)