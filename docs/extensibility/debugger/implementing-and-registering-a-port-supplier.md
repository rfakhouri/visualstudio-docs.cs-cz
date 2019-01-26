---
title: Implementace a registrace dodavatele portu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], registering port suppliers
- port suppliers, registering
ms.assetid: fb057052-ee16-4272-8e16-a4da5dda0ad4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9e02c7e7ff030d2fd2bb9de86dfd1e7211f8de1f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54946708"
---
# <a name="implement-and-register-a-port-supplier"></a>Implementace a registrace dodavatele portu
Role dodavatele portu je ke sledování a dodávky porty, které pak spravujte procesy. Dodavatele portu port je potřeba vytvořit, je vytvořena instance pomocí CoCreate s identifikátorem GUID dodavatele portu (Správce ladění relace [SDM] používat dodavatele portu, který uživatel vybral nebo dodavatele portu určené systém projektu). Pak zavolá SDM [CanAddPort](../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md) zobrazíte mohou být přidány žádné porty. Pokud port lze přidat, je nový port požadované voláním [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md) a předáním [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) port, který popisuje. `AddPort` vrátí nový port reprezentována [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) rozhraní.  
  
## <a name="discussion"></a>Diskuse  
 Port je vytvořené dodavatele portu, který je přidružen k serveru počítače nebo ladění. Server vytvoří výčet její dodavatelé portů prostřednictvím[EnumPortSuppliers](../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md) metoda a dodavatele portu zobrazí jeho portům přes [EnumPorts](../../extensibility/debugger/reference/idebugportsupplier2-enumports.md) metoda.  
  
 Kromě typické registrace modelu COM dodavatele portu musí registrovat pomocí sady Visual Studio tak, že jeho identifikátor CLSID a název v konkrétním registru umístění. Pomocná funkce ladění sady SDK volat `SetMetric` zpracovává v tomto případě: se volá jednou pro každou položku k registraci, tedy:  
  
```cpp  
SetMetric(metrictypePortSupplier,  
          <GUID of your port supplier>,  
          metricCLSID,  
          <CLSID of your port supplier>,  
          false,  
          NULL)  
SetMetric(metrictypePortSupplier,  
          <GUID of your port supplier>,  
          metricName,  
          <name of your port supplier>,  
          false,  
          NULL);  
```  
  
 Dodavatele portu zruší registraci sám voláním `RemoveMetric` (jinou funkci pomocné rutiny ladění SDK) s jednou registrací u každé položky, která byla zaregistrována takto:  
  
```cpp  
RemoveMetric(metrictypePortSupplier,  
             <GUID of your port supplier>,  
             metricCLSID,  
             NULL);  
RemoveMetric(metrictypePortSupplier,  
             <GUID of your port supplier>,  
             metricName,  
             NULL);  
```  
  
> [!NOTE]
>  [Pomocníci sad SDK pro ladění](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) `SetMetric` a `RemoveMetric` jsou statické funkce definované v *dbgmetric.h* a zkompilovaných do *ad2de.lib*. `metrictypePortSupplier`, `metricCLSID`, A `metricName` pomocné rutiny jsou také definovány v *dbgmetric.h*.  
  
 Dodavatele portu můžete zadat jeho název a identifikátor GUID prostřednictvím metod [GetPortSupplierName](../../extensibility/debugger/reference/idebugportsupplier2-getportsuppliername.md) a [GetPortSupplierId](../../extensibility/debugger/reference/idebugportsupplier2-getportsupplierid.md)v uvedeném pořadí.  
  
## <a name="see-also"></a>Viz také:  
 [Implementace dodavatele portu](../../extensibility/debugger/implementing-a-port-supplier.md)   
 [Pomocníci sad SDK pro ladění](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [Dodavatelé portů](../../extensibility/debugger/port-suppliers.md)