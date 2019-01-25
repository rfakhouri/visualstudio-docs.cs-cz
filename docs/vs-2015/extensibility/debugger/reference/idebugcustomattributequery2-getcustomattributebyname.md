---
title: IDebugCustomAttributeQuery2::GetCustomAttributeByName | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugCustomAttributeQuery2::GetCustomAttributeByName
helpviewer_keywords:
- IDebugCustomAttributeQuery2::GetCustomAttributeByName
ms.assetid: 7428dfeb-8929-41b2-9b99-cb343a86c02d
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e1af059cf4319c18b8f8bb63e7b50ec3d2822e93
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54752222"
---
# <a name="idebugcustomattributequery2getcustomattributebyname"></a>IDebugCustomAttributeQuery2::GetCustomAttributeByName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Získá počet bajtů vlastní atributy název vlastního atributu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
