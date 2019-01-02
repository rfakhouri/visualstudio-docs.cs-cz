---
title: Ladění F# | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Debugging [F#]
- F#, debugging
ms.assetid: 20bcd51c-2d06-4281-9a1e-ef2b91d1a779
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0f526eb39a62de33910bfa5e3e1e72220be3ae3c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53903978"
---
# <a name="debugging-f"></a>Ladění F#
Ladění F# je podobné ladění jakékoli spravovaného jazyka, s několika výjimkami:  
  
-   **Automatické hodnoty** okno nezobrazí F# proměnné.  
  
-   Upravit a pokračovat není podporována pro F#. Úpravy F# kódu během relace ladění je možné, ale mělo by se vyhnout. Protože během relace ladění se nepoužijí změny kódu, úpravy F# kódu během ladění způsobí neshodu mezi zdrojový kód a kód, který se právě ladí.  
  
-   Ladicí program nemůže rozpoznat F# výrazy. Zadání výrazu v okně ladicího programu nebo dialogového okna průběhu F# ladění, musí přeložit výraz, který C# syntaxe. Při překladu F# výraz, který C#, ujistěte se, že si zapamatovat, že C# používá == jako operátor porovnání rovnosti a který F# používá jeden =.  
  
## <a name="see-also"></a>Viz také  
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)
