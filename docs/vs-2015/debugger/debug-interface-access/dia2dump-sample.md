---
title: Dia2dump – ukázka | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- sample applications [DIA SDK]
- Dia2dump sample [DIA SDK]
ms.assetid: 492c0893-7043-452f-a020-890a47230d20
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 410d4e8cf2a63c7d01058e501391f02543b1eee7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671457"
---
# <a name="dia2dump-sample"></a>Dia2dump – ukázka
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [dia2dump – ukázka](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/dia2dump-sample).  
  
Dia2dump – ukázka je součástí sady Visual Studio a obsahuje dia2dump.cpp – zdrojový soubor. Kompilovaný spustitelný soubor spustí z příkazového řádku a zobrazí obsah souboru databáze (PDB) celého programu.  
  
### <a name="to-install-the-sample"></a>Ukázku nainstalujete  
  
1.  Ověřte, že váš systém splňuje všechny požadavky na nastavení, které je popsáno na úvodní stránce instalační program sady Visual Studio.  
  
2.  Instalace sady Visual Studio a postupujte podle všech nastavení a instalace pokyny uvedené ukázky.  
  
#### <a name="to-build-the-sample"></a>K vytvoření vzorku  
  
1.  Otevřete soubor Dia2dump.sln v sadě Visual Studio. (V případě potřeby sady Visual Studio nejprve vám pomůže upgradovat projekt dia2dump –.)  
  
2.  Na stránkách vlastností projektu v **C/C++** &#124; **Obecné** &#124; **další adresáře souborů k zahrnutí** vlastnost, zadejte `..\DIA SDK\include` adresáře. Zaručí se tak, že kompilátor soubor dia2.h najdete.  
  
3.  Na **sestavení** nabídky, klikněte na tlačítko **znovu sestavit řešení**.  
  
4.  Zavřete Visual Studio.  
  
#### <a name="to-run-the-sample"></a>Chcete-li spustit ukázku  
  
1.  Otevřete příkazový řádek a zadejte následující příkaz:  
  
    ```  
    dia2dump filename  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Dia2dump.cpp – zdrojový soubor](../../debugger/debug-interface-access/dia2dump-cpp-source-file.md)   
 [Postupy: řešení potíží s upgrady projektu úspěšné sady Visual Studio](../../porting/how-to-troubleshoot-unsuccessful-visual-studio-project-upgrades.md)



