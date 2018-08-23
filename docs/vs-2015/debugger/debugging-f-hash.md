---
title: 'Ladění F # | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
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
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a5790b81eedb1a1bb9dc65b7ce053089c3bc1470
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633128"
---
# <a name="debugging-f"></a>Ladění F# #
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [ladění F #](https://docs.microsoft.com/visualstudio/debugger/debugging-f-hash).  
  
Ladění F # je podobné ladění jakékoli spravovaného jazyka, s několika výjimkami:  
  
-   **Automatické hodnoty** okno nezobrazí F # proměnné.  
  
-   Upravit a pokračovat není podporována pro F #. Úpravy kódu jazyka F # během relace ladění je možné, ale mělo by se vyhnout. Protože během relace ladění se nepoužijí změny kódu, úpravy kódu jazyka F # při ladění způsobí neshodu mezi zdrojový kód a kód, který se právě ladí.  
  
-   Ladicí program nemůže rozpoznat výrazy jazyka F #. Zadání výrazu v okně ladicího programu nebo dialogové okno během ladění F #, musí přeložit výraz, který syntaxe jazyka C#. Pokud je překlad výrazu F # do jazyka C#, ujistěte se, že mějte na paměti, že jazyk C# používá == – operátor porovnání rovnosti a že F # používá jeden =.  
  
## <a name="see-also"></a>Viz také  
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)



