---
title: IDebugCustomAttribute::GetAttributeBytes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCustomAttribute::GetAttributeBytes
helpviewer_keywords: IDebugCustomAttribute::GetAttributeBytes
ms.assetid: cf34583b-6530-4dcc-89f8-eb27e4e8d594
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1258b2b7fdc1c91eaaa6265ce74a3891deda8ab0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugcustomattributegetattributebytes"></a>IDebugCustomAttribute::GetAttributeBytes
Získá informace o atributu jako objekt blob bajtů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetAttributeBytes(   
   BYTE*  ppBlob,  
   DWORD* pdwLen  
);  
```  
  
```csharp  
int GetAttributeBytes(  
   ref byte[] ppBlob,   
   ref uint   pdwLen  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppBlob`  
 [ve out] Pole, které obsahuje atribut bajtů.  
  
 `pdwLen`  
 [ve out] Určuje maximální počet bajtů, které se vrátí v `ppBlob` pole a vrátí počet bajtů ve skutečnosti zapsána do pole.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Nastavte `ppBlob` atributy parametr hodnotu null na vrátí počet bajtů, které jsou k dispozici. Potom přidělit pole a předat tohoto pole v pro `ppBlob` parametr.  
  
 Počet bajtů atribut představují nezpracovaná data vlastního atributu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)