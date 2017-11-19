---
title: "Ohodnotit příkaz – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.evaluatestatement
helpviewer_keywords:
- Debug.EvaluateStatement command
- Evaluate Statement command
ms.assetid: 032039bc-9477-4f93-9b9d-66d4be0e90f4
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 46c80a49d0e043d7cdbffbc74698a29e10ab4795
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="evaluate-statement-command"></a>Ohodnotit příkaz – příkaz
Vyhodnotí a zobrazí daný příkaz.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.EvaluateStatement text   
```  
  
## <a name="arguments"></a>Arguments  
 `text`  
 Požadováno. Příkaz k vyhodnocení.  
  
## <a name="remarks"></a>Poznámky  
 Okno používané k zadání **EvaluateStatement** příkaz určuje, zda znak rovná se (=) interpretována jako relační operátor nebo operátor přiřazení.  
  
 V **příkaz** okně znak rovná se (=) interpretována jako operátor porovnání. Ano, například pokud hodnoty proměnných `a` a `b` jsou různé a potom příkaz  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 Vrátí hodnotu `false`.  
  
 V **Immediate** okně naopak znak rovná se (=) interpretována jako operátor přiřazení. Tak například příkaz  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 přiřadí do proměnné `a` hodnotu proměnné `b`.  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.EvaluateStatement(a+b)  
```  
  
## <a name="see-also"></a>Viz také  
 [Tisk – příkaz](../../ide/reference/print-command.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)