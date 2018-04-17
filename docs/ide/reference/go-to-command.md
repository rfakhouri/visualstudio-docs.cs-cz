---
title: Přejděte na příkaz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- edit.goto
helpviewer_keywords:
- Debug.Goto command
- Go To command
ms.assetid: 201e1dd2-6701-467d-8cc1-faec2ef20511
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6b817fd11d2a731ad2c6347949f03906328c741f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="go-to-command"></a>Přejít na – příkaz
Přesune kurzor na zadaný řádek.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Edit.GoTo [linenumber]  
```  
  
## <a name="arguments"></a>Arguments  
 `linenumber`  
 Volitelné. Celé číslo představující číslo řádku přejít na.  
  
## <a name="remarks"></a>Poznámky  
 Čísla řádků začíná na jednu. Pokud hodnota `linenumber` je menší než 1, první řádek zobrazí. Pokud hodnota `linenumber` je větší než počet poslední řádek zobrazí poslední řádek.  
  
 Pokud nezadáte hodnotu `linenumber` není zadán, **přejít na řádek** zobrazí dialogové okno.  
  
 Alias pro tento příkaz je GoToLn.  
  
## <a name="example"></a>Příklad  
  
```  
>Edit.GoTo 125  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)