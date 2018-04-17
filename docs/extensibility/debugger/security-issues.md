---
title: Problémy se zabezpečením | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- security [Debugging SDK]
- debugging [Debugging SDK], security
ms.assetid: d6ffff0a-afb4-4f38-86d8-476c881c4e4b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d45ebd8c4d80b84749838c2034d72159c9e39627
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="security-issues"></a>Problémy se zabezpečením
Pouze oprávnění potřebná k ladění program pomocí sady Visual Studio, jsou stejné jako ty, které je třeba spustit program. To zahrnuje vzdáleného ladění pro většině případů (některých situacích zahrnující jiných služeb, jako je například Internetová informační služba může vyžadovat vyšší úroveň oprávnění).  
  
 Když Visual Studio je spuštěný, Správce ladění procesu (PDM) sleduje ladění procesy v místním počítači. Program s názvem msvsmon.exe vzdáleně, je spuštěna vývojáři zpracování vzdálené ladění a zpřístupněte PDM. (Všimněte si, že msvsmon.exe není služba a musí být spuštěna ručně povolit vzdálené ladění na tomto počítači.) Pokud Visual Studio (nebo msvsmon.exe) není spuštěna, jsou sledovány žádné procesy pro ladění.  
  
 To znamená, že vývojář může ladění programů, které mu začít s žádná zvláštní oprávnění. Vývojář může i ladění procesy spuštěné někdo jiný, je-li jinou osobou členem stejné skupiny zabezpečení. A chcete-li povolit vzdálené ladění, je nutné pouze zkopírovat nezbytné soubory ke vzdálenému počítači a spuštění msvsmon.exe (viz [vzdálené ladění](../../debugger/remote-debugging.md) podrobnosti).  
  
## <a name="see-also"></a>Viz také  
 [Ladění úlohy](../../extensibility/debugger/debugging-tasks.md)   
 [Správce procesu ladění](../../extensibility/debugger/process-debug-manager.md)   
 [Vzdálené ladění](../../debugger/remote-debugging.md)