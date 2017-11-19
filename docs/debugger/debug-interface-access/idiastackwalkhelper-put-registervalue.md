---
title: IDiaStackWalkHelper::put_registerValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackWalkHelper2::put_registerValue method
ms.assetid: 8f02ce54-ef59-455f-8aa6-dc26761c7aff
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8abfd209e5c2f59a0c55128eb235fda868f4bfd5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiastackwalkhelperputregistervalue"></a>IDiaStackWalkHelper::put_registerValue
Nastaví hodnotu registru.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT put_registerValue (   
   DWORD     index,  
   ULONGLONG NewVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `index`  
 [v] Hodnota z [CV_HREG_e – výčet](../../debugger/debug-interface-access/cv-hreg-e.md) výčtu zadání registrace k zápisu.  
  
 `NewVal`  
 [v] Nová hodnota registru.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Bez ohledu velikost hodnoty by měla být uložena implementace pouze co registru obvykle obsahuje. Například 8bitový registr by obsahovat pouze na nejnižší 8-bits předané hodnoty.  
  
## <a name="see-also"></a>Viz také  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [CV_HREG_e – výčet](../../debugger/debug-interface-access/cv-hreg-e.md)