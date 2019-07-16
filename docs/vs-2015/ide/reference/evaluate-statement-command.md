---
title: Ohodnotit příkaz – příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.evaluatestatement
helpviewer_keywords:
- Debug.EvaluateStatement command
- Evaluate Statement command
ms.assetid: 032039bc-9477-4f93-9b9d-66d4be0e90f4
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f774458eb63d9e56b99a635e7b32309375a903ef
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199365"
---
# <a name="evaluate-statement-command"></a>Ohodnotit příkaz – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vyhodnotí a zobrazí daný příkaz.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.EvaluateStatement text   
```  
  
## <a name="arguments"></a>Arguments  
 `text`  
 Povinný parametr. Příkaz k vyhodnocení.  
  
## <a name="remarks"></a>Poznámky  
 V okně použité ke vstupu **EvaluateStatement** příkaz určuje, zda je znak rovná se (=) interpretován jako porovnávací operátor nebo jako operátor přiřazení.  
  
 V **příkaz** okně znak rovná se (=) interpretován jako operátor porovnání. Tak například, pokud hodnoty proměnných `a` a `b` jsou odlišné, pak příkaz  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 Vrátí hodnotu `false`.  
  
 V **okamžité** okna, naopak znak rovná se (=) interpretován jako operátor přiřazení. Ano například příkaz  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 přiřadí proměnné `a` hodnotu proměnné `b`.  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.EvaluateStatement(a+b)  
```  
  
## <a name="see-also"></a>Viz také  
 [Tisk – příkaz](../../ide/reference/print-command.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
