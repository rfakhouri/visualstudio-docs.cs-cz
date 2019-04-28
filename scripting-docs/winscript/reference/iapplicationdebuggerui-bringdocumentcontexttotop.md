---
title: IApplicationDebuggerUI::BringDocumentContextToTop | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IApplicationDebuggerUI.BringDocumentContextToTop
apilocation:
- scrobj.dll
helpviewer_keywords:
- IApplicationDebuggerUI::BringDocumentContextToTop
ms.assetid: 7844217d-658b-42af-8d10-2714f4eded20
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 596f9357a8553bf6c39140a6948d8ae3085c3210
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62991136"
---
# <a name="iapplicationdebuggeruibringdocumentcontexttotop"></a>IApplicationDebuggerUI::BringDocumentContextToTop
Zobrazí se okno obsahující daný dokument kontext do horní části v uživatelském rozhraní ladicího programu a posune okno kontextu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT BringDocumentContextToTop(  
   IDebugDocumentContext*  pddc  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pddc`  
 [in] Kontext dokumentu, aby si přenesli do horní části v uživatelském rozhraní ladicího programu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_INVALIDARG`|Kontext určeného `pddc` není znám.|  
  
## <a name="remarks"></a>Poznámky  
 Tuto metodu, zobrazí se okno obsahující daný dokument kontext do horní části v uživatelském rozhraní ladicího programu a posune okno kontextu.  
  
## <a name="see-also"></a>Viz také  
 [IApplicationDebuggerUI – rozhraní](../../winscript/reference/iapplicationdebuggerui-interface.md)