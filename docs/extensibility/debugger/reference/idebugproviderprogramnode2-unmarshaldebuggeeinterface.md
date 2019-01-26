---
title: IDebugProviderProgramNode2::UnmarshalDebuggeeInterface | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
helpviewer_keywords:
- IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
ms.assetid: 2e4653c5-10f1-493c-9973-f31d266c5d48
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1af69580293e4ff37d0a23e3050955c96cc8f10b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54988269"
---
# <a name="idebugproviderprogramnode2unmarshaldebuggeeinterface"></a>IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
Získá zadaný rozhraní přes hranice procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT UnmarshalDebuggeeInterface(  
   REFIID riid,  
   void** ppvObject  
);  
```  
  
```csharp  
int UnmarshalDebuggeeInterface(  
   ref Guid   riid,  
   out IntPtr ppvObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `riid`  
 [in] Identifikátor GUID rozhraní získat.  
  
 `ppvObject`  
 [out] Vrátí objekt implementaci požadovaných rozhraní. [C++] to může být převeden přímo na typ požadované rozhraní. [C#] použít <xref:System.Runtime.InteropServices.Marshal.GetObjectForIUnknown%2A> metodu k získání požadovaných rozhraní.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda se používá při spuštění ladicího stroje [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] prostoru procesu a laděný program běží ve vlastním procesu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProviderProgramNode2](../../../extensibility/debugger/reference/idebugproviderprogramnode2.md)