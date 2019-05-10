---
title: IDebugProviderProgramNode2::UnmarshalDebuggeeInterface | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
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
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 887002086b50198ba192bde3f19390d3267a5c9d
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457355"
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

## <a name="parameters"></a>Parametry
 `riid`\

 [in] Identifikátor GUID rozhraní získat.

 `ppvObject`\

 [out] Vrátí objekt implementaci požadovaných rozhraní. [C++] to může být převeden přímo na typ požadované rozhraní. [C#] použít <xref:System.Runtime.InteropServices.Marshal.GetObjectForIUnknown%2A> metodu k získání požadovaných rozhraní.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda se používá při spuštění ladicího stroje [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] prostoru procesu a laděný program běží ve vlastním procesu.

## <a name="see-also"></a>Viz také:
- [IDebugProviderProgramNode2](../../../extensibility/debugger/reference/idebugproviderprogramnode2.md)