---
title: Idiastackwalkframe::searchforreturnaddressstart – | Dokumentace Microsoftu
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
- IDiaStackWalkFrame::searchForReturnAddressStart method
ms.assetid: 47660b9b-6e4f-4dfa-88ab-63dce28f7412
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ef077fcea728f8440ca07ae316fdc87ea5b88089
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669535"
---
# <a name="idiastackwalkframesearchforreturnaddressstart"></a>IDiaStackWalkFrame::searchForReturnAddressStart
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiastackwalkframe::searchforreturnaddressstart –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddressstart).  
  
Vyhledá zadaný zásobník snímků pro zpáteční adresu na nebo blízko ní zadané adrese.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT searchForReturnAddressStart (   
   IDiaFrameData* frame,  
   ULONGLONG      startAddress,  
   ULONGLONG*     returnAddress  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `frame`  
 [in] [Idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md) objekt, který představuje aktuální rámec zásobníku.  
  
 `startAddress`  
 [in] Virtuální paměť adresa, ze kterého má být prohledávání.  
  
 `returnAddress`  
 [out] Vrátí funkci nejbližší zpětná adresa `startAddress`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiastackwalkframe –](../../debugger/debug-interface-access/idiastackwalkframe.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)



