---
title: DBGPROP_INFO_FLAGS | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DBGPROP_INFO_FLAGS
apilocation:
- scrobj.dll
f1_keywords:
- DBGPROP_INFO_FLAGS
helpviewer_keywords:
- DBGPROP_INFO_FLAGS
ms.assetid: e9450a21-a802-4c3e-8b3d-8e202f555de1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9821cde6c159712ff44438b74eea0f8e01247155
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791826"
---
# <a name="dbgpropinfoflags"></a>DBGPROP_INFO_FLAGS
Slouží k zadání `DebugPropertyInfo` pole  
  
## <a name="syntax"></a>Syntaxe  
  
```  
enum {  
   DBGPROP_INFO_NAME  =0x001,  
   DBGPROP_INFO_TYPE  =0x002,  
   DBGPROP_INFO_VALUE  =0x004,  
   DBGPROP_INFO_FULLNAME  =0x020,  
   DBGPROP_INFO_ATTRIBUTES  =0x008,  
   DBGPROP_INFO_DEBUGPROP  =0x010,  
   DBGPROP_INFO_AUTOEXPAND  =0x8000000  
};  
```  
  
## <a name="members"></a>Členové  
 DBGPROP_INFO_NAME  
 Inicializuje `bstrName` pole.  
  
 DBGPROP_INFO_TYPE  
 Inicializuje `bstrType` pole.  
  
 DBGPROP_INFO_VALUE  
 Inicializuje `bstrValue` pole.  
  
 DBGPROP_INFO_FULLNAME  
 Inicializuje `bstrFullName` pole.  
  
 DBGPROP_INFO_ATTRIBUTES  
 Inicializuje `dwAttrib` pole.  
  
 DBGPROP_INFO_DEBUGPROP  
 Inicializuje `pDebugProp` pole, která obsahuje `IDebugProperty` rozhraní.  
  
 DBGPROP_INFO_AUTOEXPAND  
 Určuje, že pole hodnoty musí obsahovat hodnotu rozšířit automaticky, pokud je k dispozici pro tento typ objektu.  
  
## <a name="see-also"></a>Viz také  
 [Debugpropertyinfo – struktura](../../winscript/reference/debugpropertyinfo-structure.md)   
 [Idebugproperty – rozhraní](../../winscript/reference/idebugproperty-interface.md)