---
title: Seznam modulů příkaz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.listmodules
helpviewer_keywords:
- Debug.ListModules command
- ListModules command
- list modules command
ms.assetid: 3cb73774-6ac0-43b2-b781-75ed47175bfd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 621d2956807d415d1ed03799e1ef332404429603
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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