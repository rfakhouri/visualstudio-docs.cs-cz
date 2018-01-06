---
title: "Přejděte na příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: edit.goto
helpviewer_keywords:
- Debug.Goto command
- Go To command
ms.assetid: 201e1dd2-6701-467d-8cc1-faec2ef20511
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 53c45ccf528375bc31b4d61fd6af0193aa295e6c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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