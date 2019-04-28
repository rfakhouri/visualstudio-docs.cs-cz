---
title: IActiveScriptAuthor::RemoveNamedItem | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.RemoveNamedItem
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::RemoveNamedItem
ms.assetid: 1173ef46-39a5-4bc1-8e0c-89259a16be16
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 052704b9a1bef8c50c457e51438f0204813c2efe
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955142"
---
# <a name="iactivescriptauthorremovenameditem"></a>IActiveScriptAuthor::RemoveNamedItem
Odebere `NamedItem` objektů z oboru názvů skript, modul pro vytváření.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT RemoveNamedItem(  
   LPCOLESTR          pszName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszName`  
 [in] Adresa vyrovnávací paměti, který identifikuje `NamedItem` objektu, který chcete odebrat.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`S_FALSE`|`NamedItem` Objektu není k dispozici v oboru skriptu pro vytváření modulu.|  
  
## <a name="remarks"></a>Poznámky  
 [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) slouží k vložení `NamedItem` objektu do skriptu pro vytváření oboru názvů vyhledávacího stroje.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptAuthor Interface](../../winscript/reference/iactivescriptauthor-interface.md)   
 [IActiveScriptAuthor::AddNamedItem](../../winscript/reference/iactivescriptauthor-addnameditem.md)