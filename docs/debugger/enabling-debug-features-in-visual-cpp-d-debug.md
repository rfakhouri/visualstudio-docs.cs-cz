---
title: "Povolení funkcí ladění v jazyce Visual C++ (-D_DEBUG) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug
dev_langs:
- CSharp
- VB
- FSharp
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
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0f1067ee5b60b8a8a402c9612357f2d83b6da138
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="enabling-debug-features-in-visual-c-ddebug"></a>Povolení funkcí ladění v jazyce Visual C++ (/D_DEBUG)
V [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)], ladění funkcí, jako je kontrolní výrazy jsou povolené, když zkompilujete váš program symbolem **_DEBUG –** definované. Můžete definovat **_DEBUG –** v jednom ze dvou způsobů:  
  
-   Zadejte **#define _DEBUG –** ve zdrojovém kódu, nebo  
  
-   Zadejte **/D_DEBUG** – možnost kompilátoru. (Pokud vytvoříte projekt v sadě Visual Studio pomocí průvodců, **/D_DEBUG** je automaticky definována v konfiguraci ladění.)  
  
 Když **_DEBUG –** je definován, kompilátor zkompiluje sekcí kódu obklopená **_DEBUG #ifdef –** a `#endif`.  
  
 Ladicí verze knihovny MFC musí propojení konfiguraci ladění MFC programu. Soubory hlaviček MFC určit správnou verzi knihovny MFC propojit s podle symboly jste definovali, jako například **_DEBUG –** a **_UNICODE**. Podrobnosti najdete v tématu [verze knihovny MFC](/cpp/mfc/mfc-library-versions).  
  
## <a name="see-also"></a>Viz také  
 [Ladění nativního kódu](../debugger/debugging-native-code.md)   
 [Nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)