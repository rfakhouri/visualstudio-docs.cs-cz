---
title: "Dia2dump – ukázka | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- sample applications [DIA SDK]
- Dia2dump sample [DIA SDK]
ms.assetid: 492c0893-7043-452f-a020-890a47230d20
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: bd21806dee94031c6d5486daf1696e1f97e2956f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="dia2dump-sample"></a>Dia2dump – ukázka
Dia2dump – ukázka je nainstalován pomocí sady Visual Studio a obsahuje dia2dump.cpp – zdrojový soubor. Kompilované spustitelný soubor spouští z příkazového řádku a zobrazí obsah souboru databáze (.pdb) celého programu.  
  
### <a name="to-install-the-sample"></a>Ukázku nainstalujete  
  
1.  Ověřte, že váš systém splňuje všechny požadavky instalace, které jsou popsané na úvodní stránce instalace aplikace Visual Studio.  
  
2.  Instalaci sady Visual Studio a postupujte podle všechny instalace a pokyny k instalaci pro uvedené ukázky.  
  
#### <a name="to-build-the-sample"></a>Chcete-li sestavit ukázku  
  
1.  Otevřete soubor Dia2dump.sln v sadě Visual Studio. (V případě potřeby Visual Studio nejprve vám pomůže upgradu na projekt dia2dump –.)  
  
2.  Na stránkách vlastností projektu v **C/C++** &#124; **Obecné** &#124; **Další adresáře Include** vlastnost, zadejte `..\DIA SDK\include` adresáře. To zaručuje, že kompilátor můžete najít soubor dia2.h.  
  
3.  Na **sestavení** nabídky, klikněte na tlačítko **znovu sestavit řešení**.  
  
4.  Zavřete Visual Studio.  
  
#### <a name="to-run-the-sample"></a>Chcete-li spustit ukázku  
  
1.  Otevřete příkazový řádek a zadejte následující příkaz:  
  
    ```  
    dia2dump filename  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Dia2dump.cpp – zdrojový soubor](../../debugger/debug-interface-access/dia2dump-cpp-source-file.md)   
 [Port, migrace a Upgrade projektů sady Visual Studio](../../porting/port-migrate-and-upgrade-visual-studio-projects.md)