---
title: IDiaPropertyStorage::ReadPropertyNames | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadPropertyNames
ms.assetid: f8bcab77-afca-4a8f-8710-697842f8a518
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c1624e3577128556a098f96fd41c9ba1dc1eb84e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiapropertystoragereadpropertynames"></a>IDiaPropertyStorage::ReadPropertyNames
Načte odpovídající názvy řetězec pro danou vlastnost identifikátory.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT ReadPropertyNames (  
   ULONG         cpropid,  
   PROPID const* rgpropid,  
   BSTR*         rglpwstrName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cpropid`  
 [v] Počet ID vlastnosti v `rgpropid`.  
  
 `rgpropid`  
 [v] Pole ID vlastnost, pro které chcete získat názvy (`PROPID` je definována v WTypes.h jako `ULONG`).  
  
 `rglpwstrName`  
 [ve out] Pole názvy vlastností pro zadanou vlastnost ID. Pole musí být předběžně přidělených pro uložení požadovaný počet názvů vlastností a musí být schopna uchovat alespoň `cpropid``BSTR` řetězce.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Názvy vrácených vlastností, které musí být uvolněno (voláním `SysFreeString` funkce) Pokud jsou už nepotřebují.  
  
## <a name="see-also"></a>Viz také  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)