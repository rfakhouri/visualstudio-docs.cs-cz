---
title: IDiaSymbol::get_samplerSlot | Dokumentace Microsoftu
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
ms.assetid: 41c751ba-81be-4bd3-838f-8373fc146157
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 02c8028d167ed38447476d6f9d16f8f11c6a3733
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49173495"
---
# <a name="idiasymbolgetsamplerslot"></a>IDiaSymbol::get_samplerSlot
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte slotu vzorkovače.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT get_samplerSlot(   
   DWORD* pRetVal);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Ukazatel `DWORD` obsahující slotu vzorkovače.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



