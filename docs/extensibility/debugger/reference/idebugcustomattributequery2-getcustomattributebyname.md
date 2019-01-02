---
title: IDebugCustomAttributeQuery2::GetCustomAttributeByName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugCustomAttributeQuery2::GetCustomAttributeByName
helpviewer_keywords:
- IDebugCustomAttributeQuery2::GetCustomAttributeByName
ms.assetid: 7428dfeb-8929-41b2-9b99-cb343a86c02d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 95c26f1416707f0f0f04492d3b66ab1bdc8c06fc
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53895204"
---
# <a name="idebugcustomattributequery2getcustomattributebyname"></a>IDebugCustomAttributeQuery2::GetCustomAttributeByName
Získá počet bajtů vlastní atributy název vlastního atributu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetCustomAttributeByName(   
   LPCOLESTR pszCustomAttributeName,  
   BYTE*     ppBlob,  
   DWORD*    pdwLen  
);  
```  
  
```csharp  
int GetCustomAttributeByName(  
   [In] string        pszCustomAttributeName,   
   [In, Out] byte[]   ppBlob,   
   [In, Out] ref uint pdwLen  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszCustomAttributeName`  
 [in] Řetězec obsahující název vlastního atributu má hledat.  
  
 `ppBlob`  
 [out v] Pole, které se vyplní bajtů vlastního atributu.  
  
 `pdwLen`  
 [out v] Určuje maximální počet bajtů, které mají vracet v `ppBlob` pole a vrátí počet bajtů zapsaný ve skutečnosti na pole.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK nebo vrátí S_FALSE v případě vlastního atributu neexistuje. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Nastavte `ppBlob` atributy parametr na hodnotu null, vrátí počet bajtů, které jsou k dispozici. Potom přidělit pole a předejte toto pole v pro `ppBlob` parametru.  
  
 Atribut bajtů představují nezpracovaná data vlastního atributu.  
  
 Pokud `ppBlob` a `pdwLen` parametry jsou nastaveny na hodnotu null, tato metoda slouží k určení, zda je vlastní atribut pouze existuje. Jednodušší alternativu, je však volat [IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery2-iscustomattributedefined.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)   
 [IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery2-iscustomattributedefined.md)