---
title: Ladění F# | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Debugging [F#]
- F#, debugging
ms.assetid: 20bcd51c-2d06-4281-9a1e-ef2b91d1a779
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 51a8e43268718421a90d051f0d4d9b6afa96980e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68156685"
---
# <a name="debugging-f"></a>Ladění F\#

[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ladění F# je podobné ladění jakékoli spravovaného jazyka, s několika výjimkami:

- **Automatické hodnoty** okno nezobrazí F# proměnné.

- Upravit a pokračovat není podporována pro F#. Úpravy F# kódu během relace ladění je možné, ale mělo by se vyhnout. Protože během relace ladění se nepoužijí změny kódu, úpravy F# kódu během ladění způsobí neshodu mezi zdrojový kód a kód, který se právě ladí.

- Ladicí program nemůže rozpoznat F# výrazy. Zadání výrazu v okně ladicího programu nebo dialogového okna průběhu F# ladění, musí přeložit výraz, který C# syntaxe. Při překladu F# výraz, který C#, ujistěte se, že si zapamatovat, že C# používá == jako operátor porovnání rovnosti a který F# používá jeden =.

## <a name="see-also"></a>Viz také

- [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)
