---
title: Problémy se zabezpečením | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- security [Debugging SDK]
- debugging [Debugging SDK], security
ms.assetid: d6ffff0a-afb4-4f38-86d8-476c881c4e4b
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: fb6209882a7a71a68728299064edcc13afabff35
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65704424"
---
# <a name="security-issues"></a>Problémy se zabezpečením
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Chcete-li ladit aplikaci pomocí sady Visual Studio, jsou pouze potřebná oprávnění stejné těmi, které vývojář potřebuje ke spuštění programu. To zahrnuje, vzdálené ladění pro většinu situací (někdy zahrnující jiných služeb, jako je například Internetová informační služba může vyžadovat vyšší úroveň oprávnění).  
  
 Když je spuštěná sada Visual Studio, sleduje správce ladění procesu (PDM) ladění procesů na místním počítači. Vzdáleně je spuštěn program s názvem msvsmon.exe vývojářem pro zpracování, vzdálené ladění a zpřístupnit PDM. (Všimněte si, že msvsmon.exe není služba a musí být spuštěna ručně povolit vzdálené ladění na tomto počítači.) Pokud sadu Visual Studio (nebo msvsmon.exe) není spuštěna, žádné procesy jsou sledována pro ladění.  
  
 To znamená, že vývojář můžete ladit programy, které uživatel začít žádná zvláštní oprávnění. Vývojář můžete dokonce ladit procesy spuštěné někým jiným, pokud tato osoba je členem stejné skupiny zabezpečení. A pokud chcete povolit vzdálené ladění, je nezbytné pouze ke zkopírování nezbytné soubory do vzdáleného počítače a spuštění msvsmon.exe (naleznete v tématu [nastavit Up the Remote Tools na zařízení](https://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c) další podrobnosti).  
  
## <a name="see-also"></a>Viz také  
 [Ladění úloh](../../extensibility/debugger/debugging-tasks.md)   
 [Správce ladění procesu](../../extensibility/debugger/process-debug-manager.md)   
 [Nastavení nástroje Remote Tools na zařízení](https://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)
