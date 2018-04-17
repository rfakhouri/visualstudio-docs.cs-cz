---
title: Ohodnotit příkaz – příkaz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.evaluatestatement
helpviewer_keywords:
- Debug.EvaluateStatement command
- Evaluate Statement command
ms.assetid: 032039bc-9477-4f93-9b9d-66d4be0e90f4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fe960ec84830ce76095577f7d8ee2f0c9c4ccbe8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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