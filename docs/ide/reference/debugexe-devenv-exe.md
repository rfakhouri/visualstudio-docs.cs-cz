---
title: -Debugexe – (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Devenv, /DebugExe switch
- DebugExe switch
- /DebugExe [devenv.exe]
ms.assetid: cd700006-1648-418f-924b-4b1e5c1412ab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e0882ae58919cafae71bcb056e74533b7ce64a4e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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