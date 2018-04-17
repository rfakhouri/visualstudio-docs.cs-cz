---
title: Přidat existující projekt – příkaz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- file.addexistingproject
helpviewer_keywords:
- Add Existing Project command
- File.AddExistingProject
ms.assetid: 71cf3e31-c76b-405b-ad6a-1b1bc654bd40
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 278ed3e13f29746aab963129418dc07f1dcf5234
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="add-existing-project-command"></a>Přidat existující projekt – příkaz
Přidá k aktuálnímu řešení existujícího projektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
File.AddExistingProject filename  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Volitelné. Úplná cesta a projekt název, s příponou projektu pro přidání do řešení.  
  
 Pokud `filename` argument obsahuje mezery, musí být uzavřena v uvozovkách.  
  
 Pokud není zadaný žádný název souboru, bude příkaz otevřete dialogové okno souboru, tento uživatel může zvolit projektu.  
  
## <a name="remarks"></a>Poznámky  
 Automatické doplňování, pokusí se najít správnou cestu a název souboru při psaní.  
  
## <a name="example"></a>Příklad  
 Tento příklad přidá [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] projektu, TestProject1, k aktuálnímu řešení.  
  
```  
>File.AddExistingProject "c:\visual studio projects\TestProject1.vbproj"  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)