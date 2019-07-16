---
title: Idialinenumber::get_relativevirtualaddress – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_relativeVirtualAddress method
ms.assetid: ba8142e3-5c77-43cc-bd33-c077dcc18cab
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2bd700d17b3d0ebd95c7ab6639a7e219588547da
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68152025"
---
# <a name="idialinenumbergetrelativevirtualaddress"></a>IDiaLineNumber::get_relativeVirtualAddress
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte relativní virtuální adresu (RVA) bloku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_relativeVirtualAddress (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí image relativní virtuální adresu bloku.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
