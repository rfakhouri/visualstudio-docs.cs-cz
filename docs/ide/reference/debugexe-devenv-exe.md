---
title: "-Debugexe – (devenv.exe) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /DebugExe switch
- DebugExe switch
- /DebugExe [devenv.exe]
ms.assetid: cd700006-1648-418f-924b-4b1e5c1412ab
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8f50bfd0fa5b0f9303bc6256078a30da6e1c0575
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="debugexe-devenvexe"></a>/DebugExe (devenv.exe)
Otevře zadaný spustitelný soubor chcete ladit.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Devenv /debugexe ExecutableFile  
```  
  
## <a name="arguments"></a>Arguments  
 `ExecutableFile`  
 Požadováno. Název a cesta k souboru .exe.  
  
 Pokud soubor .exe nebyl nalezen nebo pokud neexistuje, je nezobrazí žádná upozornění nebo chyby a [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] spustí běžným způsobem.  
  
## <a name="remarks"></a>Poznámky  
 Všechny řetězce následující `ExecutableFile` parametru jsou předány na daný soubor jako argumenty.  
  
## <a name="example"></a>Příklad  
 Následující příklad otevře soubor `MyApplication.exe` pro ladění.  
  
```  
Devenv.exe /debugexe MyApplication.exe  
```  
  
## <a name="see-also"></a>Viz také  
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)