---
title: 'Postupy: určení verze rozhraní .NET Framework pro ladění | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- .NET Framework, specifying version for debugging
- debugging [Visual Studio], specifying .NET Framework version
ms.assetid: 7a4893ba-4620-4774-893f-378d4ca28893
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 2cb8da54b53814e7f044c67855e8071c627cf2e1
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31476670"
---
# <a name="how-to-specify-a-net-framework-version-for-debugging"></a>Postupy: Určení verze rozhraní .NET Framework pro ladění
[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] Ladicí program podporuje ladění starší verze Microsoft [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] i aktuální verze. Pokud spustíte aplikaci v sadě Visual Studio, ladicího programu můžete vždy identifikovat správnou verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] pro aplikaci, kterou ladíte. Pokud již je spuštěna aplikace a použijete **připojit k**, ladicí program nemusí být vždy možné identifikovat starší verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Pokud k tomu dojde, zobrazí se chybová zpráva s informacemi o tom,  
  
 Ladicí program udělal nesprávný předpokládá o [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] verze aplikace bude používat.  
  
 V těchto výjimečných případech můžete nastavit klíč registru a informuje ladicího programu, která verze se má použít.  
  
### <a name="to-specify-a-net-framework-version-for-debugging"></a>K určení verze rozhraní .NET Framework pro ladění  
  
1.  Podívejte se v adresáři Windows\Microsoft.NET\Framework najít verze rozhraní .NET Framework, který je nainstalovaný na počítači. Čísla verzí vypadat přibližně takto:  
  
     `V1.1.4322`  
  
     Určete číslo správnou verzi a poznamenejte si ho.  
  
2.  Spuštění **Editor registru** (regedit).  
  
3.  V **Editor registru**, otevřete složku HKEY_LOCAL_MACHINE.  
  
4.  Přejděte do: HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\10.0\AD7Metrics\Engine\\{449EC4CC-30D2-4032-9256-EE18EB41B62B}  
  
     Pokud klíč neexistuje, klikněte pravým tlačítkem na HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\10.0\AD7Metrics\Engine a klikněte na **nový klíč**. Název nového klíče `{449EC4CC-30D2-4032-9256-EE18EB41B62B}`.  
  
5.  Po přechodu na {449EC4CC-30D2-4032-9256-EE18EB41B62B}, vyhledejte v **název** sloupce a najít klíč CLRVersionForDebugging.  
  
    1.  Pokud klíč neexistuje, klikněte pravým tlačítkem na {449EC4CC-30D2-4032-9256-EE18EB41B62B} a klikněte na **novou řetězcovou hodnotu**. Klikněte pravým tlačítkem novou řetězcovou hodnotu, klikněte na tlačítko **přejmenovat**a typ `CLRVersionForDebugging`.  
  
6.  Klikněte dvakrát na **CLRVersionForDebugging**.  
  
7.  V **Upravit řetězec** zadejte číslo verze rozhraní .NET Framework v **hodnotu** pole. Příklad: V1.1.4322  
  
8.  Click **OK**.  
  
9. Zavřít **Editor registru**.  
  
     Pokud stále zobrazí chybové hlášení při spuštění ladění, ověřte, zda jste zadali číslo verze správně do registru. Ověřte také, že používáte verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] nepodporuje sady Visual Studio. Ladicí program je kompatibilní s aktuální verze rozhraní .NET Framework a předchozí verze, ale nemusí být dopředně kompatibilní s novějšími verzemi.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)