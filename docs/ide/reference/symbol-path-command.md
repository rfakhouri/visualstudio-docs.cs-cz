---
title: Symbolů cesta příkaz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.symbolpath
helpviewer_keywords:
- symbol path command
- Debug.SymbolPath command
- SymbolPath command
ms.assetid: b697ef2d-3f5d-40df-b113-7068a5bec0d4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b1b35c5d55eed31111746f2e2dbf9befb4fb7591
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="symbol-path-command"></a>Cesta k symbolu – příkaz
Nastaví seznam adresářů v ladicím programu pro vyhledávání symbolů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.SymbolPath pathname1;pathname2;... pathnameN  
```  
  
## <a name="arguments"></a>Arguments  
 `pathname`  
 Volitelné. Středníkem oddělené seznamu cest v ladicím programu pro vyhledávání symbolů.  
  
## <a name="remarks"></a>Poznámky  
 Pokud žádné `pathname` je zadán příkaz uvádí aktuální symbol cesty.  
  
## <a name="example"></a>Příklad  
 Tento příklad přidá do seznamu adresářů symbol dvě cesty.  
  
```  
Debug.SymbolPath C:\Symbol Path 1;C:\Symbol Path 2  
```  
  
## <a name="example"></a>Příklad  
 Tento příklad zobrazuje středníky oddělený seznam aktuální symbol cesty.  
  
```  
Debug.SymbolPath  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)