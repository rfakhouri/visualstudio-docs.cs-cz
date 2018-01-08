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
ms.workload: multiple
ms.openlocfilehash: eec04b3ab02f10d6eb9d745c21d2d0872df0ab8b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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