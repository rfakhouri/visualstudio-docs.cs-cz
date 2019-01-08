---
title: IDebugDocumentHelper::Init | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.Init
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::Init
ms.assetid: 1dd5a01f-0779-4109-8c6c-f16f5a3835bf
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d4bcb64b7bbb1c61e7f031d872f7d1440fd17833
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086629"
---
# <a name="idebugdocumenthelperinit"></a>IDebugDocumentHelper::Init
`Init` Metoda inicializuje dokumentu nápovědu ladicího programu s názvem a počáteční atributy.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Init(  
   IDebugApplication*  pda,  
   LPCOLESTR           pszShortName,  
   LPCOLESTR           pszLongName,  
   TEXT_DOC_ATTR       docAttr  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pda`  
 [in] Ladění aplikace spojené s tímto dokumentem.  
  
 `pszShortName`  
 [in] Řetězec zakončený hodnotou null obsahující krátký název dokumentu.  
  
 `pszLongName`  
 [in] Řetězec zakončený hodnotou null obsahující dlouhý název dokumentu.  
  
 `docAttr`  
 [in] Určuje atributy textový dokument.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda inicializuje dokumentu nápovědu ladicího programu s názvem a počáteční atributy.  
  
 Tento dokument se nezobrazí ve stromu do `IDebugDocumentHelper::Attach` je volána.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentHelper::Attach](../../winscript/reference/idebugdocumenthelper-attach.md)   
 [Idebugdocumenthelper – rozhraní](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [TEXT_DOC_ATTR – konstanty](../../winscript/reference/text-doc-attr-constants.md)