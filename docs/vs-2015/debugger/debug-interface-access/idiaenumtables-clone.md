---
title: Idiaenumtables::clone – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
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
- IDiaEnumTables::Clone method
ms.assetid: beb21109-b12c-44d8-8c1f-a332216b3713
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0c5e84f73168abd25abdb0d971ca0bda8caab73d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49832338"
---
# <a name="idiaenumtablesclone"></a>IDiaEnumTables::Clone
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Clone (   
   IDiaEnumTables** ppenum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppenum`  
 [out] Vrátí [idiaenumtables –](../../debugger/debug-interface-access/idiaenumtables.md) objekt, který obsahuje duplicitní čítače výčtu. Tabulky se neduplikují, pouze enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)



