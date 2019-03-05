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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 11a310884f9f63264157c96bafc15e8161c0239d
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/04/2019
ms.locfileid: "57323838"
---
# <a name="debugging-f"></a>Ladění F\#
Ladění F# je podobné ladění jakékoli spravovaného jazyka, s několika výjimkami:

-   **Automatické hodnoty** okno nezobrazí F# proměnné.

-   Upravit a pokračovat není podporována pro F#. Úpravy F# kódu během relace ladění je možné, ale mělo by se vyhnout. Protože během relace ladění se nepoužijí změny kódu, úpravy F# kódu během ladění způsobí neshodu mezi zdrojový kód a kód, který se právě ladí.

-   Ladicí program nemůže rozpoznat F# výrazy. Zadání výrazu v okně ladicího programu nebo dialogového okna průběhu F# ladění, musí přeložit výraz, který C# syntaxe. Při překladu F# výraz, který C#, ujistěte se, že si zapamatovat, že C# používá == jako operátor porovnání rovnosti a který F# používá jeden =.

## <a name="see-also"></a>Viz také
- [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)
