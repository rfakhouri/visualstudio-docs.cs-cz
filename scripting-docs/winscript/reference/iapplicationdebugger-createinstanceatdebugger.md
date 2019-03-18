---
title: IApplicationDebugger::CreateInstanceAtDebugger | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 601f20c530ec5e275139d1e70d3df58fa88cd715
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58147628"
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