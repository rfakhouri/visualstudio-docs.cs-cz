---
title: ICanHandleException::CanHandleException | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ICanHandleException.CanHandleException
apilocation:
- scrobj.dll
helpviewer_keywords:
- ICanHandleException::CanHandleException
ms.assetid: 0fc703bf-9518-487e-af20-00e073b640f1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 784463f9e465aac005f5454be28a0043069dcb69
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089996"
---
# <a name="icanhandleexceptioncanhandleexception"></a>ICanHandleException::CanHandleException
Určuje, pokud volající skriptovací stroj dokáže zpracovat zadané výjimky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT CanHandleException(  
   EXCEPINFO*  pExcepInfo,  
   VARIANT*    pvar  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pExcepInfo`  
 [in] Ukazatel `EXCEPINFO` struktura obsahující informace, které budou nahlášeny, pokud se nenajde žádná obslužná rutina výjimky.  
  
 `pvar`  
 [in] Hodnotu přiřazenou k výjimce, jako je hodnota vyvolané `throw` příkazu. Tento parametr může mít `NULL`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Volající může zpracovat výjimku|  
|`E_FAIL`|Volající nemůže zpracovat výjimku.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud je volání `IDispatchEx::InvokeEx`, nebo podobné metody, výsledkem výjimka, modul kontroly skript pro volajícího v volající řetězu certifikátů vašeho skriptu, který podporuje `ICanHandleException` rozhraní a označuje, že ji může zpracovat výjimku. Pokud žádný volající může zpracovat výjimku, zastaví skriptovací stroj.  
  
## <a name="see-also"></a>Viz také  
 [Icanhandleexception – rozhraní](../../winscript/reference/icanhandleexception-interface.md)   
 [IDispatchEx::InvokeEx](../../winscript/reference/idispatchex-invokeex.md)