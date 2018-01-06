---
title: IDebugAddress::GetAddress | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugAddress::GetAddress
helpviewer_keywords: IDebugAddress:GetAddress method
ms.assetid: 2590387b-5d36-4116-9a75-737957b8898e
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3fdaf96f0026a6ef89bf9eb234c97ee7bdff700a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugaddressgetaddress"></a>IDebugAddress::GetAddress
Vrací strukturu popisující objektu a jeho umístění v jeho oboru nebo kontejneru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetAddress (  
   DEBUG_ADDRESS * pAddress  
);  
```  
  
```csharp  
int GetAddress(  
   DEBUG_ADDRESS[] pAddress  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pAddress`  
 [ve out] A [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) struktura, která je vyplněno touto metodou.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) struktura je předaná této metodě, která jej vyplní pomocí příslušné informace. Jak se tyto informace interpretovat závisí na druhu vrácené informace a obslužná rutina symbol sám sebe. V tématu [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) další podrobnosti.  
  
## <a name="see-also"></a>Viz také  
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)