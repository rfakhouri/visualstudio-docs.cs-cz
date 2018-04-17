---
title: Upravit a pokračovat – dialogové okno chyby zpráva | Microsoft Docs
ms.custom: ''
ms.date: 06/22/2017
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.ENC.SupportedButNotAvaiable
- vs.debug.ENC.CannotEditWhileException
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue Error Message dialog box
ms.assetid: f98c91c0-447a-4533-85b6-87170a0dc4c3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 148fea0484bbcdfe16339ccc1b5e876506a76838
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="edit-and-continue-error-message-dialog-box"></a>Dialogové okno chybových zpráv operace Upravit a pokračovat
Toto dialogové okno se zobrazí, když jsou ladění v jazyce, který podporuje upravit a pokračovat, ale **upravit a pokračovat** není k dispozici pro typ provedené změny kódu. Chybová zpráva uvnitř pole poskytuje podrobnější vysvětlení. Možné důvody pro zobrazení tohoto dialogového okna patří:  

-   Pokusili jste se upravit kód systému SQL Server.

-   Pokusili jste se upravit optimalizovaný kód. (Můžete přepnout do sestavení ladicí verze ze sestavení pro vydání.)

-   Jste chtěli upravovat kód byl spuštěn (místo při pozastavena v ladicím programu). Zkuste [nastavení boru přerušení](../debugger/using-breakpoints.md) a úpravy kódu při pozastavena.

-   Pokusili jste se upravit spravovaného kódu, pokud bylo povoleno nespravované ladění. Upravit a pokračovat nefunguje s [ladění ve smíšeném režimu](../debugger/how-to-debug-in-mixed-mode.md).

-   Kód změnit provedené, není podporována upravit a pokračovat v programovacím jazyce. Další informace najdete v tématech nepodporovaný kód změny v [C#](../debugger/supported-code-changes-csharp.md), [jazyka Visual Basic](../debugger/unsupported-edits-in-visual-basic-edit-and-continue.md), a [C++](../debugger/supported-code-changes-cpp.md).
  
-   Pokusili jste se upravit kód v programu, který jste připojili k nespouštět z **ladění** nabídky.  
  
-   Pokusili jste se upravit kód při ladění zotavení po havárii. Watson výpis.  
  
-   Pokusili jste se upravit kód po došlo k neošetřené výjimce a možnost "**Unwind zásobníku volání na neošetřených výjimek**" nebyla vybrána.  
  
-   Pokusili jste se upravit kód při ladění aplikace embedded runtime.
  
-   Pokusili jste se upravit spravovaného kódu pomocí rozhraní .NET Framework verze před 4.5.1 a cíl je 64bitová verze aplikace. Pokud chcete použít upravit a pokračovat, musíte nastavit cíl x86. (*projectname* **vlastnosti**, **zkompilovat** kartě **Advanced kompilátoru** nastavení.).  
  
-   Pokusili jste se upravit kód v sestavení, které byla změněna během ladění a znovu načtena.  
  
-   Pokusili jste se upravit kód v sestavení, které nebyla načtena.  
  
-   Můžete spustit ladění starší verzi aplikace (protože je nová verze obsahuje chyby sestavení).
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **OK**  
 Ukončit dialogové okno a zrušit okamžitě předchozí pokus upravit.  
  
## <a name="see-also"></a>Viz také  
 [C++ upravit a pokračovat blog post](https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/)  
 [Podporované změny kódu (C++)](../debugger/supported-code-changes-cpp.md)