---
title: IDiaPropertyStorage::ReadBSTR | Dokumentace Microsoftu
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
- IDiaPropertyStorage::ReadBSTR
ms.assetid: 7214643b-3286-48ed-90aa-0fe95b4cae5b
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 70536dfa8f25f0b3c6e4bad4c28631f50cb41445
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677494"
---
# <a name="idiapropertystoragereadbstr"></a>IDiaPropertyStorage::ReadBSTR
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDiaPropertyStorage::ReadBSTR](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiapropertystorage-readbstr).  
  
Přečte `BSTR` hodnoty v sadu vlastností.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT ReadBSTR (   
   PROPID id,  
   BSTR*  pValue  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `id`  
 [in] Identifikátor vlastnosti pro čtení (`PROPID` je definována v WTypes.h jako `ULONG`).  
  
 `pValue`  
 [out] Vrátí hodnotu vlastnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_INVALIDARG` Pokud vlastnost není typu `BSTR`.  
  
## <a name="remarks"></a>Poznámky  
 A `BSTR` je definován Windows jako řetězec širokých znaků ukončit nulou.  
  
## <a name="see-also"></a>Viz také  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)



