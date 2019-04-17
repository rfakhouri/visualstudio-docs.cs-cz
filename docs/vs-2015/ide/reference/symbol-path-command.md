---
title: Symbol příkaz cesta | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.symbolpath
helpviewer_keywords:
- symbol path command
- Debug.SymbolPath command
- SymbolPath command
ms.assetid: b697ef2d-3f5d-40df-b113-7068a5bec0d4
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 27c4c8ac23e2524245107d9052642350e9db09d2
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59670394"
---
# <a name="symbol-path-command"></a>Cesta k symbolu – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nastaví seznam adresářů pro ladicí program pro hledání symbolů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.SymbolPath pathname1;pathname2;... pathnameN  
```  
  
## <a name="arguments"></a>Arguments  
 `pathname`  
 Volitelné. Středníkem oddělený seznam cest ladicího programu pro hledání symbolů.  
  
## <a name="remarks"></a>Poznámky  
 Pokud ne `pathname` není zadán, příkaz vypíše aktuální cesty symbolů.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu přidá dvě cesty do seznamu adresářů symbolů.  
  
```  
Debug.SymbolPath C:\Symbol Path 1;C:\Symbol Path 2  
```  
  
## <a name="example"></a>Příklad  
 Tento příklad zobrazuje seznam oddělený středníkem aktuálních cest symbolu.  
  
```  
Debug.SymbolPath  
```  
  
## <a name="see-also"></a>Viz také  
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
