---
title: IDebugGenericFieldInstance::GetTypeArguments | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- GetTypeArguments
- IDebugGenericFieldInstance::GetTypeArguments
ms.assetid: 6e7e0f95-181a-4805-adb3-c2407de0ab93
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d498c6f928e2c6daad71949aa7ce98104b79abae
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49274024"
---
# <a name="idebuggenericfieldinstancegettypearguments"></a>IDebugGenericFieldInstance::GetTypeArguments
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Načte argumenty parametrů typu pro tuto instanci.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetTypeArguments(  
   ULONG32       cArgs,  
   IDebugField** ppArgs,  
   ULONG32*      pcArgs  
);  
```  
  
```csharp  
int GetTypeArguments(  
   uint              cArgs,  
   out IDebugField[] ppArgs,  
   ref uint          pcArgs  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cArgs`  
 [in] Počet parametrů typu.  
  
 `ppArgs`  
 [out] Vrátí pole parametrů typu.  
  
 `pcArgs`  
 [out v] Počet členů v `ppArgs` pole.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugGenericFieldInstance](../../../extensibility/debugger/reference/idebuggenericfieldinstance.md)

