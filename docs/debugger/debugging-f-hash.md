---
title: "Ladění F # | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Debugging [F#]
- F#, debugging
ms.assetid: 20bcd51c-2d06-4281-9a1e-ef2b91d1a779
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 51eaed204db7b50e75a18dfac104a00546770abc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="debugging-f"></a>Ladění F#
Ladění F # je podobná ladění žádný spravovaný jazyk s několika výjimkami:  
  
-   **Automobily** okno nezobrazí F # proměnné.  
  
-   Upravit a pokračovat není podporována pro F #. Úpravy během relace ladění F # – kód je možné, ale je nutno. Vzhledem k tomu, že během ladicí relace se nepoužijí změny kódu, úpravy F # kódu během ladění způsobí neshodu mezi zdrojový kód a kód laděné.  
  
-   Ladicí program nemůže rozpoznat F # výrazy. Zadání výrazu, v okně ladicí program nebo dialogové okno během ladění F #, musí překládat výraz do jazyka C# – syntaxe. Pokud jste přeložit výraz F # do jazyka C#, nezapomeňte mějte na paměti, že C# používá == jako jeden = používá relační operátor rovnosti a že F #.  
  
## <a name="see-also"></a>Viz také  
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)
