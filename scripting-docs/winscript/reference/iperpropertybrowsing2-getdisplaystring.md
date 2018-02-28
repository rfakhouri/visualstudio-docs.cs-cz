---
title: IPerPropertyBrowsing2::GetDisplayString | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.GetDisplayString
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::GetDisplayString
ms.assetid: 8f75c6a9-86a9-4e2d-8cb4-74e7b1c0a524
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: be6f665d1f63966b3828868f4fb8fbf1cae002e9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="iperpropertybrowsing2getdisplaystring"></a>IPerPropertyBrowsing2::GetDisplayString
Získá řetězec k zobrazení typů, které nejsou ze své podstaty zobrazitelné vráceném textu budou zobrazeny je název popisující vlastnost a lze zobrazit v uživatelském rozhraní volajícího.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetDisplayString(  
   DISPID  dispid,  
   BSTR*  pBstr  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dispid`  
 [v] Odesílání identifikátor jehož zobrazovaný název je požadovaná vlastnost.  
  
 `pBstr`  
 [out] Ukazatel `BSTR` obsahující zobrazovaný název vlastnosti identifikovaný `dispID`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrací platnou `HRESULT`, obvykle `S_OK`.  
  
## <a name="remarks"></a>Poznámky  
 Vrácený řetězec není platnou hodnotou vlastnosti. Je právě zobrazovaný řetězec vlastnosti.  
  
## <a name="see-also"></a>Viz také  
 [Iperpropertybrowsing2 – rozhraní 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)