---
title: IDebugDocumentHost::OnCreateDocumentContext | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHost.OnCreateDocumentContext
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentHost::OnCreateDocumentContext
ms.assetid: 080c8604-cfd7-484e-a337-15040870e683
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c0f8ce73e05fa8dd163564184361254fd58163ee
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54096330"
---
# <a name="idebugdocumenthostoncreatedocumentcontext"></a>IDebugDocumentHost::OnCreateDocumentContext
Upozorňuje hostitele, že se vytváří nový kontext dokumentu a umožňuje hostiteli volitelně vrátit řízení pro nový kontext.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT OnCreateDocumentContext(  
   IUnknown**  ppunkOuter  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppunkOuter`  
 [out] Objekt, který určuje nový kontext.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_NOTIMPL`|Hostitel neposkytuje řídící objektu.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda umožňuje hostiteli přidat nové funkce do zadané pomocné rutiny dokumentu kontexty. Tato metoda může vrátit **E_NOTIMPL** nebo vnější objekt s hodnotou null, ve kterém případ volající zodpovídá za vytvoření kontextu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentHost – rozhraní](../../winscript/reference/idebugdocumenthost-interface.md)