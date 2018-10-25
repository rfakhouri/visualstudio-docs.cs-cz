---
title: IDiaPropertyStorage::ReadULONGLONG | Dokumentace Microsoftu
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
- IDiaPropertyStorage::ReadULONGLONG
ms.assetid: f80a2e24-5744-4fec-bab0-3ed51aef6e58
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 818057204143643d8fe5ca8884203e008c64f7d4
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49935007"
---
# <a name="idiapropertystoragereadulonglong"></a>IDiaPropertyStorage::ReadULONGLONG
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Přečte `ULONGLONG` hodnoty v sadu vlastností.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT ReadULONGLONG (   
   PROPID     id,  
   ULONGLONG* pValue  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `id`  
 [in] Identifikátor vlastnosti pro čtení (`PROPID` je definována v WTypes.h jako `ULONG`).  
  
 `pValue`  
 [out] Vrátí hodnotu vlastnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_INVALIDARG` Pokud vlastnost není typu `ULONGLONG`.  
  
## <a name="remarks"></a>Poznámky  
 A `ULONGLONG` je definován jako celé číslo bez znaménka 64bitová verze Windows.  
  
## <a name="see-also"></a>Viz také  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)



