---
title: IDebugDocumentText::GetText | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentText.GetText
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentText::GetText
ms.assetid: 3c940a30-6c0f-4deb-aa4d-21a0bdef8461
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 77cc255bcd04754cbfde4638b67a85f6fdc0a922
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091985"
---
# <a name="idebugdocumenttextgettext"></a>IDebugDocumentText::GetText
Načte znaky a/nebo znak atributy přidružené k pozici znaku rozsahu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetText(  
   ULONG              cCharacterPosition,  
   WCHAR*             pcharText,  
   SOURCE_TEXT_ATTR*  pstaTextAttr,  
   ULONG*             pcNumChars,  
   ULONG              cMaxChars  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cCharacterPosition`  
 [in] Počáteční umístění pozice rozsahu znaků.  
  
 `pcharText`  
 [out v] Vyrovnávací paměť textu znak. Vyrovnávací paměť musí být dostatečně velký pro uložení `cMaxChars` znaků. Pokud má parametr hodnotu NULL, metoda nevrátí znaků.  
  
 `pstaTextAttr`  
 [out v] Vyrovnávací paměť znak atributu. Vyrovnávací paměť musí být dostatečně velký pro uložení `cMaxChars` znaků. Pokud má parametr hodnotu NULL, metoda nevrátí atributy.  
  
 `pcNumChars`  
 [out v] Vrátí počet znaků nebo atributy. Tento parametr musí být nastaven na hodnotu nula před voláním této metody.  
  
 `cMaxChars`  
 [in] Počet znaků v rozsahu znaků pozici. Také určuje maximální počet znaků k vrácení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda načte znaky a/nebo znak atributy přidružené k pozici znaku rozsahu. Umístění rozsahu znaků je určené pozici znaku a počet znaků.  
  
## <a name="see-also"></a>Viz také  
 [Idebugdocumenttext – rozhraní](../../winscript/reference/idebugdocumenttext-interface.md)   
 [SOURCE_TEXT_ATTR – výčet](../../winscript/reference/source-text-attr-enumeration.md)