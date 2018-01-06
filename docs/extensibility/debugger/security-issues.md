---
title: "Problémy se zabezpečením | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [Debugging SDK]
- debugging [Debugging SDK], security
ms.assetid: d6ffff0a-afb4-4f38-86d8-476c881c4e4b
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 753f916d148675afd7313afc8673232f22280b7d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="security-issues"></a>Problémy se zabezpečením
Pouze oprávnění potřebná k ladění program pomocí sady Visual Studio, jsou stejné jako ty, které je třeba spustit program. To zahrnuje vzdáleného ladění pro většině případů (některých situacích zahrnující jiných služeb, jako je například Internetová informační služba může vyžadovat vyšší úroveň oprávnění).  
  
 Když Visual Studio je spuštěný, Správce ladění procesu (PDM) sleduje ladění procesy v místním počítači. Program s názvem msvsmon.exe vzdáleně, je spuštěna vývojáři zpracování vzdálené ladění a zpřístupněte PDM. (Všimněte si, že msvsmon.exe není služba a musí být spuštěna ručně povolit vzdálené ladění na tomto počítači.) Pokud Visual Studio (nebo msvsmon.exe) není spuštěna, jsou sledovány žádné procesy pro ladění.  
  
 To znamená, že vývojář může ladění programů, které mu začít s žádná zvláštní oprávnění. Vývojář může i ladění procesy spuštěné někdo jiný, je-li jinou osobou členem stejné skupiny zabezpečení. A chcete-li povolit vzdálené ladění, je nutné pouze zkopírovat nezbytné soubory ke vzdálenému počítači a spuštění msvsmon.exe (viz [vzdálené ladění](../../debugger/remote-debugging.md) podrobnosti).  
  
## <a name="see-also"></a>Viz také  
 [Ladění úlohy](../../extensibility/debugger/debugging-tasks.md)   
 [Správce procesu ladění](../../extensibility/debugger/process-debug-manager.md)   
 [Vzdálené ladění](../../debugger/remote-debugging.md)