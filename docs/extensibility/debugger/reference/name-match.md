---
title: NAME_MATCH | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- NAME_MATCH
helpviewer_keywords:
- NAME_MATCH enumeration
ms.assetid: 3842c417-a3c9-4259-a05f-52b64b829ef6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 26666ff9955d7516ff30c7276bfd46e990577e70
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56714826"
---
# <a name="namematch"></a>NAME_MATCH
Vybere možnost případu pro odpovídající názvy.

## <a name="syntax"></a>Syntaxe

```cpp
typedef enum { 
   nmNone            = 0,
   nmCaseSensitive   = 1,
   nmCaseInsensitive = 2
} NAME_MATCH;
```

```csharp
public enum NameMatchOptions { 
   nmNone            = 0,
   nmCaseSensitive   = 1,
   nmCaseInsensitive = 2
}
```

## <a name="members"></a>Členové
 nmNone, které nejsou zadány žádné parametry.

 Označuje, že názvy lze porovnat nmCaseSensitive rozlišují malá a velká písmena.

 Označuje, že názvy lze porovnat nmCaseInsensitive nerozlišují malá a velká písmena.

## <a name="remarks"></a>Poznámky
 Předán jako argument pro následující metody:

-   [GetTypeByName](../../../extensibility/debugger/reference/idebugsymbolprovider-gettypebyname.md)

-   [GetClassTypeByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getclasstypebyname.md)

-   [EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)

-   [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)

## <a name="requirements"></a>Požadavky
 Záhlaví: sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetTypeByName](../../../extensibility/debugger/reference/idebugsymbolprovider-gettypebyname.md)
- [GetClassTypeByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getclasstypebyname.md)
- [EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)
- [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)