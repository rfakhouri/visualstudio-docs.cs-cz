---
title: Nastavit základ – příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.setradix
helpviewer_keywords:
- Set Radix command
- Debug.SetRadix command
ms.assetid: 6ffd1554-7530-4da4-b5f5-e276a5034f3b
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c315ccb0bc7404ddbaa303430644b404a570e016
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54798087"
---
# <a name="set-radix-command"></a>Nastavit základ – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Nastaví nebo vrátí číselný základ slouží k zobrazení hodnot typu integer.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.SetRadix [10 | 16 | hex | dec]  
```  
  
## <a name="arguments"></a>Arguments  
 `10` nebo `16` nebo `hex` nebo `dec`  
 Volitelné. Určuje desetinné číslo (10 nebo dec) nebo šestnáctkové číslo (maximálně 16 šestnáctkových). Pokud je argument vynechán, je vrácena aktuální hodnota Číselná soustava.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu nastaví prostředí tak, aby zobrazení celočíselné hodnoty v šestnáctkovém formátu.  
  
```  
>Debug.SetRadix hex  
```  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio Commands](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
