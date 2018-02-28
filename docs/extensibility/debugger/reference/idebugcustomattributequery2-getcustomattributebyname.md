---
title: IDebugCustomAttributeQuery2::GetCustomAttributeByName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugCustomAttributeQuery2::GetCustomAttributeByName
helpviewer_keywords:
- IDebugCustomAttributeQuery2::GetCustomAttributeByName
ms.assetid: 7428dfeb-8929-41b2-9b99-cb343a86c02d
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c462551d5664e58727446fb4c4101446366d6c3b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
 [v] Řetězec obsahující název pro vlastní atribut má být vyhledán.  
  
 `ppBlob`  
 [ve out] Pole, které obsahuje vlastní atribut bajtů.  
  
 `pdwLen`  
 [ve out] Určuje maximální počet bajtů, které se vrátí v `ppBlob` pole a vrátí počet bajtů ve skutečnosti zapsána do pole.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK nebo vrátí S_FALSE Pokud vlastní atribut neexistuje. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Nastavte `ppBlob` atributy parametr hodnotu null na vrátí počet bajtů, které jsou k dispozici. Potom přidělit pole a předat tohoto pole v pro `ppBlob` parametr.  
  
 Počet bajtů atribut představují nezpracovaná data vlastního atributu.  
  
 Pokud `ppBlob` a `pdwLen` parametry jsou nastaveny na hodnotu null, tato metoda slouží k určení, zda vlastní atribut jenom existuje. Alternativu jednodušší, je však k volání [IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery2-iscustomattributedefined.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)   
 [IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery2-iscustomattributedefined.md)