---
title: ISetNextStatement::CanSetNextStatement | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ISetNextStatement.CanSetNextStatement
apilocation:
- scrobj.dll
ms.assetid: e2a54634-31ec-4d16-84e8-2b123845d876
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eb65faaf107c42b44201ea18c1150f8093b1654c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62786612"
---
# <a name="isetnextstatementcansetnextstatement"></a>ISetNextStatement::CanSetNextStatement
Tato metoda určuje, zda lze nastavit bod provádění, která určuje dalšího příkazu ke spuštění kódu, do zadaného umístění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT CanSetNextStatement(  
   IDebugStackFrame*  pStackFrame,  
   IDebugCodeContext*  pCodeContext  
)  
```  
  
#### <a name="parameters"></a>Parametry  
 `pStackFrame`  
 [in] Ukazatel na objekt rámce zásobníku.  
  
 `pCodeContext`  
 [in] Ukazatel na objekt kontextu kódu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Ke kontextu zadaný kód je možné aktualizovat následující příkaz.|  
|`S_FALSE`|Další příkaz nejde aktualizovat na kontext zadaného kódu.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [ISetNextStatement – rozhraní](../../winscript/reference/isetnextstatement-interface.md)