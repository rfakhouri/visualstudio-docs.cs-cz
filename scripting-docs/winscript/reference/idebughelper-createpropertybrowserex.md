---
title: IDebugHelper::CreatePropertyBrowserEx | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugHelper.CreatePropertyBrowserEx
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugHelper::CreatePropertyBrowserEx
ms.assetid: 87ad322f-09da-4ce8-bb68-0b0bbeec645b
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c3590fe05ef82f094dd5706f9f527b247d95eda8
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097731"
---
# <a name="idebughelpercreatepropertybrowserex"></a>IDebugHelper::CreatePropertyBrowserEx
Vrátí prohlížeč vlastnost, která obtéká hodnotu typu VARIANT a umožňuje vlastní převod hodnot typu VARIANT nebo typy VARTYPE na řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT CreatePropertyBrowserEx(  
   VARIANT*                  pvar,  
   LPCOLESTR                 bstrName,  
   IDebugApplicationThread*  pdat,  
   IDebugFormatter*          pdf,  
   IDebugProperty**          ppdob  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pvar`  
 [in] Kořenový typ variant Procházet.  
  
 `bstrName`  
 [in] Název kořenové.  
  
 `pdat`  
 [in] Vlákno, na kterém chcete požadovat vlastnosti. Pokud tento parametr hodnotu NULL, se neprovádí žádné zařazení.  
  
 `pdf`  
 [in] Objekt, který poskytuje vlastní formátování pro varianty.  
  
 `ppdob`  
 [out] Prohlížeč vlastností.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrátí prohlížeč vlastnost, která obtéká hodnotu typu VARIANT a umožňuje vlastní převod hodnot typu VARIANT nebo typy VARTYPE na řetězce.  
  
## <a name="see-also"></a>Viz také  
 [IDebugHelper::CreatePropertyBrowser](../../winscript/reference/idebughelper-createpropertybrowser.md)   
 [Idebughelper – rozhraní](../../winscript/reference/idebughelper-interface.md)   
 [IDebugProperty – rozhraní](../../winscript/reference/idebugproperty-interface.md)