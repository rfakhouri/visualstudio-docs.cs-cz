---
title: DBGPROP_INFO_FLAGS | Dokumentace Microsoftu
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
ms.openlocfilehash: 517999bce9c85475bd91ad2e54e7ed49cda23aab
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095755"
---
# <a name="dbgpropinfoflags"></a>DBGPROP_INFO_FLAGS
Používá se k určení `DebugPropertyInfo` pole  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
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
 Inicializuje `pDebugProp` pole s údajem `IDebugProperty` rozhraní.  
  
 DBGPROP_INFO_AUTOEXPAND  
 Určuje, že hodnota pole by měl obsahovat hodnotu automaticky rozbaleny, pokud je k dispozici pro tento typ objektu.  
  
## <a name="see-also"></a>Viz také  
 [Debugpropertyinfo – struktura](../../winscript/reference/debugpropertyinfo-structure.md)   
 [IDebugProperty – rozhraní](../../winscript/reference/idebugproperty-interface.md)