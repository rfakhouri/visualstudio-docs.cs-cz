---
title: Dia2dump – ukázka | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- sample applications [DIA SDK]
- Dia2dump sample [DIA SDK]
ms.assetid: 492c0893-7043-452f-a020-890a47230d20
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: bd52c635d5ade1bef73176601d6957ba5859723b
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54791161"
---
# <a name="dia2dump-sample"></a>Dia2dump – ukázka
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

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
 [Postupy: Řešení potíží s upgrady projektu úspěšné sady Visual Studio](../../porting/how-to-troubleshoot-unsuccessful-visual-studio-project-upgrades.md)
