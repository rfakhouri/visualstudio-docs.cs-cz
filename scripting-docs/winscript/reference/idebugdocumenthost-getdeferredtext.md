---
title: IDebugDocumentHost::GetDeferredText | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 3e5800a6de15d2d59208022fa44d3c2f4c931e14
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63446579"
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
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_NOTIMPL`|Metoda není implementována.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda může vrátit `E_NOTIMPL`, pokud hostitel nevolá `IDebugDocumentHelper::AddDeferredText`.  
  
> [!NOTE]
> Tato metoda vrátí text z původního dokumentu. Hostitel není udržovat přehled o úpravy nebo další změny v dokumentu.  
  
## <a name="see-also"></a>Viz také  
 [Idebugdocumenthost – rozhraní](../../winscript/reference/idebugdocumenthost-interface.md)   
 [IDebugDocumentHelper::AddDeferredText](../../winscript/reference/idebugdocumenthelper-adddeferredtext.md)   
 [SOURCE_TEXT_ATTR – výčet](../../winscript/reference/source-text-attr-enumeration.md)