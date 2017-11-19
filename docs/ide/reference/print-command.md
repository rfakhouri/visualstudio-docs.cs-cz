---
title: "Tisk – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.print
helpviewer_keywords:
- Debug.Print command
- Print method
- Print command
ms.assetid: 0412d381-590a-483f-bab4-6e1cca095645
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6eaf5d77da1dbc6e005764087dad338458e7ce8c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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