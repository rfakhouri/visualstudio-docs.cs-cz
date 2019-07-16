---
title: Tisk – příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.print
helpviewer_keywords:
- Debug.Print command
- Print method
- Print command
ms.assetid: 0412d381-590a-483f-bab4-6e1cca095645
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 65d78387c6d60d0b432db9aab175fbfe8dc2869b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68203556"
---
# <a name="print-command"></a>Tisk – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vyhodnotí výraz a zobrazí zadaný text.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.Print text  
```  
  
## <a name="arguments"></a>Arguments  
 `text`  
 Povinný parametr. Výraz k vyhodnocení nebo text k zobrazení.  
  
## <a name="remarks"></a>Poznámky  
 Otazník (?) můžete použít jako alias pro tento příkaz. Ano například příkaz  
  
```  
>Debug.Print expA  
```  
  
 lze také zapsat  
  
```  
>? expA  
```  
  
 Obě verze tohoto příkazu vrátí aktuální hodnotu výrazu `expA`.  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.Print varA  
```  
  
## <a name="see-also"></a>Viz také  
 [Ohodnotit příkaz – příkaz](../../ide/reference/evaluate-statement-command.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
