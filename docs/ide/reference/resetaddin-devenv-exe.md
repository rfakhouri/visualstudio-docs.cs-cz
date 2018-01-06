---
title: -ResetAddin (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disable addin
- addin state
- reset addin
ms.assetid: 9e339c8d-d768-4d86-8f45-2f479fc8255b
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 36b003f4890b16a7b69f7f66f8b0ef83a0ade7ac
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="resetaddin-devenvexe"></a>/ResetAddin (devenv.exe)
Odebere příkazy a příkaz přidružené zadaný v doplňku uživatelského rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Devenv /ResetAddin AddIn  
```  
  
## <a name="arguments"></a>Arguments  
 `AddIn`  
 Volitelné. Název příkazu Add-in.  
  
## <a name="remarks"></a>Poznámky  
 Ve výchozím nastavení, se rovná názvu příkazu add-in  *\<AddInSolutionName >*. Připojit*.\< AddInSolutionName >*a zobrazí se v Connect.cs jako `commandName` parametr `Exec` metoda. Můžete si taky ověřit název příkazu spuštěním k zadání názvu add-in do okna Příkazy v sadě Visual Studio a vyplňte zbývající pomocí Intellisense.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu spustí Visual Studio a brání `MyAddin` doplňku v běhu při spuštění.  
  
```  
Devenv.exe /ResetAddin MyAddin.Connect.MyAddin  
```  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení sady Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)   
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)