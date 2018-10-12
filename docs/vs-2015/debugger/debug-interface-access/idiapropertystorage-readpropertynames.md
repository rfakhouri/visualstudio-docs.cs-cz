---
title: IDiaPropertyStorage::ReadPropertyNames | Dokumentace Microsoftu
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
- IDiaPropertyStorage::ReadPropertyNames
ms.assetid: f8bcab77-afca-4a8f-8710-697842f8a518
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4dd1027d5921af482a71c7c45e5b6c90599df512
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49232827"
---
# <a name="idiapropertystoragereadpropertynames"></a>IDiaPropertyStorage::ReadPropertyNames
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte odpovídající názvů řetězce pro daný vlastnost identifikátory.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT ReadPropertyNames (  
   ULONG         cpropid,  
   PROPID const* rgpropid,  
   BSTR*         rglpwstrName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cpropid`  
 [in] Počet ID vlastnosti v `rgpropid`.  
  
 `rgpropid`  
 [in] Pole ID vlastnost, pro které chcete načíst názvy (`PROPID` je definována v WTypes.h jako `ULONG`).  
  
 `rglpwstrName`  
 [out v] Pole názvy vlastností pro zadanou vlastnost ID. Pole musí být předběžně přidělit k uložení požadovaného počtu názvy vlastností a musí být do něj vejít aspoň `cpropid``BSTR` řetězce.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Názvy vráceného vlastností, které musí být uvolněna (voláním `SysFreeString` funkce) když jsou už nepotřebujete.  
  
## <a name="see-also"></a>Viz také  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)



