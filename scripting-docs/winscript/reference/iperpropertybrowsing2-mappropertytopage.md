---
title: IPerPropertyBrowsing2::MapPropertyToPage | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.MapPropertyToPage
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::MapPropertyToPage
ms.assetid: e6418a8e-500b-42e1-9b5a-52e6f7567f99
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 79b8d7cb9e1c8a9f79cdddc4f8d3404ff7a2036c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24794853"
---
# <a name="iperpropertybrowsing2mappropertytopage"></a>IPerPropertyBrowsing2::MapPropertyToPage
Vrátí CLSID ze stránky vlastností, které je možné upravit tuto vlastnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT MapPropertyToPage(  
   DISPID  dispid,  
   CLSID*  pClsidPropPage  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dispid`  
 [v] Odesílání identifikátor vlastnosti, které vás zajímají.  
  
 `pClsidPropPage`  
 [out] Ukazatel na CLSID Identifikace související s vlastností stránky vlastností. Pokud tato metoda selže, *`pClsidPropPage` je nastaven na CLSID_NULL.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrací platnou `HRESULT`, obvykle `S_OK`.  
  
## <a name="see-also"></a>Viz také  
 [Iperpropertybrowsing2 – rozhraní 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)