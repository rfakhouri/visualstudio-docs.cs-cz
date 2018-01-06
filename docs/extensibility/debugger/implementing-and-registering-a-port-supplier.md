---
title: Implementace a registrace dodavatele Port | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], registering port suppliers
- port suppliers, registering
ms.assetid: fb057052-ee16-4272-8e16-a4da5dda0ad4
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1c05dc0bd15dc5c1959024327396d848cd0b1112
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-and-registering-a-port-supplier"></a>Implementace a registrace dodavatele portu
Role dodavatele portu je sledovat a zadejte porty, které pak spravovat procesy. V době, kdy port musí být vytvořen dodavatele portu je vytvořena instance pomocí CoCreate s identifikátorem GUID port dodavatele (Správce ladicí relace [SDM] použije port dodavatele vybraného uživatele nebo dodavatele port zadaný v projektu systému). Pak zavolá SDM [CanAddPort](../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md) zobrazíte mohou být přidány žádné porty. Pokud lze přidat na port, nový port je požadované voláním [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md) a předání [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) port, který popisuje. `AddPort`vrátí nový port reprezentována [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) rozhraní.  
  
## <a name="discussion"></a>Diskusní  
 Port je vytvořen dodavatele port, který je pak přidruženo k serveru počítače nebo verze pro ladění. Server můžete vytvořit výčet její dodavatelé port prostřednictvím[EnumPortSuppliers](../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md) metoda a port dodavatele můžete vytvořit výčet jeho porty prostřednictvím [EnumPorts](../../extensibility/debugger/reference/idebugportsupplier2-enumports.md) metoda.  
  
 Kromě typické registrace modelu COM port dodavatele musí se registrovat pomocí sady Visual Studio tak, že jeho CLSID a název umístění konkrétní registru. Podpůrná funkce ladění SDK volána `SetMetric` zpracovává v tomto případě: nazývá se jednou pro každou položku mají být povoleny, proto:  
  
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
  
 Port dodavatele zruší registraci samotné voláním `RemoveMetric` (jinou funkci pomocné rutiny ladění SDK) jednou pro každou položku, který byl zaregistrován proto:  
  
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
>  [SDK pomocníci pro ladění](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) `SetMetric` a `RemoveMetric` jsou statické funkce definované v dbgmetric.h a zkompilovat do ad2de.lib. `metrictypePortSupplier`, `metricCLSID`, A `metricName` pomocné rutiny, je definována v dbgmetric.h.  
  
 Port dodavatele můžete zadat jeho název a identifikátor GUID prostřednictvím metod [GetPortSupplierName](../../extensibility/debugger/reference/idebugportsupplier2-getportsuppliername.md) a [GetPortSupplierId](../../extensibility/debugger/reference/idebugportsupplier2-getportsupplierid.md), v uvedeném pořadí.  
  
## <a name="see-also"></a>Viz také  
 [Implementace Port dodavatele](../../extensibility/debugger/implementing-a-port-supplier.md)   
 [Pomocníci SDK pro ladění](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [Dodavatelé portů](../../extensibility/debugger/port-suppliers.md)