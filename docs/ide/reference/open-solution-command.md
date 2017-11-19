---
title: "Otevřít řešení – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: file.opensolution
helpviewer_keywords:
- Open Solution command
- File.OpenSolution command
ms.assetid: 61de76c8-69d7-4cdb-b605-e132f45d05d9
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bae1a28c7d9d0a87eeec3148301234cc0f45c286
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="open-solution-command"></a>Otevřít řešení – příkaz
Otevře se do stávajícího řešení zavřít všechny otevřené řešení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
File.OpenSolution filename  
```  
  
## <a name="arguments"></a>Arguments  
 `Filename`  
 Požadováno. Úplné a cesta k souboru název řešení otevřete.  
  
 Syntaxe `filename` argument vyžaduje, aby cesty obsahující mezery, použijte uvozovky.  
  
## <a name="remarks"></a>Poznámky  
 Automatické doplňování, pokusí se najít správnou cestu a název souboru při psaní.  
  
## <a name="example"></a>Příklad  
 Tento příklad otevře řešení, Test1.sln.  
  
```  
>File.OpenSolution "c:\MySolutions\Test1\Test1.sln"  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)