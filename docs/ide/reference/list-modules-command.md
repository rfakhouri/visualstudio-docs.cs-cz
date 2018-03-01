---
title: "Seznam modulů příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- debug.listmodules
helpviewer_keywords:
- Debug.ListModules command
- ListModules command
- list modules command
ms.assetid: 3cb73774-6ac0-43b2-b781-75ed47175bfd
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: bd752aca6bc52393da14da58c805d303c57673d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="list-modules-command"></a>Listovat moduly – příkaz
Seznam modulů pro aktuální proces.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.ListModules [/Address:yes|no] [/Name:yes|no] [/Order:yes|no]  
[/Path:yes|no] [/Process:yes|no] [/SymbolFile:yes|no]  
[/SymbolStatus:yes|no] [/Timestamp:yes|no] [/Version:yes|no]  
```  
  
#### <a name="parameters"></a>Parametry  
 A adresa:`yes|no`  
 Volitelné. Určuje, zda chcete zobrazit adresy paměti modulů. Výchozí hodnota je `yes`.  
  
 / Name:`yes|no`  
 Volitelné. Určuje, jestli se má zobrazit názvy modulů. Výchozí hodnota je `yes`.  
  
 / Pořadí:`yes|no`  
 Volitelné. Určuje, jestli se má zobrazit pořadí modulů. Výchozí hodnota je `no`.  
  
 Či cestu:`yes|no`  
 Volitelné. Určuje, zda chcete zobrazit cesty moduly. Výchozí hodnota je `yes`.  
  
 Nebo proces:`yes|no`  
 Volitelné. Určuje, zda chcete zobrazit procesy modulů. Výchozí hodnota je `no`.  
  
 Nebo soubor symbolů:`yes|no`  
 Volitelné. Určuje, zda chcete zobrazit soubory symbolů modulů. Výchozí hodnota je `no`.  
  
 / SymbolStatus:`yes|no`  
 Volitelné. Určuje, zda chcete zobrazit stavy symbol modulů. Výchozí hodnota je `yes`.  
  
 / Časové razítko:`yes|no`  
 Volitelné. Určuje, zda chcete zobrazit časová razítka modulů. Výchozí hodnota je `no`.  
  
 / Verze:`yes|no`  
 Volitelné. Určuje, zda chcete zobrazit verzích moduly. Výchozí hodnota je `no`.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 Tento příklad obsahuje názvy modulů, adresy a časová razítka pro aktuální proces.  
  
```  
Debug.ListModules /Address:yes /Name:yes /Order:no /Path:no /Process:no /SymbolFile:no /SymbolStatus:no /Timestamp:yes /Version:no  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Postupy: použití okna moduly](../../debugger/how-to-use-the-modules-window.md)