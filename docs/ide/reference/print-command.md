---
title: "Tisk – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- debug.print
helpviewer_keywords:
- Debug.Print command
- Print method
- Print command
ms.assetid: 0412d381-590a-483f-bab4-6e1cca095645
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: bba20817c03b7ff542c3af11a440ad8e619f5567
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="print-command"></a>Tisk – příkaz
Vyhodnotí výraz nebo zobrazí zadaný text.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.Print text  
```  
  
## <a name="arguments"></a>Arguments  
 `text`  
 Požadováno. Výraz k vyhodnocení nebo zobrazený text.  
  
## <a name="remarks"></a>Poznámky  
 Otazník (?) můžete použít jako alias pro tento příkaz. Tak například příkaz  
  
```  
>Debug.Print expA  
```  
  
 je také možné zapsat  
  
```  
>? expA  
```  
  
 Obě verze tento příkaz vrátí aktuální hodnotu výrazu `expA`.  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.Print varA  
```  
  
## <a name="see-also"></a>Viz také  
 [Ohodnotit příkaz – příkaz](../../ide/reference/evaluate-statement-command.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)