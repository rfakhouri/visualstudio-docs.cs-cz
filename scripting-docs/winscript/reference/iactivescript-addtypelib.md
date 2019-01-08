---
title: IActiveScript::AddTypeLib | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.AddTypeLib
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_AddTypeLib
ms.assetid: 8e507ea8-c80a-471c-b482-ae753c6e8595
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 695edbd6f5356959785e54dc38f28b68c8c0400e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092537"
---
# <a name="iactivescriptaddtypelib"></a>IActiveScript::AddTypeLib
Obor názvů pro skript přidá knihovnu typů. Podobá se to `#include` direktiva v jazyce C/C++. Umožňuje, aby sada předdefinovaných položek, jako jsou definice tříd `typedefs`a s názvem konstanty mají být přidány do běhové prostředí skriptu k dispozici.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT AddTypeLib(  
    REFGUID guidTypeLib,  // CLSID of type library  
    DWORD dwMaj,          // major version number  
    DWORD dwMin,          // minor version number  
    DWORD dwFlags         // option flags  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `guidTypeLib`  
 [in] Identifikátor CLSID typu knihovny přidat.  
  
 `dwMaj`  
 [in] Hlavní číslo verze.  
  
 `dwMin`  
 [in] Číslo podverze.  
  
 `dwFlags`  
 [in] Příznaky možností. Může být následující:  
  
|Hodnota|Význam|  
|-----------|-------------|  
|SCRIPTTYPELIB_ISCONTROL|Knihovna typů popisuje ovládací prvek ActiveX používá hostitel.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`E_INVALIDARG`|Argument byl neplatný.|  
|`E_UNEXPECTED`|Volání nebylo očekáváno (například skriptovací stroj má ještě nebyly načteny nebo inicializován).|  
|`TYPE_E_CANTLOADLIBRARY`|Zadanou knihovnu typů nelze načíst.|  
  
## <a name="see-also"></a>Viz také  
 [IActiveScript](../../winscript/reference/iactivescript.md)