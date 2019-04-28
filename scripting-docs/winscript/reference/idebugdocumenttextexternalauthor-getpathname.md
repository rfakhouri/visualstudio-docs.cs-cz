---
title: IDebugDocumentTextExternalAuthor::GetPathName | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentTextExternalAuthor.GetPathName
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentTextExternalAuthor::GetPathName
ms.assetid: 445152a1-9cf8-402e-93d6-3d4bf2b81d17
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5739e7cb0cb12661ee5683051fb7b687e62dfde4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62978751"
---
# <a name="idebugdocumenttextexternalauthorgetpathname"></a>IDebugDocumentTextExternalAuthor::GetPathName
Vrátí úplnou cestu a název souboru dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetPathName(  
   BSTR*  pbstrLongName,  
   BOOL*  pfIsOriginalFile  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrLongName`  
 [out] Řetězec obsahující úplnou cestu a název souboru.  
  
 `pfIsOriginalFile`  
 [out] Logická hodnota označující, pokud název a cesta k souboru odkazovat v původním dokumentu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_FAIL`|Nelze vytvořit ani určit zdrojový soubor.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrátí úplnou cestu a název souboru dokumentu.  
  
 Pokud `pfIsOriginalFile` je FALSE, cesta a název souboru v `pbstrLongName` odkazovat na nově vytvořený dočasný soubor.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentTextExternalAuthor – rozhraní](../../winscript/reference/idebugdocumenttextexternalauthor-interface.md)