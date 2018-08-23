---
title: Povolení funkcí ladění v jazyce Visual C++ (-D_DEBUG) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- /D_DEBUG compiler option [C++]
- debugging [C++], enabling debug features
- debugging [MFC], enabling debug features
- assertions, enabling debug features
- D_DEBUG compiler option
- MFC libraries, debug version
- debug builds, MFC
- _DEBUG macro
ms.assetid: 276e2254-7274-435e-ba4d-67fcef4f33bc
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 67de755105f30ee4a88daeef26bc29bc9841ae39
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666793"
---
# <a name="enabling-debug-features-in-visual-c-ddebug"></a>Povolení funkcí ladění v jazyce Visual C++ (/D_DEBUG)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [povolení funkcí ladění v jazyce Visual C++ (-D_DEBUG)](https://docs.microsoft.com/visualstudio/debugger/enabling-debug-features-in-visual-cpp-d-debug).  
  
V [!INCLUDE[vcprvc](../includes/vcprvc-md.md)], funkce ladění, jako je kontrolní výrazy jsou povolené při kompilaci programu symbol **_DEBUG** definované. Můžete definovat **_DEBUG** v jednom ze dvou způsobů:  
  
-   Zadejte **#define _DEBUG** ve zdrojovém kódu, nebo  
  
-   Zadejte **/D_DEBUG** – možnost kompilátoru. (Pokud vytváříte projekt v sadě Visual Studio pomocí průvodců **/D_DEBUG** je automaticky definovaný v konfiguraci ladění.)  
  
 Když **_DEBUG** je definován, kompilátor zkompiluje částech kód obklopený **#ifdef _DEBUG** a `#endif`.  
  
 Konfigurace ladění pro aplikace MFC je třeba propojit s ladicí verzí knihovny MFC. Soubory hlaviček knihovny MFC určit správnou verzi knihovny MFC pro propojení s založený na symboly, které jste definovali, jako například **_DEBUG** a **_UNICODE**. Podrobnosti najdete v tématu [MFC – knihovní verze](http://msdn.microsoft.com/library/3d7a8ae1-e276-4cf8-ba63-360c2f85ad0e).  
  
## <a name="see-also"></a>Viz také  
 [Ladění nativního kódu](../debugger/debugging-native-code.md)   
 [Nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)



