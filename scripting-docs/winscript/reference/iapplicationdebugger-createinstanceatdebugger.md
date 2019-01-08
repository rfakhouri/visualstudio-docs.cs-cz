---
title: IApplicationDebugger::CreateInstanceAtDebugger | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IApplicationDebugger.CreateInstanceAtDebugger
apilocation:
- scrobj.dll
helpviewer_keywords:
- IApplicationDebugger::CreateInstanceAtDebugger
ms.assetid: 6763afac-c86a-4e88-9580-77108fb242fb
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a6af315f25aa333ace4be7bb8e3584573f0cfd1f
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090919"
---
# <a name="iapplicationdebuggercreateinstanceatdebugger"></a>IApplicationDebugger::CreateInstanceAtDebugger
Povolí vytváření objektů v procesu ladicího programu pomocí kódu, který je mimo proces v ladicím programu.  
  
> [!IMPORTANT]
>  Tato metoda by neměla být implementována, protože umožňuje nedůvěryhodný kód k vytvoření libovolného objektů ve vlákně důvěryhodné ladicího programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT CreateInstanceAtDebugger(  
   REFCLSID    rclsid,  
   IUnknown*   pUnkOuter,  
   DWORD       dwClsContext,  
   REFIID      riid,  
   IUnknown**  ppvObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `rclsid`  
 [in] Identifikátor (CLSID) objekt k vytvoření třídy.  
  
 `pUnkOuter`  
 [in] Pokud `NULL`, není objekt vytváří jako součást agregace. V opačném případě `pUnkOuter` je ukazatel na agregovaný objekt `IUnknown` rozhraní (řízení `IUnknown`).  
  
 `dwClsContext`  
 [in] Kontext spuštění spustitelného kódu. Hodnoty pocházejí z výčtu `CLSCTX`.  
  
 `riid`  
 [in] Identifikátor rozhraní používaný ke komunikaci s objektem.  
  
 `ppvObject`  
 [out] Adresa proměnné ukazatele, která přijímá ukazatel rozhraní požadované `riid`. Po návratu úspěšné *`ppvObject` obsahuje ukazatel požadované rozhraní. Po selhání \* `ppvObject` obsahuje `NULL`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda delegoval vůči `CoCreateInstance`.  
  
 Metoda teď není implementovaná.  
  
## <a name="see-also"></a>Viz také  
 [IApplicationDebugger – rozhraní](../../winscript/reference/iapplicationdebugger-interface.md)