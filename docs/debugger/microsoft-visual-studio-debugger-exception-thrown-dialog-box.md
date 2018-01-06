---
title: "Sadu Microsoft Visual Studio ladicího programu dialogové okno (vyvolána výjimka) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.exceptions.thrown
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Microsoft Visual Studio Debugger (Exception Thrown) dialog box
- exception handling, during debugging
- debugger, exceptions
- throwing exceptions, during debugging
ms.assetid: 1fe98d10-c8f9-4b39-a920-99169bfd542e
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1020711c21fb7171a8f7f8b87296d300f53b78b1
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/04/2018
---
# <a name="microsoft-visual-studio-debugger-exception-thrown-dialog-box"></a>Dialogové okno programu Microsoft Visual Studio Debugger (vyvolána výjimka)
V programu došlo k výjimce. Toto dialogové okno sestavy druh došlo k výjimce. Váš kód je potřeba zpracovat výjimku. Můžete zvolit z následujících možností pro zpracování výjimky:  
  
 **Rozdělit**  
 Umožňuje na přerušení ladicího provedení. Obslužná rutina výjimky není volána před rozdělení. Pokud budete pokračovat z rozdělení, bude volána obslužná rutina výjimky.  
  
 **Pokračovat**  
 Umožňuje spuštění, chcete-li pokračovat, udělíte obslužná rutina výjimky umožňující ošetření výjimky. Tato možnost není k dispozici pro určité typy výjimek. **Pokračovat** vám umožní aplikaci pokračovat. V nativní aplikaci může to způsobit výjimka, která má být znovu vyvolány. Ve spravované aplikaci způsobí buď program ukončit nebo výjimky zpracovávat hostitelskou aplikaci.  
  
> [!NOTE]
>  Nelze pokračovat, po k neošetřené výjimce ve spravovaném kódu. Výběr **pokračovat** po k neošetřené výjimce v spravovaného kódu způsobí, že ladění zastavit.  
  
 **Ignorovat**  
 Umožňuje spuštění a pokračujte bez vyvolání obslužná rutina výjimky. Protože není volána obslužná rutina výjimky, to může vést k další důsledky, včetně další výjimek a chyb. Tato možnost není k dispozici pro určité typy výjimek.  
  
## <a name="see-also"></a>Viz také  
 [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md)   
 [Doporučené postupy pro výjimky](/dotnet/standard/exceptions/best-practices-for-exceptions)   
 [Zpracování výjimek](/cpp/windows/exception-handling-cpp-component-extensions)