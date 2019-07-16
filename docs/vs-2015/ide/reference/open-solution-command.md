---
title: Otevřít řešení – příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- file.opensolution
helpviewer_keywords:
- Open Solution command
- File.OpenSolution command
ms.assetid: 61de76c8-69d7-4cdb-b605-e132f45d05d9
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: bb99d359f3858d8e7f15e013ab56719c7ed14995
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199026"
---
# <a name="open-solution-command"></a>Otevřít řešení – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Otevře existující řešení, zavírání všechna otevřená řešení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
File.OpenSolution filename  
```  
  
## <a name="arguments"></a>Arguments  
 `Filename`  
 Povinný parametr. Úplnou cestu a název souboru název řešení mohlo být otevřeno.  
  
 Syntaxe `filename` argument vyžaduje, aby cesty obsahující mezery, použijte uvozovky.  
  
## <a name="remarks"></a>Poznámky  
 Automatické dokončování, pokusí se najít správnou cestu a název souboru během psaní.  
  
## <a name="example"></a>Příklad  
 Tento příklad otevře řešení Test1.sln.  
  
```  
>File.OpenSolution "c:\MySolutions\Test1\Test1.sln"  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
