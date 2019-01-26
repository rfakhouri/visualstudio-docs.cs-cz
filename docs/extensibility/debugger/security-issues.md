---
title: Problémy se zabezpečením | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- security [Debugging SDK]
- debugging [Debugging SDK], security
ms.assetid: d6ffff0a-afb4-4f38-86d8-476c881c4e4b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4dcd9806459a1cdc92d3eb698fcae7b4a7e0fa6f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55016450"
---
# <a name="security-issues"></a>Problémy se zabezpečením
Chcete-li ladit aplikaci pomocí sady Visual Studio, jsou pouze potřebná oprávnění stejné vývojář vyžaduje ke spuštění programu. To zahrnuje, vzdálené ladění pro většinu situací. Některé situace, zahrnující jiných služeb, jako je například Internetová informační služba může vyžadovat vyšší úroveň oprávnění.  
  
 Když je spuštěná sada Visual Studio, sleduje správce ladění procesu (PDM) ladění procesů na místním počítači. Vzdáleně, program s názvem *msvsmon.exe* je tím, že pro vývojáře pro zpracování, vzdálené ladění a zpřístupnit PDM. (*msvsmon.exe* není služba a musí být spuštěna ručně povolit vzdálené ladění na tomto počítači.) Když Visual Studio (nebo *msvsmon.exe*) je neběží, žádné procesy jsou sledována pro ladění.  
  
 Vývojář můžete ladit programy, které se spouští s žádná zvláštní oprávnění. Vývojář můžete dokonce ladit procesy spuštěné někým jiným, pokud tato osoba je členem stejné skupiny zabezpečení. A pokud chcete povolit vzdálené ladění, je nutné pouze zkopírovat požadované soubory na vzdálený počítač a spusťte *msvsmon.exe*. Další informace najdete v tématu [vzdálené ladění](../../debugger/remote-debugging.md).  
  
## <a name="see-also"></a>Viz také:  
 [Ladění úloh](../../extensibility/debugger/debugging-tasks.md)   
 [Správce ladění procesu](../../extensibility/debugger/process-debug-manager.md)   
 [Vzdálené ladění](../../debugger/remote-debugging.md)
