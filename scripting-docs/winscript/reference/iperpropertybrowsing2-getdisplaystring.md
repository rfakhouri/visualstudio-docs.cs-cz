---
title: IPerPropertyBrowsing2::GetDisplayString | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.GetDisplayString
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::GetDisplayString
ms.assetid: 8f75c6a9-86a9-4e2d-8cb4-74e7b1c0a524
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f6f63db8d9c032b8e880f05d4d21e50fd56c74e2
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58147979"
---
# <a name="iperpropertybrowsing2getdisplaystring"></a>IPerPropertyBrowsing2::GetDisplayString
Získá řetězec k zobrazení typů, které nejsou ze své podstaty zobrazitelné vráceném textu budou zobrazeny je název popisující vlastnosti a mohou být zobrazeny v uživatelském rozhraní volajícího.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetDisplayString(  
   DISPID  dispid,  
   BSTR*  pBstr  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dispid`  
 [in] Odeslání identifikátor jejichž zobrazované jméno je požadovaná vlastnost.  
  
 `pBstr`  
 [out] Ukazatel `BSTR` obsahující zobrazovaný název pro vlastnost identifikovaný `dispID`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Bude vracet platnou `HRESULT`, obvykle `S_OK`.  
  
## <a name="remarks"></a>Poznámky  
 Vrácený řetězec není platná hodnota vlastnosti. Je jenom zobrazovaný řetězec vlastnosti.  
  
## <a name="see-also"></a>Viz také  
 [IPerPropertyBrowsing2 – rozhraní 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)