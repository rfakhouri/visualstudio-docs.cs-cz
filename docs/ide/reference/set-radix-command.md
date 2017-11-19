---
title: "Nastavit základ – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.setradix
helpviewer_keywords:
- Set Radix command
- Debug.SetRadix command
ms.assetid: 6ffd1554-7530-4da4-b5f5-e276a5034f3b
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 060221e5abe0ff9082a04f8b75561a7e4dec9f64
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="set-radix-command"></a>Nastavit základ – příkaz
Nastaví nebo vrátí číselný základní slouží k zobrazení celočíselné hodnoty.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.SetRadix [10 | 16 | hex | dec]  
```  
  
## <a name="arguments"></a>Arguments  
 `10`nebo `16` nebo `hex` nebo`dec`  
 Volitelné. Určuje desetinné číslo (10 nebo dec) nebo v šestnáctkové soustavě (16 nebo šestnáctkových). Pokud je argument vynechán, je aktuální hodnota základ – vrácena.  
  
## <a name="example"></a>Příklad  
 Tento příklad nastaví prostředí k zobrazení hodnot celé číslo v šestnáctkovém formátu.  
  
```  
>Debug.SetRadix hex  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)