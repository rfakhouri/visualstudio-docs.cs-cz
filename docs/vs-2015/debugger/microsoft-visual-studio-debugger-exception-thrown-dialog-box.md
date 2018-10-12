---
title: Microsoft Visual Studio Debugger (vyvolána výjimka) dialogové okno | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.exceptions.thrown
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Microsoft Visual Studio Debugger (Exception Thrown) dialog box
- exception handling, during debugging
- debugger, exceptions
- throwing exceptions, during debugging
ms.assetid: 1fe98d10-c8f9-4b39-a920-99169bfd542e
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c3ce3a3362c657d4302ba919c866d4a32055423
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49226160"
---
# <a name="microsoft-visual-studio-debugger-exception-thrown-dialog-box"></a>Dialogové okno programu Microsoft Visual Studio Debugger (vyvolána výjimka)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ve vašem programu došlo k výjimce. Toto dialogové okno sestavy druh vyvolané výjimky. Váš kód je potřeba zpracovat tuto výjimku. Můžete si vybrat následující možnosti pro zpracování výjimek:  
  
 **Konec**  
 Umožňuje provádění přerušení ladicího programu. Před koncem není vyvolána obslužná rutina výjimky. Pokud budete pokračovat z přerušení, bude vyvolána obslužná rutina výjimky.  
  
 **Continue**  
 Umožňuje provádění pokračovat, poskytuje obslužné rutiny výjimky umožňující zpracování výjimky. Tato možnost není k dispozici pro některé typy výjimek. **Pokračovat** vám umožní aplikaci pokračovat. V nativní aplikaci způsobí výjimku, která znovu vyvolala. Ve spravované aplikaci způsobí buď program ukončit nebo výjimka, která má být zpracována hostitelské aplikace.  
  
> [!NOTE]
>  Nejde pokračovat po neošetřené výjimce ve spravovaném kódu. Výběr **pokračovat** po neošetřené výjimce ve spravovaném kódu způsobí, že chcete-li zastavit ladění.  
  
 **Ignorovat**  
 Umožňuje provádění pokračovat bez volání obslužné rutiny výjimky. Protože není vyvolána obslužná rutina výjimky, to může vést k dalším důsledky, včetně dalších výjimek a chyb. Tato možnost není k dispozici pro některé typy výjimek.  
  
## <a name="see-also"></a>Viz také  
 [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md)   
 [Doporučené postupy pro výjimky](http://msdn.microsoft.com/library/f06da765-235b-427a-bfb6-47cd219af539)   
 [Zpracování výjimek](http://msdn.microsoft.com/library/ccb11fe8-6938-41ac-b477-a183e85865b9)



