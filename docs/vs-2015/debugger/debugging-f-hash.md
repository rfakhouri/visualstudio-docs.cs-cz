---
title: 'Ladění F # | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
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
ms.openlocfilehash: dd722e40a0579181e3c361706f0775aaf350c341
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49209570"
---
# <a name="debugging-f"></a>Ladění F# #
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ladění F # je podobné ladění jakékoli spravovaného jazyka, s několika výjimkami:  
  
-   **Automatické hodnoty** okno nezobrazí F # proměnné.  
  
-   Upravit a pokračovat není podporována pro F #. Úpravy kódu jazyka F # během relace ladění je možné, ale mělo by se vyhnout. Protože během relace ladění se nepoužijí změny kódu, úpravy kódu jazyka F # při ladění způsobí neshodu mezi zdrojový kód a kód, který se právě ladí.  
  
-   Ladicí program nemůže rozpoznat výrazy jazyka F #. Zadání výrazu v okně ladicího programu nebo dialogové okno během ladění F #, musí přeložit výraz, který syntaxe jazyka C#. Pokud je překlad výrazu F # do jazyka C#, ujistěte se, že mějte na paměti, že jazyk C# používá == – operátor porovnání rovnosti a že F # používá jeden =.  
  
## <a name="see-also"></a>Viz také  
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)



