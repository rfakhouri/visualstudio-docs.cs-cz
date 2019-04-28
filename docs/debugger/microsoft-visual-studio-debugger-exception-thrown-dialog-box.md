---
title: Microsoft Visual Studio Debugger (vyvolána výjimka) dialogové okno | Dokumentace Microsoftu
titleSuffix: ''
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.exceptions.thrown
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a684002360f59d33e61c40261afc1bfd515511e3
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63408525"
---
# <a name="microsoft-visual-studio-debugger-exception-thrown-dialog-box"></a>Dialogové okno programu Microsoft Visual Studio Debugger (vyvolána výjimka)
Ve vašem programu došlo k výjimce. Toto dialogové okno sestavy druh vyvolané výjimky. Váš kód je potřeba zpracovat tuto výjimku. Můžete si vybrat následující možnosti pro zpracování výjimek:

 **Konec** umožňuje provádění přerušení ladicího programu. Před koncem není vyvolána obslužná rutina výjimky. Pokud budete pokračovat z přerušení, bude vyvolána obslužná rutina výjimky.

 **Pokračovat** umožňuje provádění pokračovat, poskytuje obslužné rutiny výjimky umožňující zpracování výjimky. Tato možnost není k dispozici pro některé typy výjimek. **Pokračovat** vám umožní aplikaci pokračovat. V nativní aplikaci způsobí výjimku, která znovu vyvolala. Ve spravované aplikaci způsobí buď program ukončit nebo výjimka, která má být zpracována hostitelské aplikace.

> [!NOTE]
> Nejde pokračovat po neošetřené výjimce ve spravovaném kódu. Výběr **pokračovat** po neošetřené výjimce ve spravovaném kódu způsobí, že chcete-li zastavit ladění.

 **Ignorovat** umožňuje provádění pokračovat bez volání obslužné rutiny výjimky. Protože není vyvolána obslužná rutina výjimky, to může vést k dalším důsledky, včetně dalších výjimek a chyb. Tato možnost není k dispozici pro některé typy výjimek.

## <a name="see-also"></a>Viz také
- [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md)
- [Doporučené postupy pro výjimky](/dotnet/standard/exceptions/best-practices-for-exceptions)
- [Zpracování výjimek](/cpp/windows/exception-handling-cpp-component-extensions)