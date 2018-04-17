---
title: Povolení funkcí ladění v jazyce Visual C++ (-D_DEBUG) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: b0e652eaf28bb66bdd1ac87e14b1cb2e3fa96169
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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