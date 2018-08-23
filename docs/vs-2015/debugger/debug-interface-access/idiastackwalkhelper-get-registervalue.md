---
title: IDiaStackWalkHelper::get_registerValue | Dokumentace Microsoftu
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
- IDiaStackWalkHelper2::get_registerValue method
ms.assetid: 46ac5eee-73a3-44a1-8635-6c58ba193cb6
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 58876436a426a71df3f13df1e5857d9dbdace025
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675549"
---
# <a name="idiastackwalkhelpergetregistervalue"></a>IDiaStackWalkHelper::get_registerValue
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDiaStackWalkHelper::get_registerValue](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackwalkhelper-get-registervalue).  
  
Načte hodnotu registru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_registerValue (   
   DWORD      index,  
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `index`  
 [in] Hodnota z [cv_hreg_e – výčet](../../debugger/debug-interface-access/cv-hreg-e.md) výčet určující, které zaregistrovat k získání hodnoty z.  
  
 `pRetVal`  
 [out] Vrátí aktuální hodnotu registru.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Bez ohledu na velikost `pRetVal` parametr, implementace by měla být uložena pouze co do registru obvykle obsahuje. Například 8bitový registr obsahuje pouze nejnižší 8 bitů předané hodnoty. Tato hodnota 8 bitů rozbalen do 64 bitů když tato metoda vrátí.  
  
## <a name="see-also"></a>Viz také  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [Cv_hreg_e – výčet](../../debugger/debug-interface-access/cv-hreg-e.md)



