---
title: "Otevřít projekt – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: file.openproject
helpviewer_keywords:
- op command
- File.OpenProject command
- Open Project command
ms.assetid: baa85f86-041b-49f4-9ced-0c397dc180e1
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a3b0916874fbd4c16dfe2232a6a5865743d0c388
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="open-project-command"></a>Otevřít projekt – příkaz
Otevře existující projekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
File.OpenProject filename  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Požadováno. Úplné a cesta k souboru název projektu otevřete.  
  
 Syntaxe `filename` argument vyžaduje, aby cesty obsahující mezery, použijte uvozovky.  
  
## <a name="remarks"></a>Poznámky  
 Automatické doplňování, pokusí se najít správnou cestu a název souboru při psaní.  
  
 Tento příkaz není k dispozici při ladění.  
  
## <a name="example"></a>Příklad  
 Otevře se v tomto příkladu [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] projektu, Test1.  
  
```  
>File.OpenProject "C:\My Projects\Test1\Test1.vbproj"  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)