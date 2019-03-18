---
title: EX_DBGPROP_INFO_FLAGS | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- EX_DBGPROP_INFO_FLAGS
apilocation:
- scrobj.dll
helpviewer_keywords:
- EX_DBGPROP_INFO_FLAGS
ms.assetid: ee309dfe-9432-4dff-8756-7a8d677f9dcc
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 086a2b7544a95a302219ddc62c15c5b31dd1d9b6
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58144833"
---
# <a name="exdbgpropinfoflags"></a>EX_DBGPROP_INFO_FLAGS
Používá se k určení `ExtendedDebugPropertyInfo` pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
enum {  
   EX_DBGPROP_INFO_ID  =0x0100,  
   EX_DBGPROP_INFO_NTYPE  =0x0200,  
   EX_DBGPROP_INFO_NVALUE  =0x0400,  
   EX_DBGPROP_INFO_LOCKBYTES  =0x0800,  
   EX_DBGPROP_INFO_DEBUGEXTPROP  =0x1000  
};  
```  
  
## <a name="members"></a>Členové  
 EX_DBGPROP_INFO_ID  
 Identifikátor pro vlastnost inicializuje.  
  
 EX_DBGPROP_INFO_NTYPE  
 Inicializuje typu vlastnosti.  
  
 EX_DBGPROP_INFO_NVALUE  
 Inicializuje hodnoty vlastnosti.  
  
 EX_DBGPROP_INFO_LOCKBYTES  
 Inicializuje `plb` pole.  
  
 EX_DBGPROP_INFO_DEBUGEXTPROP  
 Inicializuje `pDebugExtProp` pole s údajem `IDebugExtendedProperty` rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Extendeddebugpropertyinfo – struktura](../../winscript/reference/extendeddebugpropertyinfo-structure.md)   
 [IDebugExtendedProperty – rozhraní](../../winscript/reference/idebugextendedproperty-interface.md)