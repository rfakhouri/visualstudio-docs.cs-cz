---
title: IDebugPortSupplierDescription2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugPortSupplierDescription2 interface
ms.assetid: dd19b9d6-0703-44b3-9498-cedffa0ce5b7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d5f210d3f0f8f2a9d28abee3d1956a3b4d09038a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56722470"
---
# <a name="idebugportsupplierdescription2"></a>IDebugPortSupplierDescription2
Umožňuje [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] uživatelského rozhraní k zobrazení textu v **přenosu informací** část **připojit k procesu** dialogové okno.

## <a name="syntax"></a>Syntaxe

```
IDebugPortSupplierDescription2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Toto rozhraní je implementováno dodavatelé portů.

## <a name="methods"></a>Metody
 V následující tabulce jsou uvedeny metody objektu `IDebugPortSupplierDescription2`.

|Metoda|Popis|
|------------|-----------------|
|[GetDescription](../../../extensibility/debugger/reference/idebugportsupplierdescription2-getdescription.md)|Načte popis a metadata popisu pro dodavatele portu.|

## <a name="requirements"></a>Požadavky
 Záhlaví: Msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll