---
title: Idialoadcallback2::restrictdbgaccess – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback2::RestrictDBGAccess method
ms.assetid: 63b67a93-2910-4fff-aa70-6b2eaa08e5c8
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d30ab4d2c64eea3b607a582848fcd2bfbcf88819
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631659"
---
# <a name="idialoadcallback2restrictdbgaccess"></a>IDiaLoadCallback2::RestrictDBGAccess
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idialoadcallback2::restrictdbgaccess –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idialoadcallback2-restrictdbgaccess).  
  
Určuje, jestli hledáte informace o ladění je povolené z soubory dbg.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT RestrictDBGAccess();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Všechny návratové hodnoty jiné než `S_OK` zabránit hledáte informace o ladění z soubory dbg.  
  
## <a name="see-also"></a>Viz také  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)



