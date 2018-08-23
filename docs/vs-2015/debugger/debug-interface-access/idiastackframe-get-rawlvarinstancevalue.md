---
title: Idiastackframe::get_rawlvarinstancevalue – | Dokumentace Microsoftu
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
- IDiaStackFrame::get_rawLVarInstanceValue method
ms.assetid: ce526259-85a6-475b-9274-0b3a21d95db2
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2aca4ea4468409937cd0b90b7c2201898a9f93a0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670314"
---
# <a name="idiastackframegetrawlvarinstancevalue"></a>IDiaStackFrame::get_rawLVarInstanceValue
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiastackframe::get_rawlvarinstancevalue –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackframe-get-rawlvarinstancevalue).  
  
Tato metoda načte hodnotu místní proměnné zadané jako nezpracovaný bajtů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_rawLVarInstanceValue(  
   IDiaLVarInstance* pInstance,  
   DWORD             cbDataMax,  
   DWORD*            pcbData,  
   BYTE*             pbData  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pInstance`  
 [in] `IDiaLVarInstance` Objekt představující instance má být získána hodnota pro lokální proměnné.  
  
 `cbDataMax`  
 [in] Maximální počet bajtů ve vyrovnávací paměti na které odkazuje `pbData`. To může být maximálně 8 bajtů (`sizeof(ULONGLONG)`).  
  
 `pcbData`  
 [out] Vrátí skutečný počet bajtů uložených do vyrovnávací paměti.  
  
 `pbData`  
 [out] Vyrovnávací paměti, která vyplní data. IP adresa nesmí být `NULL`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)



