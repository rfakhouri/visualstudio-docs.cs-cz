---
title: IDebugDocument2::GetName | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugDocument2::GetName
helpviewer_keywords:
- IDebugDocument2::GetName
ms.assetid: 6f09ff09-b0cf-4472-8fc8-143991f0ceb1
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 09456b20faf4d5f5ea09baa55e0a7fd78a19a95c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54769690"
---
# <a name="idebugdocument2getname"></a>IDebugDocument2::GetName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Získá název dokumentu v jednom z několika způsoby.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetName(   
   GETNAME_TYPE gnType,  
   BSTR*        pbstrFileName  
);  
```  
  
```csharp  
int GetName(   
   enum_GETNAME_TYPE gnType,  
   out string        pbstrFileName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `gnType`  
 [in] Hodnota z [GETNAME_TYPE](../../../extensibility/debugger/reference/getname-type.md) výčet, který určuje typ název, který vrátí.  
  
 `pbstrFileName`  
 [out] Vrátí řetězec obsahující název dokumentu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda může například vrátit název dokumentu, jako název nebo název souboru nebo dokonce i část názvu souboru.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)   
 [GETNAME_TYPE](../../../extensibility/debugger/reference/getname-type.md)
