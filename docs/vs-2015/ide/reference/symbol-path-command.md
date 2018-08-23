---
title: Symbol příkaz cesta | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
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
manager: ghogen
ms.openlocfilehash: b21a745177722160b100d0bbad770c3a74c40ca3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628709"
---
# <a name="symbol-path-command"></a>Cesta k symbolu – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [cesty k symbolu – příkaz](https://docs.microsoft.com/visualstudio/ide/reference/symbol-path-command).  
  
  
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



