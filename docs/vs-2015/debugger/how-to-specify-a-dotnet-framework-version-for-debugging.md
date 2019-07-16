---
title: 'Postupy: Určení verze rozhraní .NET Framework pro ladění | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- .NET Framework, specifying version for debugging
- debugging [Visual Studio], specifying .NET Framework version
ms.assetid: 7a4893ba-4620-4774-893f-378d4ca28893
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4c785c419ead31ad90e2b20ae7f48af778598bb6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68176555"
---
# <a name="how-to-specify-a-net-framework-version-for-debugging"></a>Postupy: Určení verze rozhraní .NET Framework pro ladění
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] Ladicí program podporuje ladění starších verzích Microsoft [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] stejně jako aktuální verze. Pokud spouštíte aplikaci ze sady Visual Studio, ladicí program může vždy identifikovat správnou verzi [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] pro aplikaci, kterou ladíte. Pokud už je aplikace spuštěna a použijete **připojit k**, ladicí program, nemusí být vždy schopen identifikovat starší verzi [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]. Pokud k tomu dojde, zobrazí se chybová zpráva s upozorněním,  
  
 Ladicí program provedl nesprávné předpokladů o [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] verze vaší aplikace bude používat.  
  
 V těchto výjimečných případech můžete nastavit klíče registru k označení k ladicímu programu, které verze se má použít.  
  
### <a name="to-specify-a-net-framework-version-for-debugging"></a>Chcete-li určit verzi rozhraní .NET Framework pro ladění  
  
1. Hledejte v adresáři Windows\Microsoft.NET\Framework vyhledání verzí rozhraní .NET Framework nainstalované v počítači. Čísla verzí vypadat přibližně takto:  
  
     `V1.1.4322`  
  
     Identifikujte na správné číslo verze a poznamenejte si ho.  
  
2. Spustit **Editor registru** (regedit).  
  
3. V **Editor registru**, otevřete složku HKEY_LOCAL_MACHINE.  
  
4. Přejděte do: HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\10.0\AD7Metrics\Engine\\{449EC4CC-30D2-4032-9256-EE18EB41B62B}  
  
     Pokud klíč neexistuje, klikněte pravým tlačítkem na HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\10.0\AD7Metrics\Engine a klikněte na tlačítko **nový klíč**. Pojmenujte nový klíč `{449EC4CC-30D2-4032-9256-EE18EB41B62B}`.  
  
5. Po přejití do {449EC4CC-30D2-4032-9256-EE18EB41B62B}, podívejte se **název** sloupce a najít CLRVersionForDebugging klíč.  
  
    1. Pokud klíč neexistuje, klikněte pravým tlačítkem na {449EC4CC-30D2-4032-9256-EE18EB41B62B} a klikněte na tlačítko **novou řetězcovou hodnotu**. Klikněte pravým tlačítkem na novou řetězcovou hodnotu, klikněte na tlačítko **přejmenovat**a typ `CLRVersionForDebugging`.  
  
6. Dvakrát klikněte na panel **CLRVersionForDebugging**.  
  
7. V **Upravit řetězec** zadejte číslo verze rozhraní .NET Framework v **hodnotu** pole. Příklad: V1.1.4322  
  
8. Klikněte na **OK**.  
  
9. Zavřít **Editor registru**.  
  
     Pokud se stále zobrazí chybová zpráva při zahájení ladění, ověřte, že zadáte číslo verze správně v registru. Dál ověřte, že používáte verzi [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] podporovaného Visual Studiem. Ladicí program je kompatibilní s aktuální verze rozhraní .NET Framework a předchozími verzemi, ale možná není dopředně kompatibilní s budoucí verze.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení a příprava ladicího programu](../debugger/debugger-settings-and-preparation.md)
