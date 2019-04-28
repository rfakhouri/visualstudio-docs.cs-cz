---
title: IDebugCustomAttributeQuery | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugCustomAttributeQuery interface
ms.assetid: b804b619-70eb-4c38-80d9-c8b32b65ed3e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ea9c37dbb889a622d0b428d53144c27d0c04aef9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62875968"
---
# <a name="idebugcustomattributequery"></a>IDebugCustomAttributeQuery
Představuje dotaz pro vlastní atributy u metody nebo typu.

## <a name="syntax"></a>Syntaxe

```
IDebugCustomAttributeQuery : IUnknown
```

## <a name="methods"></a>Metody
 Toto rozhraní implementuje následujících metod:

|Metoda|Popis|
|------------|-----------------|
|[GetCustomAttributeByName](../../../extensibility/debugger/reference/idebugcustomattributequery-getcustomattributebyname.md)|Načte vlastní atribut jeho název.|
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery-iscustomattributedefined.md)|Určuje, do zadaného vlastního atributu je definována.|

## <a name="requirements"></a>Požadavky
 Záhlaví: Sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll