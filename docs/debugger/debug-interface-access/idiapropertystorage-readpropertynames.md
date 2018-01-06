---
title: IDiaPropertyStorage::ReadPropertyNames | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaPropertyStorage::ReadPropertyNames
ms.assetid: f8bcab77-afca-4a8f-8710-697842f8a518
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 95f535bd314ec998c83ec9c02aab2190646f3c53
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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