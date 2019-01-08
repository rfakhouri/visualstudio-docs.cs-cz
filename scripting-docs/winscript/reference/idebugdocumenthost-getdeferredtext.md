---
title: IDebugDocumentHost::GetDeferredText | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHost.GetDeferredText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentHost::GetDeferredText
ms.assetid: 527da666-fef5-4db3-a319-e68d466a7721
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1f2a39122454ea170177aee9ce7b2bbeb7ea248e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092557"
---
# <a name="idebugdocumenthostgetdeferredtext"></a>IDebugDocumentHost::GetDeferredText
Vrátí rozsah znaků, které byly přidány pomocí `IDebugDocumentHelper::AddDeferredText` metoda v původním dokumentu hostitele.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetDeferredText(  
   DWORD              dwTextStartCookie,  
   WCHAR*             pcharText,  
   SOURCE_TEXT_ATTR*  pstaTextAttr,  
   ULONG*             pcNumChars,  
   ULONG              cMaxChars  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwTextStartCookie`  
 [in] Hostitel definované souboru cookie, který představuje počáteční pozici textu.  
  
 `pcharText`  
 [out v] Vyrovnávací paměť textu znak. Tato metoda nevrací znaky, pokud je tento parametr `NULL`.  
  
 `pstaTextAttr`  
 [out v] Vyrovnávací paměť znak atributu. Tato metoda nevrací atributy, pokud je tento parametr `NULL`.  
  
 `pcNumChars`  
 [out v] Označuje skutečného člena znaky/atributy vrátil. Tento parametr musí být nastaven na hodnotu nula před voláním této metody.  
  
 `cMaxChars`  
 [in] Maximální počet znaků k vrácení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_NOTIMPL`|Metoda není implementována.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda může vrátit `E_NOTIMPL`, pokud hostitel nevolá `IDebugDocumentHelper::AddDeferredText`.  
  
> [!NOTE]
>  Tato metoda vrátí text z původního dokumentu. Hostitel není udržovat přehled o úpravy nebo další změny v dokumentu.  
  
## <a name="see-also"></a>Viz také  
 [Idebugdocumenthost – rozhraní](../../winscript/reference/idebugdocumenthost-interface.md)   
 [IDebugDocumentHelper::AddDeferredText](../../winscript/reference/idebugdocumenthelper-adddeferredtext.md)   
 [SOURCE_TEXT_ATTR – výčet](../../winscript/reference/source-text-attr-enumeration.md)